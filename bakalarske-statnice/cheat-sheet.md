# Souhrn na rychlé zopakování před termínem
Už ho udělat se správnými uvozovkami
V poznámkách můžu kouknout na žlutý nebo horší poznámky co jsem si tam nechal, ale to co je tady by mělo stačit

## Matika

### Analýza

### Lingebra

### Grafy

### Diskrétka

### Logika

## Past

## Informatika

### Automaty

### Ads

### Architektury

### Programko

## Web


### Databáze

### Data

### Web
#### Serverové PHP – Backend API, Front Controller a Databázové JSON Endpointy:
```php
<?php
// 1. Spuštění serverové relace
session_start();

// 2. Front Controller – určení požadované akce (routing)
// Pozor: V $_GET jsou vždy parametry z URL adresy (Query Stringu),
// a to i když je samotný HTTP dotaz typu POST, PUT či DELETE!
$action = $_GET['action'] ?? 'home';

// A) REST JSON Endpoint pro příjem dat (POST s JSON tělem)
if ($action === 'create_item') {
    // Proč php://input? Pokud klient posílá Content-Type: application/json,
    // superglobální pole $_POST zůstane zcela prázdné!
    $rawInput = file_get_contents('php://input');
    $data = json_decode($rawInput, true);

    if (!$data || !isset($data['name'])) {
        http_response_code(400); // 400 Bad Request
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Neplatný JSON vstup']);
        exit;
    }
    http_response_code(201); // 201 Created
    header('Content-Type: application/json; charset=utf-8');
    echo json_encode(['status' => 'created', 'id' => 42]);
    exit;
}

// B) Databázový dotaz (GET) se sanitizací a ošetřením chyb (Zkouškový vzor)
if ($action === 'get_dataset') {
    /* filter_input(INPUT_GET, 'title') vs. $_GET['title']:
       - filter_input vrátí null bez varování 'Undefined array key', pokud klíč v URL chybí.
       - Čte přímo původní request nezávisle na případných mutacích superglobálního pole.
       - Umožňuje snadnou aplikaci typových filtrů (např. FILTER_VALIDATE_INT). */
    $title = filter_input(INPUT_GET, 'title');

    if ($title === null || trim($title) === '') {
        http_response_code(400); // 400 Bad Request
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Chybí povinný parametr title']);
        exit;
    }

    try {
        // 1. Připojení a Prepared Statement přes PDO (SQL Injection ochrana)
        $pdo = new PDO('mysql:host=localhost;dbname=katalog;charset=utf8', 'user', 'pass');
        $stmt = $pdo->prepare('SELECT id, title, format FROM dataset WHERE title = :title LIMIT 1');
        $stmt->execute(['title' => $title]);
        $dataset = $stmt->fetch(PDO::FETCH_ASSOC);
        $pdo = null; // Uzavření spojení

        /* Alternativa v mysqli:
        $mysqli = new mysqli('localhost', 'user', 'pass', 'katalog');
        $stmt = $mysqli->prepare('SELECT id, title, format FROM dataset WHERE title = ? LIMIT 1');
        $stmt->bind_param('s', $title);
        $stmt->execute();
        $dataset = $stmt->get_result()->fetch_assoc();
        $stmt->close();
        $mysqli->close(); // Uzavření spojení */

        // 2. Ošetření neexistence záznamu (404 Not Found)
        if (!$dataset) {
            http_response_code(404);
            header('Content-Type: application/json; charset=utf-8');
            echo json_encode(['error' => 'Datová sada nenalezena']);
            exit;
        }

        // 3. Úspěšná odpověď (200 OK)
        http_response_code(200);
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode($dataset);

    } catch (Exception $e) {
        // 4. Systémová chyba serveru (500 Internal Server Error)
        http_response_code(500);
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Interní chyba serveru']);
    }
    exit;
}
?>
```

#### PHP Interleaving, HTML5 formulář, XSS a Anti-CSRF token:
```php
<?php
// Generování náhodného Anti-CSRF tokenu do Session
if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));
}

// Zpracování POST požadavku a ověření CSRF tokenu
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    if (!hash_equals($_SESSION['csrf_token'], $_POST['csrf_token'] ?? '')) {
        http_response_code(403);
        die('Neplatný CSRF token!');
    }
    // Uložení do DB a bezpečné přesměrování podle PRG vzoru:
    $_SESSION['flash'] = 'Úspěšně uloženo!';
    header('Location: formular.php');
    exit;
}
?>

<!-- PŘEPNUTÍ DO HTML ŠABLONY (INTERLEAVING) -->
<!DOCTYPE html>
<html lang='cs'>
<body>
  <?php if (!empty($_SESSION['flash'])): ?>
    <p class='msg'><?= htmlspecialchars($_SESSION['flash']) ?></p>
    <?php unset($_SESSION['flash']); // Flash message po zobrazení smažeme ?>
  <?php endif; ?>

  <!-- HTML5 nativní validační omezení (required, email, pattern, min/max) -->
  <form action='formular.php' method='POST'>
    <!-- Skrytý Anti-CSRF token v těle formuláře -->
    <input type='hidden' name='csrf_token' value='<?= htmlspecialchars($_SESSION['csrf_token']) ?>'>

    <label for='inp_email'>E-mail:</label>
    <input type='email' id='inp_email' name='email' required placeholder='jmeno@domena.cz'>

    <label for='inp_login'>Login (5–10 písmen):</label>
    <input type='text' id='inp_login' name='login' required pattern='[a-z]{5,10}'>

    <label for='inp_age'>Věk:</label>
    <input type='number' id='inp_age' name='age' min='18' max='99'>

    <button type='submit'>Odeslat</button>
  </form>

  <!-- Alternativní syntaxe řídicích struktur a XSS ochrana (htmlspecialchars) -->
  <?php if (!empty($clanky)): ?>
    <ul>
      <?php foreach ($clanky as $clanek): ?>
        <li><?= htmlspecialchars($clanek['title']) ?> (<?= htmlspecialchars($clanek['author']) ?>)</li>
      <?php endforeach; ?>
    </ul>
  <?php else: ?>
    <p>Zatím nebyly vydány žádné články.</p>
  <?php endif; ?>
</body>
</html>
```


#### Klientský JavaScript – Události, Asynchronní Fetch (Guard zámek) a Bezpečný DOM:

**1. Odeslání formuláře (submit), FormData, Async/Await a renderování:**
```javascript
// 1. Hledání prvků v DOMu
const form = document.getElementById('searchForm');
const resultsList = document.querySelector('#results');
let isFetching = false; // Zámek (Guard) proti data races při zběsilém klikání

// 2. Event 'submit' na formuláři (zachytí klik i klávesu Enter)
form.addEventListener('submit', async (e) => {
  e.preventDefault(); // Zabrání výchozímu odeslání a znovunačtení stránky

  if (isFetching) return;
  isFetching = true;

  try {
    // 3. Asynchronní POST request s FormData (automaticky zabalí vstupy)
    const response = await fetch('/api/search', {
      method: 'POST',
      body: new FormData(form)
    });
    if (!response.ok) throw new Error('HTTP status: ' + response.status);

    const items = await response.json(); // Druhý await pro JSON tělo

    // 4. Bezpečná manipulace s DOMem (XSS ochrana)
    resultsList.textContent = ''; // Vyčištění starých položek
    items.forEach(item => {
      const li = document.createElement('li');
      li.textContent = item.title; // textContent = klientská obdoba htmlspecialchars (nikdy ne innerHTML!)
      resultsList.appendChild(li);
    });
  } catch (err) {
    console.error('Chyba sítě/API:', err);
  } finally {
    isFetching = false; // Odemčení zámku VŽDY v bloku finally
  }
});
```

**2. Obsluha tlačítka (click), DELETE dotaz, Event Delegation a přesun v DOMu:**
```javascript
const activeList = document.getElementById('activeList');
const doneList = document.getElementById('doneList');

// Event Delegation: Posluchač je pověšený na rodiči activeList (událost click probublá nahoru).
// Jakmile položku přesuneme do doneList, bublání na activeList automaticky přestane fungovat!
activeList.addEventListener('click', async (e) => {
  // closest('.delete-btn'): Hledá předka směrem NAHORU od kliknutého prvku (e.target).
  // Spolehlivě zachytí klik, i když uživatel klikl na vnořenou ikonku uvnitř tlačítka (např. <i> či <span>).
  const btn = e.target.closest('.delete-btn');
  if (!btn) return;
  
  // Robustní vyhledání nadřazeného <li> bez ohledu na hloubku zanoření (lepší než parentElement)
  const item = btn.closest('li');
  const id = item.dataset.id;

  const res = await fetch(`/api/items/${id}`, { method: 'DELETE' });
  if (res.ok) {
    // appendChild(): Každý DOM prvek smí mít v jeden okamžik POUZE 1 rodiče!
    // Předání existujícího uzlu ho automaticky 'vytrhne' z activeList a přesune do doneList (není nutné volat removeChild).
    // (Pokud bychom chtěli prvek duplikovat místo přesunu, použije se item.cloneNode(true)).
    doneList.appendChild(item);
    // nebo pro úplné smazání ze stránky: item.remove();
  }
});
```

#### OpenAPI (Swagger) – Definice endpointu v YAML:
* **Ukázka cesty s parametrem a odpovědí 200 ($ref model):**
```yaml
paths:
  /api/users/{userId}:
    get:
      summary: 'Detail uživatele'
      parameters:
        - name: userId
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: 'Úspěch'
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/User'
        '404':
          description: 'Nenalezeno'
```

#### GraphQL – Princip, Dotaz (Query) a JSON Odpověď:
* **Princip:** Řeší *Over-fetching* (přebírání nechtěných polí) i *Under-fetching* (nutnost vícenásobných HTTP dotazů pro vazby). Má jediný endpoint (`POST /graphql`).
* **Zápis dotazu (Query):**
```graphql
query {
  produkt(id: 42) {
    nazev
    recenze {
      hodnoceni
    }
  }
}
```
* **Odpověď serveru:** Vždy obalena v kořenovém klíči `"data"` a kopíruje hierarchii:
```json
{
  "data": {
    "produkt": {
      "nazev": "Horská kola",
      "recenze": [
        { "hodnoceni": 5 },
        { "hodnoceni": 4 }
      ]
    }
  }
}
```

#### Pearsonův korelační koeficient (User Bias v UB-KNN):
* **Vzorec:** $sim(u, v) = \frac{\sum_{i \in I_{uv}} (r_{u,i} - \bar{r}_u)(r_{v,i} - \bar{r}_v)}{\sqrt{\sum_{i \in I_{uv}} (r_{u,i} - \bar{r}_u)^2} \cdot \sqrt{\sum_{i \in I_{uv}} (r_{v,i} - \bar{r}_v)^2}}$
* $I_{uv}$ = společně ohodnocené položky, $\bar{r}_u, \bar{r}_v$ = průměrná hodnocení uživatelů (centrace do nuly řeší optimisty/pesimisty).

#### nDCG@K (Normalized Discounted Cumulative Gain):
* **Vzorce:** $DCG@K = \sum_{i=1}^K \frac{rel_i}{\log_2(i + 1)}, \quad nDCG@K = \frac{DCG@K}{iDCG@K}$
* $rel_i$ = stupňovitá relevance (např. 1–5 hvězd, nákup), $\log_2(i+1)$ = logaritmický útlum s rostoucí pozicí, $iDCG$ = ideální DCG (položky seřazeny sestupně od nejlepší).

#### Precision@K a Recall@K (Ranking metriky v RecSys / IR):
* **$\text{Precision@K} = \frac{|\text{Relevantní} \cap \text{Doporučené}_K|}{K}$** (podíl relevantních mezi prvními $K$ položkami).
* **$\text{Recall@K} = \frac{|\text{Relevantní} \cap \text{Doporučené}_K|}{|\text{Všechny Relevantní}|}$** (podíl nalezených relevantních z celé DB).

#### TF-IDF (Váhování termů ve VSM):
* **Vzorec:** $w_{t,d} = TF(t,d) \times IDF(t,D) = f_{t,d} \cdot \log_{10}\left(\frac{N}{df_t}\right)$
* $TF$ = Četnost slova $t$ v dokumentu $d$ (lokální význam).
* $IDF$ = Inverzní frekvence v korpusu ($N$ dokumentů, $df_t$ obsahuje term $t$) $\implies$ vzácná slova mají vysokou váhu.

#### F1-score:
* **Vzorec (Harmonický průměr):** $F_1 = 2 \cdot \frac{P \cdot R}{P + R} = \frac{2 \cdot TP}{2 \cdot TP + FP + FN}$
* Penalizuje extrémní nepoměr mezi Precision ($P = \frac{TP}{TP+FP}$) a Recall ($R = \frac{TP}{TP+FN}$).

#### MAP (Mean Average Precision):
* **Average Precision pro 1 dotaz:** $AP@K = \frac{1}{|R|} \sum_{k=1}^K P@k \cdot rel(k)$
  * **Klíčový princip:** $P@k$ se počítá **pouze na pozicích $k$, kde je skutečně relevantní položka** ($rel(k)=1$). Tyto dílčí přesnosti se sečtou a vydělí počtem všech relevantních položek $|R|$ v databázi pro daný dotaz.
* **Mean AP přes celou sadu dotazů:** $MAP@K = \frac{1}{|Q|} \sum_{q \in Q} AP@K(q)$

#### PageRank (nenormalizovaný tvar):
$$PR^{(k+1)}(A) = (1 - d) + d \sum_{T_i \to A} \frac{PR^{(k)}(T_i)}{C(T_i)}$$
* Inicializace: $PR^{(0)}(u) = 1$.
* **Kontrolní součet:** Vždy platí $\sum_{u} PR^{(k)}(u) = N$ (lze ověřit výpočet, pokud z mrtvých konců vedou virtuální odkazy na všechny uzly).

#### Podobnostní model a fúze:
* **Formální definice:** Trojice $(O, F, D)$:
  1. **Objekty ($O$):** Původní multimediální data (obrázek, video).
  2. **Deskriptor / Příznakový vektor ($F$):** Matematická reprezentace (např. barevný histogram, CNN embedding).
  3. **Metrika vzdálenosti ($D$):** Funkce $d(x, y) \ge 0$, kde menší číslo značí vyšší podobnost (např. Euklidovská norma $d=\sqrt{\sum (x_i-y_i)^2}$ nebo kosinová vzdálenost $1 - \cos\theta$).
* **Fúze modalit (kombinace textu a obrazu):**
  * **Early Fusion (na úrovni příznaků):** Zřetězení vektorů $[V_{text}, V_{vis}]$ před výpočtem vzdálenosti (hledá křížové vazby, vyžaduje normalizaci, hrozí prokletí dimenzionality).
  * **Late Fusion (na úrovni skóre):** Samostatné vyhodnocení textu a obrazu, následná agregace skóre (např. vážený součet $Score = \alpha \cdot sim_{vis} + (1-\alpha) \cdot sim_{text}$). Robustní a modulární.

#### Multimediální formáty:
* **JPEG:** Ztrátová komprese – 8×8 bloky, **DCT (Diskrétní kosinová transformace)** do frekvenční domény, **kvantizace** (zahození vysokých frekvencí nepostřehnutelných lidským okem), Huffmanovo kódování.
* **MP4:** Multimediální **kontejner (obálka)**, nikoliv kodek. Synchronizovaně balí videostopu (HEVC/H.264), audiostopu (AAC) a titulky.

#### Metrické indexování a filtrování:
* **Filtrování pivotem (Trojúhelníková nerovnost):** Objekt $O_i$ bezpečně odfiltrujeme bez počítání $d(q, O_i)$, pokud $|d(P, q) - d(P, O_i)| > r$ (pro poloměr dotazu $r$).
* **Maticové indexy (např. LAESA):** Tabulka předpočítaných vzdáleností $N \times k$ k fixním pivotům; sekvenční čtení v paměti těží z HW vektorizace (SIMD) bez stromových cache missů.
* **Stromové indexy (např. VP-tree, M-tree):** Hierarchické dělení prostoru na koule/mezikruží kolem lokálních pivotů v uzlech; umožňují prořezávat celé větve (ve vysokých dimenzích však trpí překryvy).
* **Hašované indexy (LSH – Locality-Sensitive Hashing):** Hašovací funkce navržená tak, že podobné vektory padají do stejného bucketu; slouží pro rychlé přibližné vyhledávání (Approximate k-NN).
* **Hybridní indexy (např. PM-tree, M-Index):** Kombinují stromové dělení s maticí pivotů v listech, případně metrický index pro vizuální data s invertovaným indexem pro text.

#### SOM (Self-Organizing Map) – Algoritmus trénování:
* **Princip:** 2D grid neuronů s váhami $W_i$. Unsupervised learning, zachovává topologii, ale **negarantuje 1:1 zaplnění** (vznikají díry / shluky).
```text
Inicializuj váhy W_i náhodně
Opakuj pro náhodný vstupní vektor V:
  1. Najdi BMU = argmin_i δ(V, W_i)  // uzel s nejmenší vzdáleností
  2. Aktualizuj BMU a sousedy: W_i(t+1) = W_i(t) + lr(t) * h_BMU,i(t) * (V(t) - W_i(t))
  3. Postupně snižuj lr(t) a šíři sousedství h(t)
```

#### SSM (Self-Sorting Map) – Cílová funkce a řazení:
* **Princip:** Heuristické přerovnání existujícího gridu. **Garantuje 1:1 přiřazení** (jedna buňka = právě jeden obrázek, ideální pro UI).
* **Cílová funkce (maximalizuje Pearsonovu korelaci mřížkové vzdálenosti a vizuální nepodobnosti):**
$$\operatorname*{arg\,max}_{L} \sum_{s, t \in \Omega} \frac{\left( \|P(L_s) - P(L_t)\| - \bar{P} \right) \left( \delta(s, t) - \bar{\delta} \right)}{\sigma_P \sigma_\delta}$$
* **Řazení v 2D gridu:** Iterativně se prochází mřížka a testuje se všech $4! = 24$ možných permutací sousedních **čtveřic buněk** (swaps). Vybere se permutace, která nejvíce zvýší skóre cílové funkce.
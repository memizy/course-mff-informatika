# Test 7: Diskrétní matematika a teorie grafů – Kompletní oficiální rozbor a vzorová řešení

* **Předmět:** Diskrétní matematika a teorie grafů (Společná zkoušková matematika MFF UK)
* **Datum zpracování:** 7. 9. 2026
* **Stav:** Kompletní vzorové řešení od zkušební komise a detailní postupy pro všech 11 úloh.

---

# ČÁST 1: Vzorová řešení autentických zkouškových úloh MFF UK

---

## Úloha 1: Souvislost grafů a Mengerova věta (Podzim 2023 – 14. 9. 2023)

### Zadání:
Mějme graf $G$ na 64 vrcholech označených prvky $\{0, 1\}^6$. Hrany tvoří:
1. Dvojice vrcholů lišící se pouze v 1. souřadnici (např. `111010` a `011010`), tvořící perfektní párování.
2. Dvojice vrcholů mající první dva znaky totožné (např. `111010` a `110001`).
3. Dvojice (`111010`, `101100`), (`101100`, `010110`) a (`010110`, `111011`).

### Vzorové řešení:

#### 1. (a) Mengerova věta a zavedení pojmů
* **Definice vrcholového řezu:** Pro dva různé nesousední vrcholy $x, y \in V$ nazýváme množinu vrcholů $U \subseteq V \setminus \{x, y\}$ **vrcholovým $xy$-řezem**, pokud v grafu $G - U$ neexistuje žádná cesta mezi $x$ a $y$.
* **Definice hranového řezu:** Pro dva různé vrcholy $x, y \in V$ nazýváme množinu hran $F \subseteq E$ **hranovým $xy$-řezem**, pokud v grafu $G \setminus F$ neexistuje žádná cesta mezi $x$ a $y$.
* **Mengerova věta (lokální vrcholová verze):** Nechť $G=(V, E)$ je graf a $x, y \in V$ dva různé **nesousední** vrcholy. Pak maximální počet vrcholově disjunktních cest mezi $x$ a $y$ je roven minimální velikosti vrcholového $xy$-řezu.
* **Mengerova věta (lokální hranová verze):** Nechť $G=(V, E)$ je graf a $x, y \in V$ dva různé vrcholy. Pak maximální počet hranově disjunktních cest mezi $x$ a $y$ je roven minimální velikosti hranového $xy$-řezu.

#### 1. (b) Analýza struktury a počet hranově disjunktních cest
* **Rozklad grafu na bloky:** Vrcholy se podle prvních dvou bitů přirozeně dělí na 4 bloky po 16 vrcholech: $V_{00}, V_{01}, V_{10}, V_{11}$.
  * Protože vrcholy se shodnými prvními dvěma bity jsou navzájem všechny spojeny hranami, každý blok $V_{00}, V_{01}, V_{10}, V_{11}$ indukuje **úplný podgraf $K_{16}$**.
* **Hrany mezi bloky:**
  * Perfektní párování (liší se jen v 1. bitu):
    * Spojuje $00xxxx \leftrightarrow 10xxxx$ (přesně 16 hran mezi $V_{00}$ a $V_{10}$).
    * Spojuje $01xxxx \leftrightarrow 11xxxx$ (přesně 16 hran mezi $V_{01}$ a $V_{11}$).
    * Mezi $V_{00}$ a $V_{01}$ nevede žádná hrana párování. Mezi $V_{10}$ a $V_{11}$ nevede žádná hrana párování.
  * Tři extra hrany:
    * $e_1 = (111010, 101100)$ spojuje $V_{11}$ a $V_{10}$.
    * $e_2 = (101100, 010110)$ spojuje $V_{10}$ a $V_{01}$.
    * $e_3 = (010110, 111011)$ spojuje $V_{01}$ a $V_{11}$.
* **Úzké hrdlo mezi $000000 \in V_{00}$ a $111111 \in V_{11}$:**
  * Vrchol `000000` leží ve $V_{00}$. Z $V_{00}$ vedou hrany výhradně do $V_{10}$.
  * Z celého bloku $V_{10}$ vedou do bloků $V_{01}$ a $V_{11}$ POUZE dvě hrany: $e_1 = (101100, 111010)$ a $e_2 = (101100, 010110)$.
  * Odebráním těchto dvou hran $\{e_1, e_2\}$ je množina $V_{00} \cup V_{10}$ zcela izolována od $V_{01} \cup V_{11}$.
  * Existují 2 hranově disjunktní cesty:
    * Cesta 1: `000000` $\to$ `001100` $\to$ `101100` $\xrightarrow{e_1}$ `111010` $\to$ `111111`.
    * Cesta 2: `000000` $\to$ `000001` $\to$ `100001` $\to$ `101100` $\xrightarrow{e_2}$ `010110` $\xrightarrow{e_3}$ `111011` $\to$ `111111`.
    *(Obě cesty jsou hranově disjunktní; sdílejí sice uzel `101100`, ale žádnou společnou hranu).*
  * Podle hranové Mengerovy věty je počet hranově disjunktních cest roven **2**.

#### 1. (c) Minimální hranový a vrcholový řez
* **Minimální hranový řez:** Má velikost **2** a je tvořen hranami $\{ (101100, 111010), (101100, 010110) \}$.
* **Minimální vrcholový řez:** Má velikost **1** a je tvořen jediným vrcholem $\{ 101100 \}$.
  * *Důvod:* Každá cesta z $V_{00}$ do $V_{11}$ musí projít přes $V_{10}$ a jediným vrcholem z $V_{10}$, který má hrany do $V_{01} \cup V_{11}$, je právě `101100`. Po jeho odebrání neexistuje mezi `000000` a `111111` žádná cesta.

---

## Úloha 2: Barevnost grafů (Podzim 2024 – 3. 9. 2024)

### Vzorové řešení:

#### 2. (a) Definice barevnosti grafu
* **Dobré obarvení:** Dobré obarvení grafu $G=(V, E)$ $k$ barvami je zobrazení $c: V \to \{1, \dots, k\}$ splňující:
  $$\forall \{u, v\} \in E: c(u) \ne c(v)$$
* **Chromatické číslo $\chi(G)$:** Barevnost grafu je nejmenší přirozené číslo $k$, pro které existuje dobré $k$-obarvení grafu $G$.

#### 2. (b) Omezení pro rovinné grafy
* Pro každý rovinný graf $G$ platí:
  $$\chi(G) \le 4 \quad (\text{Věta o čtyřech barvách})$$
  Tento odhad je těsný (např. úplný graf $K_4$ je rovinný a má $\chi(K_4) = 4$).

#### 2. (c) Určení barevnosti zadaného grafu
Barevnost grafu na obrázku je přesně **$\chi(G) = 4$**.
* **Dolní odhad ($\chi(G) \ge 4$):**
  * Graf obsahuje jako podgraf kružnici délky 5 na vrcholech $\{b, c, d, e, f\}$ s hranami $(b, c), (c, d), (d, e), (e, f), (f, b)$.
  * Lichý cyklus vyžaduje alespoň 3 barvy: $\chi(C_5) = 3$.
  * Vrchol $a$ je univerzálním vrcholem pro tento cyklus – je spojen hranou se všemi pěti vrcholy $\{b, c, d, e, f\}$.
  * Protože $a$ sousedí se všemi vrcholy cyklu, nesmí mít stejnou barvu jako žádný z nich. Musí mu být přidělena 4. barva $\implies \chi(G) \ge 4$.
* **Horní odhad ($\chi(G) \le 4$):**
  * Graf je rovinný (nakreslen v rovině bez křížení hran), proto podle Věty o 4 barvách platí $\chi(G) \le 4$.
  * *Konstruktivní ověření:* 4 barvami lze vrcholy $a, b, c, d, e, f, g, h, i, j$ obarvit např. takto:
    $$a=4, \quad b=3, \quad c=2, \quad d=1, \quad e=2, \quad f=1, \quad g=2, \quad h=3, \quad i=4, \quad j=3$$
    Žádné dva sousední vrcholy nemají stejnou barvu.
* **Závěr:** $\chi(G) = 4$.

---

## Úloha 3: Eulerovské grafy (Jaro 2025 – 4. 2. 2025)

### Vzorové řešení:

#### 3. (a) Souvislost grafu $G_n$ pro $n > 1$
* Prázdná množina $\emptyset$ je podmnožinou $\{1, \dots, n\}$ a splňuje $|\emptyset| = 0 < n$, je tedy vrcholem grafu $G_n$.
* Pro libovolnou množinu $A \in V(G_n), A \ne \emptyset$, platí $A \cap \emptyset = \emptyset$.
* Z definice hran grafu $G_n$ je vrchol $\emptyset$ spojen hranou se **všemi ostatními vrcholy grafu** (jde o univerzální vrchol).
* Z libovolného vrcholu $A$ do libovolného $B$ vede cesta $A - \emptyset - B$ délky nejvýše 2.
* Graf $G_n$ je tedy **souvislý pro všechna $n > 1$**.

#### 3. (b) Stupeň vrcholu odpovídajícího množině $A$
Stupeň vrcholu závisí na parametru $n$ a na kardinalitě množiny $k = |A|$:
1. **Případ $k = |A| > 0$:**
   * Sousedé množiny $A$ jsou právě ty podmnožiny $B \subset \{1, \dots, n\}$, které jsou s $A$ disjunktní, tedy $B \subseteq \{1, \dots, n\} \setminus A$.
   * Komplement $\{1, \dots, n\} \setminus A$ má velikost $n - k$.
   * Počet všech jeho podmnožin je $2^{n-k}$.
   * Protože $k > 0$, žádná z těchto podmnožin $B$ nemá velikost $n$ (maximální velikost je $n - k < n$). Všechny jsou tedy platnými vrcholy $G_n$.
   * Stupeň vrcholu je:
     $$\deg(A) = 2^{n - |A|} = 2^{n - k}$$
2. **Případ $k = |A| = 0$ (tj. $A = \emptyset$):**
   * $\emptyset$ je disjunktní se všemi podmnožinami. Všech podmnožin množiny $\{1, \dots, n\}$ je $2^n$.
   * Vrcholy $G_n$ jsou ale pouze podmnožiny velikosti $< n$, vypadává tedy celá množina $\{1, \dots, n\}$.
   * Graf nemá smyčky, $\emptyset$ tedy není spojena sama se sebou.
   * Stupeň vrcholu je:
     $$\deg(\emptyset) = 2^n - 2$$

#### 3. (c) Definice eulerovského grafu a eulerovskost $G_n$
* **Definice:** Souvislý graf $G$ je **eulerovský**, pokud v něm existuje uzavřený eulerovský tah (tah, který projde každou hranu grafu právě jednou a skončí ve výchozím vrcholu).
* **Eulerova věta:** Souvislý graf je eulerovský $\iff$ každý jeho vrchol má **sudý stupeň**.
* **Ověření parity stupňů v $G_n$:**
  * Pro $A = \emptyset$: $\deg(\emptyset) = 2^n - 2$. Pro $n \ge 2$ je $2^n$ sudé (dělitelné 4), takže $2^n - 2$ je **sudé číslo**.
  * Pro $|A| = k > 0$: $\deg(A) = 2^{n-k}$. Jelikož $k < n$, je exponent $n - k \ge 1$. Číslo $2^{n-k}$ je tedy celočíselná mocnina dvojky s kladným exponentem, což je **vždy sudé číslo**.
* **Závěr:** Všechny vrcholy mají sudý stupeň a graf je souvislý $\implies$ graf $G_n$ je **eulerovský pro všechna $n > 1$**.

---

## Úloha 4: Rovinné grafy – triangulace a stupně (Jaro 2026 – 2. 2. 2026)

### Vzorové řešení:

#### 4. (a) Eulerova formule
Nechť $G=(V, E)$ je souvislý rovinný graf s $v = |V|$ vrcholy a $e = |E|$ hranami nakreslený v rovině se $s$ stěnami. Pak platí:
$$v - e + s = 2$$

#### 4. (b) Meze počtu hran 2-souvislého grafu s trojúhelníkovými vnitřními stěnami
* Z vrcholové 2-souvislosti plyne, že hranice každé stěny tvoří kružnici a každá hrana leží na hranici právě 2 různých stěn.
* Graf má $s$ stěn celkem: $s - 1$ vnitřních stěn, které jsou trojúhelníky ($C_3$, stupeň 3), a 1 vnější stěnu tvořenou kružnicí $C_k$, kde $3 \le k \le n$.
* Handshaking lemma pro stěny:
  $$2e = \sum_{f} \deg(f) = 3(s - 1) + k$$
* Z Eulerovy formule dosadíme $s = e - n + 2$:
  $$2e = 3(e - n + 2 - 1) + k = 3e - 3n + 3 + k \implies e = 3n - 3 - k$$
* **Maximální počet hran:** Nastává pro minimální $k = 3$ (vnější stěna je také trojúhelník, graf je maximální rovinný):
  $$e_{\max} = 3n - 3 - 3 = \mathbf{3n - 6}$$
* **Minimální počet hran:** Nastává pro maximální $k = n$ (vnější stěna je Hamiltonovská kružnice přes všechny vrcholy, graf je vnějškově rovinný):
  $$e_{\min} = 3n - 3 - n = \mathbf{2n - 3}$$

#### 4. (c) Existence rovinného grafu s $n$ vrcholy stupně 3 a $n$ vrcholy stupně 4
1. **Podmínka sudosti:**
   Graf má $2n$ vrcholů. Součet stupňů je $\sum \deg(v) = 3n + 4n = 7n$.
   Podle Handshaking lemmatu: $2e = 7n \implies e = \frac{7n}{2}$.
   Protože počet hran musí být celé číslo, **$n$ musí být sudé**.
2. **Minimální počet vrcholů:**
   Graf bez smyček a násobných hran s vrcholem stupně 4 musí mít alespoň 5 vrcholů: $2n \ge 5 \implies n \ge 2.5 \implies n \ge 3$.
   Ve spojení se sudostí dostáváme nutnou podmínku: **$n \ge 4$ je sudé číslo** ($n \in \{4, 6, 8, \dots\}$).
3. **Konstrukce pro sudá $n \ge 4$:**
   Pro každé sudé $n = 2k \ge 4$ takový rovinný graf existuje.
   *Konstrukční princip:* Vytvoříme dva soustředné cykly – vnitřní cyklus z $n$ vrcholů stupně 3 a vnější cyklus z $n$ vrcholů stupně 4. Propojením paprsků z vnitřního do vnějšího cyklu a vnější triangulací dorovnáme stupně přesně na požadované hodnoty bez křížení hran.
   Hustota hran $e = 3.5n$ vyhovuje rovinné mezi $e \le 3(2n) - 6 = 6n - 6$ (pro $n \ge 4$ platí $3.5n \le 6n - 6 \iff 2.5n \ge 6 \iff n \ge 2.4$, což je splněno).
* **Závěr:** Rovinný graf existuje právě pro **všechna sudá přirozená čísla $n \ge 4$**.

---

## Úloha 5: Rovinné grafy – komponenty a grafy bez trojúhelníků (Jaro 2023 – 3 body)

### Vzorové řešení:

#### 5. (a) Eulerova formule
Pro obecný rovinný graf s $v = |V|$ vrcholy, $e = |E|$ hranami, $s$ stěnami a $c$ komponentami souvislosti platí:
$$v - e + s = 1 + c$$
*(Vnější neomezená stěna je společná všem komponentám).*

#### 5. (b) Existence grafu s $v = 40, e = 80, c = 5$ bez $C_3$
* Protože graf neobsahuje kružnici $C_3$, každá kružnice má délku alespoň 4.
* Každá stěna rovinného nakreslení má proto stupeň $\deg(f) \ge 4$.
* Z Handshaking lemmatu pro stěny:
  $$2e = \sum_{f} \deg(f) \ge 4s \implies s \le \frac{e}{2}$$
* Dosadíme horní odhad pro $s$ do Eulerovy formule pro $c$ komponent:
  $$1 + c = v - e + s \le v - e + \frac{e}{2} = v - \frac{e}{2}$$
  $$\frac{e}{2} \le v - (1 + c) \implies e \le 2v - 2c - 2$$
* Pro zadané hodnoty $v = 40$ a $c = 5$:
  $$e \le 2(40) - 2(5) - 2 = 80 - 10 - 2 = \mathbf{68}$$
* **Závěr:** Graf s $e = 80$ hranami **nemůže existovat**, neboť maximální počet hran je shora omezen číslem 68 (a $80 > 68$).

#### 5. (c) Nejvyšší možný počet hran
* Nejvyšší možný počet hran je **68**.
* *(Realizovatelnost: Lze sestrojit např. graf se 4 izolovanými vrcholy jako samostatnými komponentami a jednou velkou komponentou o 36 vrcholech bez trojúhelníků, která je maximálním rovinným bipartitním grafem s $e = 2(36) - 4 = 68$ hranami).*

---

## Úloha 6: Binární relace a ekvivalence (Podzim 2025 – 8. 9. 2025)

### Vzorové řešení:

#### 6. (a) Formální definice ekvivalence
Relace $R \subseteq X \times X$ na neprázdné množině $X$ je ekvivalence, právě když splňuje:
1. **Reflexivita:** $\forall x \in X: (x, x) \in R$
2. **Symetrie:** $\forall x, y \in X: (x, y) \in R \implies (y, x) \in R$
3. **Tranzitivita:** $\forall x, y, z \in X: ((x, y) \in R \land (y, z) \in R) \implies (x, z) \in R$

#### 6. (b) Počet různých ekvivalencí na $X = \{a, b, c, d\}$
Počet ekvivalencí odpovídá počtu rozkladů 4-prvkové množiny na disjunktní třídy (Bellovo číslo $B_4$):
* Rozklad $4$ (1 třída velikosti 4): $\binom{4}{4} = \mathbf{1}$
* Rozklad $3 + 1$ (jedna 3-prvková, jedna 1-prvková): $\binom{4}{1} = \mathbf{4}$
* Rozklad $2 + 2$ (dvě 2-prvkové): $\frac{1}{2}\binom{4}{2} = \mathbf{3}$
* Rozklad $2 + 1 + 1$ (jedna 2-prvková, dvě 1-prvkové): $\binom{4}{2} = \mathbf{6}$
* Rozklad $1 + 1 + 1 + 1$ (čtyři 1-prvkové): $\mathbf{1}$
* **Celkem:** $1 + 4 + 3 + 6 + 1 = \mathbf{15}$ ekvivalencí.

#### 6. (c) Příklad relace (tranzitivní, nesymetrická, neantisymetrická)
* **Konstrukce relace:**
  $$R = \{ (a, a), (a, b), (b, a), (b, b), (c, d) \}$$
* **Ověření vlastností:**
  * **Není symetrická:** $(c, d) \in R$, ale $(d, c) \notin R$.
  * **Není antisymetrická:** $(a, b) \in R$ a současně $(b, a) \in R$, avšak $a \ne b$.
  * **Je tranzitivní:** Netriviální předpoklady tranzitivity nastávají pouze pro prvky $a, b$:
    $(a, b) \land (b, a) \implies (a, a) \in R$,
    $(b, a) \land (a, b) \implies (b, b) \in R$.
    Dvojice $(c, d)$ nemá v relaci žádného partnera s počátkem v $d$, implikace tranzitivity tedy platí vakuózně.

---

# ČÁST 2: Vzorová řešení klíčových úloh ze sylabu

---

## Úloha 7: Toky v sítích a Věta o maximálním toku a minimálním řezu

### Vzorové řešení:

#### 7. (a) Definice sítě, toku a velikosti toku
* **Toková síť:** Pětice $(V, E, z, s, c)$, kde $(V, E)$ je konečný orientovaný graf, $z \in V$ je zdroj, $s \in V \setminus \{z\}$ je spotřebič (stok) a $c: E \to [0, +\infty)$ je kapacitní funkce hran.
* **Tok v síti:** Funkce $f: E \to [0, +\infty)$ splňující:
  1. *Kapacitní omezení:* $\forall e \in E: 0 \le f(e) \le c(e)$.
  2. *Kirchhoffův zákon (zachování toku):* Pro každý vnitřní uzel $u \in V \setminus \{z, s\}$ platí:
     $$\sum_{v: (v, u) \in E} f(v, u) = \sum_{v: (u, v) \in E} f(u, v) \quad (\text{přítok do } u = \text{odtok z } u)$$
* **Velikost toku $w(f)$:** Čistý odtok ze zdroje $z$:
  $$w(f) = \sum_{v: (z, v) \in E} f(z, v) - \sum_{v: (v, z) \in E} f(v, z)$$

#### 7. (b) Řez v síti a věta Max-Flow Min-Cut
* **Řez v síti:** Množina hran odpovídající rozkladu $V = A \cup B$ s podmínkou $z \in A, s \in B, A \cap B = \emptyset$. Hrany řezu jsou orientované hrany vedoucí z $A$ do $B$.
* **Kapacita řezu:**
  $$c(A, B) = \sum_{u \in A, v \in B, (u, v) \in E} c(u, v)$$
* **Věta o maximálním toku a minimálním řezu (Ford-Fulkerson):**
  Pro každý tok $f$ a každý řez $(A, B)$ platí $w(f) \le c(A, B)$. Navíc v každé síti existuje maximální tok $f_{\max}$ a minimální řez $(A, B)_{\min}$ a platí:
  $$w(f_{\max}) = c(A, B)_{\min}$$

#### 7. (c) Výpočet pro zadanou síť
* **Zadání hran a kapacit:**
  $c(z, a) = 10, c(z, b) = 10$;
  $c(a, b) = 2, c(a, c) = 4, c(a, d) = 8$;
  $c(b, d) = 9$;
  $c(c, s) = 10, c(d, s) = 10$.
* **Postupné posílání toku (zlepšující cesty):**
  1. Cesta $z \to a \to c \to s$: úzké hrdlo $c(a, c) = 4 \implies$ pošleme **4**.
  2. Cesta $z \to a \to d \to s$: na hraně $(z, a)$ zbývá $10 - 4 = 6$, $c(a, d) = 8, c(d, s) = 10 \implies$ pošleme **6**.
     *Nyní je hrana $(z, a)$ plně nasycena ($f(z, a) = 10$).*
  3. Cesta $z \to b \to d \to s$: na hraně $(d, s)$ zbývá rezerva $10 - 6 = 4$. Hrany $(z, b)$ a $(b, d)$ mají rezervy dostatek $\implies$ pošleme **4**.
     *Nyní je hrana $(d, s)$ plně nasycena ($f(d, s) = 10$).*
* **Celková velikost toku:**
  $$w(f) = 4 + 6 + 4 = \mathbf{14}$$
* **Nalezení minimálního řezu:**
  Prozkoumáme uzly dosažitelné ze zdroje $z$ po nenasycených (reziduálních) hranách:
  * Z $z$ vede nenasycená hrana do $b$ ($f(z, b) = 4 < 10$) $\implies b \in A$.
  * Z $b$ vede nenasycená hrana do $d$ ($f(b, d) = 4 < 9$) $\implies d \in A$.
  * Z $d$ vede zpětná reziduální hrana do $a$ ($f(a, d) = 6 > 0$, tok lze ubrat) $\implies a \in A$.
  * Z $a$ vede do $c$ hrana s kapacitou 4, která je plně nasycena ($f(a, c) = 4$). Uzel $c$ není dosažitelný $\implies c \in B$.
  * Z $d$ vede do $s$ hrana s kapacitou 10, která je plně nasycena ($f(d, s) = 10$). Uzel $s$ není dosažitelný $\implies s \in B$.
* **Minimální řez:**
  $$A = \{z, a, b, d\}, \quad B = \{c, s\}$$
  Hrany vedoucí z $A$ do $B$ jsou $(a, c)$ a $(d, s)$.
  Kapacita řezu: $c(A, B) = c(a, c) + c(d, s) = 4 + 10 = \mathbf{14}$.
* **Závěr:** Protože velikost toku $w(f) = 14$ se přesně rovná kapacitě řezu $c(A, B) = 14$, je maximální tok roven **14** a nalezený řez je minimální.

---

## Úloha 8: Stromy a jejich ekvivalentní charakteristiky

### Vzorové řešení:

#### 8. (a) Definice stromu a 4 ekvivalentní charakteristiky
* **Základní definice:** Strom je souvislý acyklický graf.
* **Ekvivalentní charakteristiky (pro graf $G=(V, E)$ s $|V| = n$):**
  1. Mezi každými dvěma různými vrcholy $u, v \in V$ existuje **právě jedna cesta**.
  2. $G$ je souvislý a odebráním libovolné hrany $e \in E$ se stane nesouvislým (minimální souvislost / každá hrana je most).
  3. $G$ je acyklický a přidáním libovolné nové hrany $e \in \binom{V}{2} \setminus E$ vznikne graf obsahující právě jednu kružnici (maximální acykličnost).
  4. $G$ je souvislý a platí $|E| = |V| - 1 = n - 1$.
  *(Další možná: $G$ je acyklický a platí $|E| = n - 1$).*

#### 8. (b) Důkaz existence alespoň dvou listů pro $n \ge 2$
* **Důkaz přes nejdelší cestu:**
  * Nechť $G=(V, E)$ je strom s $n \ge 2$ vrcholy. Protože $G$ je konečný acyklický graf s alespoň jednou hranou, existuje v něm nejdelší prostá cesta $P = (v_0, v_1, \dots, v_k)$, kde $k \ge 1$.
  * Uvažme koncový vrchol $v_k$:
    * Všichni sousedé vrcholu $v_k$ musí nutně ležet na cestě $P$. Kdyby existoval soused $w \notin P$, mohli bychom cestu prodloužit o hranu $\{v_k, w\}$, což je spor s maximalitou cesty $P$.
    * Žádný uzel $v_i$ pro $i \in \{0, 1, \dots, k - 2\}$ nemůže být sousedem $v_k$, jinak by hrana $\{v_k, v_i\}$ spolu s úsekem cesty mezi $v_i$ a $v_k$ vytvořila kružnici, což je spor s acykličností stromu.
    * Jediným sousedem vrcholu $v_k$ je tedy jeho bezprostřední předchůdce $v_{k-1}$ na cestě.
    * Tedy $\deg(v_k) = 1$, což znamená, že $v_k$ je list.
  * Zcela totožnou úvahou pro počáteční vrchol cesty $v_0$ plyne, že jeho jediným sousedem je $v_1$, tedy $\deg(v_0) = 1$ a $v_0$ je list.
  * Protože $k \ge 1$, jsou $v_0$ a $v_k$ dva různé vrcholy.
  * Každý strom s $n \ge 2$ má tedy alespoň **dva listy**. $\square$

---

## Úloha 9: Princip inkluze a exkluze (PIE) a problém šatnářky

### Vzorové řešení:

#### 9. (a) Věta o PIE a myšlenka důkazu
* **Znění věty:** Pro konečné množiny $A_1, A_2, \dots, A_n$ platí:
  $$\left|\bigcup_{i=1}^n A_i\right| = \sum_{\emptyset \ne I \subseteq \{1, \dots, n\}} (-1)^{|I|+1} \left|\bigcap_{i \in I} A_i\right| = \sum_{i} |A_i| - \sum_{i < j} |A_i \cap A_j| + \sum_{i < j < k} |A_i \cap A_j \cap A_k| - \dots + (-1)^{n+1} |A_1 \cap \dots \cap A_n|$$
* **Myšlenka důkazu:**
  Uvažme libovolný prvek $x$, který náleží do právě $k$ množin z tohoto systému ($1 \le k \le n$).
  Na pravé straně vzorce se prvek $x$ započítá:
  * v jednoprvkových podmnožinách právě $\binom{k}{1}$-krát,
  * ve dvouprvkových průnicích se znaménkem $-$ právě $\binom{k}{2}$-krát,
  * ve tříprvkových průnicích se znaménkem $+$ právě $\binom{k}{3}$-krát, atd.
  Jeho celkový příspěvek na pravé straně je roven:
  $$S = \binom{k}{1} - \binom{k}{2} + \binom{k}{3} - \dots + (-1)^{k+1}\binom{k}{k}$$
  Podle binomické věty pro $(1 - 1)^k$ platí:
  $$0 = (1 - 1)^k = \binom{k}{0} - \binom{k}{1} + \binom{k}{2} - \dots = 1 - S \implies S = 1$$
  Každý prvek ze sjednocení se tedy na pravé straně započítá právě jednou.

#### 9. (b) Odvození počtu permutací bez pevného bodu a výpočet $D_5$
* **Pevný bod:** Prvek $i \in \{1, \dots, n\}$ je pevným bodem permutace $\pi \in S_n$, pokud $\pi(i) = i$.
* **Odvození $D_n$:**
  * Univerzum je množina všech permutací $U = S_n$, $|U| = n!$.
  * Nechť $A_i$ je množina permutací majících pevný bod $i$ ($\pi(i) = i$).
  * Pro libovolnou $k$-prvkovou množinu indexů $I \subseteq \{1, \dots, n\}$ je v průniku $\bigcap_{i \in I} A_i$ fixováno daných $k$ prvků. Zbývajících $n - k$ prvků lze zpermutovat libovolně:
    $$\left|\bigcap_{i \in I} A_i\right| = (n - k)!$$
  * Všech $k$-prvkových podmnožin indexů je $\binom{n}{k}$.
  * Podle PIE je počet permutací s alespoň jedním pevným bodem roven:
    $$\left|\bigcup_{i=1}^n A_i\right| = \sum_{k=1}^n (-1)^{k+1} \binom{n}{k} (n - k)! = \sum_{k=1}^n (-1)^{k+1} \frac{n!}{k!}$$
  * Počet permutací bez pevného bodu $D_n = |U| - |\bigcup A_i|$:
    $$D_n = n! - \sum_{k=1}^n (-1)^{k+1} \frac{n!}{k!} = n! \sum_{k=0}^n \frac{(-1)^k}{k!}$$
* **Výpočet $D_5$:**
  $$D_5 = 5! \left( \frac{1}{0!} - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \frac{1}{4!} - \frac{1}{5!} \right) = 120 \left( 1 - 1 + \frac{1}{2} - \frac{1}{6} + \frac{1}{24} - \frac{1}{120} \right)$$
  $$D_5 = 120 \cdot \frac{60 - 20 + 5 - 1}{120} = 60 - 20 + 5 - 1 = \mathbf{44}$$

---

## Úloha 10: Hallova věta o systému různých reprezentantů (SRR)

### Vzorové řešení:

#### 10. (a) Definice systému různých reprezentantů (SRR)
Nechť $\mathcal{M} = (M_1, M_2, \dots, M_n)$ je systém podmnožin množiny $X$. Systém různých reprezentantů pro $\mathcal{M}$ je uspořádaná $n$-tice navzájem různých prvků $(x_1, x_2, \dots, x_n) \in X^n$ taková, že:
$$\forall i \in \{1, \dots, n\}: x_i \in M_i \quad \land \quad \forall i \ne j: x_i \ne x_j$$

#### 10. (b) Znění Hallovy věty
Systém množin $\mathcal{M} = (M_1, \dots, M_n)$ má systém různých reprezentantů právě tehdy, když pro každou podmnožinu indexů $I \subseteq \{1, \dots, n\}$ platí tzv. **Hallova podmínka**:
$$\left| \bigcup_{i \in I} M_i \right| \ge |I|$$

#### 10. (c) Analýza zadaného systému množin
Zadán systém:
$$M_1 = \{1, 2\}, \quad M_2 = \{2, 3\}, \quad M_3 = \{1, 3\}, \quad M_4 = \{1, 2, 3\}, \quad M_5 = \{3, 4, 5\}$$
* **Ověření Hallovy podmínky:**
  Zvolme podmnožinu indexů $I = \{1, 2, 3, 4\}$.
  * Počet indexů je $|I| = 4$.
  * Sjednocení odpovídajících množin:
    $$\bigcup_{i \in I} M_i = M_1 \cup M_2 \cup M_3 \cup M_4 = \{1, 2\} \cup \{2, 3\} \cup \{1, 3\} \cup \{1, 2, 3\} = \{1, 2, 3\}$$
  * Velikost sjednocení:
    $$\left| \bigcup_{i \in I} M_i \right| = |\{1, 2, 3\}| = 3$$
  * Vidíme, že:
    $$\left| \bigcup_{i \in I} M_i \right| = 3 < 4 = |I|$$
* **Závěr:** Systém **nemá systém různých reprezentantů**, protože pro indexovou množinu $I = \{1, 2, 3, 4\}$ je porušena Hallova podmínka (4 množiny pokrývají dohromady pouze 3 různé prvky).

---

## Úloha 11: Částečná uspořádání (Posety), extrémy a Věta o dlouhém a širokém

### Vzorové řešení:

#### 11. (a) Definice posetu
Částečně uspořádaná množina (poset) je dvojice $(X, \le)$, kde $X$ je množina a $\le$ je binární relace na $X$, která je:
1. **Reflexivní:** $\forall x \in X: x \le x$
2. **Slabě antisymetrická:** $\forall x, y \in X: (x \le y \land y \le x) \implies x = y$
3. **Tranzitivní:** $\forall x, y, z \in X: (x \le y \land y \le z) \implies x \le z$

#### 11. (b) Rozdíl mezi nejmenším a minimálním prvkem
* **Nejmenší prvek $m \in X$:** Prvek, který je menší nebo roven **úplně všem** prvkům v množině $X$:
  $$\forall x \in X: m \le x$$
  Nejmenší prvek existuje nejvýše jeden.
* **Minimální prvek $m \in X$:** Prvek, pod kterým už v uspořádání neleží žádný jiný prvek:
  $$\forall x \in X: x \le m \implies x = m \quad (\text{ekvivalentně } \neg\exists x \in X: x < m)$$
  Minimálních prvků může existovat více (mohou být vzájemně neporovnatelné). Pokud však v posetu existuje nejmenší prvek, je zároveň jediným minimálním prvkem.

#### 11. (c) Řetězec, antiřetězec, výška, šířka a Věta o dlouhém a širokém
* **Řetězec:** Podmnožina $C \subseteq X$, jejíž každé dva prvky jsou navzájem porovnatelné ($\forall x, y \in C: x \le y \lor y \le x$).
* **Antiřetězec:** Podmnožina $A \subseteq X$, jejíž žádné dva různé prvky nejsou navzájem porovnatelné ($\forall x, y \in A, x \ne y: x \not\le y \land y \not\le x$).
* **Výška posetu:** Velikost (počet prvků) nejdelšího řetězce v $(X, \le)$.
* **Šířka posetu:** Velikost (počet prvků) největšího antiřetězce v $(X, \le)$.
* **Věta o dlouhém a širokém posetu:**
  Každá konečná částečně uspořádaná množina $(X, \le)$ s alespoň $a \cdot b + 1$ prvky obsahuje buď řetězec velikosti alespoň $a + 1$, nebo antiřetězec velikosti alespoň $b + 1$ (platí $|X| \le \text{výška} \cdot \text{šířka}$).

#### 11. (d) Analýza posetu dělitelnosti na $X = \{1, 2, 3, 4, 6, 8, 12, 24\}$
1. **Extrémy:**
   * Číslo $1$ dělí každé číslo z $X$ ($\forall x \in X: 1 \mid x$). Číslo $1$ je tedy **jediný minimální prvek** a současně **nejmenší prvek**.
   * Každé číslo z $X$ dělí číslo $24$ ($\forall x \in X: x \mid 24$). Číslo $24$ je tedy **jediný maximální prvek** a současně **největší prvek**.
2. **Výška posetu (nejdelší řetězec):**
   * Každý krok v dělitelnostním řetězci odpovídá vynásobení alespoň jedním prvočíslem.
   * Prvočíselný rozklad maxima: $24 = 2^3 \cdot 3^1$. Součet exponentů je $3 + 1 = 4$.
   * Maximální řetězec může mít nejvýše $4 + 1 = 5$ prvků.
   * Příklad maximálního řetězce:
     $$1 \mid 2 \mid 4 \mid 8 \mid 24 \quad (\text{délka 5})$$
     *(Další možnosti: $1 \mid 2 \mid 4 \mid 12 \mid 24$ nebo $1 \mid 3 \mid 6 \mid 12 \mid 24$).*
   * **Výška posetu je 5**.
3. **Šířka posetu (největší antiřetězec):**
   * Hledáme prvky, které se navzájem nedělí.
   * Prvek $1$ dělí vše, prvek $24$ je dělitelný vším $\implies$ v netriviálním antiřetězci nemohou figurovat.
   * V množině $\{2, 3, 4, 6, 8, 12\}$:
     * Dvojice $\{8, 12\}$ tvoří antiřetězec ($8 \nmid 12$ a $12 \nmid 8$).
     * Dvojice $\{3, 8\}$ tvoří antiřetězec ($3 \nmid 8$ a $8 \nmid 3$).
   * Tříprvkový antiřetězec neexistuje:
     * Pokud bychom vzali $3$, nesmíme vzít násobky $6, 12$. Zbývá $\{2, 4, 8\}$, kde ale platí $2 \mid 4 \mid 8$ (řetězec), z nichž lze vybrat nejvýše 1 prvek $\implies$ velikost nanejvýš $1 + 1 = 2$.
     * Pokud $3$ nevezmeme, ze zbylých prvků $\{2, 4, 6, 8, 12\}$ má každý maximální antiřetězec velikost nejvýše 2.
   * **Šířka posetu je 2**.
   *(Poznámka: $|X| = 8 \le 5 \cdot 2 = 10$, což přesně demonstruje Větu o dlouhém a širokém).*

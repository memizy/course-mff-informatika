# Test 5: Specializace (Web, DB, Data) a Architektury & Programování

* **Datum zadání:** 5. 9. 2026
* **Okruhy:** Architektury počítačů a OS, Programování (C++/C#), Databáze (SQL, BCNF), Webová bezpečnost (CSRF, XSS), Datový management a NoSQL (B+ stromy, Cypher).
* **Styl:** Praktické, aplikované zkouškové úlohy z minulých termínů MFF UK.
* **Časový rámec:** Doporučeno cca 90–120 minut (v klidu, s rozmyslem).
* **Instrukce:** Do označených bloků `> **Tvé řešení:**` piš přímo své odpovědi.

---

## Úloha 1: Architektury a OS – Dvouúrovňové stránkování a překlad adres (MMU)

Uvažujte 32bitovou architekturu s virtuální pamětí se stránkováním.
* Velikost stránky je **4 KiB** ($2^{12}$ B).
* Používá se standardní **dvouúrovňový stránkovací mechanismus**:
  * 10 bitů: Index do adresáře stránek (Page Directory Index, PDI)
  * 10 bitů: Index do tabulky stránek (Page Table Index, PTI)
  * 12 bitů: Posun v rámci stránky (Offset)
* Položka adresáře i položka tabulky stránek má velikost **4 bajty** (obsahuje číslo fyzického rámce a příznaky jako Present, Writable, User).

Mějme virtuální adresu v šestnáctkové soustavě: `0x00403ABC`.

### Podotázky:
1. **(a)** Rozdělte tuto adresu na jednotlivé složky: určete **Page Directory Index**, **Page Table Index** a **Offset**. Uveďte jejich hodnoty v hexadecimálním i dekadickém zápisu.
2. **(b)** Jaká je velikost jedné tabulky stránek (druhé úrovně) v bajtech? Proč je tato velikost zvolena právě takto vzhledem k velikosti rámce? Kolik úrovní stránkování by bylo potřeba, kdybychom přešli na 64bitovou architekturu se 4KiB stránkami a 48bitovým virtuálním adresním prostorem (při zachování 512 položek na tabulku, tj. 9 bitů na úroveň a 8 B na položku)?
3. **(c)** K čemu slouží hardwarová vyrovnávací paměť **TLB** (Translation Lookaside Buffer)? Co se s obsahem TLB musí stát při přepnutí kontextu mezi dvěma různými uživatelskými procesy, pokud procesor nepodporuje identifikátory adresního prostoru (ASID / PCID)?

> **Tvé řešení 1:**
> 
> *(a) Rozdělení adresy:*
> 
> *(b) Velikost tabulky a přechod na 64 bitů:*
> 
> *(c) Role TLB a přepnutí kontextu:*
> 

---

## Úloha 2: Architektury a OS – Synchronizace, Souběh a Uváznutí (Deadlock)

Mějme bankovní aplikaci s převody mezi účty v jazyce C++ / C#. Každý účet má svůj vlastní zámek (mutex).

```cpp
class Account {
public:
    int id;
    int balance;
    std::mutex mtx;
};

void transfer(Account& from, Account& to, int amount) {
    from.mtx.lock();
    to.mtx.lock();

    from.balance -= amount;
    to.balance += amount;

    to.mtx.unlock();
    from.mtx.unlock();
}
```

Dvě vlákna současně provádějí převody mezi účty `acc1` (id: 101) a `acc2` (id: 202):
* **Vlákno A:** volá `transfer(acc1, acc2, 500);`
* **Vlákno B:** volá `transfer(acc2, acc1, 300);`

### Podotázky:
1. **(a)** Popište scénář (posloupnost kroků vláken A a B), který vede k **uváznutí (deadlocku)**.
2. **(b)** Vyjmenujte **4 Coffmanovy podmínky**, které musí současně platit, aby mohl deadlock nastat.
3. **(c)** Navrhněte konkrétní a jednoduchou úpravu funkce `transfer`, která deadlocku spolehlivě zabrání bez použití globálního zámku. Kterou z Coffmanových podmínek vaše úprava poruší?

> **Tvé řešení 2:**
> 
> *(a) Scénář vedoucí k deadlocku:*
> 
> *(b) 4 Coffmanovy podmínky:*
> 
> *(c) Návrh opravy a porušená podmínka:*
> 

---

## Úloha 3: Programování – Objektový layout, Vtables a Object Slicing (C++)

Uvažujte následující kód v C++ na 64bitové architektuře (ukazatele mají 8 bajtů, `int` má 4 bajty):

```cpp
#include <iostream>

class Base {
public:
    int x = 10;
    virtual void f() { std::cout << "Base::f\n"; }
    void g() { std::cout << "Base::g\n"; }
    virtual ~Base() {}
};

class Derived : public Base {
public:
    int y = 20;
    void f() override { std::cout << "Derived::f\n"; }
    void g() { std::cout << "Derived::g\n"; }
};

int main() {
    Derived d;
    Base* p = &d;

    p->f();
    p->g();

    Base b = d;
    b.f();
}
```

### Podotázky:
1. **(a)** Jaký bude přesný textový výstup programu po spuštění?
2. **(b)** Vysvětlete detailně mechanismus volání `p->f()` vs. `p->g()`:
   * Které volání se překládá staticky a které dynamicky?
   * Jak přesně funguje překlad `p->f()` přes ukazatel `vptr` a tabulku virtuálních metod `vtable`?
3. **(c)** Co přesně se stalo na řádku `Base b = d;` (tzv. *object slicing*) a proč následné volání `b.f()` nevypíše `Derived::f`? Jak vypadá paměťové uspořádání (layout a zarovnání/padding) objektu `Derived` a jaká je jeho hodnota `sizeof(Derived)` na 64bitové architektuře?

> **Tvé řešení 3:**
> 
> *(a) Výstup programu:*
> 
> *(b) Mechanismus volání f() vs. g() a role vtable:*
> 
> *(c) Object slicing a paměťový layout Derived:*
> 

---

## Úloha 4: Specializace Databáze – Funkční závislosti, BCNF a SQL

Mějme relační schéma $R(A, B, C, D, E)$ a množinu funkčních závislostí:
$$F = \{ A \to B, \ B \to C, \ CD \to E, \ E \to A \}$$

### Podotázky:
1. **(a)** Určete uzávěr atributů $\{B, D\}^+$ vzhledem k $F$.
2. **(b)** Najděte **všechny kandidátní klíče** relace $R$.
3. **(c)** Zjistěte, zda je relace $R$ v **Boyce-Coddově normální formě (BCNF)**. Pokud ne, uveďte závislost, která BCNF porušuje, a proveďte bezeztrátovou dekompozici relace $R$ do BCNF. Zachovává vaše dekompozice všechny funkční závislosti?
4. **(d) SQL dotaz:** Mějme tabulku:
   `Objednavky(id INT, zakaznik_id INT, datum DATE, castka DECIMAL(10,2))`
   Napište standardní SQL dotaz, který vypíše `zakaznik_id` a celkovou sumu útraty pro všechny zákazníky, kteří v roce 2025:
   * udělali **alespoň 3 objednávky**,
   * a jejich celková útrata v tomto roce přesáhla **10 000 Kč**.
   Výsledek seřaďte sestupně podle celkové útraty.

> **Tvé řešení 4:**
> 
> *(a) Uzávěr {B, D}^+:*
Na B závisí C přidáme ho do množiny, pak E závisí na CD také ho přidáme a A na E, také ho tedy přidáme takže uzávěrem je {A,B,C,D,E}
> 
> *(b) Kandidátní klíče:*
Kandidátními klíči jsou AD, BD, CD, ED
> 
> *(c) BCNF test a dekompozice:*
Problémem je že máme závislosti které nejsou závislé na nadklíči
Zvolme tedy jako klíč CD, pak množinu funkčních závislostí změníme na
CD->A,B,E
> 
> *(d) SQL dotaz:*
>
SELECT zakaznik_id, SUM(castka)
FROM Objednavky
WHERE YEAR(datum) = 2025
AND (SELECT COUNT(id) FROM Objednavky GROUP BY zakaznik_id) >= 3
GROUP BY zakaznik_id
HAVING SUM(castka) > 10000
ORDER BY SUM(castka) DESC

---

## Úloha 5: Specializace Web – Bezpečnost (CSRF vs. XSS, Cookies a CORS)

Banka provozuje webové bankovnictví. Přihlášený uživatel má v prohlížeči uloženu relační session cookie:
`Set-Cookie: session_id=abc123secret; Path=/; Domain=mojebanka.cz`

Převod peněz se provádí odesláním HTTP požadavku:
`POST /api/prevod HTTP/1.1`
`Host: mojebanka.cz`
`Content-Type: application/x-www-form-urlencoded`
`Příjemce=987654&Castka=50000`

### Podotázky:
1. **(a) Útok CSRF (Cross-Site Request Forgery):**
   * Útočník vytvoří stránku `http://utocnik.cz/soutez.html`. Jak na ni umístí kód, který bez vědomí oběti převede peníze, pokud má oběť v jiném tabu otevřené bankovnictví?
   * Proč prohlížeč k tomuto požadavku na `mojebanka.cz` automaticky přiloží cookie `session_id`?
2. **(b) Obrana proti CSRF:**
   * Vysvětlete rozdíl mezi nastavením cookie `SameSite=Strict`, `SameSite=Lax` a `SameSite=None`. Ochrání `SameSite=Lax` před tímto POST formulářem?
   * Jak funguje obrana pomocí **CSRF tokenu** (Synchronizer Token Pattern)? Proč útočník ze své domény `utocnik.cz` nemůže tento token přečíst (jaký mechanismus prohlížeče mu v tom brání)?
3. **(c) Vztah s XSS a příznak `HttpOnly`:**
   * Pokud by aplikace obsahovala zranitelnost **Stored XSS** (útočník injectnul `<script>`), zabrání příznak `HttpOnly` na session cookie tomu, aby útočník převedl peníze? Vysvětlete proč ano, nebo proč ne.

> **Tvé řešení 5:**
> 
> *(a) Průběh CSRF útoku a chování prohlížeče:*
Umístí tam redirect na stránky banky s POST metodou na endpoint pro převod peněz s vyplněným body pro přeposlání peněz
Protože prohlížeč cookies automaticky příkládá k dotazům na server na dané stránce a z pohledu prohlížeče je uživatel po přesměrování na url adrese banky  
> 
> *(b) SameSite cookies a Synchronizer Token Pattern:*
Samesite none udělá že se cookie bude posílat i při dotazech na ostatní stránky než jen naše to určitě necheme, samesite lax posílá token pouze na naší doméně a subdoménách a strict pouze na této doméně, před tím CSRF útokem nás to neochrání protože uživatel je fyzicky na doméně banky
Abychom měli ochranu proti CSRF je potřeba aby server při generování formuláře vygeneroval na serveru token a ten poslal uživateli tedy kódu frontendu protože server může povolovat jen dotazy z naší domény tak někdo jiný nemůže ze své domény tento tajný token získat a jeho požadavky po přesměrování uživatele ho nebudou obsahovat a budou tedy neplatné
> 
> *(c) Dopad XSS při existenci HttpOnly cookie:*
> Útočník se v takovémto případě nedostane k samotné cookie tedy nemůže se vydávat za samotného uživatele na svém zařízení, ale stále je to ale velmi nebezpečné protože nyní může pokud je uživatel přihlášen a načte se mu škodlivý skript, tak může nyní získat ten anti-csrf token od serveru který si myslí že ho uživatel normálně chce a následně ho poslat i s příkazem na převod peněz když například uživatel na něco klikne

---

## Úloha 6: Specializace Datový management – B+ stromy a Grafové dotazování (Cypher)

### Podotázky:
1. **(a) B+ stromy vs. B-stromy a disková paměť:**
   * Databázové stroje (jako PostgreSQL nebo InnoDB v MySQL) používají pro indexy téměř výhradně **B+ stromy** namísto klasických B-stromů nebo binárních stromů (AVL, Červeno-černé).
   * Uveďte **dvě hlavní výhody** B+ stromu pro disková úložiště a rozsahové dotazy (např. `WHERE vek BETWEEN 20 AND 30`).
   * Jak v B+ stromu funguje zřetězení listů?
2. **(b) Grafová databáze a jazyk Cypher (Neo4j):**
   Mějme sociální síť reprezentovanou v grafové databázi:
   * Uzly s návěštím `:Uzivatel` a vlastností `jmeno: STRING`.
   * Orientované hrany `:SLEDUJE` (např. `(u1)-[:SLEDUJE]->(u2)` znamená, že uživatel $u_1$ sleduje $u_2$).
   
   Napište dotaz v jazyce **Cypher**, který pro uživatele se jménem `"Petr"` najde **doporučení nových lidí ke sledování** („přátelé přátel“):
   * Hledáme uživatele $X$, které sleduje někdo, koho sleduje Petr.
   * Petr sám uživatele $X$ ještě nesleduje a $X$ není sám Petr.
   * Vraťte jméno doporučeného uživatele $X$ a počet společných vazeb (kolik lidí, které Petr sleduje, sleduje $X$). Výsledek seřaďte sestupně podle počtu těchto vazeb.

> **Tvé řešení 6:**
> 
> *(a) Výhody B+ stromů na disku a rozsahové dotazy:*
V B stromu jsou všechna data uložena pouze v listech, díky tomu nejsou stromy hluboké většinou pouze 3 až 4 patra což díky tomu že každé čtení z pevného disku je pomalé hodně pomáhá oproti AVL či červeno černým stromům, zároveň všechny listy což jsou bloky dat jsou propojeny tvoří linked list od nižších po vyší indexy díky tomu mohou rozsahové dotazy pouze skákat po těchto linkách a načítat rychle další bloky dat uložené na heapu
> 
> *(b) Cypher dotaz pro doporučování uživatelů:*
MATCH
(u)<-[:SLEDUJE]-(:Uzivatel)<-[:SLEDUJE]-("Petr")
WHERE
NOT ("Petr")-[:SLEDUJE]->(u)
AND "Petr" <> u
RETURN u, COUNT(u-[:SLEDUJE]->(:Uzivatel)<-("Petr"))

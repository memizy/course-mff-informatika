# Předpoklady vět (Přísně dle Cheat-Sheetu – čtení na 1 minutu)

---

# MATEMATICKÁ ANALÝZA

### 1. Předpoklad: Spojitá na uzavřeném a omezeném intervalu $[a, b]$
* **Weierstrassova věta** (funkce je omezená a **nabývá maxima i minima**)
* **Bolzano-Darbouxova věta** (nabývání mezihodnot, pro $f(a)f(b) < 0$ existence kořene $f(c) = 0$)
* **Riemannovská integrovatelnost** (spojitost na $[a, b]$ zaručuje existenci integrálu)

### 2. Předpoklad: Otevřený interval $I$
* **Definice primitivní funkce** ($F'(x) = f(x)$)
* **Existence primitivní funkce** (spojitá na $I \implies$ má primitivní funkci)
* **Integrace per partes** pro neurčitý integrál
* **2. věta o substituci** (navíc: $\varphi$ je prostá a $\varphi'(t) \ne 0$)

### 3. Předpoklad: Vlastní (konečná) derivace v bodě / na okolí
* **Diferencovatelnost $\implies$ spojitost** (vlastní derivace $f'(b) \in \mathbb{R} \implies$ spojitost v $b$)
* **Aritmetika derivací** (vzorce pro $(f \pm g)', (fg)', (f/g)'$)
* **Fermatova věta** (nutná podmínka lokálního extrému: existuje-li $f'(a)$, pak $f'(a) = 0$)
* **Taylorova věta s Peanovým zbytkem** (vyžaduje vlastní $n$-tou derivaci v bodě $a$)
* **l'Hospitalovo pravidlo** (vlastní derivace na $P(a, \delta)$, $g' \ne 0$, typ $\frac{0}{0}$ nebo $\frac{\text{cokoliv}}{\pm\infty}$, existence limity derivací)

### 4. Předpoklad: $f \in \mathcal{R}[a, b]$ (Riemannovsky integrovatelná)
* **1. základní věta analýzy** (funkce horní meze $F(x) = \int_a^x f$ je spojitá; v bodě spojitosti $f$ platí $F' = f$)
* **2. základní věta analýzy / Newton-Leibniz** ($\int_a^b f = [F]_a^b$, kde $F$ je primitivní na $(a, b)$ a spojitá na $[a, b]$)

### 5. Předpoklad: Monotonie a omezenost
* **Věta o limitě monotónní posloupnosti** (monotónní + omezená $\implies$ vlastní limita)
* **Integrální kritérium řad** (funkce je spojitá, kladná a **nerostoucí** na $[1, \infty)$)

### 6. Předpoklad: Výraz má v $\mathbb{R}^*$ smysl / vlastnosti limit
* **Aritmetika limit posloupností a funkcí** (výraz musí mít smysl: vyloučeno $\infty - \infty, \frac{0}{0}, 0 \cdot \infty, \frac{A}{0}$)
* **Věta o dvou policajtech** ($a_n \le c_n \le b_n$, obě krajní jdou ke **stejné** limitě)
* **Heineho věta** (platí pro **každou** posloupnost $x_n \to a, x_n \ne a$)
* **Věta o limitě složené funkce (VOLSF)** (podmínka P1: $f$ je spojitá v limitě $g$, NEBO P2: $g(x) \ne B$ na $P$)
* **Přechod k limitě v nerovnosti** (z $a_n < b_n$ plyne pouze neostrá $\lim a_n \le \lim b_n$)

---

# LINEÁRNÍ ALGEBRA

### 1. Předpoklad: Čtvercová matice $n \times n$
* **Determinant a Laplaceův rozvoj** (definováno pouze pro čtvercové matice)
* **Charakteristický polynom a vlastní čísla** ($\det(A - \lambda I) = 0$, $Ax = \lambda x$)
* **Stopa matice $\operatorname{trace}(A)$** (součet prvků na hlavní diagonále)
* **Podobnost matic ($A \sim B$)** ($A = R B R^{-1}$, vyžaduje regulární matici $R$)
* **Diagonalizovatelnost ($A = S D S^{-1}$)** (podmínka: algebraická násobnost = geometrická násobnost pro všechna vlastní čísla)

### 2. Předpoklad: Reálná symetrická matice ($A = A^T$)
* **Spektrální věta pro symetrické matice** (všechna vl. čísla jsou reálná $\implies$ je **ortogonálně diagonalizovatelná** $A = Q D Q^T$)

### 3. Předpoklad: Symetrická pozitivně definitní matice (PD, $x^T A x > 0$ pro $x \ne 0$)
* **Věta o Choleského rozkladu** ($A = U^T U$, kde $U$ je jediná horní trojúhelníková s kladnou diagonálou)
* **Sylvestrovo kritérium** (matice je PD $\iff$ všechny hlavní minory $\det(A_k) > 0$)
* **Gramova matice** ($G_{ij} = \langle v_i, v_j \rangle$ je PD $\iff$ vektory $v_i$ jsou lineárně nezávislé)

### 4. Předpoklad: Regulární matice ($\det(A) \ne 0 \iff \operatorname{rank}(A) = n$)
* **Existence inverzní matice $A^{-1}$** ($A A^{-1} = I$)
* **Jednoznačnost řešení soustavy $Ax = b$** ($x = A^{-1}b$)
* **Triviální jádro** ($\operatorname{Ker}(A) = \{\mathbf{0}\}$)

### 5. Předpoklad: Obecná matice $A \in \mathbb{K}^{m \times n}$ (libovolné rozměry)
* **Frobeniova věta** (soustava $Ax = b$ má řešení $\iff \operatorname{rank}(A) = \operatorname{rank}(A \mid b)$)
* **Věta o dimenzích / Rank-Nullity teorém** ($\dim \operatorname{Ker}(A) + \operatorname{rank}(A) = n$, kde $n$ je počet sloupců)
* **Ortogonalita podprostorů** ($\operatorname{Ker}(A) = (\operatorname{Row}(A))^\perp$)

### 6. Předpoklad: Konečně dimenzionální vektorové prostory
* **Steinitzova věta o výměně** ($L$ je lineárně nezávislá, $G$ generuje $\implies |L| \le |G|$ a $L$ lze doplnit z $G$)
* **Věta o dimenzi jádra a obrazu zobrazení** ($f: U \to V \implies \dim \operatorname{Ker}(f) + \dim \operatorname{Im}(f) = \dim U$)
* **Věta o isomorfismu** ($U \cong V \iff \dim U = \dim V$)

### 7. Předpoklad: Skalární součin a ortogonalita
* **Definice skalárního součinu** (pozitivní definitnost $\langle x, x \rangle > 0$ pro $x \ne 0$, symetrie, linearita v 1. složce)
* **Cauchyho-Schwarzova nerovnost** ($|\langle u, v \rangle| \le \|u\| \cdot \|v\|$)
* **Pythagorova věta** ($u \perp v \implies \|u + v\|^2 = \|u\|^2 + \|v\|^2$)
* **Gramova-Schmidtova ortogonalizace** (vstup: lineárně nezávislé vektory $\implies$ výstup: ortonormální báze)

---

# DISKRÉTNÍ MATEMATIKA A TEORIE GRAFŮ

### 1. Předpoklad: Souvislý graf
* **Eulerovský graf a tah** (uzavřený tah $\iff$ souvislý a všechny stupně sudé; otevřený $\iff$ souvislý a právě 2 liché stupně)
* **Eulerovský orientovaný graf** (vyvážený $\deg^+ = \deg^-$ a **slabě souvislý** $\iff$ má uzavřený eulerovský tah $\iff$ vyvážený a **silně souvislý**)
* **Existence kostry grafu** (podgraf je kostra $\iff$ původní graf je souvislý)
* **Metrika vzdáleností $d(u, v)$** (splňuje trojúhelníkovou nerovnost $d(u, w) \le d(u, v) + d(v, w)$; bez souvislosti je $d = \infty$)

### 2. Předpoklad: Acyklický graf (graf bez kružnic)
* **Ekvivalence stromu** (souvislý + acyklický $\iff$ právě jedna cesta mezi každou dvojicí $\iff$ minimální souvislý $\iff$ $|E| = |V| - 1$)
* **Listy stromu** (každý strom s $|V| \ge 2$ má alespoň 2 listy $\deg(v) = 1$)
* **Les** (acyklický graf s $k$ komponentami má $|E| = |V| - k$)

### 3. Předpoklad: Rovinný graf (nakreslitelný v $\mathbb{R}^2$ bez křížení hran)
* **Eulerova formule** ($v - e + f = 2$ pro **souvislý** rovinný graf; pro $c$ komponent obecně platí $v - e + f = 1 + c$)
* **Maximální počet hran** ($|E| \le 3|V| - 6$ pro $|V| \ge 3$; bez trojúhelníků či pro bipartitní $|E| \le 2|V| - 4$)
* **Existence vrcholu malého stupně** (každý rovinný graf má $\delta(G) \le 5$, plyne sporem z $e \le 3v - 6$)
* **Kuratowského věta** (graf je rovinný $\iff$ neobsahuje podgraf izomorfní dělení $K_5$ ani $K_{3,3}$)

### 4. Předpoklad: Bipartitní graf ($G = (A \cup B, E)$)
* **Charakterizace 2-obarvitelnosti** ($\chi(G) \le 2 \iff$ graf je bipartitní $\iff$ graf neobsahuje lichou kružnici)
* **Hallova věta o SRR a párování** (párování nasycující celou partitu $A$ existuje $\iff \forall S \subseteq A: |N(S)| \ge |S|$)
* **Bergeovo lemma** (párování $M$ je maximální $\iff$ neexistuje zlepšující střídavá cesta)

### 5. Předpoklad: Dva nesousední vrcholy $\{x, y\} \notin E$ (Zkouškový chyták!)
* **Lokální vrcholová Mengerova věta** (max počet vrcholově disjunktních cest = min velikost vrcholového $xy$-řezu; **podmínka $\{x, y\} \notin E$ je nutná**, hranu nelze přerušit vrcholy)
* *(Pro srovnání: lokální hranová Mengerova věta vyžaduje pouze $x \ne y$)*

### 6. Předpoklad: Toková síť $(V, E, z, s, c)$ a celočíselnost
* **Kirchhoffův zákon (zachování toku)** (platí pouze pro **vnitřní uzly** $u \in V \setminus \{z, s\}$)
* **Max-Flow Min-Cut věta** (maximální velikost toku $w(f_{max}) = \min$ kapacita řezu $c(R_{min})$)
* **Ford-Fulkersonův algoritmus** (při celočíselných kapacitách $c(e) \in \mathbb{N}_0$ zaručeně **končí v konečném čase** a najde celočíselný tok)

### 7. Předpoklad: Částečně uspořádaná množina (Poset $(X, \le)$)
* **Axiomy uspořádání** (reflexivita, slabá antisymetrie $x \le y \wedge y \le x \implies x = y$, tranzitivita)
* **Věta o dlouhém a širokém posetu** ($|X| \ge n \cdot m + 1 \implies$ obsahuje řetězec délky $\ge n+1$ NEBO antiřetězec velikosti $\ge m+1$)

### 8. Předpoklad: Konečné množiny a zobrazení ($|X|=n, |Y|=m$)
* **Princip inkluze a exkluze (PIE)** (aplikace: šatnářka $D_n \approx n!/e$, surjekce $m! S(n,m)$, Eulerova funkce $\varphi(n) = n \prod(1 - 1/p_i)$)
* **Binomická věta** ($(x+y)^n = \sum_{k=0}^n \binom{n}{k} x^{n-k} y^k$; pro $x=y=1$ dává $\sum \binom{n}{k} = 2^n$)
* **Podmínky existence zobrazení** (injekce vyžaduje $n \le m$, surjekce $n \ge m$, bijekce $n = m$)



## Analýza
Limita funkce v bodě to že nalevo implikace je 0 < a napravo je odečteno L
U limit jsou důležité deklarce co je vlastní R nebo nevlastní R* z věcí ve vzorečcích
Pozor na negaci definice často je to chyták ale další úlohy často napovídají
Věta o nabývání extrémů - funkce je spojitá - nejde 1/x a interval je omezený a uzavřený - nejde do nekonečna a lze jít na okraj kdyby nešlo jít na okraj nenašli bychom maximum u f(x) = x

Definice derivace nechť f je definovaná na okolí bodu b
Má li funkce v bodě b vlastní derivaci pak je tam spojitá a ta vlastní derivace je potřeba i na všechny ty vzorce součtů atd.
Zapsat součin s per partes, podíl a řetízkové pravidlo se substitucí

L Hopital zase ty předpoklady
Taylorův polynom

Primitivní funkce je na otevřeném intevalu I
Riemannův integrál
Základní věta analýzy je li funkce Riemanovsky integrovatelná na a,b pak ..
Délka grafu funkce bzorec a objemu rotačního tělesa a povrch

dx u integrálu !!!!!!!!!!!!!!!!!!!!!

Plochy je si dobré namalovat grafy někdy je to potřeba rozdělit a uvažovat
U Hopitala je často problém že si myslím že nejde použít a přitom jde protože mi nedojde že e na 0 je 1
A nesmím to trhat dokud je to nekonečno - nekonečno což je neurčitý výraz, maximálně 1 z těch dvou může být neurčitý

U substituce hledej poflakující se derivaci vedle něčho hnusného čeho je to derivací

Vždycky se zamyslet jaký byly předpoklady jaký by tam dávaly smysl

Hlavně u těch klíčových vět ty předpoklady

## Diskrétka
Bacha že v těch relacích jsou i ty prvky samy se sebou a pro to taky musí platit ty věci

Barevnost nejmenší k počet barev i hranová a vrcholová souvislost jsou nejmenší k pro které graf neobsahuje řez velikosti k
U vrcholové musí mít alespoň k+1 vrcholů
Vrcholová souvislost je největší k takové že graf je k vrcholově souvislý

Když je tam něco s množinama bacha že i prázdná množina je množina!!!!!!!

Určitě umět barevnost a vrcholové a hranové souvislosti a mengery pozor vrcholy v mengerovi musí být nesousední
a ještě SSR je taky možný

Rozhodněte pro která n něco platí musim dokázat např. konstrukcí že pro věechny pro který to tvrdim to platí
Často jsem udělal chybu že jsem řekl že to jde jenom z toho že to splňovalo nerovnost ale neukázal jsem jak

Barevnost defininuce
Vrcholový řez a vrcholová souvislost
Menger pozor na to že nesousední pro xy řez
Velikost toku
Nejmenší prvek
Antiřetězec
Binomická věta, součet podmnožin a alternující součet
Hallova věta a SSR

## Automaty
Na doplněk musí být funkce totální a automat deterministický změnim přímající a nepřímající stavy
q0 se píše jen jako jeden stav ale F je množina
P u gramatiky je konečná množina a v sjednoceno s T na hvězdičku
U zásobníkovýho automatu pozor vstupní abeceda a abych u gamma v deltě nezapomněl hvězdičku a že to je Pfin
A také nezapomenout u q, Z0, a F definovat z čeho jsou
Automat namalovat vymyslet stranou pokud je složitý pak přemalovat a k tomu přemalovaným napsat formálně a teď vypsat množiny nebo prvky akorát deltu nechat a napsat s přechodovou funkcí delta popsanou grafem
Jen to velké epsilon je jeden znak co není prázdný ale jakmile je to s hvězdičkou obsahuje to i prázdný znak
Pozor v induktivní definici a v jazyku přijímaným automatem nesmí chybět definice z čeho jsou ty používaný symboly
Znak odvoditelnosti s *
Při převodu gramatiky na zásobníkovej automat přijímající prázdným zásobníkem tam nedávat Z protože pak bychom nepřijmuli prázdné slovo
U psaní gramatiky je oddělovač | ne ,
diagram nazýváme stavovým diagramem

Přesné znění pumping lemmatu

Někdy může bejt snažší udělat nejdřív gramatiku a prostě z ní přepsat zísobníkovej automat

!!!!!! Dobrý trik pojmenovat ty stavy podle sufixu ( neboli prefixu hledaného vzoru ), nebo podle zbytkové třídy, nebo dvojici třeba sudý počet jednoho a lichý druhého, třetí znak od konce potřebuju všech 8 stavů posledních trojic

„Jaká minimální informace o dosud přečtené části slova mi stačí k tomu, abych mohl po přečtení dalšího znaku udělat správné rozhodnutí?“
Každá hodnota této informace pak tvoří přesně jeden stav automatu.

Pointa často je že stačí sledovat stav několika posledních znaků tak je to například i u toho dělení
Může se vyplatit nejdřív udělat ten příklad tři třeba když má být dvojka obecně jako jaro 2026
Také se může vyplatit použít k označení stavu uspořádanou dvojici
Jew také dobré uvést ostatní přechody jsou nedefinované nebo vedou do žumpy

δ(i, 0) = 2i mod p,
δ(i, 1) = (2i + 1) mod p

Bezkontextovou gramatiku, zásobníkový automat, konečný automat, nedeterministický konečný automat, jazyk příjímaný konečný automatem, rozšířená přechodová funkce

Když je čas vyzkoušet si jestli to funguje třeba prázdný či nějaký zákeřný vstup

U převodu z NFA na DFA pozor vždy jít jedno písmenko po druhým nenechat se zvyklat tim když jsou někde obě vždy si říct do jaký množiny stavů můžu s thle množiny stavů přejít timhle písmenkem jedno pod ruhym

Zopakovat konkrétně nejvíc definici gramatiky, zísobníkového automatu tvorbu gramatiky a převod gramatiky na zásobníkový automat

Když je gramatika a nevim zkusit si to rozdlěi tna stejně velký části od okrajů dovnitř

## Programko
* **Vzorec pro reálná čísla (IEEE 754):** $x = (-1)^s \cdot (1 + M) \cdot 2^{E - B}$
  * $s$: znaménko ($1\text{b}$), $E$: exponent s biasem $B$, $M$: mantisa (implicitní jednička před čárkou $1.M$).
  * `float` (32b): $s=1, E=8$ (bias $B=127$), $M=23$. `double` (64b): $s=1, E=11$ (bias $B=1023$), $M=52$.
  * Exponent samé 1 a $M=0 \implies \pm\infty$; Exponent samé 1 a $M \ne 0 \implies \text{NaN}$.

* **Pointery v C (`&` adresa vs `*` dereference):**
  * `int x = 42;`
  * `int* ptr = &x;` $\implies$ `&` získá adresu buňky paměti, kde leží `x` (např. `0x7fff00`) to samé jako `int *ptr = &x;`.
  * `*ptr = 100;` $\implies$ dereference `*`: zápis přímo do buňky na dané adrese $\implies$ hodnota `x` je nyní 100.


Třída s registry tedy reference i lock musí být readonly a private věci musí být private jinak nám to někdo může změnit tedy bez baší funkce tedy bez locku
Lock s Monitor Wait uvitř

Definice Data Race:
Kritická sekce se netýká jen zápisu, ale jakéhokoliv souběžného přístupu ke sdíleným datům, kde alespoň jeden z přístupů je zápis.

OOP návrh (Interface vs Abstraktní třída vs Enum):
* Interface: jen chování (CAN-DO). ❌ NIKDY v něm nesmí být proměnné (fields)! ✅ Vlastnosti VŽDY jen `{ get; }` (read-only kontrakt, ať nenutíš třídy k public setu).
* Abstraktní třída: vztah IS-A, sdílený stav (`Name`, konstruktor) a stromy (vzor Composite: `TypeElement : IdeElement` obsahuje kolekci `IdeElement`).
* Enum: kdykoliv zadání žádá „druh / typ / variantu“ z pevné sady (např. `enum TypeKind { Class, Struct... }`), nevymýšlet další třídy ani stringy!

Když je tam zadání v C/C++ pseudokódu, typy proměnných v zadání ti radí, co přesně použít.

Ovladače a HW registry (MMIO v C):
* `volatile` dát na celou strukturu: `typedef volatile struct { uint32_t status, size, command, lba, dma; } disk_regs_t;`
* Typy: vždy `uint32_t` (ne int ani uint_32) koukat na to co oni předávaj do metod.
* Přetypování adresy: `disk->ctl = (disk_regs_t *) register_address;` a pak přistupovat přes šipku `ctl->lba`.
*  `==` má přednost před `&`, VŽDY ZÁVORKOVAT: `(status & 2) == 0`!
* Bity testovat maskou: `(status & 1) != 0` (ne natvrdo `== 1`), ať nenaletíš, když je v registru víc čísel/flagů.
* V C/jádře nelze použít C# `lock`: procesy mají izolovanou paměť (lock funguje jen mezi vlákny 1 procesu)! Nutný jaderný `mutex_t` typ, `mutex_lock(&m)` a nezapomenout `mutex_unlock(&m)` před KAŽDÝM returnem (`&` je adresa/pointer na mutex – v C se jinak vše předává kopií a kopii zamknout nelze).
* Počkat na připravenost PŘED i PO: ověřit `!BUSY` i `!ERR` (pokud naskočí chyba ERR, hned končit s false, ať nezapisujeme do chybového stavu).
* Range check: hned na začátku ověřit `if (lba >= max_lba) return false;`.


* **Rozhodovací pravidla pro OOP návrh u zkoušky (Interface vs. Abstraktní třída vs. Enum):**
  * **Kdy `interface`:**
    * Kontrakt o **chování a schopnostech** (role CAN-DO: `IComparable`, `IDisposable`), které implementují různé nesouvisející třídy.
    * **V interface NIKDY nesmí být proměnné (*fields*)!** Interface definuje chování, ne paměťový stav (`string name;` je chyba), jsou tam jen properties u kterých se ten `{ get; či set; }` překládá na metodu get_NazevProperty.
    * **Vlastnosti VŽDY jen s `{ get; }`** (`string Name { get; }`). Dává se pouze getter (read-only kontrakt); třída si pak sama určí implementaci (`init`, `private set`, get-only). Pokud napíšeme `{ get; set; }`, nutíme každou třídu mít veřejný setter!
  * **Kdy `abstraktní třídu` (hierarchii tříd):**
    * Vztah **„JE NĚČÍM“ (IS-A)** a sdílení **vnitřního stavu a kódu** (společný `Name`, bázový konstruktor `base(name)`). (a také struct může implementovat interface)
    * Stromové hierarchie a návrhový vzor **Composite** (např. prvky IDE: `abstract class IdeElement`, ze kterého dědí `FieldElement`, `MethodElement`, `TypeElement`).
    * Disjunktní polymorfismus pro pattern matching (prvek je garantovaně právě jednoho konkrétního typu), používat `sealed`.
    * *Ukázka: Disjunktní hierarchie se `sealed record` a switch výrazem:*
      ```csharp
      public abstract record StavPlatby;

      public sealed record CekaSeNaPlatbu : StavPlatby;
      public sealed record Zaplaceno(DateTime Kdy) : StavPlatby;
      public sealed record Selhalo(string Duvod) : StavPlatby;

      // Díky sealed:
      // 1. Kompilátor ví, že větve jsou vzájemně výlučné (objekt nemůže být zároveň Zaplaceno i něco jiného).
      // 2. Žádná cizí knihovna vám do této hierarchie nemůže podstrčit nečekaného potomka.
      string zprava = stav switch
      {
          CekaSeNaPlatbu => "Čekáme...",
          Zaplaceno z => $"Uhrazeno: {z.Kdy}",
          Selhalo s => $"Chyba: {s.Duvod}"
      };
      ```
  * **Kdy `enum` (Zkouškový reflex):**
    * Kdykoliv zadání žádá **„druh / typ / variantu“ z pevné sady hodnot** (např. druh typu: `enum TypeKind { Class, Struct, Interface, Enum }`, barva, stav).
    * Nevymýšlet na to další hierarchii tříd ani textové řetězce (`string`)! `enum` je v C# nejrychlejší, typově bezpečný a ideální pro switch/pattern matching.

Nezapomínat u tříd na konstruktory a ten abstraktní dát protected, ten 4. příklad z testu to hezky ukazuje.

Matice a OOP syntaktické body:
* **Indexer v C# (hranaté závorky `m[r, c]`):** Píše se přes klíčové slovo `this` (nikdy `static`):
  `double this[int r, int c] { get; }`
* **Aritmetické operace / operátory:**
  * Nebo operátory (C# 11 v interface): `static abstract IMatrix operator +(IMatrix a, IMatrix b);`
  * Ve třídě: `public static Matrix operator +(Matrix a, Matrix b) => ...;`
* **Ve `struct` nezapomenout `public`:** Bez modifikátoru jsou pole privátní!
* **C# Switch výraz:** `return matrixMetadata.matrixType switch { MatrixType.Dense => new DenseMatrix(...), MatrixType.Sparse => ... };`
* **Velká vs. malá písmena:** Třídy, metody, properties, enumy = PascalCase (`Rows`, `Add`, `Dense`). Parametry a proměnné = camelCase (`rows`, `filePath`). Privátní pole = `_camelCase` (`_data`).

I když je tam C# a nevím přesnou syntaxi nevadí nenechat se tim znervóznit důležitý je když umím používat ty koncepty a nejsou tam kritické chyby

U těhle technických je tam spousta skrytých pastí na které člověk zapomene protože to zadání je dlouhé když je čas tak si to ještě projít a kontrolovat
* Konstruktor heapu: u 1. volného bloku nastavit i `Next = 0xFFFF` (-1 konec seznamu), nejen `Size`!
* `FindFirstFree`: potřebná velikost bloku je $\ge$ `2 + payloadSize` (hlavička Size má 2B)! Cyklus řídit `while (offset != 0xFFFF)`, ať nespadne čtení na neplatné adrese, když je to prázdný!
* `Mark(offset, isFree)`: v C# nelze bitové `| bool`. Bacha na význam bitu: `isFree == true` $\implies$ bit 0 je **0**! Tedy: `isFree ? (size & ~1) : ((size & ~1) | 1)`.

U hexdumpu nikdy nezapomínat na little endian

U složitých implementací funkcí kde se například načítaj byty a offsety si nejdřív napsat vedle pseudokód klidě ho tam nechat neb to chtěj stejěn vysvětlený

U hexdumpu pozor když hledám 0x900a tak to hledám na řádce kde už je 0x9000

freq_t *head; znamená pointer na nějaký freq_t a ten pointer se jmenuje head zatímco freq_t head znamená freq_t proměná s názvem head

Zase pozor na prázdný seznam nebo prostě prvotní stav aby to nespadlo

U úloh typu officiální low level dokumentace skočit na to kde se začínají definovat třídy a kde jsou otázky číst to nejdřív odtamtud z toho je tomu většinou rozumět o dost lépe, napsat si krátce co má daná třída mít pod sebe, to pomůže nejvíc kreslení diagramu samotné dokumentace moc nepomáhá
U tříd pak se často nevyplatí začínat fieldama ty vyplynou cestou nechat si na ně místo
Začít psát uprostřed konstruktorem až pak dopsat později hlavní obal podle počtu atributů
Koukat dobře na to co už mi tam připravili jako tady třeba enum a já ho přehlídl

Zapomněl jsem pro file co jsem dostal ho zapsat jako privátní field a volat metodu readBytes na něm
A fieldy delat private readonly neb se nemění

Když je tqamněco co nevim v tom programování nenechat se tim rozhodit a nějak to dodělat aspoň
Tu poslední věc často dávaj jen na bitové operace a přetypování
To že chtěj konstatní čas znamená prostě zapsat si pozice každého atributu
Dá se to zkrátit pomocí:
public int attributes() => _types.Length;
public AttrType getType(int i) => _types[i];
public long getRoot() => _rootPos;

Nedělat zbytečné validace které kontroluje sám C# jako přístup mimo pole pokud to není výslovně požadováno
Soustředit se na to aby to fungovalo na začátku pro prázdný či první stav např. u whilů ale tyhle chyby neřešit neb je Cš vyhodí sám

!!!!!! readonly když se něco nemění, sealed když už od toho nedědíme

Kdybych hodně nestíhal napsat to pseudokódem

Když je něco stejné pro všechny časti něčeho v návrhu třeba intefaců že to může být různé ale zvolím to jednou pro to strukturu nabízí se to jako generický paramatr ten typ toho
pro seznam něčeho použít IEnumerable

Když je tam spojení algoritmů a programování v C# vklidu napsat algorimus vedle klidně se pak bude hodit ho tam nechat a pak až začít psát kód

načtení 1 čtení z paměti znamená že položka nesmí být než délka slova procesoru

Stránky mají Dirty, accesed, Executable, Writable, Present


### 1. Archetyp: „Virtuální paměť a formát položky (PTE)“
* **Spouštěč:** Stránkování, velikost stránky (např. 4 KiB), 32bit / 64bit adresa.
* **Chyták:** 
  1. $4\text{ KiB} = 2^{12} \implies$ **offset má 12 bitů**. 
  2. Báze rámce má dolních 12 bitů nulových $\implies$ tam se nacpou **atributy/bity** (P, W, X, A, D).
  3. „Na 1 čtení“ $\implies$ velikost položky PTE se rovná šířce architektury (32 bitů = 4 bajty).
* **Formule pro body:**
  * Počet položek tabulky $= 2^{(\text{adresa} - \text{offset})} = 2^{20} = 1\text{M}$.
  * Velikost tabulky $= 2^{20} \times 4\text{ B} = 4\text{ MiB}$.
  * Čtení nastaví bit $A=1$. **Zápis nastaví $A=1$ I $D=1$!**


V zadání je vždy **špatný původní kód**, který máš předělat. Hledej tyto 3 vzory:

| Co vidíš v zadání (Příznak) | Jaký návrhový vzor použít | Co napsat na papír |
| :--- | :--- | :--- |
| **„Podpora pluginů za běhu / načítání z DLL“** nebo `if (ext == ".jpg")` | **Registry pattern / Factory** | Slovník `Dictionary<string, IPlugin>` + metoda `Register(IPlugin p)`. Žádný `if-else`! (Splňuje OCP). |
| **„Uživatel nakliká akce a spustí je najednou (nebo Undo/Redo)“** | **Command pattern (Příkaz)** | Rozhraní `interface ICommand { void Execute(); }`. Třída si pamatuje parametry a dokument má `List<ICommand>`. |
| **Třída dědí podle typu souboru (`PngImage : Image`)** | **Separation of Concerns (SRP)** | Zrušit dědičnost! `Image` jsou jen čistá data (`Color[,]`). Formáty jsou externí kodeky (`IImageCodec`). |

* **Zkouškový trik pro kód na papíře:** NIKDY nepiš implementaci metod, pokud to zadání výslovně nepřikazuje. Napiš jen `interface`, prázdné třídy se signaturami a maximálně ten jeden klíčový slovník.

# Archetyp: „Grafové rozhraní a komponenty s filtrem“

* **Spouštěč:** „Rozhraní pro graf (matice i seznam sousedů), generické tagy, komponenty souvislosti s prahem $r$“.
* **Chyták:** 
  1. Vždy použij **`interface`**, ne třídu (matice a seznam nemají společná data, v C# navíc `struct` nemůže dědit ze třídy).
  2. Hrana je neorientovaná $\to$ soused je ten druhý konec: `(e.V1 == u ? e.V2 : e.V1)`.
* **Formule pro body:**
  1. **3 rozhraní s generiky:**  
     `IEdge<V,E>` (má `V1`, `V2`, `Tag`), `IVertex<V,E>` (má `Edges`, `Tag`), `IGraph<V,E>` (má `Vertices`).
  2. **Komponenty souvislosti:**  
     Klasické **BFS s frontou**:
     * Na začátku nastav všem vrcholům `Tag = -1`.
     * V cyklu přes hrany ignoruj dlouhé: `if (edge.Tag > r) continue;`.
     * Nenavštíveným sousedům nastav stejné číslo komponenty a dej je do fronty.

## Lingebra
Stenitzova věta o výměně vhodných vektorů mezi lineárně nezávislou a generující množinou (čili nikoli
nutně bázemi).
Matice jako lineární zobrazení, podobnost, diagonalizovatelnost, pozitivní definičnost vlastnosti, regularita vlastnosti
Cauchy Schwarz, Gram-Schmidt

U soustava zkontrolovat jednou aspoň že jsem správně opsal zadání není nic horšího než počítat ze špatnýho zadání nebo rovnou provést první úpravy z původního zadání, ale když beru jen nějaký vektory tak to moc nejde tady byl ještě trik že tam jednou byla jen jednička takže se dal tenhle vektor rovnou odečíst od výsledku a udělat si to lehčí
Pak je dobré to zkontrolovat jestli opravdu lze vektor tak sestavit

To že součet vlastních čísel je součet čísel na diagonále se může hodit když mi je jen zadaj ale neřeknou mi jejich násobnost

U Cauchy schwarze když je tma nějaká nerovnost druhý vektor je většinou sqamé jedničky nebo jednotková matice

Nebát se napsat si vzorce a klidně to pak přenásobit třeba A-1 na obou stranách a vyjádřit tu matici co mě zajímá.

* **Sestavení matice zobrazení $[\varphi]_{A, B}$:**
  * Do **sloupců** matice $[\varphi]_{A, B}$ dáváš obrazy vektorů z **VÝCHOZÍ báze $A$**, vyjádřené v souřadnicích vůči **CÍLOVÉ bázi $B$**:
    $$[\varphi]_{A, B} = \Big( [\varphi(v_1)]_B \;\big|\; [\varphi(v_2)]_B \;\big|\; \dots \;\big|\; [\varphi(v_n)]_B \Big)$$
  * *Mnemotechnická pomůcka:* $[\varphi(x)]_B = [\varphi]_{A, B} \cdot [x]_A$ (vektor $x$ z báze $A$ „vstupuje“ zprava a výsledkem je obraz v bázi $B$).

Často jsou tam časové pasti nenechat se chytit
Když mám A = BC, tak když to beru jako zobrazení nejdřív násobím tou maticí C ten vstupní vektor pak tou B, koukat na počty sloupců

Jádro matice 
Ker(M) není nic jiného než podprostor vlastních vektorů příslušných vlastnímu číslu λ = 0

### Zkouškový rychlý tahák – Klíčové triky

#### 1. Vlastní čísla a Diagonalizace
* **Stopa a Determinant (blesková kontrola násobností):**
  * $\sum \lambda_i = \operatorname{Tr}(A)$ *(součet diagonály)* $\quad\Big|\quad$ $\prod \lambda_i = \det(A)$.
  * *Trik:* Znáš-li čísla $3$ a $1$ u matice $3 \times 3$ a $\operatorname{Tr}(A) = 5$, z rovnice $3 + 1 + \lambda_3 = 5$ je hned $\lambda_3 = 1$ (jednička je dvojnásobná bez počítání polynomu).
* **Jádro je podprostor pro $\lambda = 0$:**
  * $Ax = 0 \iff Ax = 0 \cdot x$. Dimenze jádra $\dim(\operatorname{Ker}(A))$ je přímo **geometrická násobnost čísla $\lambda = 0$**.
* **Mocnění matice a spektrální trik ($A^2, A^k, \sqrt{A}$):**
  * $Av = \lambda v \implies A^k v = \lambda^k v$. Vlastní vektory zůstávají, čísla se umocní.
  * $B$ reálná symetrická regulární $\implies \lambda_i \in \mathbb{R} \setminus \{0\} \implies \lambda_i(B^2) = \lambda_i^2 > 0 \implies B^2$ je vždy pozitivně definitní.
* **Princip nezávislých světů:**
  * Vlastní vektor nemůže být lineární kombinací vektorů z různých vlastních podprostorů. Místo jedné obří soustavy testuj příslušnost k jednotlivým podprostorům zvlášť v malých soustavách.

---

#### 2. Matice, Báze a Zobrazení
* **Úzké hrdlo $A = BC$ (NIKDY NENÁSOB!):**
  * Pokud $B$ je $5 \times 2$ a $C$ je $2 \times 5$, pak $\operatorname{rank}(A) \le 2$. 
  * Sloupcový prostor $\operatorname{Col}(BC) = \operatorname{Col}(B)$. Bázi $\operatorname{Col}(A)$ tvoří rovnou nezávislé sloupce matice $B$.
* **Gaussovka na matici přechodu (od $\mathcal{A}$ k $\mathcal{B}$):**
  * Sestav matici: **$\mathbf{(B \mid A) \sim \dots \sim (I \mid B^{-1}A)}$**.
  * *Mnemotechnika:* **V čem** vyjadřuji ($B$), dám **vlevo**; **co** vyjadřuji ($A$), dám **vpravo**. Vpravo ti vyjde matice přechodu.
* **Souřadnice obrazu a skládání:**
  * Do sloupců matice zobrazení dáváš obrazy **vstupní** báze vyjádřené v souřadnicích **výstupní** báze.
  * Skládání zobrazení $f \circ g$ odpovídá násobení matic $F \cdot G$. Vektor se násobí **zprava** ($Ax$).

---

#### 3. Geometrie, Skalární součin a Definitnost
* **Kolmost vs. Rovnost:**
  * Vektory jsou **kolmé** $\iff \langle Ax, Bx \rangle = 0 \iff x^T A^T B x = 0$. *(Pozor: $(A - B)x = 0$ znamená, že jsou rovnoběžné/stejné, nikoliv kolmé!).*
* **Změna plochy / objemu:**
  * Koeficient změny plochy je $|\det(M)|$. Pokud vyjde $|\det(M)| = 1$, zobrazení plochu **ani nezvětšuje, ani nezmenšuje (zachovává ji)**.
* **Ortogonální vs. Ortonormální:**
  * *Ortogonální:* $\langle u_i, u_j \rangle = 0$ pro $i \neq j$ (pouze kolmost, **délka nemusí být 1**, neděl odmocninami!).
  * *Ortonormální:* navíc $\|u_i\| = 1$.
* **Cauchyho–Schwarzova finta:**
  * Tvar: $\langle u, v \rangle^2 \le \langle u, u \rangle \langle v, v \rangle$.
  * V abstraktních maticových nerovnostech (se stopou a číslem $n$) bývá neznámým vektorem **jednotková matice $I_n$** (protože $\langle I, A \rangle = \operatorname{Tr}(A)$ a $\langle I, I \rangle = \operatorname{Tr}(I) = n$).
* **Sylvestrovo kritérium (Pozitivní definitnost):**
  * Determinanty čtverců v **LEVÉM HORNÍM ROHU** ($1 \times 1, 2 \times 2, \dots$) musí být ostře **$> 0$**.
  * U matice $a_{ij} = \min(i,j)$ odečti sousední řádky $\to$ vznikne trojúhelníková matice se samými $1$ na diagonále $\to \det = 1 > 0 \implies$ je PD.

---

> **Zlaté pravidlo zkoušky:** Pokud by výpočet hrubou silou trval déle než 3 minuty, zastav se. Zkoušející tam schoval větu, která to zkrátí na jeden řádek.

## Ads
Master theorem
Pozor že tam je v něm theta pro to n na c

Pozor nepředávat pole ale pointery na půlku a je dobré zmínit i prostorovou složitost zásobníku
Min-heap je záchrana vkladání i vybírání v O(log n)
Dopsat tam že pro nízké n dopočítáme medián v konstatním čase
Nezapomínat na tuhle okrajovou podmínku

Existuje deterministický !! algoritmus/verifikátor

## Logika
jazyk dodá do čeho dosazovat struktura co dosazovat a ohodnocení dosadí a u těch funkčních a relačních symbolů přiřadí struktura význam neboli jak je vyhodnocovat
Model je celá struktura A
Univerzum výrokové logiky je jen 0,1
U uzavřené formule na ohodnocení vůbec nezáleží
Substituci lze dělat kdyz mam exisuje neco že substituuju jdn do toho vnitřku z konkrétního faktu plyne existence
Logická ekvivalence (
φ
≡
ψ
φ≡ψ
)
Znamená: Formule mají úplně stejnou pravdivost v úplně každém modelu.

Znamená mnohem slabší věc:
φ
 je splniteln
a
ˊ
 
⟺
ψ
 je splniteln
a
ˊ
φ je splniteln 
a
ˊ
  ⟺ψ je splniteln 
a
ˊ
 
Lidsky řečeno: „Pokud existuje svět, kde platí 
φ
φ
, tak existuje i nějaký svět, kde platí 
ψ
ψ
. A pokud 
φ
φ
 vede ke sporu (je nesplnitelná), tak 
ψ
ψ
 vede ke sporu taky.

U zkoušky se často ptají: „Jak poznáte konzervativní extenzi přes modely?“
Trik je v tom, že nezměníte univerzum, jen do něj domalujete nový symbol (tzv. expanze modelu):
Máte model 
A
A
 původní teorie 
T
T
.
Pokud se vám podaří vzít jeho stávající prvky a jenom jim přiřadit chování té nové funkce 
f
f
 (nebo predikátu), aniž byste museli měnit univerzum nebo původní relace, vyrobíte model 
A
′
A 
′
 
 nové teorie

Otevřená formule 
φ
(
x
)
φ(x) platí ve struktuře 
A
A (
A
⊨
φ
A⊨φ), právě když platí pro každé ohodnocení 
e
e 
  
⟺
  
A
⊨
(
∀
x
)
φ
(
x
)
⟺A⊨(∀x)φ(x). Proto se u vět v matematice i při Skolemizaci univerzální kvantifikátory vynechávají (volné proměnné automaticky znamenají „pro jakékoliv 
x
x“).

Pointa je že nelze substituovat bez toho abych to změnil i ve kvantifikátoru proto se do uzavřených formulí nesmí substituovat

Obraceni kvantifikátoru u implace pokud vaechno neco pak neco pro aspon jeden z tech vsech plati cela ta implikace


D8 tse m definici struktury a že univerzum je neprázdné
A pak extenzi teoriea semanticke kriterium, konzervativní extenze nedokazuje v původním jazyce L žádné nové formule
V tablu neodvozovat vždy používat pouze ty přesná pravidla
Nejdřív svěděk tedy t existuje či false všichni vytvoříme si konstatny, pak až dosadíme libovolné do věichni 

Vlatnšě struktura doručí doménu a pomocí těch realčních  afunkčních symbolů které už mohou mít význam v jazyce jako složil zkoušku Z(x) tak struktura řekne pro každý prvek z univerza zdali složilo zkoušku

Když se přepisujou formule z lidského znění psát je už s rozdílnými písmeny pro každy kvantifikátor
U tabla nejdřív rozmyslet jak chci spor najít ať nejdu zbytečně slepou uličkou
Ta struktura se zpaisuje jako A = ⟨{0}, ZA = {0}, SA = P
A = ∅⟩.

Při extenzi musím ve struktuře dát ohodnocení nových věcí z jazyka, nemusí obsahovat c co přidáme stačí když ve starém jazyce použijeme existuje pro to cpro co jsme v novém dávali konstantu a to do staré teorie přidala

## Web

R-strom chybělo mi že je výškově vyvážený a že v listech jsou odkazy na objekty
Nebát se když je tam konkrétní příklad napsat co se stane v něm jako u MapReduce kde tam byl
U rozvrhu jsem nenapsal jak je na tom původní stav což je pro řešení důležité, já jsem to věděl ale nenapsal
Primární klíč tlustou čárou kandidátní tenkou foreign vlnovkou
Pozor když je někde 0..1 tak je ve spojovací tabulce je primárním klíč pouze ten co má toho druhého 0..1 !!!!!
Nevypisovat se tam s tak dlouhými názvy v tom UML prostě OdRoku nemusí tam být názvy obou tabulek
Pozor fyzická úroveň jsou indexy, a optimalizace výkojnu a uložení dat a výstupem jsou fyzické ddl skripty a indexy, logický model dělá databázový návrhář - ten jakoby navrhne to převedení do relačního modelu jak píšeme
V UML používat hvězdičku ne m a n 0..*
Často chtějí jestli umíme atribut na relaci když se to nabízí dát to tam
Pozor ministerstvo má právě jednoho ministra neznamená že ministr musí mít ministerstvo
dá se psát UNIQUE NOT NULL třeba i do toho relačního zápisu když to má být 1 ku 0..1 tak tohle musí být v té co má druhého určitě, nemůže to být u té druhé protože pak bychom nezaručili že ta první někoho má
Samotné UNIQUE je pro 0..1 na obou stranách nebo samostnatná tabulka kde je jedno z nich klíč a druhé alternativní klíč
NOt_NULL když je to ten koho jiný může mít 0..n
Pozor píše se 1..1 ne jen 1
Dávat na to pozor spíš co tam asi chtějí např. když tam je určete, které vztahy mají vlastní atributy, tak tam asi nějaký chtěj

Je potřeba psát document.getElementById ne jen getElementById
Dávat věcem krátké názvy když to jde jako ul nebo li
a document.createElement pak li.textContent a appendChild
U posílání nezapomenout na hlavičku application JSON a na JSON.stringify
Když používám await funkci musím deklarovat jako async

Když je tam několik věcí v zadání třeba endpointů a některé jsem ještě nepoužil a je tam nějaká nejasná otázka zamyslet se jestli náhodou by nebylo chytré něco z toho nepoužitého použít

U podobnosti je jednoduší použít eukleidovskou vzdálenost když si můžu vybrat

Tu definici B stormu tam mají dost důkladně rozepsané ty podmínky, všechny listy se nacházejí na stejné úrovni to je důležité napsat prostě všechny podmínky které mě napadnou

U CYPHERU mi chyběl return distinct s čím to chci

Naznačte jak reprezentovat v relační databázi znamená převeďte to na logický model

U toho grafu v konfliktové uspořadatelnosti to nepsat za sebe to se pak napíše pořadí neb to že T1->T2 a T2->T3 neznamená tranzitivně T1->T3 což z toho může jinak vyplynout

CONSTRAINT fk_tahletabulka_tabulka FOREIGN KEY neco REFERENCES Tabulka(id) ON DELETE CASCADE
nejdřív se píše název sloupce pak klíč id INT PRIMARY KEY;
TIMESTAMP WITH TIME ZONE

V BCNF to musí závuset na nadklíči tedy klíč a něco nesplést s částí klíče
Často se tam psalo as v těch testech
Pravidlo: Jakýkoliv sloupec, který uvedete v SELECT a není uvnitř agregační funkce (jako SUM, AVG, COUNT), musí být uveden v GROUP BY.
CONSTRAINT FK_Diplomka_Vedouci FOREIGN KEY (VedouciID) REFERENCES Osoba(OsobaID)

U JSON Schema je potřeba "$schema", "$id" je online primární identifikátor, "type": "object" a "required", "properties"
Vše je v uvozovkách
Když má dataset nadřazený catalog tak ho stejně můžu uvést stejně tak distribuce

Zajistit že opakované stisknutí tlačítka to nepošle vícekrát
Null ošetření a takový věci neřešit

Aby db věděla odkuď hledat potřebuje label u:User a vlastnost v {name: "Alice"}

AND NOT EXISTS s poddotazem
Průměry či kounty vždy přejmenovat COUNT(z.predmet_id) AS pocet_zkousek a jsou v selectu i v having

XML schema je prostě xs:schema, complex, sequence, element, attribute, maxOccurs, name a type 
XSLT - stylesheet, template, foreach, value-of select="cesta v původním XML"

!!!!!! V JSONu pozor dvojité uvozovky se musí psát u názvů properties!!!
Json Schema - $schema, $id identifikátor tohohle type, required, properties, type: array items, one of, $ref odkaz na jiné schéma

JSON-LD - @context tam se definují zkratky iri jako foaf: 
pak je tam název property co pak používáme a uvnitř @id s rdf typem a pak kdyžta vedle toho @id třeba ještě @type:@id když je to samostatný objekt s iri nebo @container:"@language"
@id = v context říká jaké je iri tohohle predikátu oco je tohle za predikát
@type = říká co je objekt na kterej ten predikát ukazuje když je tam prostě id tak ukazuje na jiný uzel grafu, mohl by tam být třeba int

CSVW - @context, url, tableSchema to má pak "aboutUrl", columns a ty mají name a propertyUrl což říká jaký je ten vztah toho s id k té hodnotě
"aboutUrl": "http://example.org/student/{id}"
Slovo {id} v závorce je proměnná šablona. CSVW vezme hodnotu ze sloupce id v daném řádku (což je 1234) a dosadí ji do URL.

@prefix ex:

Kdy použít RDFS / OWL:
V zadání je slovo „Ontologie“, „Třídy a vlastnosti“ nebo vztahy typu „Pes je podtřída Zvířete“.
 Použiješ: rdfs:Class, rdfs:subClassOf, rdf:Property, rdfs:domain, rdfs:range.
Kdy použít SKOS:
V zadání je výslovně „SKOS“, „Tezaurus“, „Řízený slovník“ nebo „Číselník / Taxonomie“.
 Tady na rdfs:Class úplně zapomeň! Všechno jsou to jen pojmy: skos:Concept, skos:ConceptScheme, skos:broader, skos:prefLabel "Editace dokumentu"@cs, skos:inScheme.
SELECT ?url WHERE { ?a vyucuje iri tisknutí dokumentů }

ex:Katalog a dcat:Catalog ;
   dcterms:title "Katalog otevřených dat města"@cs ;
    dcat:dataset  ex:JizdniRady .

Dataset, Distribution, DataService

PROV-O Trojúhelník (Základní entity a vztahy):
prov:Entity: Datový artefakt/soubor (surova_data.csv, cista_data.csv).
prov:Activity: Proces, výpočet nebo transformace v čase (ex:Agregace).
prov:Agent: Hybatel zodpovědný za spuštění (člověk, organizace, software: ex:Alice).
prov:used, prov:wasGeneratedBy

?osoba wdt:P39 wd:Q1914624 FILTER podmínky

geo:Feature geo:hasGeometry

Vidíš query("... $promenna ...") 
⟹
⟹
 SQL Injection 
→
→
 fix: prepare() a bind_param().
Vidíš setcookie('user', $id) 
⟹
⟹
 Cookie tampering / Broken Auth 
→
→
 fix: serverové $_SESSION.
Vidíš echo "<tag>$promenna</tag>" 
⟹
⟹
 XSS 
→
→
 fix: htmlspecialchars().

 const query = document.getElementById(’searchInput’).value();
A nezapomínat na lock

Neposílat chyby v URL ale uložit do user session či do db kde uživatel dá kód který se pošel v url jinak servery logují hesla a tak což je chyba

U RESTu se parametr píše do {}
Když je tam víc dotazů na různá tlačítka pozor ať si nepřepisují věci jak necheme

termy v boolovském modelu můžou být i třeba symptomy nemocí a dokumenty popis nemocí, nedali jsme do termů každé slovo jen symptomy proto je to specializovaný slovník

ALTER TABLE zpevak ADD FOREIGN KEY (clen) REFERENCES kapela (id_k);
ADD COLUMN

SELECT jmeno FROM zpevak z
WHERE NOT EXISTS(SELECT * FROM skladba WHERE interpret = z.id_z);

objednavky JSONB
objednavky->>’Cislo_obj’ as cislo_obj,

const url = "./api/singer/" + encodeURI(identifier);
function addToList(name) {
  const li = document.createElement("li");
  li.innerText = name;
  document.getElementById("deleted-list").appendChild(li);
}

!!!!!!! Redundatní strom nedělat mechanicky pozor že musí být redundatní

Specifikujte dotaz, který vrátí počty zpráv dlouhých konverzací. Dlouhou konverzaci definujeme jako konverzaci, která
obsahuje alespoň 100 zpráv.
select id_k, count(*) as pocet from Zprava group by (id_k) having count(*) > 100;

U drop table pozor na pořadí


B strom zmínit řazení klíčů 
A má aspoň hirní čast z m/2 potomků
Všechny listy ve stejné hloubce
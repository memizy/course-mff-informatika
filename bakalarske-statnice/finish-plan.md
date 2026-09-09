# 6.9.
Logika reálný příklad
Udělat zobrazení poznámek na mobilu co to načte z vloženýho linku souboru s nějakým stránkování či přeskakováním snadným
Stanovit testovou strategii a projít poznámky z tamtěch testů

# půl 7.9
Automaty - projet definice, všechny zkouškové příklady udělat závěry z příkladů

# půl 7.9. a půl 8.9
C# a Architektury - všechny minulý příklady, vyvození závěrů pro test a chyb to napsat a poslední den si to přečtu, taky tam dát core syntaxi či tu co mi nejde

# půl 8.9. a 9.9.
Web - všechny příklady a projetí zbytku zapsat core co mi nepůjde z databází a PHP/Javascriptu případně vzorce, vyvození závěrů co si přečtu poslední den

# půl 10.9.
Lingebra - definice a minulé příklady zapsání poznatků

# půl 10.9., ráno 11.9. Ads, Lingebra skim definic už ne příklady
Past - definice jeden 2 příklady a minulý, Ads - definice, minulý příklady zapsání poznatků

# zbytek 11.9
Automaty - definice, Logika pár příkladů na tablo, extenzi, přepsání světa do logiky

# 12.9
Rano analýza zopakování definic a vět aktivní zapisování a strategie a chyby z příkladů, potom logika krátce podobně, potom dikrétka a grafy, zopakování strategie a chyb z příkladů


# 13.9.
Projetí těch zapsaných poznatk, chyb a nejdůležitějších věcí, rezerva nenechávat sem žádný příklady, cesta do Prahy

## Final
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

## Ads
Existuje deterministický !! algoritmus/verifikátor

## Programko
* **Vzorec pro reálná čísla (IEEE 754):** $x = (-1)^s \cdot (1 + M) \cdot 2^{E - B}$
  * $s$: znaménko ($1\text{b}$), $E$: exponent s biasem $B$, $M$: mantisa (implicitní jednička před čárkou $1.M$).
  * `float` (32b): $s=1, E=8$ (bias $B=127$), $M=23$. `double` (64b): $s=1, E=11$ (bias $B=1023$), $M=52$.
  * Exponent samé 1 a $M=0 \implies \pm\infty$; Exponent samé 1 a $M \ne 0 \implies \text{NaN}$.

* **Pointery v C (`&` adresa vs `*` dereference):**
  * `int x = 42;`
  * `int* ptr = &x;` $\implies$ `&` získá adresu buňky paměti, kde leží `x` (např. `0x7fff00`).
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
    * Vztah **„JE NĚČÍM“ (IS-A)** a sdílení **vnitřního stavu a kódu** (společný `Name`, bázový konstruktor `base(name)`).
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

Nezapomínat u tříd na konstruktory a ten abstraktní dát protected, ten 4. příklad z testu to hezky ukazuje

Sčítání, odčítání, násobení APOD. znamená Použijte generiku!

I když je tam C# a nevím přesnou syntaxi nevadí nenechat se tim znervóznit důležitý je když umím používat ty koncepty a nejsou tam kritické chyby

## Celkově
Neškrtat dokud si nejsem stopro jistý škrtnutím někdy toho pak člověk lituje
Raději dopsat celé hnusně a pak celé předělat než 2x protože jsem udělal půlku a pak to zas přeškrtal samozřejmě jen pokud je to rozumně čitelné
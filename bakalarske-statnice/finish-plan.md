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
vzorec pro reprezentaci reálných čísel

## Celkově
Neškrtat dokud si nejsem stopro jistý škrtnutím někdy toho pak člověk lituje
Raději dopsat celé hnusně a pak celé předělat než 2x protože jsem udělal půlku a pak to zas přeškrtal samozřejmě jen pokud je to rozumně čitelné
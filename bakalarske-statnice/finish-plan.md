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

U těch negací a tak se radši vyvarovat používaní toho značení lim něco lepší je vždycky to zapsat rovnou negací toho výroku jinak riskuju nějaké problémy
Pozor u dúkazů tam nezapomínat na n menší než n0 např. u omezenosti

Vzorec pro asymptotu

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
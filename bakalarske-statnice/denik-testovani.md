# Deník testování a studijních bloků (MFF UK)

Tento soubor slouží k trackování časů strávených opakováním v `cheat-sheet.md`, pauz mezi bloky a výsledků následných testů.

---

## 📊 Souhrnná tabulka testů

| # | Datum | Předmět / Téma | Čas učení | Pauza | Čas testu | Skóre / Hodnocení | Hlavní zjištění a mezery |
|---|---|---|:---:|:---:|:---:|:---:|---|
| 1 | 4. 9. 2026 | Lineární algebra (Lingebra) | 75 min | 24 min | 47 min | **7,7 / 10 (77 %)** | Pozor na nenulovost ($v \ne 0, x \ne 0$), absolutní hodnotu u Cauchy-Schwarze, $\langle u \mid u \rangle \ge 0$ a numeriku dimenzí ($6-3=3$). |
| 2 | 4. 9. 2026 | Matematická analýza | 120 min | 44 min | 90 min | **6,85 / 10 (69 %)** *(přísně)* | Rozdíl limita vs. spojitost ($L$ vs. $f(x_0)$), 2× l'Hospital za sebou pro $0/0$, per partes člen $[uv]_a^b$. |
| 3 | 5. 9. 2026 | Matematická logika | 90 min | 35 min | 70 min | **7,5 / 10 (75 %)** *(přísně 75 %, mírně 81 %)* | Ekvisplnitelnost $\ne$ stejné modely, kompaktnost (platí v *nějaké* konečné, ne v každé), Łoś-Vaught (nemá konečné modely), PNF implikace. |
| 4 | 5. 9. 2026 | Algoritmy a datové struktury (ADS) | 105 min | 38 min | 120 min | **7,65 / 10 (77 %)** *(přísně 77 %, mírně 83 %)* | Counting Sort neporušuje dolní mez, protože neporovnává; Kruskal a Union-Find; Jarník polem $\mathcal{O}(n^2)$ pro husté grafy; In-order průchod BVS. |

---

## 📝 Detailní záznamy jednotlivých sezení

### 1. Lineární algebra (4. 9. 2026)
* **Předmět:** Lineární algebra (Lingebra) – kompletní průřez (10 otázek: struktury, soustavy, báze, zobrazení, skalární součin, determinanty, vlastní čísla, pozitivní definitnost).
* **Čas učení:** **75 minut** (dokončeno v 10:55)
* **Pauza:** **24 minut** (10:55 – 11:19)
* **Režim testu:** **Režim A (Matematika)** – psaní na papír bez nahlížení do taháku.
* **Test:** [test-01-lingebra.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-01-lingebra.md) – 10 otázek (11:22 – 12:09, celkem **47 minut**).
* **Rozbor a řešení:** [test-01-lingebra-rozbor.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-01-lingebra-rozbor.md)
* **Výsledek:** **7,7 / 10 bodů (77 % – známka Velmi dobře / 2)**
* **Klíčová zjištění a zkouškové chytáky k zafixování:**
  1. **Nenulovost u vlastního vektoru a definitnosti:** Vlastní vektor MUSÍ být $v \ne 0$ (jinak by každé číslo bylo vlastním číslem). Kvadratická forma $x^T A x > 0$ platí výhradně pro $\forall x \ne 0$ (pro $x = 0$ je vždy rovna 0).
  2. **Absolutní hodnota u Cauchyho-Schwarze:** Vždy $|\langle u \mid v \rangle| \le \|u\| \cdot \|v\|$. Bez absolutní hodnoty nerovnost neříká nic o záporných hodnotách.
  3. **Pozitivní definitnost skalárního součinu:** $\langle u \mid u \rangle \ge 0$ platí pro tentýž vektor, nikoli pro různé $u, v$ (různé vektory svírající tupý úhel mají záporný součin!).
  4. **Numerická pozornost u dimenzí:** U matice $4 \times 6$ je $n = 6$. Tedy $\dim(\operatorname{Ker}(A)) = 6 - 3 = 3$, a proto $(\operatorname{Ker}(A))^\perp = \operatorname{Row}(A)$ (součet dimenzí $3 + 3 = 6$).
  5. **Definice báze:** Vždy explicitně uvést obě podmínky: 1. lineárně nezávislá množina, 2. generuje celý prostor ($\operatorname{span}(B) = V$).
  6. **Diagonála pozitivně definitní matice:** Důkaz, že $a_{ii} > 0$, se provádí dosazením kanonického vektoru $e_i \ne 0$: $e_i^T A e_i = a_{ii} > 0$.

### 2. Matematická analýza (4. 9. 2026)
* **Předmět:** Matematická analýza (posloupnosti, řady, limity funkcí, spojitost, derivace, l'Hospital & průběh, Taylorův polynom, integrály a aplikace).
* **Čas učení:** **120 minut** (dokončeno v ~18:00)
* **Pauza:** **44 minut** (18:00 – 18:44)
* **Režim testu:** **Režim A (Matematika)** – psaní na papír bez nahlížení do taháku.
* **Test:** [test-02-analyza.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-02-analyza.md) – 10 otázek (18:45 – 20:15, celkem **90 minut**).
* **Rozbor a řešení:** [test-02-analyza-rozbor.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-02-analyza-rozbor.md)
* **Výsledek:** **6,85 / 10 bodů (69 % – známka 2- až 3 / Dobře)** *(při mírnějším hodnocení 78 %)*
* **Klíčová zjištění a zkouškové chytáky k zafixování:**
  1. **Definice limity vs. spojitost:** U limity je v cíli vždy hodnota limity $L$, nikoli funkční hodnota $f(x_0)$, a vyšetřuje se prstencové okolí: $0 < |x - x_0| < \delta \implies |f(x) - L| < \varepsilon$. Zápis s $f(x_0)$ je definice spojitosti!
  2. **Dvojitý l'Hospital:** Pokud po prvním zderivování podílu typu $0/0$ vyjde v čitateli i jmenovateli opět 0, aplikuje se l'Hospital podruhé za sebou. Nikdy nerozdělovat na rozdíl limit, pokud nevíme, že existují konečné.
  3. **Základní Taylorovy rozvoje:** $\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \dots$
  4. **Per partes u určitého integrálu:** Vzorec je $\int_a^b u' v = [uv]_a^b - \int_a^b uv'$. Nezapomínat na první integrovaný člen $[uv]_a^b$.

### 3. Matematická logika (5. 9. 2026)
* **Předmět:** Matematická logika (syntaxe a sémantika VL a PL, PNF a generální uzávěr, analýza teorií, tablo metoda pro VL a PL, Skolemizace a extenze, věta o kompaktnosti, Łoś-Vaught, rozhodnutelnost).
* **Čas učení:** **90 minut** (08:05 – 09:35)
* **Pauza:** **35 minut** (09:35 – 10:10)
* **Režim testu:** **Režim A (Matematika)** – psaní na papír bez nahlížení do taháku.
* **Test:** [test-03-logika.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-03-logika.md) – 10 otázek (10:10 – 11:20, celkem **~70 minut**).
* **Rozbor a řešení:** [test-03-logika-rozbor.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-03-logika-rozbor.md)
* **Výsledek:** **7,5 / 10 bodů (75 % – známka Velmi dobře / 2)** *(při mírnějším hodnocení 81 %)*
* **Detailní rozbor chyb a zkouškových chytáků k zafixování:**
  1. **Ekvisplnitelnost $\ne$ stejné modely (Otázka 5):**
     * *Chyba studenta:* Zapsáno *„je ekvisplnitelná neboli platí ve stejných modelech“*.
     * *Zkouškový chyták:* Kdyby platily ve stejných modelech, šlo by o *sémantickou ekvivalenci*. Skolemovská varianta $\varphi_{sk}$ má bohatší jazyk (obsahuje novou funkci či konstantu), pro původní jazyk model $\varphi_{sk}$ vůbec neexistuje.
     * *Správné znění:* Formule jsou pouze **ekvisplnitelné** ($\varphi \text{ má model} \iff \varphi_{sk} \text{ má model}$). Každý model $\mathcal{M} \models \varphi$ lze na model $\mathcal{M}^* \models \varphi_{sk}$ pouze **expandovat** vhodnou volbou realizací Skolemových funkcí (přes axiom výběru).
  2. **Věta o kompaktnosti – kvantifikátory a důkaz konečnosti (Otázka 7):**
     * *Chyba studenta:* Napsáno *„platí v každé konečné podmnožině“*. Kdyby platila v každé, platila by i v prázdné $\emptyset$, tedy by musela být tautologií.
     * *Správné znění:* $T \models \varphi \iff$ existuje **alespoň jedna konečná podmnožina** $T' \subseteq_{fin} T$, pro kterou $T' \models \varphi$. (Pro splnitelnost: $T$ má model $\iff$ každá konečná $T' \subseteq_{fin} T$ má model).
     * *Důkaz nemožnosti vyjádřit konečnost:* Sporem. Nechť $T$ axiomatizuje konečnost. Zavedeme spočetnou řadu axiomů $\alpha_n$ („existuje alespoň $n$ různých prvků“). Každá konečná podmnožina $T \cup \{\alpha_n\}$ má konečný model (velikosti max indexu $N+1$). Dle věty o kompaktnosti by pak měla model i celá nekonečná teorie $T \cup \{\alpha_n\} \implies$ nekonečný model splňující $T$, což je spor.
  3. **Łoś-Vaughtovo kritérium (Otázka 8):**
     * *Chyba studenta:* Záměna za *„nekonečná teorie“* a překlep v pojmu *„charakteristická“*.
     * *Správné znění:* Podmínkou kritéria je, že teorie **nemá žádné konečné modely** (všechny její modely jsou nekonečné množiny), jazyk $L$ je nejvýše spočetný, teorie je bezesporná a **$\kappa$-kategorická** (má až na izomorfismus jediný model mohutnosti $\kappa \ge |L|$). Pak je teorie **kompletní**.
  4. **Převod implikace do PNF a generální uzávěr (Otázka 1):**
     * *Chyba studenta:* Napsáno $\neg A \lor \neg B$ místo $\neg A \lor B$, a kvantifikátor nevytknut do prefixu. U generálního uzávěru vynechán vnitřní kvantifikátor podformule.
     * *Správné znění:* Implikace je $A \to B \equiv \neg A \lor B$. Vytýkání kvantifikátoru z předpokladu obrací kvantifikátor ($\forall \leftrightarrow \exists$): $(\forall z P(z) \to Q(x, y)) \sim (\exists z)\big(P(z) \to Q(x, y)\big)$. Kvantifikátor musí stát na samém začátku (v prefixu). Generální uzávěr pro $\varphi: (\forall x)P(x) \to Q(x,y)$ je $(\forall x)(\forall y)\big((\forall x)P(x) \to Q(x, y)\big)$.
  5. **Tablo v PL – pravidla Všichni vs. Svědek a označení (Otázka 4):**
     * *Poznatek:* Položky $T(\forall x)\varphi$ i $F(\exists x)\varphi$ jsou obě typu **Všichni** (lze dosadit libovolný zavedený term nebo novou konstantu).
     * *Chyba zápisu:* Do položek označeného tabla se nevpisuje negace $\neg P(c)$. Větve se vedou striktně formulemi $TP(c)$ a $FP(c)$, jejichž souběh na jedné větvi tvoří uzavření sporem $\times$.
  6. **Zlatá věta o rozhodnutelnosti (Otázka 9):**
     * Rekurzivně axiomatizovaná a kompletní teorie je rozhodnutelná. Algoritmus systematicky prochází a generuje formální důkazy. Jelikož je teorie kompletní, v konečném čase narazí buď na důkaz $\varphi$, nebo na důkaz $\neg\varphi$.

### 4. Algoritmy a datové struktury (5. 9. 2026)
* **Předmět:** Algoritmy a datové struktury (RAM model a složitost, Master Theorem, BVS a operace, vyvažované AVL stromy, Quicksort a skoromedián, dolní odhad porovnávání a Counting Sort, grafové průchody BFS/DFS a hrany, nejkratší cesty Dijkstra vs. Bellman-Ford, minimální kostry Jarník vs. Kruskal, P vs. NP a NP-úplnost).
* **Čas učení:** **105 minut** (dokončeno v 16:15)
* **Pauza:** **38 minut** (16:15 – 16:53)
* **Režim testu:** **Režim A (Matematika & Teorie)** – psaní na papír bez nahlížení do taháku.
* **Test:** [test-04-ads.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-04-ads.md) – 10 otázek (16:53 – 18:53, celkem **120 minut**).
* **Rozbor a řešení:** [test-04-ads-rozbor.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-04-ads-rozbor.md)
* **Výsledek:** **7,65 / 10 bodů (77 % – známka 2 / Velmi dobře)** *(při mírnějším hodnocení 8,25 / 10 bodů – 83 %)*
* **Detailní rozbor chyb a zkouškových chytáků k zafixování:**
  1. **Counting Sort vs. Dolní mez $\Omega(n \log n)$ (Otázka 6):**
     * *Chyba studenta:* Zapsáno *„Protože $K$ není omezené a může být v nejhorším případě libovolně velké např. $\Omega(n^2)$“*.
     * *Zkouškový chyták:* I kdyby bylo $K = \mathcal{O}(n)$ (třídíme čísla $1 \dots n$), Counting Sort seřadí pole v čase $\mathcal{O}(n)$, což je asymptoticky rychlejší než $\Omega(n \log n)$.
     * *Správné znění:* Counting Sort **neporušuje dolní mez**, protože **není porovnávacím algoritmem**! Vůbec neprovádí porovnávání prvků navzájem ($A[i] \le A[j]$), ale používá hodnoty prvků přímo jako **adresy / indexy do pomocného pole paměti RAM**. Dolní mez $\Omega(n \log n)$ z modelu rozhodovacího stromu platí výhradně pro třídění porovnáváním.
  2. **Kruskalův algoritmus a detekce cyklů (Otázka 9):**
     * *Chyba studenta:* Zapsáno *„detekuje cykly procházením vrcholů stromů lesa“*.
     * *Zkouškový chyták:* Procházení lesa DFS/BFS by trvalo $\mathcal{O}(V)$ na hranu, celkem $\mathcal{O}(V \cdot E)$, což by algoritmus zbytečně degradovalo.
     * *Správné znění:* Kruskal striktně vyžaduje datovou strukturu **Union-Find (Disjoint-Set Union)** s operacemi `Find` a `Union` (s kompresí cest a sjednocením podle hodnosti). Test na cyklus a spojení komponent trvá amortizovaně téměř konstantně: celkem pro všechny hrany $\mathcal{O}(m \cdot \alpha(n))$.
  3. **Husté grafy $m = \Theta(n^2)$ a Jarník vs. Kruskal (Otázka 9):**
     * *Chyba studenta:* Zapsána u obou složitost $m \log n$ a zmíněna Fibonacciho halda, čímž nebyla vysvětlena podstata výhody pro husté grafy.
     * *Správné znění:*
       * **Kruskal:** Musí nejprve setřídit všechny hrany $\implies \mathcal{O}(m \log m) = \mathcal{O}(m \log n)$. Pro hustý graf je to $\mathcal{O}(n^2 \log n)$.
       * **Jarník:** Pro husté grafy **nepoužívá žádnou haldu, ale obyčejné pole** vzdáleností! V každém kroku najde minimum prostým projitím pole za $\mathcal{O}(n)$. Celkový čas je $V \times \mathcal{O}(n) + E \times \mathcal{O}(1) = \mathbf{\mathcal{O}(n^2) = \mathcal{O}(m)}$. Běží tedy v **lineárním čase vzhledem k počtu hran** a poráží Kruskalovo třídění o faktor $\log n$.
  4. **Master Theorem – 1. případ rovnováhy (Otázka 2):**
     * *Chyba studenta:* Pro rovnovážný případ zapsáno $T(n) = \mathcal{O}(n^c \cdot n^{\log_b a})$ (což by dalo $n^{2c}$!).
     * *Správné znění:* Pro $\frac{a}{b^c} = 1 \iff c = \log_b a$ platí $T(n) = \mathbf{\Theta(n^c \log n)} = \mathbf{\Theta(n^{\log_b a} \log n)}$. Master Theorem dává těsnou mez $\Theta$, nikoli jen $\mathcal{O}$.
  5. **Binární vyhledávací strom – seřazený výpis (Otázka 3):**
     * *Chyba studenta:* Zapsáno pouze obecné *DFS*.
     * *Správné znění:* Zkoušející striktně vyžaduje název **In-order průchod** (Levý podstrom $\to$ Kořen $\to$ Pravý podstrom), který jediný vypíše klíče v čase $\Theta(n)$ vzestupně seřazené.
  6. **4 typy hran v DFS a topologické uspořádání (Otázka 7):**
     * *Chyba studenta:* Vynechány *stromové hrany* (uvedeny jen dopředné, zpětné a příčné). U topologie nebylo explicitně uvedeno, že jde o *obrácené* pořadí.
     * *Správné znění:* V orientovaném DFS existují 4 typy hran:
       1. **Stromové** (vedou do dosud nenavštíveného vrcholu),
       2. **Dopředné** (vedou do potomka v DFS stromu),
       3. **Zpětné** (vedou do předka – **detekují orientovaný cyklus**!),
       4. **Příčné** (mezi různými větvemi).
       Topologické uspořádání orientovaného acyklického grafu odpovídá **obrácenému (sestupnému)** pořadí časů dokončení/opuštění $out(v)$ z DFS (první vypsaný je vrchol s nejvyšším $out$).
  7. **Dijkstra složitost s binární haldou (Otázka 8):**
     * *Chyba studenta:* Zapomenuto uvést složitost Dijkstry.
     * *Správné znění:* Dijkstra s binární haldou má časovou složitost $\mathbf{\mathcal{O}((V + E) \log V) = \mathcal{O}(m \log n)}$ a vyžaduje striktně nezáporné váhy hran. Bellman-Ford má $\mathcal{O}(V \cdot E) = \mathcal{O}(n \cdot m)$ a v $n$-tém ($|V|$-tém) kroku relaxace odhalí záporný cyklus, pokud se ještě zkrátí vzdálenost.
  8. **Podmínka nejhoršího případu Quicksortu (Otázka 5):**
     * *Chyba studenta:* Neuvedeno explicitně, kdy nastává nejhorší případ $\mathcal{O}(n^2)$.
     * *Správné znění:* Nejhorší případ nastává při soustavně **extrémní volbě pivota** (pivot je v každém kroku minimem nebo maximem aktuálního úseku). Příklad: již vzestupně setříděné pole při fixní volbě prvního prvku jako pivota $\implies$ dělení na $0$ a $n-1$ prvků $\implies \sum_{i=1}^n i = \Theta(n^2)$.


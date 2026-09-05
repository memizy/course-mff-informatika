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
* **Klíčová zjištění a zkouškové chytáky k zafixování:**
  1. **Ekvisplnitelnost $\ne$ stejné modely:** $\varphi$ a $\varphi_{sk}$ jsou ekvisplnitelné ($\varphi$ má model $\iff \varphi_{sk}$ má model), ale **nemají stejné modely**! Skolemovská varianta má bohatší jazyk (obsahuje novou funkci či konstantu), pro původní jazyk model neexistuje. Každý model lze na model Skolemovy varianty pouze *expandovat*.
  2. **Věta o kompaktnosti – kvantifikátory:** $T \models \varphi \iff$ existuje **alespoň jedna konečná podmnožina** $T' \subseteq_{fin} T$, pro kterou $T' \models \varphi$. (Nikoliv v každé!).
  3. **Łoś-Vaughtovo kritérium:** Podmínkou je, že teorie **nemá žádné konečné modely** (všechny modely jsou nekonečné množiny), nikoli že teorie má nekonečně mnoho axiomů. Termín je **kategorická** (má izomorfní modely dané mohutnosti).
  4. **Převod implikace do PNF a generální uzávěr:** $A \to B \equiv \neg A \lor B$. Při vytýkání kvantifikátoru z předpokladu: $(\forall z P(z) \to Q) \sim \exists z (P(z) \to Q)$ (obrací se $\forall \leftrightarrow \exists$). Kvantifikátor musí být v PNF vytažen před celou formuli. U generálního uzávěru nezapomínat na vnitřní kvantifikátory u podformulí: $(\forall x)(\forall y)\big((\forall x)P(x) \to Q(x, y)\big)$.
  5. **Tablo v PL (Všichni vs. Svědek):** Obě položky $T(\forall x)\varphi$ i $F(\exists x)\varphi$ jsou typu **Všichni** (lze dosadit libovolný zavedený term nebo novou konstantu).
  6. **Důkaz nemožnosti vyjádřit konečnost (Kompaktnost):** Důkaz sporem se provádí přidáním spočetné množiny axiomů $\alpha_n$ („existuje alespoň $n$ různých prvků“). Každá konečná podmnožina má konečný model, ale celá teorie by pak musela mít model $\implies$ nekonečný model $\implies$ spor.

### 4. Algoritmy a datové struktury (5. 9. 2026)
* **Předmět:** Algoritmy a datové struktury (RAM model a složitost, Master Theorem, BVS a operace, vyvažované AVL stromy, Quicksort a skoromedián, dolní odhad porovnávání a Counting Sort, grafové průchody BFS/DFS a hrany, nejkratší cesty Dijkstra vs. Bellman-Ford, minimální kostry Jarník vs. Kruskal, P vs. NP a NP-úplnost).
* **Čas učení:** **105 minut** (dokončeno v 16:15)
* **Pauza:** **38 minut** (16:15 – 16:53)
* **Režim testu:** **Režim A (Matematika & Teorie)** – psaní na papír bez nahlížení do taháku.
* **Test:** [test-04-ads.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-04-ads.md) – 10 otázek (16:53 – 18:53, celkem **120 minut**).
* **Rozbor a řešení:** [test-04-ads-rozbor.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-04-ads-rozbor.md)
* **Výsledek:** **7,65 / 10 bodů (77 % – známka 2 / Velmi dobře)** *(při mírnějším hodnocení 8,25 / 10 bodů – 83 %)*
* **Klíčová zjištění a zkouškové chytáky k zafixování:**
  1. **Counting Sort vs. Dolní mez:** Counting Sort $\mathcal{O}(n + K)$ neporušuje dolní mez $\Omega(n \log n)$, protože **není porovnávacím algoritmem**! Vůbec neprovádí porovnávání prvků navzájem, ale využívá přímé adresování do indexů pole paměti RAM.
  2. **Kruskal a detekce cyklů:** Kruskalův algoritmus používá k detekci cyklů datovou strukturu **Union-Find (Disjoint-Set Union)** s kompresí cest a váhovým sjednocováním v celkovém čase $\mathcal{O}(m \cdot \alpha(n))$, nikoli procházení komponent lesa.
  3. **Husté grafy a Jarník:** Pro husté grafy s $m = \Theta(n^2)$ se Jarníkův algoritmus implementuje **obyčejným polem** (bez haldy), čímž dosáhne času $\mathcal{O}(n^2) = \mathcal{O}(m)$ – je lineární v počtu hran a o faktor $\log n$ rychlejší než Kruskal (který musí hrany třídit v čase $\mathcal{O}(m \log n)$).
  4. **Master Theorem (rovnovážný případ):** Pokud $\frac{a}{b^c} = 1$, složitost je $T(n) = \Theta(n^c \log n) = \Theta(n^{\log_b a} \log n)$ (pozor na zápis $n^c \cdot n^{\log_b a}$, což by bylo $n^{2c}$!).
  5. **BVS výpis a průchod:** Vzestupně seřazenou posloupnost klíčů v čase $\Theta(n)$ získáme **In-order průchodem** (Levý podstrom $\to$ Kořen $\to$ Pravý podstrom).
  6. **4 typy hran v DFS a topologie:** Stromové (Tree), Dopředné (Forward), Zpětné (Back – detekují cykly!) a Příčné (Cross). Topologické uspořádání odpovídá **obrácenému (sestupnému)** pořadí časů opuštění $out(v)$ z DFS (první vypsaný je vrchol s nejvyšším $out$).
  7. **Dijkstra složitost s binární haldou:** Časová složitost je $\mathcal{O}((V + E) \log V)$ resp. $\mathcal{O}(m \log n)$. Vyžaduje nezáporné hrany.
  8. **Nejhorší případ Quicksortu:** Nastává při systematické volbě extrémního pivota (minimum/maximum v každém kroku), např. na setříděném poli při volbě prvního prvku $\implies \Theta(n^2)$.


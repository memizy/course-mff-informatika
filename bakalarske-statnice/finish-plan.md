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

* **Věta o limitě složené funkce (VOLSF):**
  Nechť $\lim_{x \to A} g(x) = B$ a $\lim_{y \to B} f(y) = C$. Potom:
  $$\lim_{x \to A} f(g(x)) = C$$
  pokud je splněna **alespoň jedna** z následujících podmínek:
  * **(P1) Spojitost vnější funkce:** Funkce $f$ je spojitá v bodě $B$ (tj. $f(B) = C$).
  * **(P2) Nenabývání limitní hodnoty:** Na nějakém prstencovém okolí $P(A, \eta)$ funkce $g$ nenabývá své limity $B$, tj. $\forall x \in P(A, \eta): g(x) \ne B$.

* **l'Hospitalovo pravidlo:**
  Nechť $a \in \mathbb{R}^*$, funkce $f, g$ mají na prstencovém okolí $P(a, \delta)$ vlastní derivaci a $g'(x) \ne 0$.
  Jestliže platí jedna z podmínek:
  1. $\lim_{x \to a} f(x) = \lim_{x \to a} g(x) = 0$ (typ $\frac{0}{0}$), **nebo**
  2. $\lim_{x \to a} |g(x)| = +\infty$ (typ $\frac{\text{cokoliv}}{\pm\infty}$),
  potom platí:
  $$\lim_{x \to a} \frac{f'(x)}{g'(x)} = A \in \mathbb{R}^* \implies \lim_{x \to a} \frac{f(x)}{g(x)} = A$$

* **Weierstrassova věta:** Nechť $f: [a, b] \to \mathbb{R}$ je spojitá funkce na **uzavřeném a omezeném (kompaktním)** intervalu $[a, b]$. Potom:
1. Funkce $f$ je na $[a, b]$ **omezená**.
2. Funkce $f$ na $[a, b]$ **nabývá svého maxima i minima**, tj. existují body $x_{min}, x_{max} \in [a, b]$ takové, že:
    $$\forall x \in [a, b]: f(x_{min}) \le f(x) \le f(x_{max})$$
*(Odtud plyne, že obrazem uzavřeného intervalu $[a, b]$ spojitou funkcí je opět uzavřený omezený interval $[f(x_{min}), f(x_{max})]$).*

## Diskrétka

#### Hallova věta o SRR a párování v bipartitním grafu:
* **Systém různých reprezentantů (SRR):** Pro systém množin $\mathcal{M} = \{M_1, \dots, M_n\}$ je SRR výběr $n$ navzájem různých prvků $x_1 \in M_1, \dots, x_n \in M_n$ ($x_i \ne x_j$ pro $i \ne j$).
**párování nasycujícímu celou partitu $A$** ($|M| = n$).
* **Hallova věta (podmínka pro existenci SRR):** SRR existuje $\iff$ platí **Hallova podmínka**:
  $$\forall I \subseteq \{1, \dots, n\}: \left|\bigcup_{i \in I} M_i\right| \ge |I| \quad (\text{grafově } \forall S \subseteq A: |N(S)| \ge |S|)$$



## Lingebra

* **Steinitzova věta o výměně:**
  * Předpoklady: $X$ je LN množina ve $V$, $Y$ je systém generátorů $V$ ($\mathcal{L}(Y) = V$).
  1. $|X| \le |Y|$
  2. $\exists Z \subseteq Y, |Z| = |Y| - |X|: \mathcal{L}(X \cup Z) = V$
  * *Důsledky:* každou LN množinu lze doplnit na bázi, z generátorů vybrat bázi, všechny báze mají stejnou velikost $\dim(V)$.

* **Matice jako lineární zobrazení:**
  * $[f(x)]_B = [f]_{A, B} \cdot [x]_A$ (ve sloupcích jsou $[f(a_i)]_B$).
  * **Prostory matice a vlastnosti zobrazení:**
    * $\operatorname{Ker}(A) = \operatorname{Ker}(f)$
    * $f$ je **prosté (injekce)** $\iff \operatorname{Ker}(A) = \{0\} \iff \operatorname{rank}(A) = n$
    * $\operatorname{Col}(A) = \operatorname{Im}(f)$
    * $f$ je **na (surjekce)** $\iff \operatorname{rank}(A) = m \iff \operatorname{Col}(A) = \mathbb{K}^m$
    * **Rank-Nullity teorém:** $\dim(\operatorname{Ker}(f)) + \dim(\operatorname{Im}(f)) = \dim(U) \implies \dim(\operatorname{Ker}(A)) + \operatorname{rank}(A) = n$
    * **Isomorfismus (bijekce):** $m = n \land \operatorname{rank}(A) = n$ (matice $A$ je regulární)

* **Složení zobrazení:**
  * $(g \circ f)(x) = g(f(x)) \implies [g \circ f] = G \cdot F$
  * Vektor vstupuje zprava: $(GF)x = G(Fx)$. Rozměry: $G_{m \times k} \cdot F_{k \times n} \in \mathbb{K}^{m \times n}$.

* **Podobnost matic ($A \sim B$):**
  * $B = R^{-1} A R$ (tatáž transformace v jiné bázi, $R$ je matice přechodu).
  * **Invarianty:** stejný $p(\lambda) \implies$ stejná vl. čísla $\lambda_i$ a násobnosti, $\det(A) = \det(B)$, $\operatorname{Tr}(A) = \operatorname{Tr}(B)$, $\operatorname{rank}(A) = \operatorname{rank}(B)$, $\dim \operatorname{Ker}(A) = \dim \operatorname{Ker}(B)$.

* **Diagonalizovatelnost (Kritéria):**
  * $A = S \Lambda S^{-1} \iff S^{-1} A S = \operatorname{diag}(\lambda_1, \dots, \lambda_n)$ ($S$ má ve sloupcích vl. vektory).
  * **Ekvivalentní kritérium:** $\mathbb{K}^n$ má bázi z vlastních vektorů $\iff \forall \lambda_i: \text{alg. násobnost} = \text{geom. násobnost } (\dim \operatorname{Ker}(A - \lambda_i I))$.
  * **Postačující kritérium:** $n$ navzájem různých vlastních čísel $\implies$ vždy diagonalizovatelná.
  * **Symetrické matice ($A = A^T$):** Vždy ortogonálně diagonalizovatelná $A = Q \Lambda Q^T$ ($Q^{-1} = Q^T$, $\lambda_i \in \mathbb{R}$, vl. vektory jsou navzájem kolmé).

* **Pozitivní definitnost (Kritéria):**
  * Definice: $A = A^T$ a $\forall x \ne 0: x^T A x > 0$ (PSD: $x^T A x \ge 0$).
  * **Kritéria (ekvivalence pro PD):**
    1. **Vlastní čísla:** $\forall i: \lambda_i > 0$ (pro PSD $\lambda_i \ge 0$).
    2. **Sylvestrovo kritérium:** Všechny hlavní vedoucí minory $\det(A_k) > 0$ pro $k = 1, \dots, n$ (levé horní rohy).
    3. **Choleského rozklad:** $\exists! U$ horní trojúhelníková s $u_{ii} > 0$ t.ž. $A = U^T U$ (resp. $A = L L^T$).
    4. **Gramova matice:** $A$ je Gramova matice LN vektorů ($a_{ij} = \langle v_i, v_j \rangle$).
    5. **Skalární součin:** $\langle x, y \rangle_A = x^T A y$ je skalární součin.
  * *Vlastnosti:* $\det(A) > 0$, $\operatorname{Tr}(A) > 0$, diagonála $a_{ii} > 0$, $A$ je regulární, $A^{-1}$ je PD.

* **Regularita matice (Kritéria a ekvivalence):**
  * $\exists A^{-1} \iff \det(A) \ne 0 \iff \operatorname{rank}(A) = n \iff \operatorname{Ker}(A) = \{0\} \iff 0 \notin \sigma(A)$ (žádné $\lambda = 0$) $\iff$ sloupce (řádky) tvoří bázi $\iff \operatorname{RREF}(A) = I_n \iff Ax = b$ má právě 1 řešení $\forall b$.

* **Cauchyho–Schwarzova nerovnost:**
  * $|\langle u, v \rangle| \le \|u\| \cdot \|v\| \iff \langle u, v \rangle^2 \le \langle u \mid u \rangle \cdot \langle v \mid v \rangle$
  * Rovnost nastává $\iff u, v$ jsou lineárně závislé.

* **Gramova–Schmidtova ortogonalizace:**
  * $y_1 = x_1$
  * $y_k = x_k - \sum_{j=1}^{k-1} \frac{\langle x_k, y_j \rangle}{\langle y_j, y_j \rangle} y_j \quad$ *(pokud jsou již $z_j$ normalizované: $y_k = x_k - \sum_{j=1}^{k-1} \langle x_k, z_j \rangle z_j$)*
  * Normalizace (jen pro ON bázi): $z_k = \frac{y_k}{\|y_k\|}$.
  * *Pozor:* Chce-li zadání jen ortogonální bázi, **nenormalizuj** (neodmocňuj). Vede na QR rozklad ($A = QR$).



* **Sestavení matice zobrazení $[\varphi]_{A, B}$:**
  * Do **sloupců** matice $[\varphi]_{A, B}$ dáváš obrazy vektorů z **VÝCHOZÍ báze $A$**, vyjádřené v souřadnicích vůči **CÍLOVÉ bázi $B$**:
    $$[\varphi]_{A, B} = \Big( [\varphi(v_1)]_B \;\big|\; [\varphi(v_2)]_B \;\big|\; \dots \;\big|\; [\varphi(v_n)]_B \Big)$$
  * *Mnemotechnická pomůcka:* $[\varphi(x)]_B = [\varphi]_{A, B} \cdot [x]_A$ (vektor $x$ z báze $A$ „vstupuje“ zprava a výsledkem je obraz v bázi $B$).

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



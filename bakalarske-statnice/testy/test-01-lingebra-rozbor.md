# Rozbor Testu 1: Lineární algebra (Vyhodnocení a vzorová řešení)

* **Datum:** 4. 9. 2026
* **Doba psaní:** 47 minut (11:22 – 12:09)
* **Hodnocení:**
  * **Mírnější (průběžné) hodnocení:** **7,7 / 10 bodů (77 % – známka 2 / Velmi dobře)**
  * **Přísné zkouškové hodnocení MFF:** **7,15 / 10 bodů (72 % – známka 2 / Velmi dobře)**
* **Výchozí test:** [test-01-lingebra.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-01-lingebra.md)

---

## 📊 Rychlý přehled výsledků

| Otázka | Téma | Mírně | Přísně MFF | Hlavní zjištění |
|:---:|---|:---:|:---:|---|
| **1** | Znaménko permutace z cyklů | 1,0 | 1,0 | Perfektní započtení pevného bodu ($c=3$). |
| **2** | Frobeniova věta a dimenze jádra | 1,0 | 1,0 | Věta i dimenze správně; ujasněn afinní podprostor. |
| **3** | Definice báze vektorového prostoru | 0,6 | 0,5 | Chybělo explicitní uvedení lineární nezávislosti. |
| **4** | Dimenze podprostorů a ortogonalita | 0,35 | 0,25 | Numerická chyba $6-3=1$ shodila celou ortogonalitu. |
| **5** | Lineární zobrazení a isomorfismus | 0,95 | 0,9 | Výborně, drobný překlep v definičním oboru vzoru ($u \in U$). |
| **6** | Matice zobrazení vůči bázím | 1,0 | 1,0 | Naprosto přesné sestavení matice derivace. |
| **7** | Skalární součin a Cauchy-Schwarz | 0,5 | 0,4 | Chybí $|\langle u \mid v \rangle|$ a $\langle u \mid u \rangle \ge 0$ (ne pro $u \ne v$). |
| **8** | Vlastnosti determinantu | 0,9 | 0,8 | Vzorce výborně, u $A^{-1}$ nedopsáno číslo $1/3$. |
| **9** | Vlastní čísla a diagonalizace | 0,7 | 0,6 | V definici vlastního vektoru chybí podmínka $v \ne 0$. |
| **10** | Pozitivní definitnost matic | 0,7 | 0,7 | V definici chybí $x \ne 0$; důkaz diagonály přes $e_i^T A e_i$. |
| **CELKEM** | | **7,7** | **7,15** | **Úspěšnost 72 % (zkouška splněna bezpečně)** |

---

## 🔍 Detailní rozbor s přesnými vzorovými řešeními

### 1. Znaménko permutace
* **Zadání:** $\pi = (1, 3, 5)(2, 4) \in S_6$. Určete $\operatorname{sgn}(\pi)$.
* **Odpověď studenta:**
  $$\operatorname{sgn}(\pi) = (-1)^{n-c} = -1, \quad c = 3, \quad n - c = 3$$
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – bezchybné.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  Rozklad permutace $\pi \in S_6$ na nezávislé cykly je $\pi = (1, 3, 5)(2, 4)(6)$.
  * Celkový počet prvků: $n = 6$.
  * Celkový počet nezávislých cyklů (včetně cyklu délky 1, tj. pevného bodu 6): $c = 3$.
  * Podle vzorce pro znaménko:
    $$\operatorname{sgn}(\pi) = (-1)^{n - c} = (-1)^{6 - 3} = (-1)^3 = \mathbf{-1}$$
  *(Permutace je lichá).*

---

### 2. Řešitelnost soustav a Frobeniova věta
* **Zadání:** Zformulujte Frobeniovu větu pro $Ax = b$ a určete dimenzi řešení homogenní soustavy $Ax = 0$.
* **Odpověď studenta:**
  * Soustava $Ax = b$ má řešení $\iff \operatorname{rank}(A) = \operatorname{rank}(A \mid b)$.
  * $\dim(\operatorname{Ker}(A)) = n - \operatorname{rank}(A)$.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – přesné.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Frobeniova věta:**
     Soustava lineárních rovnic $Ax = b$ s maticí $A \in \mathbb{K}^{m \times n}$ a vektorem pravých stran $b \in \mathbb{K}^m$ má alespoň jedno řešení právě tehdy, když se hodnost matice soustavy rovná hodnosti rozšířené matice soustavy:
     $$\operatorname{rank}(A) = \operatorname{rank}(A \mid b)$$
  2. **Dimenze řešení homogenní soustavy $Ax = 0$:**
     Množina všech řešení tvoří vektorový podprostor $\operatorname{Ker}(A) \le \mathbb{K}^n$. Dle věty o dimenzích je jeho dimenze rovna:
     $$\dim(\operatorname{Ker}(A)) = n - \operatorname{rank}(A)$$
     *(kde $n$ je počet neznámých / sloupců matice $A$).*

---

### 3. Báze vektorového prostoru
* **Zadání:** Definujte pojem báze vektorového prostoru $V$ nad tělesem $\mathbb{K}$ (uveďte obě podmínky).
* **Odpověď studenta:**
  * „Libovolná minimální množina $v \in V$ taková, že $\operatorname{span}(\{v \in V\}) = V$.“
* **Hodnocení:** **0,6 b (přísně 0,5 b)** – chybělo explicitní uvedení lineární nezávislosti.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  Podmnožina $B \subseteq V$ (resp. uspořádaná $n$-tice vektorů) se nazývá **báze** vektorového prostoru $V$ nad tělesem $\mathbb{K}$, pokud splňuje následující dvě podmínky:
  1. Množina $B$ je **lineárně nezávislá** (žádný vektor nelze vyjádřit jako lineární kombinaci ostatních, tj. $\sum_{i=1}^k \alpha_i v_i = 0 \implies \alpha_1 = \dots = \alpha_k = 0$).
  2. Množina $B$ **generuje celý prostor $V$**, tj. $\operatorname{span}(B) = \mathcal{L}(B) = V$ (každý vektor z $V$ lze vyjádřit jako lineární kombinaci vektorů z $B$).

---

### 4. Dimenze podprostorů matice a ortogonalita
* **Zadání:** $A \in \mathbb{R}^{4 \times 6}$, $\operatorname{rank}(A) = 3$. Určete $\dim(\operatorname{Row}(A)), \dim(\operatorname{Col}(A)), \dim(\operatorname{Ker}(A)), \dim(\operatorname{Ker}(A^T))$ a ortogonální doplněk k $\operatorname{Ker}(A)$ v $\mathbb{R}^6$.
* **Odpověď studenta:**
  * $\dim(\operatorname{Row}(A)) = \dim(\operatorname{Col}(A)) = 3$, $\dim(\operatorname{Ker}(A)) = 1$ *(chyba)*, $\dim(\operatorname{Ker}(A^T)) = 1$. Závěr: žádný ortogonální doplněk.
* **Hodnocení:** **0,35 b (přísně 0,25 b)** – numerická chyba $6-3=1$ shodila celou ortogonalitu.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  Matice má $m = 4$ řádků, $n = 6$ sloupců a hodnost $r = \operatorname{rank}(A) = 3$:
  1. $\dim(\operatorname{Row}(A)) = r = \mathbf{3}$ (řádkový prostor je podprostor $\mathbb{R}^6$).
  2. $\dim(\operatorname{Col}(A)) = r = \mathbf{3}$ (sloupcový prostor je podprostor $\mathbb{R}^4$).
  3. $\dim(\operatorname{Ker}(A)) = n - r = 6 - 3 = \mathbf{3}$ (jádro je podprostor $\mathbb{R}^6$).
  4. $\dim(\operatorname{Ker}(A^T)) = m - r = 4 - 3 = \mathbf{1}$ (levé jádro je podprostor $\mathbb{R}^4$).
  * **Ortogonální doplněk:**
    Podle základní věty lineární algebry platí:
    $$(\operatorname{Ker}(A))^\perp = \operatorname{Row}(A)$$
    *(Kontrola dimenzí v $\mathbb{R}^6$: $\dim(\operatorname{Ker}(A)) + \dim(\operatorname{Row}(A)) = 3 + 3 = 6$).*

---

### 5. Lineární zobrazení a Isomorfismus
* **Zadání:** Definujte lineární zobrazení $f: U \to V$ a uveďte podmínku isomorfismu pro konečně-dimenzionální prostory.
* **Odpověď studenta:**
  * Aditivita i homogenita uvedeny, podmínka $\dim(U) = \dim(V)$.
* **Hodnocení:** **0,95 b (přísně 0,9 b)** – skvělé.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice lineárního zobrazení:**
     Zobrazení $f: U \to V$ mezi vektorovými prostory nad stejným tělesem $\mathbb{K}$ je lineární, pokud pro všechny vektory $u, v \in U$ a každý skalár $\alpha \in \mathbb{K}$ platí:
     * $f(u + v) = f(u) + f(v)$ (aditivita),
     * $f(\alpha \cdot u) = \alpha \cdot f(u)$ (homogenita).
  2. **Podmínka pro isomorfismus:**
     Dva konečně-dimenzionální vektorové prostory $U, V$ nad stejným tělesem $\mathbb{K}$ jsou isomorfní ($U \cong V$) právě tehdy, když mají stejnou dimenzi:
     $$\dim(U) = \dim(V)$$

---

### 6. Matice zobrazení vůči bázím
* **Zadání:** $P_2$, báze $B = (1, x, x^2)$, derivace $D(p(x)) = p'(x)$. Určete matici $[D]_B \in \mathbb{R}^{3 \times 3}$.
* **Odpověď studenta:**
  $$[D]_B = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 2 \\ 0 & 0 & 0 \end{pmatrix}$$
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – dokonalé.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  Sloupce matice $[D]_B$ tvoří souřadnice obrazů bázových vektorů vyjádřené v bázi $B = (1, x, x^2)$:
  * $D(1) = 0 = 0\cdot 1 + 0\cdot x + 0\cdot x^2 \implies [D(1)]_B = (0, 0, 0)^T$ (1. sloupec)
  * $D(x) = 1 = 1\cdot 1 + 0\cdot x + 0\cdot x^2 \implies [D(x)]_B = (1, 0, 0)^T$ (2. sloupec)
  * $D(x^2) = 2x = 0\cdot 1 + 2\cdot x + 0\cdot x^2 \implies [D(x^2)]_B = (0, 2, 0)^T$ (3. sloupec)
  Výsledná matice zobrazení:
  $$[D]_B = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 2 \\ 0 & 0 & 0 \end{pmatrix}$$

---

### 7. Skalární součin a Cauchyho-Schwarzova nerovnost
* **Zadání:** Axiomy reálného skalárního součinu a Cauchyho-Schwarzova nerovnost včetně podmínky rovnosti.
* **Odpověď studenta:**
  * $\langle u \mid v \rangle \ge 0$, chybí absolutní hodnota u Cauchy-Schwarze.
* **Hodnocení:** **0,5 b (přísně 0,4 b)**.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Axiomy reálného skalárního součinu ($\langle \cdot \mid \cdot \rangle: V \times V \to \mathbb{R}$):**
     * **Pozitivní definitnost:** $\forall u \in V: \langle u \mid u \rangle \ge 0$ a zároveň $\langle u \mid u \rangle = 0 \iff u = 0$.
     * **Symetrie:** $\forall u, v \in V: \langle u \mid v \rangle = \langle v \mid u \rangle$.
     * **Linearita v 1. složce:** $\forall u, v, w \in V, \forall \alpha \in \mathbb{R}$:
       $\langle u + v \mid w \rangle = \langle u \mid w \rangle + \langle v \mid w \rangle$ a $\langle \alpha u \mid v \rangle = \alpha \langle u \mid v \rangle$.
  2. **Cauchyho-Schwarzova nerovnost:**
     Pro libovolné vektory $u, v \in V$ platí:
     $$|\langle u \mid v \rangle| \le \|u\| \cdot \|v\| \quad \left(= \sqrt{\langle u \mid u \rangle} \cdot \sqrt{\langle v \mid v \rangle}\right)$$
     Rovnost $|\langle u \mid v \rangle| = \|u\| \cdot \|v\|$ nastává právě tehdy, když jsou vektory $u, v$ **lineárně závislé** (tj. jeden je skalárním násobkem druhého).

---

### 8. Vlastnosti determinantu
* **Zadání:** $A \in \mathbb{R}^{4 \times 4}$, $\det(A) = 3$. Spočtěte $\det(2A)$, $\det(A^{-1})$, $\det(A^T A)$.
* **Odpověď studenta:**
  * $\det(2A) = 2^4 \cdot 3 = 48$, $\det(A^{-1}) = \frac{1}{\det(A)}$, $\det(A^T A) = 9$.
* **Hodnocení:** **0,9 b (přísně 0,8 b)** – zapomenuto dopsat $1/3$.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  Pro čtvercovou matici $A \in \mathbb{R}^{4 \times 4}$ s $\det(A) = 3$:
  1. $\det(2A) = 2^n \det(A) = 2^4 \cdot 3 = 16 \cdot 3 = \mathbf{48}$.
  2. $\det(A^{-1}) = \frac{1}{\det(A)} = \mathbf{\frac{1}{3}}$ (protože $\det(A) = 3 \ne 0$, matice je regulární a inverze existuje).
  3. $\det(A^T A) = \det(A^T) \cdot \det(A) = \det(A) \cdot \det(A) = 3 \cdot 3 = \mathbf{9}$.

---

### 9. Vlastní čísla, vlastní vektory a diagonalizovatelnost
* **Zadání:** Definice vlastního čísla a vektoru. Rozhodněte o diagonalizovatelnosti matice s $n$ navzájem různými vlastními čísly.
* **Odpověď studenta:**
  * $A v = \lambda v$, diagonalizovatelnost ano přes násobnost 1.
* **Hodnocení:** **0,7 b (přísně 0,6 b)** – chybí $v \ne 0$.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice vlastního čísla a vlastního vektoru:**
     Číslo $\lambda \in \mathbb{R}$ (resp. $\mathbb{C}$) je vlastním číslem čtvercové matice $A \in \mathbb{R}^{n \times n}$, pokud existuje **nenulový vektor $v \in \mathbb{R}^n \setminus \{0\}$** takový, že:
     $$A v = \lambda v \quad (\iff (A - \lambda I_n)v = 0)$$
     Vektor $v$ nazýváme vlastním vektorem příslušným vlastnímu číslu $\lambda$.
  2. **Rozhodnutí o diagonalizovatelnosti: ANO, PLATÍ.**
     *Zdůvodnění:* Vlastní vektory příslušné navzájem různým vlastním číslům jsou vždy **lineárně nezávislé**. Má-li matice $A \in \mathbb{R}^{n \times n}$ celkem $n$ různých vlastních čísel, existuje k nim soubor $n$ lineárně nezávislých vlastních vektorů. Tyto vektory tvoří bázi prostoru $\mathbb{R}^n$, z čehož přímo plyne, že matice $A$ je diagonalizovatelná (matice přechodu $P$ sestavená z těchto vlastních vektorů splňuje $P^{-1} A P = D$, kde $D$ je diagonální matice s vlastními čísly na diagonále).

---

### 10. Pozitivní definitnost matic
* **Zadání:** Definice pozitivní definitnosti, 2 kritéria a rozhodnutí o prvcích na diagonále.
* **Odpověď studenta:**
  * Kvadratická forma $> 0$, vlastní čísla kladná, Choleský rozklad, na diagonále nemůže být $\le 0$ kvůli Choleskému.
* **Hodnocení:** **0,7 b (přísně 0,7 b)**.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice pozitivně definitní matice:**
     Reálná symetrická matice $A \in \mathbb{R}^{n \times n}$ je **pozitivně definitní**, pokud pro každý **nenulový vektor $x \in \mathbb{R}^n \setminus \{0\}$** platí:
     $$x^T A x > 0$$
  2. **Ekvivalentní kritéria (stačí uvést 2):**
     * Všechna vlastní čísla matice $A$ jsou ostře kladná: $\forall i: \lambda_i > 0$.
     * **Sylvesterovo kritérium:** Všechny hlavní vedoucí minory matice $A$ jsou ostře kladné: $\det(A_k) > 0$ pro $k = 1, \dots, n$.
     * **Choleského rozklad:** Existuje regulární dolní trojúhelníková matice $L$ s kladnou diagonálou taková, že $A = L L^T$.
  3. **Prvky na hlavní diagonále: NEMŮŽE.**
     *Zdůvodnění:* Zvolme $i$-tý kanonický bázový vektor $e_i = (0, \dots, 1, \dots, 0)^T$, který má jedničku na $i$-té pozici. Protože $e_i \ne 0$, musí z definice pozitivní definitnosti platit:
     $$e_i^T A e_i > 0$$
     Přímým roznásobením ale dostáváme $e_i^T A e_i = a_{ii}$ (prvek na hlavní diagonále na $i$-tém řádku a sloupci). Tedy nutně $a_{ii} > 0$. Žádný prvek na diagonále nemůže být záporný ani nulový.

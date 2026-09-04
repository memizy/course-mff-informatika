# Rozbor Testu 1: Lineární algebra (Vyhodnocení a vzorová řešení)

* **Datum:** 4. 9. 2026
* **Doba psaní:** 47 minut (11:22 – 12:09)
* **Celkové skóre:** **7,7 / 10 bodů (77 % – známka Velmi dobře / 2)**
* **Výchozí test:** [test-01-lingebra.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-01-lingebra.md)

---

## 📊 Rychlý přehled výsledků

| Otázka | Téma | Body | Úspěšnost | Hlavní poznámka |
|:---:|---|:---:|:---:|---|
| **1** | Znaménko permutace z cyklů | 1,0 / 1,0 | 100 % | Perfektní započtení pevného bodu ($c=3$). |
| **2** | Frobeniova věta a dimenze jádra | 1,0 / 1,0 | 100 % | Věta i dimenze správně; ujasněn afinní podprostor. |
| **3** | Definice báze vektorového prostoru | 0,6 / 1,0 | 60 % | Chybělo explicitní uvedení lineární nezávislosti. |
| **4** | Dimenze podprostorů a ortogonalita | 0,35 / 1,0 | 35 % | Numerická chyba $6-3=1$ shodila celou ortogonalitu. |
| **5** | Lineární zobrazení a isomorfismus | 0,95 / 1,0 | 95 % | Výborně, drobný překlep v definičním oboru vzoru. |
| **6** | Matice zobrazení vůči bázím | 1,0 / 1,0 | 100 % | Naprosto přesné sestavení matice derivace. |
| **7** | Skalární součin a Cauchy-Schwarz | 0,5 / 1,0 | 50 % | Chybí $|\langle u \mid v \rangle|$ a $\langle u \mid u \rangle \ge 0$ (ne pro $u \ne v$). |
| **8** | Vlastnosti determinantu | 0,9 / 1,0 | 90 % | Vzorce výborně, u $A^{-1}$ nedopsáno číslo $1/3$. |
| **9** | Vlastní čísla a diagonalizace | 0,7 / 1,0 | 70 % | V definici vlastního vektoru chybí podmínka $v \ne 0$. |
| **10** | Pozitivní definitnost matic | 0,7 / 1,0 | 70 % | V definici chybí $x \ne 0$; důkaz diagonály přes $e_i^T A e_i$. |

---

## 🔍 Detailní rozbor otázku po otázce

### 1. Znaménko permutace
* **Zadání:** $\pi = (1, 3, 5)(2, 4) \in S_6$. Určete $\operatorname{sgn}(\pi)$.
* **Odpověď studenta:**
  $$\operatorname{sgn}(\pi) = (-1)^{n-c} = -1, \quad c = 3, \quad n - c = 3$$
* **Hodnocení:** **1,0 / 1,0 (100 %)**
* **Komentář:** Perfektní aplikace rychlého vzorce. Zkouškový chyták spočíval v tom nezapomenout na pevný bod $(6)$, který tvoří samostatný cyklus délky 1. Tedy $c = 3$ (cykly $(1, 3, 5)$, $(2, 4)$ a $(6)$), $n = 6 \implies n - c = 3 \implies \operatorname{sgn}(\pi) = (-1)^3 = -1$.

---

### 2. Řešitelnost soustav a Frobeniova věta
* **Zadání:** Zformulujte Frobeniovu větu pro $Ax = b$ a určete dimenzi řešení homogenní soustavy $Ax = 0$.
* **Odpověď studenta:**
  * Soustava $Ax = b$ má řešení $\iff \operatorname{rank}(A) = \operatorname{rank}(A \mid b)$.
  * $\dim(\operatorname{Ker}(A)) = n - \operatorname{rank}(A)$.
  * *Poznámka:* „tohle je afinní?“
* **Hodnocení:** **1,0 / 1,0 (100 %)**
* **Komentář k poznámce studenta:**
  * **Homogenní soustava $Ax = 0$:** Množina řešení $\operatorname{Ker}(A)$ je přímo **vektorovým podprostorem** (obsahuje nulový vektor $0$). Vektorový prostor je speciálním případem afinního podprostoru (prochází počátkem).
  * **Nehomogenní soustava $Ax = b$:** Pokud existuje partikulární řešení $x_0$, je množina všech řešení tvaru $x_0 + \operatorname{Ker}(A)$, což je **afinní podprostor** se zaměřením $\operatorname{Ker}(A)$ a dimenzí $n - \operatorname{rank}(A)$.

---

### 3. Báze vektorového prostoru
* **Zadání:** Definujte pojem báze vektorového prostoru $V$ nad tělesem $\mathbb{K}$ (uveďte obě podmínky).
* **Odpověď studenta:**
  * „Libovolná minimální (neexistuje menší taková množina) množina $v \in V$ taková, že $\operatorname{span}(\{v \in V\}) = V$.“
* **Hodnocení:** **0,6 / 1,0 (60 %)**
* **Výtka zkoušejícího:**
  * Intuice „minimální množiny generátorů“ je matematicky ekvivalentní charakteristika, ale zkoušející na MFF u otázky „definujte bázi (obě podmínky)“ striktně vyžaduje standardní definiční znění:
    1. Množina $B$ je **lineárně nezávislá**.
    2. Množina $B$ **generuje celý prostor** ($\operatorname{span}(B) = V$).
  * *Pozor na formulaci „neexistuje menší“:* V teorii se tím myslí minimální vzhledem k uspořádání inkluzí $\subseteq$ (tj. žádná vlastní podmnožina už negeneruje $V$).

---

### 4. Dimenze podprostorů matice a ortogonalita
* **Zadání:** $A \in \mathbb{R}^{4 \times 6}$, $\operatorname{rank}(A) = 3$. Určete $\dim(\operatorname{Row}(A)), \dim(\operatorname{Col}(A)), \dim(\operatorname{Ker}(A)), \dim(\operatorname{Ker}(A^T))$ a ortogonální doplněk k $\operatorname{Ker}(A)$ v $\mathbb{R}^6$.
* **Odpověď studenta:**
  * $\dim(\operatorname{Row}(A)) = \dim(\operatorname{Col}(A)) = 3$
  * $\dim(\operatorname{Ker}(A)) = n - \operatorname{rank}(A) = 1$  *(chyba!)*
  * $\dim(\operatorname{Ker}(A^T)) = m - \operatorname{rank}(A) = 1$
  * „Žádný, protože součty dimenzí nedají 6.“
* **Hodnocení:** **0,35 / 1,0 (35 %)**
* **Rozbor fatální chyby:**
  * Matice má rozměr $4 \times 6$, tedy **$m = 4$ řádků**, **$n = 6$ sloupců** a hodnost $r = 3$.
  * Správný výpočet: $\dim(\operatorname{Ker}(A)) = n - r = 6 - 3 = \mathbf{3}$ (ve výpočtu se objevilo $1$, pravděpodobně záměnou $n$ za $m$).
  * Správný ortogonální doplněk: Protože $\dim(\operatorname{Ker}(A)) = 3$ a $\dim(\operatorname{Row}(A)) = 3$, platí $3 + 3 = 6$. Ortogonálním doplňkem k $\operatorname{Ker}(A)$ v prostoru $\mathbb{R}^6$ je **přesně řádkový prostor $\operatorname{Row}(A)$**!
  * **Základní věta LA k zapamatování:** $(\operatorname{Ker}(A))^\perp = \operatorname{Row}(A)$ a $(\operatorname{Ker}(A^T))^\perp = \operatorname{Col}(A)$.

---

### 5. Lineární zobrazení a Isomorfismus
* **Zadání:** Definujte lineární zobrazení $f: U \to V$ a uveďte nutnou a postačující podmínku pro isomorfismus konečně-dimenzionálních prostorů.
* **Odpověď studenta:**
  * $f(u + v) = f(u) + f(v)$, $f(a \cdot u) = a \cdot f(u)$.
  * Isomorfismus nastává, pokud $\dim(U) = \dim(V)$.
* **Hodnocení:** **0,95 / 1,0 (95 %)**
* **Komentář:** Výborné, obě podmínky linearity i dimenzionální kritérium isomorfismu jsou přesné. Pouze drobný překlep v textu u vzorů ($u \in U$, nikoliv $V$).

---

### 6. Matice zobrazení vůči bázím
* **Zadání:** $P_2$, báze $B = (1, x, x^2)$, operátor derivace $D(p(x)) = p'(x)$. Určete matici $[D]_B \in \mathbb{R}^{3 \times 3}$.
* **Odpověď studenta:**
  $$[D]_B = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 2 \\ 0 & 0 & 0 \end{pmatrix}$$
* **Hodnocení:** **1,0 / 1,0 (100 %)**
* **Komentář:** Naprosto brilantní. Včetně správné úvahy se souřadnicemi obrazů bázových vektorů:
  * $D(1) = 0 = 0\cdot 1 + 0\cdot x + 0\cdot x^2 \implies [D(1)]_B = (0, 0, 0)^T$ (1. sloupec)
  * $D(x) = 1 = 1\cdot 1 + 0\cdot x + 0\cdot x^2 \implies [D(x)]_B = (1, 0, 0)^T$ (2. sloupec)
  * $D(x^2) = 2x = 0\cdot 1 + 2\cdot x + 0\cdot x^2 \implies [D(x^2)]_B = (0, 2, 0)^T$ (3. sloupec)

---

### 7. Skalární součin a Cauchyho-Schwarzova nerovnost
* **Zadání:** Axiomy reálného skalárního součinu a znění Cauchyho-Schwarzovy nerovnosti včetně podmínky rovnosti.
* **Odpověď studenta:**
  * Axiomy: $\forall u, v \in V: \langle u \mid v \rangle = \langle v \mid u \rangle \ge 0$, linearita v 1. složce.
  * Nerovnost: $\langle u \mid v \rangle \le \|u\| \cdot \|v\|$, rovnost pro $u = a \cdot v$.
* **Hodnocení:** **0,5 / 1,0 (50 %)**
* **Kritické chyby k zapamatování:**
  1. **Pozitivní definitnost:** Platí **pouze pro tentýž vektor**:
     $$\forall u \in V: \langle u \mid u \rangle \ge 0 \quad \text{a} \quad \langle u \mid u \rangle = 0 \iff u = 0$$
     Pro dva různé vektory $u, v$ skalární součin **může být záporný** (např. v $\mathbb{R}^2$ vektory $(1, 0)$ a $(-1, 0)$ mají $\langle u \mid v \rangle = -1 < 0$).
  2. **Cauchy-Schwarz:** V nerovnosti **musí být absolutní hodnota**:
     $$|\langle u \mid v \rangle| \le \|u\| \cdot \|v\|$$
     *(Bez absolutní hodnoty nerovnost neříká vůbec nic o tom, jak hluboko do záporu může součin jít).*
  * Rovnost $u = a \cdot v$ (lineární závislost) uvedena správně.

---

### 8. Vlastnosti determinantu
* **Zadání:** $A \in \mathbb{R}^{4 \times 4}$, $\det(A) = 3$. Spočtěte $\det(2A)$, $\det(A^{-1})$, $\det(A^T A)$.
* **Odpověď studenta:**
  * $\det(2A) = 2^4 \cdot 3 = 48$
  * $\det(A^{-1}) = \frac{1}{\det(A)}$
  * $\det(A^T A) = \det(A^T) \cdot \det(A) = 9$
* **Hodnocení:** **0,9 / 1,0 (90 %)**
* **Komentář:** Všechny vlastnosti aplikovány korektně (včetně $2^n$ pro $n=4$). U $\det(A^{-1})$ stačilo jen dopsat číslo $\frac{1}{3}$.

---

### 9. Vlastní čísla, vlastní vektory a diagonalizovatelnost
* **Zadání:** Definujte vlastní číslo a vlastní vektor. Rozhodněte, zda matice s $n$ navzájem různými vlastními čísly je nutně diagonalizovatelná.
* **Odpověď studenta:**
  * Definice: $Av = \lambda v$.
  * Diagonalizovatelnost: Ano, protože každé má násobnost 1 $\implies n$ vlastních vektorů $\implies$ diagonalizovatelná.
* **Hodnocení:** **0,7 / 1,0 (70 %)**
* **Chyba v definici:**
  * Vlastní vektor MUSÍ být **nenulový: $v \ne 0$** ($v \in V \setminus \{0\}$).
  * *Proč je to fatální detail:* Pokud by mohl být $v = 0$, pak rovnost $A \cdot 0 = \lambda \cdot 0 = 0$ platí triviálně pro úplně každé číslo $\lambda \in \mathbb{C}$, takže by pojem vlastního čísla ztratil jakýkoliv smysl.
* Odůvodnění diagonalizovatelnosti je správné (vlastní vektory k různým vlastním číslům jsou lineárně nezávislé $\implies$ tvoří bázi celého prostoru $\mathbb{R}^n$).

---

### 10. Pozitivní definitnost matic
* **Zadání:** Definujte pozitivní definitnost symetrické matice, uveďte 2 kritéria a rozhodněte o prvcích na diagonále.
* **Odpověď studenta:**
  * Definice: pro každý vektor $x: x A x^T > 0$.
  * Kritéria: všechna vlastní čísla kladná; Choleského rozklad $A = L L^T$.
  * Diagonála: Ne, nemůže, protože by v Choleském vyšla odmocnina ze záporného čísla nebo 0.
* **Hodnocení:** **0,7 / 1,0 (70 %)**
* **Výtky a formální zkouškový postup:**
  1. V definici opět chybí **nenulovost vektoru: $\forall x \in \mathbb{R}^n \setminus \{0\}$** (pro $x = 0$ je $x^T A x = 0$ vždy). Standardní notace pro sloupcový vektor je $x^T A x > 0$.
  2. Dvě kritéria (vlastní čísla $\lambda_i > 0$ a Choleského rozklad) jsou uvedena správně.
  3. **Zdůvodnění prvků na diagonále na MFF:** Intuice přes Choleského je věcně v pořádku, ale formální důkaz přímo z definice spočívá v dosazení $i$-tého vektoru standardní báze $e_i = (0, \dots, 1, \dots, 0)^T \ne 0$:
     $$e_i^T A e_i = a_{ii}$$
     Z pozitivní definitnosti musí pro nenulový vektor $e_i$ platit $e_i^T A e_i > 0 \implies \mathbf{a_{ii} > 0}$. Tedy diagonální prvek nemůže být $\le 0$.

---

## 🎯 4 hlavní zkoušková ponaučení pro příště:
1. **Podmínka nenulovosti ($v \ne 0, x \ne 0$):**
   * Vlastní vektor je VŽDY $v \ne 0$.
   * Pozitivní definitnost je $x^T A x > 0$ pro VŠECHNA $x \ne 0$.
2. **Absolutní hodnota v nerovnostech:**
   * Cauchy-Schwarz: $|\langle u \mid v \rangle| \le \|u\| \cdot \|v\|$.
3. **Pozitivní definitnost skalárního součinu:**
   * $\langle u \mid u \rangle \ge 0$ platí jen pro stejný vektor!
4. **Pozor na numeriku u dimenzí:**
   * Počet sloupců je $n$, počet řádků je $m$. Neztrácet body na $6 - 3 = 1$.

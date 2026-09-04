# Test 1: Lineární algebra (10 otázek)

* **Datum:** 4. 9. 2026
* **Doporučený čas:** 25–30 minut
* **Pravidla:** Piš na papír bez nahlížení do taháku či poznámek. Odpovědi formuluj přesně se všemi předpoklady.

---

### Část 1: Struktury, Soustavy a Vektorové prostory

#### 1. Znaménko permutace
Mějme permutaci $\pi \in S_6$ zadanou zápisem nezávislých cyklů:
$$\pi = (1, 3, 5)(2, 4)$$
* Určete znaménko $\operatorname{sgn}(\pi)$ a svůj výpočet stručně zdůvodněte.

---

#### 2. Řešitelnost soustav a Frobeniova věta
* Nechť $A \in \mathbb{K}^{m \times n}$ a $b \in \mathbb{K}^m$. Zformulujte **Frobeniovu větu** o řešitelnosti soustavy lineárních rovnic $Ax = b$.
* Jaká je dimenze afinního podprostoru všech řešení homogenní soustavy $Ax = 0$ vyjádřená pomocí $n$ a hodnosti matice $A$?

---

#### 3. Báze vektorového prostoru
* Definujte pojem **báze** vektorového prostoru $V$ nad tělesem $\mathbb{K}$ (uveďte obě podmínky).

---

#### 4. Dimenze podprostorů matice a ortogonalita
Nechť matice $A \in \mathbb{R}^{4 \times 6}$ má hodnost $\operatorname{rank}(A) = 3$.
* Určete přesné dimenze těchto čtyř prostorů:
  1. $\dim(\operatorname{Row}(A))$
  2. $\dim(\operatorname{Col}(A))$
  3. $\dim(\operatorname{Ker}(A))$
  4. $\dim(\operatorname{Ker}(A^T))$
* Který z těchto prostorů je ortogonálním doplňkem k prostoru jádra $\operatorname{Ker}(A)$ v prostoru $\mathbb{R}^6$?

---

### Část 2: Zobrazení, Skalární součin, Determinanty, Vlastní čísla a Pozitivní definitnost

#### 5. Lineární zobrazení a Isomorfismus
* Definujte **lineární zobrazení** $f: U \to V$ mezi vektorovými prostory nad tělesem $\mathbb{K}$ (obě podmínky linearity).
* Za jaké nutné a postačující podmínky na dimenze jsou dva konečně-dimenzionální prostory $U, V$ nad stejným tělesem $\mathbb{K}$ **isomorfní** ($U \cong V$)?

---

#### 6. Matice zobrazení vůči bázím
Uvažujme vektorový prostor reálných polynomů stupně nejvýše 2:
$$P_2 = \{a x^2 + b x + c \mid a, b, c \in \mathbb{R}\}$$
s uspořádanou bází $B = (1, x, x^2)$.
* Nechť $D: P_2 \to P_2$ je operátor derivace, tj. $D(p(x)) = p'(x)$.
* Napište matici tohoto zobrazení vůči bázi $B$, tedy matici $[D]_B = {_B[D]_B} \in \mathbb{R}^{3 \times 3}$.

---

#### 7. Skalární součin a Cauchyho-Schwarzova nerovnost
* Uveďte axiomy, které musí splňovat reálný **skalární součin** $\langle \cdot \mid \cdot \rangle: V \times V \to \mathbb{R}$.
* Zformulujte **Cauchyho-Schwarzovu nerovnost** a uveďte, kdy přesně v ní nastává rovnost.

---

#### 8. Vlastnosti determinantu
Nechť čtvercová matice $A \in \mathbb{R}^{4 \times 4}$ má determinant $\det(A) = 3$.
Určete hodnoty:
1. $\det(2A)$
2. $\det(A^{-1})$
3. $\det(A^T A)$

---

#### 9. Vlastní čísla, vlastní vektory a diagonalizovatelnost
* Definujte **vlastní číslo** $\lambda$ a jemu příslušný **vlastní vektor** $v$ čtvercové matice $A \in \mathbb{R}^{n \times n}$.
* Rozhodněte o platnosti tvrzení a zdůvodněte:
  > *„Pokud má matice $A \in \mathbb{R}^{n \times n}$ celkem $n$ navzájem různých reálných vlastních čísel, je nutně diagonalizovatelná?“*

---

#### 10. Pozitivní definitnost matic
* Definujte pojem **pozitivně definitní matice** pro reálnou symetrickou matici $A \in \mathbb{R}^{n \times n}$.
* Uveďte alespoň 2 ekvivalentní kritéria pro ověření pozitivní definitnosti.
* **Rozhodněte a zdůvodněte:** Může mít pozitivně definitní matice na hlavní diagonále prvek menší nebo roven nule ($a_{ii} \le 0$)?

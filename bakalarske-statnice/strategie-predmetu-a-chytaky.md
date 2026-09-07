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


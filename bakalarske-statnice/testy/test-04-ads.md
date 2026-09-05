# Test 4: Algoritmy a datové struktury (10 otázek)

* **Datum:** 5. 9. 2026
* **Doporučený čas:** 25–30 minut
* **Pravidla:** Piš na papír bez nahlížení do taháku či poznámek. Odpovědi formuluj přesně se všemi předpoklady.

---

### Část 1: Složitost, Model RAM a Master Theorem

#### 1. Model RAM a Landauova notace
* **a)** Definujte pojem **jednotkové ceny** (uniform cost) a **logaritmické ceny** (logarithmic cost) v modelu RAM.
* **b)** Jaké teoretické omezení (či předpoklad na velikost strojového slova $w$) se v modelu RAM zavádí, aby jednotková cena nebyla zneužitelná k nerealisticky rychlým výpočtům?
* **c)** Rozhodněte o platnosti tvrzení a stručně zdůvodněte:
  1. Platí $2^{n+1} \in \mathcal{O}(2^n)$?
  2. Platí $2^{2n} \in \mathcal{O}(2^n)$?

---

#### 2. Master Theorem (Kuchařková věta a blesková aplikace)
* **a)** Zformulujte **Master Theorem** pro rekurentní rovnici $T(n) = a \cdot T(n/b) + \Theta(n^c)$ (uveďte podmínky na konstanty $a, b, c$ a všechny 3 případy porovnání $c$ a $\log_b a$).
* **b)** Pomocí Master Theoremu bleskově určete asymptotickou složitost rekurencí:
  1. $T_1(n) = 4 T_1(n/2) + \Theta(n)$
  2. $T_2(n) = 3 T_2(n/2) + \Theta(n)$
  3. $T_3(n) = 2 T_3(n/2) + \Theta(n^2)$

---

### Část 2: Vyhledávací stromy (BVS a AVL)

#### 3. Binární vyhledávací stromy (BVS) a mazání
Mějme binární vyhledávací strom.
* **a)** Uveďte **invariant BVS**. Který průchod stromem projde klíče ve vzestupně setříděném pořadí a v jakém čase?
* **b)** Popište algoritmus operace `Delete(x)` v případě, že uzel s klíčem $x$ má **dva syny** (koho vybereme jako náhradníka a jak se strom upraví).
* **c)** Jaká je časová složitost operace `Find` v nejhorším případě a jaký tvar stromu tento nejhorší případ způsobí?

---

#### 4. AVL stromy a vyvažování
* **a)** Definujte **AVL strom** (přesné znění invariantu hloubkového vyvážení).
* **b)** Jaká je maximální hloubka AVL stromu o $n$ uzlech v závislosti na $n$?
* **c)** Mějme podstrom s kořenem $10$, jeho levý syn je $4$ a pravý syn uzlu $4$ je $7$ (případ přetížení „cik-cak“ / LR). Jaký typ rotace je nutné provést pro obnovení vyvážení a který klíč se stane novým kořenem tohoto podstromu?

---

### Část 3: Třídění a dolní meze

#### 5. Quicksort a průměrná složitost
* **a)** Uveďte časovou složitost Quicksortu v **nejhorším** i v **průměrném** případě. Kdy nastává nejhorší případ?
* **b)** Stručně vysvětlete myšlenku odvození průměrné složitosti $\Theta(n \log n)$ pomocí **skoromediánu** a **lemmatu o džbánu**.
* **c)** Lze průměrný případ Quicksortu odvodit přímým dosazením do Master Theoremu? Zdůvodněte.

---

#### 6. Dolní mez porovnávacího třídění a model rozhodovacího stromu
* **a)** Zformulujte větu o **dolní mezi složitosti pro třídění porovnáváním** v nejhorším případě.
* **b)** Popište model **rozhodovacího stromu** (co reprezentují vnitřní uzly, listy a výška stromu $h$) a uveďte klíčovou nerovnost mezi počtem listů $L$ a počtem prvků pole $n$.
* **c)** Proč algoritmus Counting Sort (třídění počítáním) zvládne seřadit $n$ celých čísel v čase $\mathcal{O}(n + K)$, a přesto neporušuje tuto dolní mez $\Omega(n \log n)$?

---

### Část 4: Grafové algoritmy

#### 7. Prohledávání grafu (BFS vs. DFS) a klasifikace hran
* **a)** Kterou datovou strukturu využívá BFS a jakou vlastnost mají nalezené cesty v neohodnoceném grafu?
* **b)** Jaké 4 typy hran rozlišuje algoritmus DFS v orientovaném grafu? Který z těchto typů hran detekuje přítomnost orientovaného cyklu?
* **c)** Jak pomocí DFS nalézt **topologické uspořádání** orientovaného acyklického grafu (DAG)?

---

#### 8. Nejkratší cesty v grafech (Dijkstra vs. Bellman-Ford)
* **a)** Zformulujte předpoklady pro použití **Dijkstrova algoritmu** a uveďte jeho asymptotickou časovou složitost při implementaci s prioritní frontou (např. binární haldou).
* **b)** Nakreslete/popište jednoduchý orientovaný graf se zápornou hranou, na kterém Dijkstrův algoritmus selže a nenajde nejkratší cestu.
* **c)** Jaký algoritmus použijeme pro hledání nejkratších cest v grafu se zápornými hranami a jaká je jeho složitost? Jak tento algoritmus detekuje přítomnost záporného cyklu?

---

#### 9. Minimální kostra grafu (MST)
* **a)** Zformulujte **řezové pravidlo** (Cut property) pro hledání minimální kostry v hranově ohodnoceném grafu.
* **b)** Porovnejte algoritmy **Jarníkův (Primův)** a **Kruskalův**:
  * Kterou datovou strukturu používá Kruskalův algoritmus k efektivní detekci cyklů při přidávání hran a jaká je jeho celková složitost?
  * Který z těchto dvou algoritmů je asymptoticky výhodnější pro velmi husté grafy ($|E| = \Theta(|V|^2)$) a proč?

---

### Část 5: Složitostní třídy P a NP

#### 10. Třídy složitosti P, NP a NP-úplnost
* **a)** Definujte třídu **NP** pomocí polynomiálního verifikátoru (uveďte všechny požadavky na relaci/verifikátor $V(x, y)$ a délku certifikátu $y$).
* **b)** Definujte pojem **NP-úplného problému** (obě podmínky).
* **c)** Předpokládejme, že chceme dokázat, že nově zkoumaný problém $B \in \text{NP}$ je NP-úplný, a máme k dispozici již známý NP-úplný problém $A$ (např. 3-SAT). Kterou Karpovu polynomiální redukci musíme sestrojit: **$A \le_P B$**, nebo **$B \le_P A$**? Zdůvodněte.

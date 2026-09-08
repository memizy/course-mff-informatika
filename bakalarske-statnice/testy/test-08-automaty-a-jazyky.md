# Test 8: Automaty a formální jazyky (Všechna minulá zkoušková zadání MFF UK)

* **Datum zadání:** 7. 9. 2026
* **Rozsah:** Všech 7 autentických úloh z Automatů a jazyků ze všech 10 dostupných státnicových termínů MFF UK (2023–2026).
* **Styl zadání:** Reálná zkoušková zadání MFF UK v přesném znění.
* **Poznámka k diagramům:** U úloh s diagramy automatů se můžeš podívat přímo do přiložených PDF zadání (odkazy jsou u každé úlohy), základní přechody jsou popsány i v textu.
* **Instrukce:** Do připravených bloků `> **Tvé řešení:**` piš přímo své formální definice, gramatiky, stavy a přechodové funkce.

---

## Úloha 1: Převod bezkontextové gramatiky na automat (MFF termín Léto 2023 – 27. 6. 2023)

*Zdroj: [leto-2023.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/leto-2023.pdf) (Úloha 2, 3 body)*

1. Uveďte definici *bezkontextové gramatiky*.
2. Sestrojte bezkontextovou gramatiku $G$ generující následující jazyk:
   $$L = \{a^i b^j \mid i, j \ge 0 \text{ a platí } 2i = 3j\}$$
3. Převeďte gramatiku $G$ z předchozí části na zásobníkový automat přijímající prázdným zásobníkem. (Pokud se vám nepodařilo gramatiku sestrojit, sestrojte libovolný zásobníkový automat přijímající jazyk $L$ prázdným zásobníkem.)

> **Tvé řešení 1:**
> 
> *(a) Definice bezkontextové gramatiky:*
> 
> *(b) Bezkontextová gramatika $G$ pro jazyk $L$:*
> 
> *(c) Převod gramatiky $G$ na zásobníkový automat (PDA) přijímající prázdným zásobníkem:*
> 

<details>
<summary><b>💡 Klikni pro zobrazení vzorového řešení (Léto 2023)</b></summary>

### Vzorové řešení Úlohy 1 (Léto 2023)

#### 1. Definice bezkontextové gramatiky:
Bezkontextová gramatika (CFG) je čtveřice $G = (V, T, P, S)$, kde:
* $V$ (resp. $N$) je konečná neprázdná množina **neterminálních symbolů** (proměnných),
* $T$ (resp. $\Sigma$) je konečná neprázdná množina **terminálních symbolů**, přičemž $V \cap T = \emptyset$,
* $P$ je konečná množina **přepisovacích pravidel** tvaru $A \to \alpha$, kde $A \in V$ a $\alpha \in (V \cup T)^*$,
* $S \in V$ je **počáteční neterminální symbol**.
*(Jazyk generovaný gramatikou je $L(G) = \{w \in T^* \mid S \Rightarrow^* w\}$, kde $\Rightarrow^*$ je reflexivní a tranzitivní uzávěr relace přímé derivace $\Rightarrow$).*

#### 2. Bezkontextová gramatika $G$ pro jazyk $L$:
Podmínka $2i = 3j$ pro celá nezáporná čísla $i, j \ge 0$:
Protože čísla $2$ a $3$ jsou nesoudělná ($\gcd(2, 3) = 1$), musí být $i$ násobkem $3$ a $j$ násobkem $2$. Tedy existuje $k \in \mathbb{N}_0$ takové, že $i = 3k$ a $j = 2k$.
Jazyk tedy obsahuje právě slova tvaru $a^{3k} b^{2k}$ pro $k \ge 0$ (tj. pro $k=0$ prázdné slovo $\varepsilon$, pro $k=1$ slovo $aaabb$, pro $k=2$ slovo $aaaaaabbbb$, atd.).

Gramatika $G = (\{S\}, \{a, b\}, P, S)$ má pravidla:
$$S \to aaa S bb \mid \varepsilon$$
*(Pravidlo při každém použití přidá 3 znaky $a$ vlevo a 2 znaky $b$ vpravo).*

#### 3. Převod gramatiky $G$ na zásobníkový automat přijímající prázdným zásobníkem:
Použijeme **standardní kanonickou konstrukci převodu CFG na jednostavový PDA shora dolů** (simulace levé derivace na zásobníku).

Sestrojíme zásobníkový automat $M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0)$ přijímající prázdným zásobníkem:
* $Q = \{q\}$ (stačí jediný stav!)
* $\Sigma = \{a, b\}$ (vstupní abeceda odpovídá terminálům $T$)
* $\Gamma = \{S, a, b\}$ (zásobníková abeceda je sjednocením neterminálů a terminálů $V \cup T$)
* $q_0 = q$ (počáteční stav)
* $Z_0 = S$ (počáteční zásobníkový symbol odpovídá počátečnímu neterminálu)
* Množina koncových stavů $F$ se neuvádí (nebo $F = \emptyset$), protože automat přijímá **prázdným zásobníkem** ($\text{Null}(M)$).

Přechodová funkce $\delta: Q \times (\Sigma \cup \{\varepsilon\}) \times \Gamma \to \mathcal{P}_{\text{fin}}(Q \times \Gamma^*)$ je dána pravidly:
1. **Expanze neterminálu (krok derivace bez čtení vstupu):**
   * $\delta(q, \varepsilon, S) = \{(q, aaaSbb), (q, \varepsilon)\}$
2. **Porovnání a smazání terminálu (přečtení písmene ze vstupu):**
   * $\delta(q, a, a) = \{(q, \varepsilon)\}$
   * $\delta(q, b, b) = \{(q, \varepsilon)\}$

Všechny ostatní přechody jsou nedefinované ($\emptyset$).
</details> 

---

## Úloha 2: Zásobníkový automat pro jazyk s podmínkou na počet znaků (MFF termín Podzim 2023 – 14. 9. 2023)

*Zdroj: [podzim-2023.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/podzim-2023.pdf) (Úloha 2)*

1. Uveďte definici *zásobníkového automatu*.
2. Sestrojte zásobníkový automat $A$, který přijímá právě řetězce $w \in \{a, b\}^*$, které mají více znaků $a$ než $b$ a zároveň počet $a$ je lichý, tj.
   $$L(A) = \{w \mid w \in \{a, b\}^* \ \& \ |w|_a > |w|_b \ \& \ (\exists k \in \mathbb{N}_0) |w|_a = 2k + 1\}$$
   *(Za částečné řešení se uznává i automat rozpoznávající „více $a$ než $b$“).*

> **Tvé řešení 2:**
> 
> *(a) Definice zásobníkového automatu:*
> 
> *(b) Sestrojení zásobníkového automatu $A$ (stavy, abecedy, přechodová funkce $\delta$, počáteční stav a symbol, přijímací podmínka):*
> 

---

## Úloha 3: Reprezentace bezkontextového jazyka (MFF termín Jaro 2024 – 9. 2. 2024)

*Zdroj: [jaro-2024.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2024.pdf) (Úloha 1)*

Uvažme následující jazyk nad abecedou $\{0, 1, \#\}$:
$$L = \{w \# s^R \mid w, s \in \{0, 1\}^* \text{ a slovo } s \text{ je podslovem slova } w\}$$
*(Poznámka: $s^R$ označuje slovo $s$ napsané pozpátku; podslovo je souvislý podřetězec, vč. prázdného a celého slova.)*

1. Uveďte formální definici bezkontextové gramatiky a formální definici zásobníkového automatu.
2. Sestrojte nějakou bezkontextovou gramatiku generující jazyk $L$.
3. Sestrojte nějaký zásobníkový automat přijímající jazyk $L$.

> **Tvé řešení 3:**
> 
> *(a) Formální definice CFG a PDA:*
> 
> *(b) Bezkontextová gramatika pro $L$:*
> 
> *(c) Zásobníkový automat pro $L$:*
> 

---

## Úloha 4: Doplněk regulárního výrazu (MFF termín Podzim 2024 – 3. 9. 2024)

*Zdroj: [podzim-2024.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/podzim-2024.pdf) (Úloha 1)*

Mějme následující regulární výraz nad abecedou $\Sigma = \{a, b\}$:
$$R = ((a + b)(a + b))^* ab$$
Označme jako $L$ regulární jazyk popsaný výrazem $R$.

1. Sestrojte (co nejmenší) nedeterministický konečný automat $A$ rozpoznávající jazyk $L$.
2. Pomocí podmnožinové konstrukce převeďte automat $A$ na deterministický konečný automat $B$.
3. Z automatu $B$ sestrojte deterministický konečný automat $C$ rozpoznávající doplněk jazyka $L$.

*Sestrojené automaty $A$, $B$ a $C$ znázorněte pomocí stavových diagramů (nebo přechodových tabulek).*

> **Tvé řešení 4:**
> 
> *(a) NFA $A$ (stavy, přechody, počáteční a koncové stavy):*
> 
> *(b) Podmnožinová konstrukce a DFA $B$:*
> 
> *(c) DFA $C$ pro doplněk jazyka $L$:*
> 

---

## Úloha 5: Průnik bezkontextového a regulárního jazyka (MFF termín Jaro 2025 – 4. 2. 2025)

*Zdroj: [jaro-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2025.pdf) (Úloha 1)*

1. Uveďte formální definici *zásobníkového automatu*.
2. Uvažme následující jazyky nad abecedou $\Sigma = \{0, 1\}$:
   - $L_1$ je jazyk generovaný bezkontextovou gramatikou $G = (\{S\}, \Sigma, P, S)$ s množinou pravidel $P = \{S \to SS \mid 0S1 \mid \epsilon\}$ (kde $\epsilon$ značí prázdné slovo),
   - $L_2$ je jazyk rozpoznávaný deterministickým konečným automatem $A = (\{q_0, q_1, q_2, q_3\}, \Sigma, \delta_A, q_0, \{q_0, q_1, q_2, q_3\})$, jehož přechodová funkce $\delta_A$ je dána stavovým diagramem v zadání:
     *(Na diagram automatu se můžeš podívat přímo v [jaro-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2025.pdf) na str. 1. Přechody jsou: $q_0$ je start; $\delta_A(q_0, 1) = q_0, \delta_A(q_0, 0) = q_1$; $\delta_A(q_1, 0) = q_1, \delta_A(q_1, 1) = q_2$; $\delta_A(q_2, 0) = q_3, \delta_A(q_2, 1) = q_0$; $\delta_A(q_3, 0) = q_1$, na 1 je přechod nedefinovaný; všechny 4 stavy jsou přijímající).*

Sestrojte zásobníkový automat rozpoznávající průnik $L = L_1 \cap L_2$ jazyků $L_1$ a $L_2$.

> **Tvé řešení 5:**
> 
> *(a) Formální definice zásobníkového automatu:*
> 
> *(b) Konstrukce zásobníkového automatu pro průnik $L_1 \cap L_2$ (synchronní součin):*
> 

---

## Úloha 6: Deterministické konečné automaty a podslova (MFF termín Léto 2025 – 23. 6. 2025)

*Zdroj: [leto-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/leto-2025.pdf) (Úloha 1)*

1. Uveďte definici jazyka $L(A)$ přijímaného daným deterministickým konečným automatem $A = (Q, \Sigma, \delta, q_0, F)$ včetně definice jeho rozšířené přechodové funkce $\delta^*$.
2. Nechť $S \subseteq \Sigma^*$ je neprázdná konečná množina slov, $Q$ je množina všech prefixů slov z $S$ (včetně prázdného slova $\varepsilon$ a slov z $S$) a $A = (Q, \Sigma, \delta, \varepsilon, S)$ je deterministický konečný automat s množinou stavů $Q$. Definujte jeho přechodovou funkci $\delta$ tak, aby přijímal jazyk:
   $$L(A) = \{w \in \Sigma^* \mid w \text{ obsahuje nějaké } s \in S \text{ (jako podslovo)}\}$$
3. Sestrojte deterministický konečný automat přijímající jazyk:
   $$\{w \in \{0, 1\}^* \mid w \text{ obsahuje } 010 \text{ nebo končí na } 10\}$$

> **Tvé řešení 6:**
> 
> *(a) Definice $L(A)$ a rozšířené přechodové funkce $\delta^*$:*
> 
> *(b) Definice přechodové funkce $\delta$ pro podslova z množiny prefixů $Q$:*
> 
> *(c) Konstrukce DFA pro jazyk (stavy, přechody, přijímající stavy):*
> 

---

## Úloha 7: Porovnání modulárních hashů (MFF termín Jaro 2026 – 2. 2. 2026)

*Zdroj: [jaro-2026.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2026.pdf) (Úloha 1)*

Mějme dané prvočíslo $p \ge 2$. Pro slovo $w \in \{0, 1\}^*$ nechť $h(w)$ je zbytek modulo $p$ z nezáporného celého čísla, jehož binární reprezentace je $w$, přičemž povolujeme úvodní nuly. Přesněji, definujeme funkci $h: \{0, 1\}^* \to \{0, 1, \dots, p - 1\}$ následovně:
$$h(w) = \left( \sum_{i=1}^{|w|} w_i 2^{|w|-i} \right) \bmod p$$
kde $w = w_1 w_2 \cdots w_{|w|}$ a $w_i \in \{0, 1\}$. (Pro prázdné slovo je tedy $h(\varepsilon) = 0$.)

Nyní uvažte následující jazyk nad abecedou $\Sigma = \{0, 1, \#\}$:
$$L_p = \{u \# v \mid u, v \in \{0, 1\}^* \text{ a platí } h(u) = h(v)\}$$

1. Uveďte formální definici *deterministického konečného automatu (DFA)*.
2. Formálně popište konstrukci DFA $A_p$, který rozpoznává jazyk $L_p$, v závislosti na parametru $p$.
3. Nakreslete stavový diagram automatu $A_2$ (rozpoznávajícího jazyk $L_2$).

> **Tvé řešení 7:**
> 
> *(a) Formální definice DFA:*
> 
> *(b) Konstrukce DFA $A_p$ pro obecné prvočíslo $p$:*
> 
> *(c) Stavový diagram nebo tabulka přechodů pro $A_2$ ($p = 2$):*
> 

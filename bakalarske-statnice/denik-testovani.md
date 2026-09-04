# Deník testování a studijních bloků (MFF UK)

Tento soubor slouží k trackování časů strávených opakováním v `cheat-sheet.md`, pauz mezi bloky a výsledků následných testů.

---

## 📊 Souhrnná tabulka testů

| # | Datum | Předmět / Téma | Čas učení | Pauza | Čas testu | Skóre / Hodnocení | Hlavní zjištění a mezery |
|---|---|---|:---:|:---:|:---:|:---:|---|
| 1 | 4. 9. 2026 | Lineární algebra (Lingebra) | 75 min | 24 min | 47 min | **7,7 / 10 (77 %)** | Pozor na nenulovost ($v \ne 0, x \ne 0$), absolutní hodnotu u Cauchy-Schwarze, $\langle u \mid u \rangle \ge 0$ a numeriku dimenzí ($6-3=3$). |
| 2 | 4. 9. 2026 | Matematická analýza | 120 min | 44 min | 90 min | **6,85 / 10 (69 %)** *(přísně)* | Rozdíl limita vs. spojitost ($L$ vs. $f(x_0)$), 2× l'Hospital za sebou pro $0/0$, per partes člen $[uv]_a^b$. |

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

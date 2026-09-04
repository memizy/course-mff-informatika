# Deník testování a studijních bloků (MFF UK)

Tento soubor slouží k trackování časů strávených opakováním v `cheat-sheet.md`, pauz mezi bloky a výsledků následných testů.

---

## 📊 Souhrnná tabulka testů

| # | Datum | Předmět / Téma | Čas učení | Pauza | Čas testu | Skóre / Hodnocení | Hlavní zjištění a mezery |
|---|---|---|:---:|:---:|:---:|:---:|---|
| 1 | 4. 9. 2026 | Lineární algebra (Lingebra) | 75 min | 24 min | 47 min | **7,7 / 10 (77 %)** | Pozor na nenulovost ($v \ne 0, x \ne 0$), absolutní hodnotu u Cauchy-Schwarze, $\langle u \mid u \rangle \ge 0$ a numeriku dimenzí ($6-3=3$). |
| 2 | 4. 9. 2026 | Matematická analýza | 120 min | *probíhá* | *čeká se* | – | *Probíhá pauza před testem* |

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
* **Předmět:** Matematická analýza (posloupnosti, řady, limity funkcí, spojitost, derivace a věty o střední hodnotě, l'Hospital & průběh, Taylorův polynom, integrály a aplikace).
* **Čas učení:** **120 minut** (dokončeno v ~18:00)
* **Doporučená pauza:** **25–30 minut** (do ~18:30)
* **Režim testu:** **Režim A (Matematika)** – psaní na papír bez nahlížení do taháku.
* **Test:** *(Bude připraven v testy/)*

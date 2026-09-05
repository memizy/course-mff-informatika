# Rozbor Testu 4: Algoritmy a datové struktury (Vyhodnocení a vzorová řešení)

* **Datum:** 5. 9. 2026
* **Doba psaní:** ~120 minut (včetně pauz a psaní)
* **Hodnocení:**
  * **Mírnější (průběžné) hodnocení:** **8,25 / 10 bodů (83 % – známka 2 / Velmi dobře)**
  * **Přísné zkouškové hodnocení MFF:** **7,65 / 10 bodů (77 % – známka 2 / Velmi dobře)**
* **Výchozí test:** [test-04-ads.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-04-ads.md)

---

## 📊 Rychlý přehled výsledků

| Otázka | Téma | Mírně | Přísně MFF | Hlavní zjištění |
|:---:|---|:---:|:---:|---|
| **1** | RAM model a Landauova notace | 1,0 | 0,95 | Skvěle jednotková/logaritmická cena i limity podílů pro $2^{n+1}$ a $2^{2n}$. |
| **2** | Master Theorem a aplikace | 0,8 | 0,7 | Aplikace bezchybné ($n^2, n^{1.58}, n^2$); u rovnovážného případu omylem napsáno $n^c \cdot n^{\log_b a}$ místo $n^c \log n$. |
| **3** | BVS a mazání se dvěma syny | 0,85 | 0,8 | Invariant a symetrický následník výborně; chyběl termín *In-order* průchod (uvedeno jen obecné DFS). |
| **4** | AVL stromy a vyvažování | 1,0 | 1,0 | Bezchybný invariant $|h(L)-h(R)| \le 1$, hloubka $\mathcal{O}(\log n)$ i LR rotace s kořenem 7. |
| **5** | Quicksort a skoromedián | 0,9 | 0,85 | Skoromedián i lemma o džbánu super; zapomenuto uvést, kdy nastává nejhorší případ (extrémní pivot). |
| **6** | Dolní mez třídění a Counting Sort | 0,65 | 0,55 | Rozhodovací strom výborně; chybné vysvětlení chytáku u Counting Sortu (neporušuje mez, protože *neporovnává*, ale indexuje). |
| **7** | Grafy (BFS, DFS a klasifikace hran) | 0,75 | 0,65 | Fronta a cyklus přes zpětné hrany správně; zapomenuty *stromové hrany* a u topologie neupřesněno obrácené pořadí. |
| **8** | Dijkstra vs. Bellman-Ford | 0,8 | 0,75 | Nezápornost, protipříklad i Bellman-Ford bezchybně; zapomenuta složitost Dijkstry $\mathcal{O}((V+E)\log V)$. |
| **9** | Minimální kostra (Jarník vs. Kruskal) | 0,5 | 0,4 | Řezové pravidlo správně; chybí struktura *Union-Find* a vysvětlení, proč je Jarník polem $\mathcal{O}(n^2)$ lepší pro husté grafy. |
| **10** | Třídy P, NP a NP-úplnost | 1,0 | 1,0 | Perfektní polynomiální verifikátor, definice NPC i správný směr redukce $A \le_P B$ přes tranzitivitu. |
| **CELKEM** | | **8,25** | **7,65** | **Úspěšnost 77 % (zkouška bezpečně splněna na Velmi dobře)** |

---

## 🔍 Detailní rozbor s přesnými vzorovými řešeními

### 1. Model RAM a Landauova notace
* **Zadání:** Jednotková vs. logaritmická cena. Omezení na strojové slovo $w$. Rozhodněte o $2^{n+1} \in \mathcal{O}(2^n)$ a $2^{2n} \in \mathcal{O}(2^n)$.
* **Odpověď studenta:**
  * Jednotková cena: operace stojí $\mathcal{O}(1)$. Logaritmická: cena odpovídá délce čísla v bitech.
  * Omezení slova: do buňky se vejde maximálně $\mathcal{O}(\log n)$ bitů.
  * $2^{n+1} = 2 \cdot 2^n \le 3 \cdot 2^n \implies \in \mathcal{O}(2^n)$ pro $c=3, n_0=1$.
  * $2^{2n} / 2^n = 2^n \to +\infty \implies \notin \mathcal{O}(2^n)$.
* **Hodnocení:** **1,0 b (přísně 0,95 b)** – Vynikající, formálně přesně zdůvodněné konstantami i limitou.

---

### 2. Master Theorem (Kuchařková věta)
* **Zadání:** Znění Master Theoremu a určení složitosti pro 3 rekurence.
* **Odpověď studenta:**
  * Podmínky: $a \ge 1, b > 1, c \ge 0$.
  * Případy: pro $< 1: \mathcal{O}(n^c)$, pro $> 1: \mathcal{O}(n^{\log_b a})$, pro $= 1: \mathcal{O}(n^c \cdot n^{\log_b a})$.
  * Aplikace: $T_1 = \mathcal{O}(n^2), T_2 = \mathcal{O}(n^{\log_2 3}) \approx \mathcal{O}(n^{1.58}), T_3 = \mathcal{O}(n^2)$.
* **Hodnocení:** **0,8 b (přísně 0,7 b)**
  * ✅ Všechny 3 konkrétní aplikace $T_1, T_2, T_3$ jsou **100% správně**.
  * ⚠️ **Chyba ve znění 1. případu:** Napsal jsi $n^c \cdot n^{\log_b a}$. To by znamenalo $n^{2c}$!
* 🎯 **Přesné znění 1. případu (rovnováha):**
  Když $\frac{a}{b^c} = 1 \iff c = \log_b a$, pak:
  $$T(n) = \mathbf{\Theta(n^c \log n)} = \mathbf{\Theta(n^{\log_b a} \log n)}$$
  *(Poznámka: Master Theorem dává těsnou mez $\Theta$, nikoli jen $\mathcal{O}$).*

---

### 3. Binární vyhledávací stromy (BVS) a mazání
* **Zadání:** Invariant BVS, seřazený průchod. Delete(x) se 2 syny. Nejhorší případ operace Find.
* **Odpověď studenta:**
  * Invariant: pro levý podstrom $k(u) < k(v)$, pro pravý $k(w) > k(v)$.
  * Průchod: DFS v čase $\mathcal{O}(n)$.
  * Delete(x): vybere nejlevějšího náhradníka z pravého podstromu, vloží místo $x$ a jeho původního syna napojí na otce.
  * Nejhorší případ: degenerace na řetízek, čas $\mathcal{O}(n)$.
* **Hodnocení:** **0,85 b (přísně 0,8 b)**
  * ✅ Invariant, náhradník (symetrický následník) i degenerace na řetízek jsou **naprosto přesně**.
  * ⚠️ **Chybějící termín:** Napsal jsi obecně *DFS*. Na MFF se striktně vyžaduje název **In-order průchod** (průchod v pořadí: Levý podstrom $\to$ Kořen $\to$ Pravý podstrom).

---

### 4. AVL stromy a vyvažování
* **Zadání:** Invariant hloubkového vyvážení, maximální hloubka, rotace pro 10 -> vlevo 4 -> vpravo 7.
* **Odpověď studenta:**
  * Invariant: pro všechny vrcholy se hloubka levého a pravého podstromu liší max o 1.
  * Hloubka: maximálně $\mathcal{O}(\log n)$.
  * Rotace: vyzdvihnout 7 do kořene, jedná se o LR rotaci.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – Perfektní a bezchybné.

---

### 5. Quicksort a průměrná složitost
* **Zadání:** Složitosti, kdy nastává nejhorší případ. Skoromedián a lemma o džbánu. Proč nelze Master Theorem přímo.
* **Odpověď studenta:**
  * Složitosti: nejhorší $\mathcal{O}(n^2)$, průměrná $\mathcal{O}(n \log n)$.
  * Skoromedián: pravděpodobnost $1/2$ padnout do $(25\%, 75\%)$, průměrná hloubka $2 \log_{4/3} n \implies \mathcal{O}(n \log n)$.
  * Master Theorem: nelze použít, dělení musí být vždy stejné, což zde není.
* **Hodnocení:** **0,9 b (přísně 0,85 b)**
  * ✅ Skoromedián, lemma o džbánu (faktor 2) i nemožnost použít Master Theorem pro asymetrické dělení jsou **výborně zdůvodněné**.
  * ⚠️ Zapomněl jsi dopsat, **kdy nastává nejhorší případ:** nastává při volbě extrémního pivota (minimum/maximum v každém kroku), např. na již setříděném poli při volbě prvního prvku.

---

### 6. Dolní mez porovnávacího třídění a model rozhodovacího stromu
* **Zadání:** Věta o dolní mezi. Model rozhodovacího stromu ($L \ge n!$). Proč Counting Sort $\mathcal{O}(n+K)$ neporušuje tuto mez?
* **Odpověď studenta:**
  * Libovolný třídicí algoritmus zvládne třídění nejlépe v čase $\Omega(n \log n)$ v nejhorším případě.
  * Strom má alespoň $n!$ listů (počet permutací), hloubka alespoň $\log_2(n!)$. Listy = uspořádání, uzly = porovnání.
  * *„Protože K není nijak omezené může být v nejhorším případě libovolně velké tedy např. $\Omega(n^2)$.“*
* **Hodnocení:** **0,65 b (přísně 0,55 b)**
  * ⚠️ V úvodní větě chybí klíčové slovo **porovnávací** (pro neporovnávací třídění mez neplatí!).
  * ⚠️ **Zkouškový chyták u Counting Sortu:** Tvá odpověď o neomezeném $K$ míjí podstatu. I kdyby $K = \mathcal{O}(n)$ (čísla od 1 do $n$), Counting Sort seřadí pole v čase $\mathcal{O}(n)$ (lineárně, tedy rychleji než $\Omega(n \log n)$!).
* 🎯 **Správné vysvětlení pro zkoušejícího:**
  Counting Sort **neporušuje dolní mez**, protože **není porovnávacím algoritmem**! Vůbec neprovádí porovnání prvků mezi sebou ($A[i] \le A[j]$), ale používá hodnoty prvků přímo jako **adresy (indexy) do pomocného pole četností**. Využívá tedy vlastnost paměti RAM modelu s přímým adresováním.

---

### 7. Prohledávání grafu (BFS vs. DFS) a klasifikace hran
* **Zadání:** Datová struktura BFS, 4 typy hran DFS a detekce cyklu, topologické uspořádání.
* **Odpověď studenta:**
  * Fronta, nejkratší cesty.
  * Typy hran: dopředné, zpětné (detekují cykly), příčné.
  * Topologické uspořádání: podle času $out(v)$, kdy je DFS uzavřelo.
* **Hodnocení:** **0,75 b (přísně 0,65 b)**
  * ✅ Fronta, nejkratší cesty a detekce cyklu přes zpětné hrany správně.
  * ⚠️ Vyjmenoval jsi jen 3 typy hran, zapomněl jsi na základní: **stromové hrany** (hrany prohledávacího stromu).
  * ⚠️ U topologického uspořádání musí být uvedeno **obrácené (sestupné) pořadí** časů $out(v)$ (od nejvyššího po nejnižší).

---

### 8. Nejkratší cesty (Dijkstra vs. Bellman-Ford)
* **Zadání:** Předpoklady Dijkstry a složitost s binární haldou. Protipříklad se zápornou hranou. Bellman-Ford a detekce záporného cyklu.
* **Odpověď studenta:**
  * Nezáporné váhy, jinak se zacyklí/neoptimální. Nákres protipříkladu.
  * Bellman-Ford: složitost $\mathcal{O}(m \cdot n)$. Detekce cyklu: pokud se v $n$-tém kroku cena cesty sníží.
* **Hodnocení:** **0,8 b (přísně 0,75 b)**
  * ✅ Nezápornost, protipříklad i Bellman-Ford s $|V|$-tým krokem relaxace jsou **výborně**.
  * ⚠️ Zapomněl jsi napsat složitost Dijkstry: **$\mathcal{O}((V + E) \log V)$** resp. **$\mathcal{O}(m \log n)$**.

---

### 9. Minimální kostra grafu (MST)
* **Zadání:** Řezové pravidlo. Kruskal vs. Jarník (struktura na cykly, složitost, který pro husté grafy $m = \Theta(n^2)$).
* **Odpověď studenta:**
  * Řezové pravidlo: kostra obsahuje hranu řezu s nejmenší vahou.
  * Pro husté grafy lepší Jarník na Fibonacciho haldě se složitostí $m \log n$, Kruskal má $m \log n$.
  * Cykly detekuje procházením vrcholů stromů lesa.
* **Hodnocení:** **0,5 b (přísně 0,4 b)**
  * ✅ Myšlenka řezového pravidla v pořádku.
  * ⚠️ **Závažná mezera u Kruskala:** Datová struktura na detekci cyklů je **Union-Find (Disjoint-Set Union / rozkladové množiny)** s operacemi `Find` a `Union`!
  * ⚠️ **Složitosti a husté grafy:** Napsal jsi u obou $m \log n$, čímž jsi nevysvětlil, proč je Jarník lepší.
* 🎯 **Vzorové vysvětlení pro zkoušejícího:**
  * **Kruskalův algoritmus:** Vyžaduje nejprve setřídit všechny hrany $\implies \mathcal{O}(E \log E) = \mathcal{O}(m \log n)$. Detekci cyklů provádí přes **Union-Find** v čase $\mathcal{O}(m \cdot \alpha(n))$.
  * **Jarníkův algoritmus:** Pro velmi husté grafy ($m = \Theta(n^2)$) jej implementujeme **obyčejným polem** (bez jakékoliv haldy!), kdy v každém kroku najdeme minimum z pole v čase $\mathcal{O}(n)$. Celkový čas je **$\mathcal{O}(n^2) = \mathcal{O}(m)$**, což je **lineární vzhledem k počtu hran** (výrazně rychlejší než Kruskal, který musí třídit a má faktor $\log n$).

---

### 10. Složitostní třídy P, NP a NP-úplnost
* **Zadání:** Definice NP přes verifikátor. Definice NP-úplnosti. Směr redukce $A \le_P B$ vs. $B \le_P A$.
* **Odpověď studenta:**
  * $L \in NP \iff \exists y$ (certifikát polynomiální délky), $\exists V \in P: L(x) = 1 \iff V(x, y) = 1$.
  * NP-úplnost: je v NP a zároveň NP-těžký (lze na něj převést libovolný problém z NP).
  * Směr redukce: Musíme sestrojit $A \le_P B$, protože když umíme vše z NP převést na $A$, díky tranzitivitě to umíme převést i na $B$.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – Naprosto perfektní, učebnicová odpověď včetně tranzitivity!

---

## 📌 Co si ihned zapsat do `chyby.md`:

> **Algoritmy a datové struktury – Zkouškové chytáky:**
> 1. **Counting Sort vs. Dolní mez:** Counting Sort $\mathcal{O}(n + K)$ neporušuje dolní mez $\Omega(n \log n)$, protože **není porovnávací algoritmus** (využívá adresování do paměti RAM modelu).
> 2. **Kruskal a Union-Find:** Detekci cyklů v Kruskalově algoritmu provádí struktura **Union-Find** (komprese cest + váhové sjednocení), nikoliv procházení lesa.
> 3. **Husté grafy a Jarník:** Pro $m = \Theta(n^2)$ se Jarník implementuje **obyčejným polem**, čímž dosáhne času $\mathcal{O}(n^2) = \mathcal{O}(m)$ (lineární k hranám, poráží Kruskala o faktor $\log n$).
> 4. **Master Theorem (rovnováha):** Pro $\frac{a}{b^c} = 1$ je složitost $\Theta(n^c \log n)$ (nikoli $n^c \cdot n^{\log_b a}$).
> 5. **BVS seřazený výpis:** Vzestupné seřazení prvků v čase $\Theta(n)$ provádí **In-order průchod** (Levý $\to$ Kořen $\to$ Pravý).
> 6. **Topologické uspořádání:** Odpovídá **obrácenému (sestupnému)** pořadí časů opuštění $out(v)$ z DFS.

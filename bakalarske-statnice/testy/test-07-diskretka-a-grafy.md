# Test 7: Diskrétní matematika a teorie grafů (Kompletní zkouškový průřez)

* **Datum zadání:** 7. 9. 2026
* **Rozsah:** 11 ucelených zkouškových úloh (6 přesných autentických úloh ze všech dostupných termínů MFF UK včetně J 2023 + 5 klíčových teoretických a aplikačních úloh pokrývajících zbývající stěžejní témata sylabu).
* **Styl zadání:** Reálná zkoušková zadání MFF UK bez napovídání metod řešení.
* **Instrukce:** Do připravených bloků `> **Tvé řešení:**` piš přímo své postupy, důkazy a výsledky.

---

# ČÁST 1: Všechny minulé úlohy ze státnicových termínů MFF UK v přesném znění

---

## Úloha 1: Souvislost grafů a Mengerova věta (MFF termín Podzim 2023 – 14. 9. 2023)

Mějme graf $G$ na 64 vrcholech, přičemž jeho vrcholy jsou označeny různými šesticemi nul a jedniček (tedy prvky $\{0, 1\}^6$). Hrany tvoří:
* vrcholy, které se liší pouze v první souřadnici, např. `111010` a `011010` (tyto hrany tvoří perfektní párování),
* vrcholy, které mají první dva znaky totožné, např. `111010` a `110001`, a také
* dvojice vrcholů (`111010`, `101100`), (`101100`, `010110`) a (`010110`, `111011`).

Jiné dvojice vrcholů spojeny nejsou.

1. **(a)** Vyslovte Mengerovu větu (o vrcholové souvislosti a řezech) včetně formálního zavedení potřebných pojmů.
2. **(b)** Určete, kolik hranově disjunktních cest vede mezi vrcholy `000000` a `111111`.
3. **(c)** Nalezněte nejmenší hranový řez a nejmenší vrcholový řez oddělující `000000` a `111111`.

> **Tvé řešení 1:**
> 
> *(a) Mengerova věta a definice potřebných pojmů:*
> 
> *(b) Počet hranově disjunktních cest mezi 000000 a 111111:*
> 
> *(c) Nejmenší hranový řez a nejmenší vrcholový řez oddělující 000000 a 111111:*
> 

---

## Úloha 2: Barevnost grafů (MFF termín Podzim 2024 – 3. 9. 2024)

1. **(a)** Definujte, co je barevnost grafu.
2. **(b)** Jaké platí omezení pro barevnosti rovinných grafů?
3. **(c)** Určete barevnost grafu na obrázku níže.

![Barevnost grafu](file:///C:/Users/nagyl/.gemini/antigravity-ide/brain/1c803353-10ab-4be8-afdd-ba161f4762a7/podzim-2024-graf-barevnost.png)

*(Poznámka k topologii grafu na obrázku: Graf má 10 vrcholů $a, b, c, d, e, f, g, h, i, j$. Centrální uzel $a$ tvoří kolo s 5-cyklem $b-c-d-e-f-b$, tedy $a$ sousedí se všemi vrcholy $\{b, c, d, e, f\}$. Dále zespodu navazují vrcholy $g, h, i, j$: hrany $\{f, g\}, \{g, h\}, \{f, h\}, \{h, i\}, \{e, i\}, \{e, j\}, \{i, j\}$).*

> **Tvé řešení 2:**
> 
> *(a) Definice barevnosti grafu:*
> 
> *(b) Omezení pro barevnosti rovinných grafů:*
> 
> *(c) Určení barevnosti zadaného grafu a zdůvodnění (horní i dolní odhad):*
> 

---

## Úloha 3: Eulerovské grafy (MFF termín Jaro 2025 – 4. 2. 2025)

Nechť $n$ je přirozené číslo větší než 1. Definujeme graf $G_n$ takto: jeho vrcholy jsou všechny množiny $A \subset \{1, \dots, n\}$, pro něž platí $|A| < n$. Dvě (různé) z nich jsou spojeny hranou právě tehdy, když jsou disjunktní ($A \cap B = \emptyset$).

Například pro $n = 3$ dostaneme tento graf:

![Eulerovský graf pro n=3](file:///C:/Users/nagyl/.gemini/antigravity-ide/brain/1c803353-10ab-4be8-afdd-ba161f4762a7/jaro-2025-graf-euler.png)

1. **(a)** Pro která $n > 1$ je graf $G_n$ souvislý?
2. **(b)** Nechť $A \subset \{1, \dots, n\}$ je množina velikosti menší než $n$. Jaký je stupeň vrcholu, který odpovídá množině $A$? (Závisí nějak na velikosti množiny $A$, na $n$, nebo případně na něčem jiném)?
3. **(c)** Formulujte, co znamená pojem eulerovský graf a rozhodněte, pro která $n > 1$ je graf $G_n$ eulerovský?

Odpovědi přiměřeně zdůvodněte.

> **Tvé řešení 3:**
> 
> *(a) Souvislost grafu $G_n$ v závislosti na $n > 1$:*
> 
> *(b) Stupeň vrcholu odpovídajícího množině $A$:*
> 
> *(c) Definice pojmu eulerovský graf a rozhodnutí, pro která $n > 1$ je $G_n$ eulerovský:*
> 

---

## Úloha 4: Rovinné grafy – triangulace a stupně (MFF termín Jaro 2026 – 2. 2. 2026)

1. **(a)** Uveďte Eulerovu formuli pro rovinné grafy (o počtu vrcholů, hran a stěn).
2. **(b)** Uvažujme vrcholově 2-souvislý rovinný graf, který má rovinné nakreslení, jehož každá vnitřní stěna je trojúhelník (je ohraničena kružnicí $C_3$), vnější stěna může, ale nemusí být ohraničená $C_3$. Jaký je minimální a maximální počet hran takového grafu, pokud víme, že má $n \ge 3$ vrcholů? Odpověď přiměřeně zdůvodněte.
3. **(c)** Rozhodněte, pro která $n \in \mathbb{N}$ existuje rovinný graf s $2n$ vrcholy takový, že $n$ z nich má stupeň 3 a zbývajících $n$ má stupeň 4. Odpověď přiměřeně zdůvodněte.

> **Tvé řešení 4:**
> 
> *(a) Znění Eulerovy formule:*
> 
> *(b) Minimální a maximální počet hran pro $n \ge 3$ s trojúhelníkovými vnitřními stěnami:*
> 
> *(c) Existence rovinného grafu s $n$ vrcholy stupně 3 a $n$ vrcholy stupně 4:*
> 

---

## Úloha 5: Rovinné grafy – komponenty a grafy bez trojúhelníků (MFF termín Jaro 2023 – 3 body)

1. **(a)** Uveďte Eulerovu formuli pro rovinné grafy (o počtu vrcholů, hran a stěn).
2. **(b)** Rozhodněte, zdali může existovat rovinný graf $G$ na 40 vrcholech s 80 hranami a 5 komponentami souvislosti takový, že neobsahuje $C_3$ jako podgraf.
3. **(c)** Určete, jaký nejvyšší možný počet hran může mít rovinný graf, který má 40 vrcholů, 5 komponent souvislosti a neobsahuje $C_3$ jako podgraf.

> **Tvé řešení 5:**
> 
> *(a) Znění Eulerovy formule:*
> 
> *(b) Existence rovinného grafu na 40 vrcholech, s 80 hranami, 5 komponentami a bez $C_3$:*
> 
> *(c) Nejvyšší možný počet hran takového grafu (včetně odvození/zdůvodnění):*
> 

---

## Úloha 6: Binární relace a ekvivalence (MFF termín Podzim 2025 – 8. 9. 2025)

1. **(a)** Definujte podmínky, které musí splňovat binární relace $R$ na neprázdné množině $X$, aby byla ekvivalencí. Podmínky formulujte pomocí matematických zápisů s použitím logických spojek, kvantifikátorů a podobně.
2. **(b)** Pro $X = \{a, b, c, d\}$ určete, kolik různých ekvivalencí na množině $X$ existuje.
3. **(c)** Pro $X = \{a, b, c, d\}$ najděte příklad binární relace, která je tranzitivní, ale není symetrická ani (slabě) antisymetrická. Zdůvodněte, že nalezená relace má požadované vlastnosti.
*(Poznámka: Antisymetrií míníme $\forall x, y \in X: ((x, y) \in R \land (y, x) \in R) \implies x = y$.)*

> **Tvé řešení 6:**
> 
> *(a) Formální definice ekvivalence (pomocí kvantifikátorů):*
> 
> *(b) Počet různých ekvivalencí na množině o 4 prvcích (včetně rozpadu):*
> 
> *(c) Příklad relace (tranzitivní, nesymetrická, neantisymetrická) a zdůvodnění:*
> 

---

# ČÁST 2: Klíčová teorie ze sylabu a doplňující zkouškové otázky

---

## Úloha 7: Toky v sítích a Věta o maximálním toku a minimálním řezu

1. **(a)** Definujte pojem **toková síť** $(V, E, z, s, c)$, pojem **tok v síti** $f$ (formulujte přesně kapacitní omezení a Kirchhoffův zákon zachování toku pro vnitřní uzly) a definujte **velikost toku** $w(f)$.
2. **(b)** Definujte pojem **řez v síti** a **kapacitu řezu**. Zformulujte **Větu o maximálním toku a minimálním řezu** (Max-Flow Min-Cut Theorem).
3. **(c) Doplňující úloha:** Mějme síť se zdrojem $z$, spotřebičem $s$ a vnitřními uzly $\{a, b, c, d\}$. Kapacity orientovaných hran jsou zadány následovně:
   * $c(z, a) = 10, \quad c(z, b) = 10$
   * $c(a, b) = 2, \quad c(a, c) = 4, \quad c(a, d) = 8$
   * $c(b, d) = 9$
   * $c(c, s) = 10, \quad c(d, s) = 10$
   
   Určete velikost maximálního toku $w(f_{\max})$ a nalezněte konkrétní minimální řez $R = (A, B)$ (kde $z \in A, s \in B$), který tuto kapacitu realizuje.

> **Tvé řešení 7:**
> 
> *(a) Definice tokové sítě, toku a velikosti toku:*
> 
> *(b) Definice řezu, kapacity a formulace věty Max-Flow Min-Cut:*
> 
> *(c) Výpočet maximálního toku a určení minimálního řezu v zadané síti:*
> 

---

## Úloha 8: Stromy a jejich ekvivalentní charakteristiky

1. **(a)** Definujte pojem **strom**. Uveďte alespoň **4 vzájemně ekvivalentní charakteristiky** stromu pro graf $G = (V, E)$ s $|V| = n$.
2. **(b) Doplňující úloha:** Dokažte formálně (např. pomocí principu sudosti / součtu stupňů, nebo indukcí / nejdelší cestou), že každý konečný strom s alespoň dvěma vrcholy ($n \ge 2$) má **alespoň dva listy** (vrcholy stupně 1).

> **Tvé řešení 8:**
> 
> *(a) Definice stromu a 4 ekvivalentní charakteristiky:*
> 
> *(b) Důkaz existence alespoň dvou listů pro $n \ge 2$:*
> 

---

## Úloha 9: Princip inkluze a exkluze (PIE) a problém šatnářky

1. **(a)** Zformulujte obecnou větu o **Principu inkluze a exkluze** pro systém konečných množin $A_1, A_2, \dots, A_n$ (vzorec pro velikost sjednocení $|\bigcup_{i=1}^n A_i|$). Stručně vysvětlete myšlenku důkazu (jakým celkovým příspěvkem se do pravé strany započítá libovolný prvek $x$, který náleží do právě $k$ množin z tohoto systému).
2. **(b) Doplňující úloha:**
   * Definujte pojem **pevný bod** permutace $\pi \in S_n$.
   * Pomocí principu inkluze a exkluze odvoďte vzorec pro počet permutací bez pevného bodu $D_n$ (tzv. problém šatnářky / derangements) na množině $\{1, 2, \dots, n\}$.
   * Spočítejte přesné číslo $D_5$ (počet permutací bez pevného bodu pro $n = 5$).

> **Tvé řešení 9:**
> 
> *(a) Formulace PIE a myšlenka důkazu:*
> 
> *(b) Odvození vzorce pro počet permutací bez pevného bodu $D_n$ a výpočet $D_5$:*
> 

---

## Úloha 10: Hallova věta o systému různých reprezentantů (SRR)

1. **(a)** Nechť $\mathcal{M} = (M_1, M_2, \dots, M_n)$ je systém podmnožin konečné množiny $X$. Definujte pojem **systém různých reprezentantů (SRR)** pro tento systém.
2. **(b)** Vyslovte **Hallovu větu** (podmínku nutnou a postačující pro existenci SRR).
3. **(c) Doplňující úloha:** Rozhodněte, zda existuje systém různých reprezentantů pro následující systém množin nad $X = \{1, 2, 3, 4, 5, 6\}$:
   $$M_1 = \{1, 2\}, \quad M_2 = \{2, 3\}, \quad M_3 = \{1, 3\}, \quad M_4 = \{1, 2, 3\}, \quad M_5 = \{3, 4, 5\}$$
   Pokud SRR existuje, explicitně jej zadejte (který prvek reprezentuje kterou množinu). Pokud neexistuje, nalezněte konkrétní podmnožinu indexů $I \subseteq \{1, 2, 3, 4, 5\}$, která porušuje Hallovu podmínku.

> **Tvé řešení 10:**
> 
> *(a) Definice systému různých reprezentantů (SRR):*
> 
> *(b) Znění Hallovy věty (Hallova podmínka):*
> 
> *(c) Vyšetření existence SRR pro zadaný systém množin:*
> 

---

## Úloha 11: Částečná uspořádání (Posety), extrémy a Věta o dlouhém a širokém

1. **(a)** Definujte pojem **částečně uspořádaná množina (poset)** $(X, \le)$.
2. **(b)** Vysvětlete formální rozdíl mezi **nejmenším prvkem** a **minimálním prvkem** posetu (definujte oba pojmy pomocí predikátové logiky / kvantifikátorů).
3. **(c)** Definujte pojmy **řetězec**, **antiřetězec**, **výška** a **šířka** posetu a vyslovte **Větu o dlouhém a širokém posetu**.
4. **(d) Doplňující úloha:** Mějme množinu $X = \{1, 2, 3, 4, 6, 8, 12, 24\}$ uspořádanou relací dělitelnosti ($a \le b \iff a \mid b$):
   * Určete všechny minimální prvky, všechny maximální prvky, a rozhodněte, zda existuje nejmenší a největší prvek posetu $(X, \mid)$.
   * Určete výšku posetu (najděte maximální řetězec) a šířku posetu (najděte maximální antiřetězec).

> **Tvé řešení 11:**
> 
> *(a) Definice posetu:*
> 
> *(b) Rozdíl mezi nejmenším a minimálním prvkem (formální zápisy):*
> 
> *(c) Definice řetězce, antiřetězce, výšky, šířky a znění Věty o dlouhém a širokém:*
> 
> *(d) Analýza posetu dělitelnosti na množině $X$:*
> 

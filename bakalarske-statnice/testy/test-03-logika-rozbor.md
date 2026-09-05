# Rozbor Testu 3: Matematická logika (Vyhodnocení a vzorová řešení)

* **Datum:** 5. 9. 2026
* **Doba psaní:** ~70 minut
* **Hodnocení:**
  * **Mírnější (průběžné) hodnocení:** **8,1 / 10 bodů (81 % – známka 2 / Velmi dobře)**
  * **Přísné zkouškové hodnocení MFF:** **7,5 / 10 bodů (75 % – známka 2 / Velmi dobře)**
* **Výchozí test:** [test-03-logika.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-03-logika.md)

---

## 📊 Rychlý přehled výsledků

| Otázka | Téma | Mírně | Přísně MFF | Hlavní zjištění |
|:---:|---|:---:|:---:|---|
| **1** | Dosah, volné proměnné a PNF | 0,7 | 0,6 | Proměnné i dosah výborně; chyba v negaci implikace ($\neg A \lor B$, ne $\neg B$) a kvantifikátor nevytknut do prefixu. |
| **2** | Analýza teorií nad $\mathbb{P}$ | 1,0 | 1,0 | Naprosto bezchybné ($256$ teorií, $8$ kompletních, $4$ modely $\implies$ nekompletní). |
| **3** | Tablo metoda ve výrokové logice | 1,0 | 1,0 | Perfektní, čistý tablo důkaz s uzavřením obou větví sporem $\times$. |
| **4** | Tablo v predikátové logice | 0,8 | 0,7 | Skvělé rozpoznání typu Všichni u obou pravidel; v zápisu míchána negace do položek tabla. |
| **5** | Skolemizace a ekvisplnitelnost | 0,75 | 0,65 | Skolemovy funkce i konstanty bezchybně; závažný omyl v definici ekvisplnitelnosti („platí ve stejných modelech“). |
| **6** | Konzervativní extenze | 0,9 | 0,85 | Přesná formální definice $Csq(T') \cap VF_L = Csq(T)$ i správné ANO. |
| **7** | Věta o kompaktnosti | 0,45 | 0,35 | Chyba v kvantifikaci důsledku (platí v *nějaké* konečné, ne v *každé*); nedotažený důkaz konečnosti. |
| **8** | Łoś-Vaughtovo kritérium | 0,6 | 0,5 | Záměna „nemá konečné modely“ za „nekonečná teorie“; překlep v pojmu kategorická. |
| **9** | Zlatá věta o rozhodnutelnosti | 0,9 | 0,85 | Věta i myšlenka paralelního prohledávání důkazů sporem správně. |
| **10** | Hranice rozhodnutelnosti | 1,0 | 1,0 | Brilantní a výstižné zdůvodnění přes prvočísla, kódování programů a simulaci TM. |
| **CELKEM** | | **8,1** | **7,5** | **Úspěšnost 75 % (zkouška bezpečně splněna)** |

---

## 🔍 Detailní rozbor s přesnými vzorovými řešeními

### 1. Dosah kvantifikátoru, volné proměnné a převod do PNF
* **Zadání:** $\varphi: (\forall x) P(x) \to Q(x, y)$. Určete vázané/volné proměnné, generální uzávěr a převeďte do PNF.
* **Odpověď studenta:**
  * Výskyt v $P(x)$ vázaný, výskyty $x, y$ v $Q(x, y)$ volné.
  * $GU: (\forall x)(\forall y)(P(x) \to Q(x, y))$.
  * PNF: $(\forall z) P(z) \to Q(x, y) \sim \neg(\forall z)P(z) \lor \neg Q(x, y) \sim \exists z \neg P(z) \lor \neg Q(x, y)$.
* **Hodnocení:** **0,7 b (přísně 0,6 b)**
  * ✅ Rozpoznání dosahu a volných proměnných je **naprosto správné**.
  * ⚠️ V generálním uzávěru chyběl vnitřní kvantifikátor: má být $(\forall x)(\forall y)\big((\forall x)P(x) \to Q(x, y)\big)$.
  * ⚠️ **Chyba v převodu implikace:** $A \to B \equiv \neg A \lor B$. Ty jsi napsal $\neg A \lor \neg B$ (přidal jsi negaci k $Q(x, y)$!).
  * ⚠️ Formule v PNF musí mít **kvantifikátory vytknuté před celou formuli (v prefixu)**:
* 🎯 **Vzorové řešení pro zkoušejícího:**
  1. Dosah $\forall x$ končí na $P(x)$. Tedy $x$ v $P(x)$ je **vázaná**, zatímco $x$ i $y$ v $Q(x, y)$ jsou **volné**.
  2. Generální uzávěr: $(\forall x)(\forall y) \big( (\forall x)P(x) \to Q(x, y) \big)$.
  3. Převod do PNF:
     * Krok 1 (přejmenování vázané proměnné, aby nekolidovala s volnou $x$): $(\forall z) P(z) \to Q(x, y)$.
     * Krok 2 (vytknutí kvantifikátoru z předpokladu implikace – $\forall$ se obrací na $\exists$):
       $$(\forall z) P(z) \to Q(x, y) \ \sim \ (\exists z) \big( P(z) \to Q(x, y) \big)$$
       *(nebo ekvivalentně přes negaci: $(\exists z)(\neg P(z) \lor Q(x, y))$).*

---

### 2. Analýza teorií nad konečným jazykem
* **Zadání:** $\mathbb{P} = \{p, q, r\}$. Počet teorií, počet kompletních teorií, modely $T = \{p \to q, q \to r\}$.
* **Odpověď studenta:**
  * Počet teorií: $2^{2^3} = 2^8 = 256$.
  * Kompletní bezesporné teorie: $2^3 = 8$.
  * Tabulka modelů pro $T$: 4 modely: $(0,0,0), (0,0,1), (0,1,1), (1,1,1)$. Není kompletní.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – Bezchybné, přesné a rychlé.

---

### 3. Tablo metoda ve výrokové logice
* **Zadání:** Dokažte tablo metodou: $\tau = (p \to q) \to (\neg q \to \neg p)$.
* **Odpověď studenta:**
  Kmen $F\tau \implies T(p \to q)$ a $F(\neg q \to \neg p) \implies T\neg q, F\neg p \implies Fq, Tp$.
  Rozvětvení $T(p \to q)$ na $Fp$ a $Tq$. Obě větve uzavřeny křížkem $\times$.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – Čistý, učebnicový tablo důkaz.

---

### 4. Tablo metoda v predikátové logice
* **Zadání:** Důkaz $\psi = (\forall x)P(x) \to (\exists x)P(x)$. Určete typy pravidel pro $T(\forall x)P(x)$ a $F(\exists x)P(x)$, zaveďte term a uzavřete větev.
* **Odpověď studenta:**
  Správně uvedeno: „jedná se o typ všichni“. Odvozeno $P(c)$ a spor $\times$.
* **Hodnocení:** **0,8 b (přísně 0,7 b)**
  * ✅ Skvělé! Zkouškový chyták jsi prokoukl: **obě** formule $T(\forall x)P(x)$ i $F(\exists x)P(x)$ představují pravidlo typu **Všichni**!
  * ⚠️ V zápisu tabla nepoužívej neoznačenou negaci $\neg P(c)$. V označeném tablu se píše:
    1. $T(\forall x)P(x)$
    2. $F(\exists x)P(x)$
    3. $TP(c)$ (aplikace pravidla Všichni z 1 pro novou konstantu $c$)
    4. $FP(c)$ (aplikace pravidla Všichni z 2 pro term $c$)
    5. Větev obsahuje $TP(c)$ i $FP(c) \implies$ spor $\times$.

---

### 5. Skolemizace a ekvisplnitelnost
* **Zadání:** Skolemizace $\varphi_1 = (\forall x)(\exists y)(\forall z)(\exists w) R(x, y, z, w)$ a $\varphi_2 = (\exists u)(\forall v) S(u, v)$. Sémantický vztah $\varphi$ a $\varphi_{sk}$.
* **Odpověď studenta:**
  * $\varphi_2 \to S(c, v)$, $\varphi_1 \to R(x, f_1(x), z, f_2(x, z))$.
  * Vztah: *„Ne, skolemova varianta není ekvivalentní, je ekvisplnitelná neboli platí ve stejných modelech.“*
* **Hodnocení:** **0,75 b (přísně 0,65 b)**
  * ✅ Samotná Skolemizace (konstanta $c$, funkce $f_1(x)$ a $f_2(x, z)$) je **100% správně**.
  * ⚠️ **Pozor na fatální protimluv:** Napsal jsi *„je ekvisplnitelná neboli platí ve stejných modelech“*.
    * Kdyby platily ve stejných modelech, byly by **ekvivalentní**!
    * Skolemovská varianta má **rozšířený jazyk** (přibyla funkce $f$). Původní model $\mathcal{M}$ pro ni vůbec nemůže být modelem, protože nezná interpretaci symbolu $f$!
* 🎯 **Přesná formulace MFF:**
  Formule $\varphi$ a $\varphi_{sk}$ **nejsou ekvivalentní**, jsou pouze **ekvisplnitelné**:
  $$\varphi \text{ má model} \iff \varphi_{sk} \text{ má model}$$
  Každý model $\mathcal{M} \models \varphi$ lze **expandovat** na model $\mathcal{M}^* \models \varphi_{sk}$ vhodnou volbou realizací Skolemových funkcí (přes axiom výběru).

---

### 6. Extenze teorií
* **Zadání:** Definice konzervativní extenze. Je Skolemizace konzervativní extenzí?
* **Odpověď studenta:**
  $Csq(T') \cap VF_L = Csq(T)$. Ano, je konzervativní extenze.
* **Hodnocení:** **0,9 b (přísně 0,85 b)** – Výborné. Stačilo dodat stručné odůvodnění (každý model $T$ lze expandovat na model Skolemovy extenze).

---

### 7. Věta o kompaktnosti a vyjadřovací síla PL
* **Zadání:** Znění věty o kompaktnosti (obě verze). Zdůvodněte, proč nelze vyjádřit „doména je konečná“.
* **Odpověď studenta:**
  * Věta: *„Sentence $\varphi$ platí v $T \iff$ platí v každé její konečné podmnožině.“*
  * Důkaz konečnosti: *„Protože pak by toto tvrzení platilo asi i v teorii s nekonečnou doménou...“*
* **Hodnocení:** **0,45 b (přísně 0,35 b)**
  * ⚠️ **Chyba v kvantifikátoru věty:** Napsal jsi *„platí v každé konečné podmnožině“*. Kdyby to platilo v každé, platilo by to i v prázdné podmnožině $\emptyset$, takže by $\varphi$ musela být tautologie!
    * Správně: $T \models \varphi \iff$ existuje **alespoň jedna konečná podmnožina** $T' \subseteq_{fin} T$ taková, že $T' \models \varphi$.
    * Verze s modely: $T \text{ má model} \iff \text{každá konečná } T' \subseteq_{fin} T \text{ má model}$.
* 🎯 **Přesný důkaz nemožnosti vyjádřit konečnost:**
  1. Sporem: Nechť teorie $T$ má za modely právě všechny konečné struktury.
  2. Zavedeme sentence $\alpha_n$ („existuje alespoň $n$ různých prvků“):
     $$\alpha_n = (\exists x_1)\dots(\exists x_n) \bigwedge_{1 \le i < j \le n} (x_i \ne x_j)$$
  3. Uvažme teorii $T^* = T \cup \{ \alpha_n \mid n \ge 2 \}$.
  4. Každá konečná podmnožina $T' \subseteq_{fin} T^*$ obsahuje jen konečně mnoho axiomů $\alpha_n$ (s indexem nejvýše $N$). Má tedy konečný model velikosti $N+1$, takže $T'$ má model.
  5. Dle věty o kompaktnosti má i celá teorie $T^*$ model $\mathcal{M}$.
  6. Model $\mathcal{M}$ splňuje všechny $\alpha_n \implies$ je **nekonečný**. Současně $\mathcal{M} \models T \implies$ je **konečný**. **Spor.**

---

### 8. Łoś-Vaughtovo kritérium a kompletnost teorií
* **Zadání:** Znění Łoś-Vaughtova kritéria. Je DeLO $\text{Th}(\mathbb{Q}, \le)$ kompletní?
* **Odpověď studenta:**
  Každá bezesporná teorie, která nemá konečné modely a je $\kappa$-charakteristická, je kompletní. DeLO je $\aleph_0$-kategorická, tedy kompletní.
* **Hodnocení:** **0,6 b (přísně 0,5 b)**
  * ⚠️ Původně jsi napsal *„nekonečná teorie“* – pozor, podmínka kritéria zní: **nemá žádné konečné modely** (všechny její modely jsou nekonečné množiny).
  * ⚠️ Překlep v termínu: ne *charakteristická*, ale **kategorická** ($\kappa$-kategorická).
  * ✅ Aplikace na DeLO: DeLO je bezesporná, nemá konečné modely, jazyk je spočetný a je $\aleph_0$-kategorická (Cantorova věta: každá dvě spočetná hustá lineární uspořádání bez konců jsou izomorfní $\mathbb{Q}$) $\implies$ **je kompletní**.

---

### 9. Zlatá věta o rozhodnutelnosti
* **Zadání:** Zlatá věta o rozhodnutelnosti a popis algoritmu.
* **Odpověď studenta:**
  Rekurzivně axiomatizovaná a kompletní $\implies$ rozhodnutelná. Algoritmus generuje důkazy a dojde ke sporu.
* **Hodnocení:** **0,9 b (přísně 0,85 b)** – Velmi dobré.
* 🎯 **Přesné zdůvodnění algoritmu:**
  Pro danou sentenci $\varphi$ algoritmus systematicky generuje formální důkazy z axiomů $T$.
  Protože $T$ je **kompletní**, nutně platí buď $T \vdash \varphi$, nebo $T \vdash \neg\varphi$.
  Díky rekurzivní axiomatizaci a úplnosti důkazového kalkulu se důkaz jedné z nich v konečném čase najde $\implies$ algoritmus vždy zastaví a odpoví ANO nebo NE.

---

### 10. Hranice rozhodnutelnosti
* **Zadání:** Presburger vs. Peano vs. PL s binárním predikátem.
* **Odpověď studenta:**
  Presburger je rozhodnutelná (pouze sčítání, bez prvočísel, nelze kódovat TM). Zbylé dvě jsou nerozhodnutelné, protože simulují výpočet Turingova stroje.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – Naprosto přesné shrnutí podstaty.

---

## ⏱️ Analýza času: Proč to trvalo 70 minut a jak to zkrátit na 25 minut?
Trvalo ti to 70 minut hlavně ze dvou důvodů:
1. **Přeškrtávání a hledání formátu tabla u otázek 3 a 4:** Kreslení stromu a váhání nad značením tě zdrželo. Jakmile víš, že u $T(p \to q)$ se větví a u $F(p \to q)$ jde pod sebe, tablo pro VL máš hotové za **90 sekund**.
2. **Rozepisování úvah slovy u otázek 7 a 8:** Zkoušející nechce esej. Stačí napsat odrážky s matematickými symboly.

---

## 📌 Úkoly do `chyby.md`

Tento bod si ihned zapiš do `chyby.md`:

> **Matematická logika – Zkouškové přesnosti:**
> 1. **Ekvisplnitelnost $\ne$ stejné modely:** $\varphi$ a $\varphi_{sk}$ jsou ekvisplnitelné ($\varphi$ má model $\iff \varphi_{sk}$ má model), ale **nemají stejné modely** (Skolemovský jazyk má navíc nové symboly funkcí/konstant!).
> 2. **Věta o kompaktnosti (kvantifikátory):** $T \models \varphi \iff \exists T' \subseteq_{fin} T: T' \models \varphi$ (existuje **alespoň jedna** konečná podmnožina, nikoliv každá!).
> 3. **Łoś-Vaught:** Podmínkou je, že teorie **nemá konečné modely** (nikoliv že teorie má nekonečně mnoho axiomů) a je **$\kappa$-kategorická**.
> 4. **Převod implikace do PNF:** $A \to B \equiv \neg A \lor B$. Při vytýkání kvantifikátoru z předpokladu: $(\forall z P(z) \to Q) \sim \exists z (P(z) \to Q)$ (obrací se $\forall \leftrightarrow \exists$).

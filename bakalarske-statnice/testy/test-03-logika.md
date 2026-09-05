# Test 3: Matematická logika (10 otázek)

* **Datum:** 5. 9. 2026
* **Doporučený čas:** 25–30 minut
* **Pravidla:** Piš na papír bez nahlížení do taháku či poznámek. Odpovědi formuluj přesně se všemi předpoklady.

---

### Část 1: Syntaxe, Sémantika a Normální formy

#### 1. Dosah kvantifikátoru, volné proměnné a převod do PNF
Mějme formuli predikátové logiky:
$$\varphi: \quad (\forall x) P(x) \to Q(x, y)$$
a) Určete, které výskyty proměnných $x$ a $y$ jsou vázané a které volné.
b) Jak zní generální (univerzální) uzávěr této formule?
c) Převeďte formuli $\varphi$ korektně do prenexní normální formy (PNF). *(Pozor na dosah, přejmenování proměnných a obracení kvantifikátoru v implikaci!)*

---

#### 2. Analýza teorií nad konečným jazykem
Mějme jazyk výrokové logiky se 3 prvovýroky $\mathbb{P} = \{p, q, r\}$.
a) Kolik existuje různých (navzájem neekvivalentních) teorií v tomto jazyce?
b) Kolik existuje různých kompletních bezesporných teorií?
c) Mějme teorii $T = \{p \to q, q \to r\}$. Kolik má teorie $T$ modelů? Je teorie $T$ kompletní?

---

### Část 2: Formální systémy a Tablo metoda

#### 3. Tablo metoda ve výrokové logice (Konstrukce důkazu)
Pomocí tablo metody dokažte, že formule je tautologie:
$$\tau: \quad (p \to q) \to (\neg q \to \neg p)$$
* Začněte kořenem $F\tau$.
* Rozepište kroky tablo důkazu (ukažte položky na větvích, větvení a uzavření větví sporem $\times$).

---

#### 4. Tablo metoda v predikátové logice (Pravidla pro kvantifikátory)
Chceme tablo metodou dokázat formuli:
$$\psi: \quad (\forall x) P(x) \to (\exists x) P(x)$$
a) Začněte kořenem $F\psi$ a aplikujte pravidlo pro implikaci. Jaké dvě označené formule dostanete na kmeni?
b) Na větvi máte nyní položky $T(\forall x) P(x)$ a $F(\exists x) P(x)$. O jaký typ pravidel se jedná (Svědek vs. Všichni)? Jak zavedete term a jak se větev uzavře?

---

### Část 3: Teorie, Extenze a Skolemizace

#### 5. Skolemizace (Převod na otevřenou teorii)
Převeďte následující dvě formule v PNF na Skolemovu variantu (odstraňte existenční kvantifikátory):
1. $\varphi_1 = (\forall x)(\exists y)(\forall z)(\exists w) \, R(x, y, z, w)$
2. $\varphi_2 = (\exists u)(\forall v) \, S(u, v)$
* Pro každou formuli uveďte zavedené Skolemovy symboly (včetně jejich arity) a výslednou otevřenou formuli.
* Jaký je přesný sémantický vztah mezi původní formulí $\varphi$ a její Skolemovou variantou $\varphi_{sk}$ (platí $\varphi \sim \varphi_{sk}$)?

---

#### 6. Extenze teorií
* Definujte pojem **konzervativní extenze** teorie $T$ v jazyce $L$ teorií $T'$ v jazyce $L'$.
* Rozhodněte a zdůvodněte: Je Skolemovo rozšíření teorie $T$ o nové funkční symboly konzervativní extenzí teorie $T$?

---

### Část 4: Věty o kompaktnosti, úplnosti a rozhodnutelnosti

#### 7. Věta o kompaktnosti a vyjadřovací síla PL
* Zformulujte **větu o kompaktnosti** pro predikátovou logiku (obě ekvivalentní znění – přes model i přes sémantický důsledek).
* Pomocí věty o kompaktnosti zdůvodněte, proč v predikátové logice 1. řádu **nelze** žádnou teorií vyjádřit vlastnost: *„Doména struktury je konečná.“*

---

#### 8. Łoś-Vaughtovo kritérium a kompletnost teorií
* Zformulujte **Łoś-Vaughtovo kritérium** kompletnosti teorie (všechny 3 předpoklady na teorii $T$).
* Uvažujme teorii hustých lineárních uspořádání bez koncových bodů DeLO $\text{Th}(\mathbb{Q}, \le)$. Je tato teorie kompletní?

---

#### 9. Zlatá věta o rozhodnutelnosti
* Nechť $T$ je rekurzivně axiomatizovaná teorie.
  a) Zformulujte **Zlatou větu** dávající postačující podmínku pro to, aby $T$ byla rozhodnutelná.
  b) Stručně popište rozhodovací algoritmus pro formuli $\varphi$ a vysvětlete, proč se nezacyklí.

---

#### 10. Hranice rozhodnutelnosti (Příklady)
U každé z následujících tří teorií rozhodněte, zda je **rozhodnutelná**, či **nerozhodnutelná**, a uveďte klíčový důvod:
1. **Presburgerova aritmetika $\text{Th}(\mathbb{N}, +, 0)$**
2. **Peanova aritmetika $\text{Th}(\mathbb{N}, +, \cdot, 0, S, \le)$**
3. **Predikátová logika 1. řádu s alespoň jedním binárním predikátem (Church-Turing)**

# Rozbor Testu 2: Matematická analýza (Vyhodnocení a vzorová řešení)

* **Datum:** 4. 9. 2026
* **Doba psaní:** 90 minut (18:45 – 20:15)
* **Hodnocení:**
  * **Mírnější (průběžné) hodnocení:** **7,75 / 10 bodů (78 % – známka 2 / Velmi dobře)**
  * **Přísné zkouškové hodnocení MFF:** **6,85 / 10 bodů (69 % – známka 2- až 3 / Dobře)**
* **Výchozí test:** [test-02-analyza.md](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/testy/test-02-analyza.md)

---

## ⚖️ Realistický pohled na přísnost hodnocení

Ptal ses, zda nehodnotím moc mírně. **Máš pravdu v tom, že u zkoušky na MFF by ti přísný zkoušející dal méně:**
1. **Otázka 3 (Limita vs. Spojitost):** Napsal jsi definici spojitosti ($f(x_0)$ místo $L$ a chybí prstencové okolí $0 < |x-x_0|$). Mnoho zkoušejících za to dá rovnou **0 bodů** z dané podotázky.
2. **Otázka 7 (l'Hospital):** Výpočet limity ti zkolaboval na neplatné algebraické úpravě a výsledek $-\infty$ je zcela mimo (správně je $1/2$). Za samotný výpočet bys dostal 0.
3. **Otázky 9 a 10:** Nedopočítaný Taylor a chybějící integrovaný člen $[uv]$ v per partes by přísná komise osekala na minimum.

**Přísné zkouškové skóre:** **6,85 / 10 bodů (69 %)**. 
I při této nejtvrdší laťce je to ale **bezpečné splnění písemky** (hranice bývá 50 %).

---

## 📊 Rychlý přehled výsledků

| Otázka | Téma | Mírně | Přísně MFF | Hlavní zjištění |
|:---:|---|:---:|:---:|---|
| **1** | Limita posloupnosti a dva policajti | 1,0 | 0,85 | Doplněná definice super; u policajtů chybělo slůvko „vlastní limita $A \in \mathbb{R}$“. |
| **2** | Řady a geometrická řada | 1,0 | 1,0 | Perfektní (nutná podmínka, harmonický protipříklad, součet). |
| **3** | Limita funkce v bodě a Heine | 0,6 | 0,4 | Záměna limity se spojitostí ($f(x_0)$ místo $L$, chybí $0 <$). Heine dobrý. |
| **4** | Spojitost a nabývání mezihodnot | 0,95 | 0,9 | Výborně Bolzano i kořen polynomu na $(0, 1)$. |
| **5** | Weierstrassova věta a protipříklad | 0,9 | 0,8 | Správná věta i protipříklad $1/x$ na $(0, 1]$. Chybělo zmínit omezenost. |
| **6** | Definice derivace a spojitost | 1,0 | 1,0 | Naprosto přesné (definice, obě implikace, protipříklad $\|x\|$). |
| **7** | l'Hospitalovo pravidlo | 0,4 | 0,3 | Typy správně; u limity neplatné dělení místo 2. l'Hospitala (výsledek špatně). |
| **8** | Průběh funkce a extrémy | 1,0 | 1,0 | Bezchybné derivace, stacionární body, znaménka i inflexe. |
| **9** | Taylorův polynom (limitní forma) | 0,5 | 0,3 | Vzorec a malé $o$ v jádru trefeno, rozvoj $\ln(1+x)$ nedokončen. |
| **10** | Integrály a obsah plochy | 0,4 | 0,3 | Volba $u, v$ v per partes správně, ale výpočet plochy nedotažen. |
| **CELKEM** | | **7,75** | **6,85** | **Úspěšnost 69 % (zkouška splněna s rezervou)** |

---

## 🔍 Detailní rozbor s přesnými vzorovými řešeními

### 1. Limita posloupnosti a věta o dvou policajtech
* **Zadání:** Formální definice vlastní limity posloupnosti $(a_n)$ ($L \in \mathbb{R}$) a znění Věty o dvou policajtech.
* **Odpověď studenta:**
  * $\forall \varepsilon > 0 \ \exists n_0 \ \forall n \ge n_0 : |a_n - L| < \varepsilon$.
  * Mějme $(a_n), (b_n)$ se stejnou limitou a $\exists n_0 \forall n \ge n_0: a_n \le c_n \le b_n$, pak $\lim c_n = \lim a_n = \lim b_n$.
* **Hodnocení:** **1,0 b (přísně 0,85 b)** – u policajtů chyběl předpoklad konečnosti limity ($A \in \mathbb{R}$).
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice vlastní limity posloupnosti:**
     $$\lim_{n \to \infty} a_n = L \iff \forall \varepsilon > 0 \ \exists n_0 \in \mathbb{N} \ \forall n \ge n_0: |a_n - L| < \varepsilon$$
  2. **Věta o dvou policajtech:**
     Nechť $(a_n), (b_n), (c_n)$ jsou reálné posloupnosti splňující:
     1. $\lim_{n \to \infty} a_n = \lim_{n \to \infty} b_n = A \in \mathbb{R}$ (společná **vlastní** limita),
     2. existuje index $n_0 \in \mathbb{N}$ takový, že pro všechna $n \ge n_0$ platí $a_n \le c_n \le b_n$.
     Potom posloupnost $(c_n)$ konverguje a platí $\lim_{n \to \infty} c_n = A$.

---

### 2. Nekonečné řady a geometrická řada
* **Zadání:** Nutná podmínka konvergence řady $\sum a_n$, platnost obrácené implikace a geometrická řada.
* **Odpověď studenta:**
  * $\sum a_n$ konverguje $\implies \lim a_n = 0$.
  * Obrácená neplatí, protipříklad harmonická řada $\sum \frac{1}{n}$.
  * Geometrická řada konverguje pro $q \in (-1, 1)$, součet $\frac{1}{1-q}$ (resp. $\frac{a}{1-q}$).
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – naprosto bezchybné.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Nutná podmínka konvergence:** Pokud řada $\sum_{n=1}^\infty a_n$ konverguje, potom $\lim_{n \to \infty} a_n = 0$.
  2. **Obrácená implikace neplatí:** Protipříkladem je harmonická řada $\sum_{n=1}^\infty \frac{1}{n}$, pro kterou platí $\lim_{n \to \infty} \frac{1}{n} = 0$, ale řada diverguje do $+\infty$.
  3. **Geometrická řada:** Řada $\sum_{n=0}^\infty q^n$ konverguje právě tehdy, když $|q| < 1$ (tj. $q \in (-1, 1)$). Její součet je roven $\frac{1}{1 - q}$ (obecně pro $\sum_{n=0}^\infty a q^n = \frac{a}{1 - q}$). Pro $|q| \ge 1$ řada diverguje.

---

### 3. Limita funkce v bodě a Heineho věta
* **Zadání:** $\varepsilon$-$\delta$ definice vlastní limity $\lim_{x \to x_0} f(x) = L$ a Heineho věta.
* **Odpověď studenta:**
  * $\forall \varepsilon > 0 \exists \delta > 0 : |x - x_0| < \delta \implies |f(x) - f(x_0)| < \varepsilon$
  * Heine: pro každou posloupnost $a_n \to x_0$ platí $\lim f(a_n) = L$.
* **Hodnocení:** **0,6 b (přísně 0,4 b)** – fatální záměna limity se spojitostí.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice vlastní limity funkce v bodě ($x_0, L \in \mathbb{R}$):**
     $$\lim_{x \to x_0} f(x) = L \iff \forall \varepsilon > 0 \ \exists \delta > 0 \ \forall x \in D(f): \mathbf{0 < |x - x_0| < \delta} \implies |f(x) - \mathbf{L}| < \varepsilon$$
     *(Zásadní: v cíli je $L$, nikoliv $f(x_0)$! Podmínka $0 < |x - x_0|$ zajišťuje, že vyšetřujeme prstencové okolí – funkční hodnota přímo v bodě $x_0$ na limitu nemá žádný vliv).*
  2. **Heineho věta:**
     $\lim_{x \to x_0} f(x) = L$ platí právě tehdy, když pro každou posloupnost $(x_n)_{n=1}^\infty \subseteq D(f) \setminus \{x_0\}$ splňující $\lim_{n \to \infty} x_n = x_0$ platí $\lim_{n \to \infty} f(x_n) = L$.

---

### 4. Spojitost na intervalu a nabývání mezihodnot
* **Zadání:** Věta o nabývání mezihodnot a důkaz kořene $x^3 - 3x + 1 = 0$ na $(0, 1)$.
* **Odpověď studenta:**
  * Spojitá funkce na $[a, b] \implies$ pro každé $y$ mezi $m$ a $M$ existuje $x$ t.ž. $f(x) = y$.
  * $f(0) = 1 > 0$ a $f(1) = -1 < 0 \implies$ existuje kořen $f(x) = 0$.
* **Hodnocení:** **0,95 b (přísně 0,9 b)** – věcně výborné.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Bolzano-Darbouxova věta o nabývání mezihodnot:**
     Nechť $f$ je spojitá funkce na uzavřeném intervalu $[a, b]$. Označme $m = \min\{f(a), f(b)\}$ a $M = \max\{f(a), f(b)\}$. Potom pro každé $y \in [m, M]$ existuje bod $c \in [a, b]$ takový, že $f(c) = y$.
     *(Speciálně: pokud $f(a) \cdot f(b) < 0$, existuje $c \in (a, b)$ takové, že $f(c) = 0$).*
  2. **Důkaz pro rovnici:**
     Definujme $f(x) = x^3 - 3x + 1$. Funkce $f$ je polynom, tudíž je spojitá na celém $\mathbb{R}$, a tedy i na $[0, 1]$.
     Spočteme hodnoty v krajích:
     * $f(0) = 0 - 0 + 1 = 1 > 0$
     * $f(1) = 1 - 3 + 1 = -1 < 0$
     Protože $f(0) > 0 > f(1)$ a $f$ je spojitá na $[0, 1]$, plyne z Bolzanovy věty existence bodu $c \in (0, 1)$ takového, že $f(c) = 0$.

---

### 5. Weierstrassova věta a zkouškový protipříklad
* **Zadání:** Weierstrassova věta o nabývání extrémů a protipříklad na porušený předpoklad.
* **Odpověď studenta:**
  * Spojitá funkce na uzavřeném omezeném intervalu nabývá minima i maxima.
  * Protipříklad: $f(x) = \frac{1}{x}$ na $(0, 1]$ (není omezená).
* **Hodnocení:** **0,9 b (přísně 0,8 b)** – chybělo explicitně uvést 1. tvrzení věty (omezenost).
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Weierstrassova věta:**
     Nechť funkce $f$ je spojitá na **uzavřeném a omezeném (kompaktním)** intervalu $[a, b]$. Potom:
     1. funkce $f$ je na $[a, b]$ **omezená**,
     2. funkce $f$ na $[a, b]$ **nabývá svého maxima i minima** (tj. $\exists x_{\min}, x_{\max} \in [a, b] \ \forall x \in [a, b]: f(x_{\min}) \le f(x) \le f(x_{\max})$).
  2. **Protipříklad:**
     Funkce $f(x) = \frac{1}{x}$ na intervalu $(0, 1]$.
     * Funkce je na intervalu spojitá a interval $(0, 1]$ je omezený.
     * **Porušený předpoklad:** Interval **není uzavřený** (v bodě 0 je otevřený).
     * **Důsledek:** Pro $x \to 0^+$ platí $\lim_{x \to 0^+} \frac{1}{x} = +\infty$, funkce není shora omezená a na $(0, 1]$ nenabývá maxima.

---

### 6. Definice derivace a vztah se spojitostí
* **Zadání:** Definice $f'(x_0)$ a platnost obou implikací mezi derivací a spojitostí.
* **Odpověď studenta:**
  * $f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}$.
  * 1. Platí (derivace $\implies$ spojitost).
  * 2. Neplatí, protipříklad $|x|$ v bodě $0$.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – naprosto čisté.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Definice derivace:**
     $$f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$$
  2. **Implikace 1 (Derivace $\implies$ Spojitost): PLATÍ.**
     Má-li $f$ v bodě $x_0$ vlastní derivaci $f'(x_0) \in \mathbb{R}$, pak platí:
     $$\lim_{x \to x_0} (f(x) - f(x_0)) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \cdot (x - x_0) = f'(x_0) \cdot 0 = 0$$
     Odtud $\lim_{x \to x_0} f(x) = f(x_0)$, což je přesně definice spojitosti funkce $f$ v bodě $x_0$.
  3. **Implikace 2 (Spojitost $\implies$ Derivace): NEPLATÍ.**
     Protipříklad: Funkce $f(x) = |x|$ v bodě $x_0 = 0$ je spojitá, ale její jednostranné derivace jsou $f'_+(0) = 1$ a $f'_-(0) = -1$. Jelikož se nerovnají, oboustranná derivace $f'(0)$ neexistuje.

---

### 7. l'Hospitalovo pravidlo a výpočet limity
* **Zadání:** Typy neurčitých podílů a výpočet $\lim_{x \to 0} \frac{e^x - 1 - x}{x^2}$.
* **Odpověď studenta:**
  * Typy: $\frac{0}{0}$ a $\frac{\infty}{\infty}$.
  * Výpočet: neplatné dělení na zlomky $\implies$ výsledek $-\infty$.
* **Hodnocení:** **0,4 b (přísně 0,3 b)** – typy ano, samotný výpočet nula.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Základní typy pro l'Hospitala:** Podíly typu $\frac{0}{0}$ a $\frac{\pm\infty}{\pm\infty}$ (přesněji: $\lim f = \lim g = 0$ nebo $\lim |g| = +\infty$).
  2. **Výpočet limity:**
     Dosazením $x = 0$ zjistíme, že jde o typ $\frac{e^0 - 1 - 0}{0^2} = \frac{0}{0}$:
     $$\lim_{x \to 0} \frac{e^x - 1 - x}{x^2} \stackrel{\text{l'H } \frac{0}{0}}{=} \lim_{x \to 0} \frac{(e^x - 1 - x)'}{(x^2)'} = \lim_{x \to 0} \frac{e^x - 1}{2x}$$
     Po dosazení $x = 0$ dostáváme opět $\frac{e^0 - 1}{2 \cdot 0} = \frac{0}{0}$. Použijeme l'Hospitalovo pravidlo podruhé:
     $$\stackrel{\text{l'H } \frac{0}{0}}{=} \lim_{x \to 0} \frac{(e^x - 1)'}{(2x)'} = \lim_{x \to 0} \frac{e^x}{2} = \frac{e^0}{2} = \mathbf{\frac{1}{2}}$$

---

### 8. Průběh funkce a extrémy
* **Zadání:** $f(x) = x^3 - 3x^2 + 2$. Monotonie, extrémy, inflexní bod.
* **Odpověď studenta:**
  * $f'(x) = 3x^2 - 6x = 3x(x - 2) \implies x = 0, 2$.
  * Intervaly: $(-\infty, 0)$ roste, $(0, 2)$ klesá, $(2, \infty)$ roste.
  * Maximum v $x = 0$, minimum v $x = 2$, inflexe v $x = 1$.
* **Hodnocení:** **1,0 b (přísně 1,0 b)** – naprosto dokonalé.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **1. derivace a stacionární body:**
     $$f'(x) = 3x^2 - 6x = 3x(x - 2)$$
     Stacionární body ($f'(x) = 0$): $x_1 = 0$, $x_2 = 2$.
  2. **Monotonie:**
     * $x \in (-\infty, 0): f'(x) > 0 \implies$ funkce je **rostoucí** na $(-\infty, 0]$.
     * $x \in (0, 2): f'(x) < 0 \implies$ funkce je **klesající** na $[0, 2]$.
     * $x \in (2, \infty): f'(x) > 0 \implies$ funkce je **rostoucí** na $[2, \infty)$.
  3. **Lokální extrémy:**
     * V bodě $x = 0$ derivace mění znaménko z $+$ na $-$ $\implies$ **ostré lokální maximum** s hodnotou $f(0) = 2$.
     * V bodě $x = 2$ derivace mění znaménko z $-$ na $+$ $\implies$ **ostré lokální minimum** s hodnotou $f(2) = 2^3 - 3\cdot 2^2 + 2 = -2$.
  4. **2. derivace a inflexe:**
     $$f''(x) = 6x - 6 = 6(x - 1)$$
     * $x \in (-\infty, 1): f''(x) < 0 \implies$ funkce je konkávní.
     * $x \in (1, \infty): f''(x) > 0 \implies$ funkce je konvexní.
     * Bod $x = 1$ je **inflexní bod** (hodnota $f(1) = 0$).

---

### 9. Taylorův polynom (limitní forma)
* **Zadání:** Obecný vzorec $T_n$, Peanův zbytek a Taylor 3. stupně pro $\ln(1+x)$ v $0$.
* **Odpověď studenta:**
  * Obecný tvar s faktoriálem i malé $o((x - x_0)^n)$ uvedeno.
  * Pro $\ln(1+x)$ nedopočteno.
* **Hodnocení:** **0,5 b (přísně 0,3 b)** – rozvoj chybí.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Taylorův polynom stupně $n$ se středem v $x_0$:**
     $$T_n^{f, x_0}(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k = f(x_0) + f'(x_0)(x - x_0) + \frac{f''(x_0)}{2!}(x - x_0)^2 + \dots + \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n$$
  2. **Taylorův vzorec s Peanovým zbytkem:**
     $$f(x) = T_n^{f, x_0}(x) + o((x - x_0)^n) \quad \text{pro } x \to x_0$$
     *(Význam: zbytek klesá k nule rychleji než $(x - x_0)^n$, tj. $\lim_{x \to x_0} \frac{f(x) - T_n(x)}{(x - x_0)^n} = 0$).*
  3. **Taylor 3. stupně pro $f(x) = \ln(1 + x)$ v $x_0 = 0$:**
     * $f(0) = \ln(1) = 0$
     * $f'(x) = \frac{1}{1+x} \implies f'(0) = 1$
     * $f''(x) = -\frac{1}{(1+x)^2} \implies f''(0) = -1$
     * $f'''(x) = \frac{2}{(1+x)^3} \implies f'''(0) = 2$
     Dosazení koeficientů:
     $$T_3(x) = 0 + \frac{1}{1!} x + \frac{-1}{2!} x^2 + \frac{2}{3!} x^3 = \mathbf{x - \frac{x^2}{2} + \frac{x^3}{3}}$$

---

### 10. Integrály a obsah plochy
* **Zadání:** Vzorec per partes a obsah plochy pod $f(x) = x e^{-x}$ na $[0, 1]$.
* **Odpověď studenta:**
  * Vzorec uveden, volba $u' = e^{-x}, v = x$ správně.
  * Výpočet integrálu nedotažen (vypadl člen $uv$).
* **Hodnocení:** **0,4 b (přísně 0,3 b)** – integrál nedopočítán.
* 🎯 **Vzorové 100% řešení pro zkoušejícího:**
  1. **Metoda per partes pro neurčitý integrál:**
     $$\int u'(x) v(x) \, dx = u(x) v(x) - \int u(x) v'(x) \, dx$$
     *(Pro určitý integrál: $\int_a^b u' v = [uv]_a^b - \int_a^b uv'$).*
  2. **Výpočet obsahu plochy:**
     Funkce $f(x) = x e^{-x}$ je na intervalu $[0, 1]$ nezáporná ($f(x) \ge 0$), obsah plochy pod grafem je dán určitým integrálem:
     $$S = \int_0^1 x e^{-x} \, dx$$
     Použijeme per partes s volbou:
     * $u'(x) = e^{-x} \implies u(x) = -e^{-x}$
     * $v(x) = x \implies v'(x) = 1$
     Integrace:
     $$\int_0^1 x e^{-x} \, dx = \left[ -x e^{-x} \right]_0^1 - \int_0^1 (-e^{-x}) \, dx = \left[ -x e^{-x} \right]_0^1 + \int_0^1 e^{-x} \, dx$$
     $$= \left[ -x e^{-x} - e^{-x} \right]_0^1 = \left[ -e^{-x}(x + 1) \right]_0^1$$
     Dosazení mezí:
     * Horní mez ($x = 1$): $-e^{-1}(1 + 1) = -\frac{2}{e}$
     * Dolní mez ($x = 0$): $-e^0(0 + 1) = -1$
     Výsledná plocha (horní mez mínus dolní mez):
     $$S = -\frac{2}{e} - (-1) = \mathbf{1 - \frac{2}{e}} \approx \mathbf{0{,}264}$$

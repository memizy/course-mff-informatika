# Souhrn na rychlé zopakování před termínem
Už ho udělat se správnými uvozovkami
V poznámkách můžu kouknout na žlutý nebo horší poznámky co jsem si tam nechal, ale to co je tady by mělo stačit

## Matika

### Analýza
#### Posloupnosti reálných čísel a jejich limity:
* **Definice posloupnosti:** Reálná posloupnost je zobrazení $a: \mathbb{N} \to \mathbb{R}$, značíme $(a_n)_{n=1}^\infty$, kde $a_n$ je $n$-tý člen.
  * **Monotonie:** Posloupnost je *rostoucí* ($a_n < a_{n+1}$), *klesající* ($a_n > a_{n+1}$), *neklesající* ($a_n \le a_{n+1}$), *nerostoucí* ($a_n \ge a_{n+1}$).
* **Definice limity posloupnosti (vlastní i nevlastní, $L \in \mathbb{R}^* = \mathbb{R} \cup \{\pm\infty\}$):**
  Posloupnost $(a_n)$ má limitu $L$ (píšeme $\lim_{n \to \infty} a_n = L$), pokud:
  $$\forall \varepsilon > 0 \ \exists n_0 \in \mathbb{N} \ \forall n \ge n_0: a_n \in U(L, \varepsilon)$$
  * **Vlastní limita v konečném čísle ($L \in \mathbb{R}$):** $\forall \varepsilon > 0 \ \exists n_0 \ \forall n \ge n_0: |a_n - L| < \varepsilon$ (od indexu $n_0$ leží všechny členy v pásu kolem $L$). Posloupnost s vlastní limitou nazýváme **konvergentní**.
  * **Nevlastní limita $+\infty$:** $\forall K \in \mathbb{R} \ \exists n_0 \ \forall n \ge n_0: a_n > K$ (členy přerostou libovolnou mez).
  * **Nevlastní limita $-\infty$:** $\forall K \in \mathbb{R} \ \exists n_0 \ \forall n \ge n_0: a_n < K$.
* **Aritmetika limit posloupností:**
  Nechť $\lim a_n = K \in \mathbb{R}^*$ a $\lim b_n = L \in \mathbb{R}^*$. Pokud mají výrazy v $\mathbb{R}^*$ smysl, platí:
  1. $\lim (a_n \pm b_n) = K \pm L$
  2. $\lim (a_n \cdot b_n) = K \cdot L$
  3. $\lim \left(\frac{a_n}{b_n}\right) = \frac{K}{L}$ (pokud $b_n \ne 0$ pro všechna $n \ge n_0$ a $L \ne 0$).
  * *Pozor na neurčité výrazy:* $\infty - \infty, \ 0 \cdot (\pm\infty), \ \frac{\pm\infty}{\pm\infty}, \ \frac{0}{0}$ (zde nelze aritmetiku limit přímo použít, je třeba výraz algebraicky upravit).
* **Věta o dvou policajtech (Sandwich theorem):**
  Nechť $(a_n), (b_n), (c_n)$ jsou posloupnosti splňující $\lim a_n = \lim b_n = A \in \mathbb{R}$ a od indexu $n_0$ platí $a_n \le c_n \le b_n$.
  Potom i sevřená posloupnost $(c_n)$ konverguje a platí:
  $$\lim_{n \to \infty} c_n = A$$
  *(Varianta „jeden policajt“ pro nevlastní limitu: pokud $c_n \ge a_n$ a $a_n \to +\infty$, pak nutně $c_n \to +\infty$).*
* **Limity a uspořádání:**
  * **Přenos ostré nerovnosti z limit na členy:** Pokud $\lim a_n = K < L = \lim b_n$, pak existuje index $n_0$ takový, že $\forall n \ge n_0: a_n < b_n$.
  * **Přechod k limitě v nerovnosti:** Pokud od indexu $n_0$ platí $a_n \le b_n$, potom $\lim a_n \le \lim b_n$. *(Pozor: i z ostré nerovnosti $a_n < b_n$ v limitě plyne pouze neostrá nerovnost $\lim a_n \le \lim b_n$, např. $\frac{1}{n} > 0$, ale limita je $0$)*.
* **Důležité vlastnosti posloupností:**
  * **Věta o limitě monotónní posloupnosti:** Každá monotónní posloupnost má limitu (je-li navíc omezená, má vlastní limitu $L \in \mathbb{R}$; je-li neomezená shora a neklesající, má limitu $+\infty$).
  * **Vybraná podposloupnost:** Má-li $(a_n)$ limitu $L$, má každá její vybraná podposloupnost $(a_{k_n})$ tutéž limitu $L$.
  * **Kritérium nulové vzdálenosti:** Pro $L \in \mathbb{R}$ platí $\lim a_n = L \iff \lim |a_n - L| = 0$.

#### Nekonečné číselné řady:
* **Definice řady a jejího součtu:**
  * **Řada:** Formální součet členů posloupnosti $(a_n)_{n=1}^\infty$, značíme $\sum_{n=1}^\infty a_n = a_1 + a_2 + a_3 + \dots$
  * **Posloupnost částečných součtů:** $s_n = \sum_{k=1}^n a_k = a_1 + a_2 + a_3 + \dots + a_n$.
  * **Součet řady:** Limita posloupnosti částečných součtů:
    $$\sum_{n=1}^\infty a_n = \lim_{n \to \infty} s_n \in \mathbb{R}^*$$
    * Existuje-li konečná limita $s = \lim s_n \in \mathbb{R}$, říkáme, že řada **konverguje** k součtu $s$.
    * Pokud limita neexistuje nebo je $\pm\infty$, řada **diverguje** (do $\pm\infty$, popř. osciluje).
* **Nutná podmínka konvergence řady:**
  $$\sum_{n=1}^\infty a_n \text{ konverguje} \implies \lim_{n \to \infty} a_n = 0$$
  *(Pokud $\lim a_n \ne 0$ nebo neexistuje, řada zaručeně diverguje. Obrácená implikace ale NEPLATÍ – viz harmonická řada!).*
* **Absolutní konvergence:** Řada $\sum a_n$ je absolutně konvergentní, pokud konverguje řada absolutních hodnot $\sum |a_n|$. Platí: absolutní konvergence $\implies$ konvergence.
* **Geometrická řada:** $\sum_{n=0}^\infty q^n = 1 + q + q^2 + \dots$ s kvocientem $q \in \mathbb{R}$:
  * Pro $|q| < 1$ (tj. $q \in (-1, 1)$): **konverguje** a její součet je $\frac{1}{1 - q}$ (obecně pro $\sum_{n=0}^\infty a q^n = \frac{a}{1 - q}$).
  * Pro $q \ge 1$: **diverguje** do $+\infty$ ($s_n \to +\infty$).
  * Pro $q \le -1$: **diverguje** (součet neexistuje, posloupnost $s_n$ osciluje).
* **Harmonická řada:**
  * **Základní harmonická řada ($s = 1$):** $\sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \dots$ **diverguje do $+\infty$** (přestože $\lim \frac{1}{n} = 0$).
  * **Obecná harmonická (Dirichletova) řada $\sum_{n=1}^\infty \frac{1}{n^s}$:**
    * **Konverguje** právě tehdy, když **$s > 1$** (např. $\sum \frac{1}{n^2} = \frac{\pi^2}{6}$).
    * **Diverguje** do $+\infty$ pro všechna **$s \le 1$**.

#### Reálné funkce jedné proměnné – Limita v bodě:
* **Okolí bodu:**
  * **$\delta$-okolí bodu $a \in \mathbb{R}$:** $U(a, \delta) = (a - \delta, a + \delta) = \{x \in \mathbb{R} \mid |x - a| < \delta\}$.
  * **Prstencové (redukované) okolí:** $P(a, \delta) = U(a, \delta) \setminus \{a\} = \{x \in \mathbb{R} \mid 0 < |x - a| < \delta\}$.
  * **Okolí nevlastních bodů:** $U(+\infty, \varepsilon) = P(+\infty, \varepsilon) = (1/\varepsilon, +\infty)$, resp. $U(-\infty, \varepsilon) = (-\infty, -1/\varepsilon)$.
* **Definice limity funkce v bodě ($a \in \mathbb{R}^*, A \in \mathbb{R}^*$):**
  Funkce $f$ má v bodě $a$ limitu $A$ (píšeme $\lim_{x \to a} f(x) = A$), pokud:
  $$\forall \varepsilon > 0 \ \exists \delta > 0 \ \forall x \in P(a, \delta): f(x) \in U(A, \varepsilon)$$
  * **Vlastní limita ve vlastním bodě ($a, A \in \mathbb{R}$):**
    $$\forall \varepsilon > 0 \ \exists \delta > 0 \ \forall x \in \mathbb{R}: 0 < |x - a| < \delta \implies |f(x) - A| < \varepsilon$$
  * *Poznámka:* Limita v bodě $a$ vůbec **nezávisí na hodnotě $f(a)$**; funkce $f$ v bodě $a$ ani nemusí být definována (zajímá nás pouze chování na prstencovém okolí $P(a, \delta)$).
* **Jednostranné limity a Heineho věta:**
  * **Jednostranné limity:** Limita zprava $\lim_{x \to a^+} f(x)$ uvažuje $x \in (a, a+\delta)$; limita zleva $\lim_{x \to a^-} f(x)$ uvažuje $x \in (a-\delta, a)$. Oboustranná limita existuje $\iff \lim_{x \to a^+} f(x) = \lim_{x \to a^-} f(x) = A$.
  * **Heineho věta (most mezi funkcemi a posloupnostmi):**
    $\lim_{x \to a} f(x) = A \iff$ pro každou posloupnost $(x_n)$ v definičním oboru splňující $x_n \ne a$ a $\lim_{n \to \infty} x_n = a$ platí $\lim_{n \to \infty} f(x_n) = A$.
* **Aritmetika limit funkcí:**
  Nechť $\lim_{x \to a} f(x) = A \in \mathbb{R}^*$ a $\lim_{x \to a} g(x) = B \in \mathbb{R}^*$. Pokud mají výrazy v $\mathbb{R}^*$ smysl:
  1. $\lim_{x \to a} (f(x) \pm g(x)) = A \pm B$
  2. $\lim_{x \to a} (f(x) \cdot g(x)) = A \cdot B$
  3. $\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{A}{B}$ (pokud navíc $g(x) \ne 0$ na nějakém $P(a, \delta)$ a $B \ne 0$).
* **Limity funkcí a uspořádání:**
  1. **Zachování ostré nerovnosti:** Pokud $\lim_{x \to a} f(x) > \lim_{x \to a} g(x)$, pak $\exists \delta > 0 \ \forall x \in P(a, \delta): f(x) > g(x)$.
  2. **Přechod k limitě:** Pokud na nějakém $P(a, \delta)$ platí $f(x) \le g(x)$, pak $\lim_{x \to a} f(x) \le \lim_{x \to a} g(x)$.
  3. **Věta o dvou policajtech pro funkce:** Pokud na nějakém $P(a, \delta)$ platí $f(x) \le h(x) \le g(x)$ a $\lim_{x \to a} f(x) = \lim_{x \to a} g(x) = A \in \mathbb{R}^*$, potom existuje i limita $h(x)$ a $\lim_{x \to a} h(x) = A$.
* **Věta o limitě složené funkce (VOLSF):**
  Nechť $\lim_{x \to A} g(x) = B$ a $\lim_{y \to B} f(y) = C$. Potom:
  $$\lim_{x \to A} f(g(x)) = C$$
  pokud je splněna **alespoň jedna** z následujících podmínek:
  * **(P1) Spojitost vnější funkce:** Funkce $f$ je spojitá v bodě $B$ (tj. $f(B) = C$).
  * **(P2) Nenabývání limitní hodnoty:** Na nějakém prstencovém okolí $P(A, \eta)$ funkce $g$ nenabývá své limity $B$, tj. $\forall x \in P(A, \eta): g(x) \ne B$.

#### Funkce spojité na intervalu a jejich vlastnosti:
* **Spojitost v bodě a na intervalu:**
  * **Spojitost v bodě:** Funkce $f$ je spojitá v bodě $a \in \mathbb{R} \iff \lim_{x \to a} f(x) = f(a)$ (limita se rovná funkční hodnotě).
  * **Spojitost na intervalu $I$:** Funkce $f$ je spojitá na intervalu $I$, je-li spojitá v každém vnitřním bodě $I$ a v případných krajních bodech je jednostranně spojitá zevnitř intervalu.
* **Věta o nabývání mezihodnot (Bolzano-Darbouxova věta):**
  Nechť funkce $f$ je spojitá na uzavřeném intervalu $[a, b]$.
  Označme $m = \min\{f(a), f(b)\}$ a $M = \max\{f(a), f(b)\}$.
  Potom pro každé číslo $y \in [m, M]$ existuje alespoň jedno $c \in [a, b]$ takové, že:
  $$f(c) = y$$
  * **Důsledek (Bolzanova věta o kořeni):** Pokud $f$ je spojitá na $[a, b]$ a $f(a) \cdot f(b) < 0$ (v krajích má opačná znaménka), pak existuje $c \in (a, b)$ takové, že $f(c) = 0$ (funkce protíná osu $x$).
  * **Důsledek pro intervaly:** Spojitý obraz libovolného intervalu je opět interval (spojitá funkce „netrhá“ intervaly).
* **Extrémy a nabývání maxima (Weierstrassova věta o nabývání extrémů):**
  * **Globální (absolutní) extrémy:** Funkce $f$ nabývá v bodě $a \in M$ svého maxima na $M$, pokud $\forall x \in M: f(x) \le f(a)$ (minima, pokud $\forall x \in M: f(x) \ge f(a)$).
  * **Weierstrassova věta:** Nechť $f: [a, b] \to \mathbb{R}$ je spojitá funkce na **uzavřeném a omezeném (kompaktním)** intervalu $[a, b]$. Potom:
    1. Funkce $f$ je na $[a, b]$ **omezená**.
    2. Funkce $f$ na $[a, b]$ **nabývá svého maxima i minima**, tj. existují body $x_{min}, x_{max} \in [a, b]$ takové, že:
       $$\forall x \in [a, b]: f(x_{min}) \le f(x) \le f(x_{max})$$
    *(Odtud plyne, že obrazem uzavřeného intervalu $[a, b]$ spojitou funkcí je opět uzavřený omezený interval $[f(x_{min}), f(x_{max})]$).*

#### Derivace funkce a základní pravidla pro výpočet:
* **Definice derivace v bodě:**
  Nechť $f$ je definována na okolí bodu $b \in \mathbb{R}$. Derivace funkce $f$ v bodě $b$ je limita:
  $$f'(b) = \lim_{h \to 0} \frac{f(b + h) - f(b)}{h} = \lim_{x \to b} \frac{f(x) - f(b)}{x - b} \in \mathbb{R}^*$$
  * *Jednostranné derivace:* $f'_+(b)$ pro $h \to 0^+$ (resp. $x \to b^+$), $f'_-(b)$ pro $h \to 0^-$. Oboustranná derivace existuje $\iff f'_+(b) = f'_-(b)$.
  * **Geometrický význam:** Směrnice tečny ke grafu funkce v bodě $[b, f(b)]$. Rovnice tečny má tvar: $y - f(b) = f'(b)(x - b)$.
  * **Fyzikální význam:** Okamžitá rychlost změny veličiny $f$ v čase $b$.
* **Diferencovatelnost a spojitost:**
  * Má-li funkce $f$ v bodě $b$ **vlastní derivaci** ($f'(b) \in \mathbb{R}$), pak je v bodě $b$ **spojitá**.
  * *(Obrácená implikace neplatí! Např. $f(x) = |x|$ je v $0$ spojitá, ale $f'_+(0) = 1 \ne -1 = f'_-(0)$, derivace neexistuje).*
* **Aritmetika derivací (Základní algebraická pravidla):**
  Nechť $f, g$ mají v bodě $b$ vlastní derivaci:
  1. **Součet a rozdíl:** $(f \pm g)'(b) = f'(b) \pm g'(b)$
  2. **Násobek konstantou:** $(\alpha f)'(b) = \alpha f'(b)$ pro $\alpha \in \mathbb{R}$
  3. **Součin (Leibnizovo pravidlo):** $(f \cdot g)'(b) = f'(b)g(b) + f(b)g'(b)$
  4. **Podíl:** $\left(\frac{f}{g}\right)'(b) = \frac{f'(b)g(b) - f(b)g'(b)}{g(b)^2}$ (pokud $g(b) \ne 0$)
  5. **Řetízkové pravidlo (derivace složené funkce):** $(f(g(x)))' = f'(g(x)) \cdot g'(x)$
  6. **Derivace inverzní funkce:** $(f^{-1})'(y_0) = \frac{1}{f'(x_0)}$, kde $y_0 = f(x_0)$ a $f'(x_0) \ne 0$.
* **Souhrn vzorců základních derivací:**
  * $(x^n)' = n x^{n-1} \quad (n \in \mathbb{R}, x > 0)$
  * $(e^x)' = e^x, \quad (a^x)' = a^x \ln a$
  * $(\ln x)' = \frac{1}{x}, \quad (\log_a x)' = \frac{1}{x \ln a}$
  * $(\sin x)' = \cos x, \quad (\cos x)' = -\sin x$
  * $(\operatorname{tg} x)' = \frac{1}{\cos^2 x}, \quad (\operatorname{cotg} x)' = -\frac{1}{\sin^2 x}$
  * $(\arcsin x)' = \frac{1}{\sqrt{1-x^2}}, \quad (\arccos x)' = -\frac{1}{\sqrt{1-x^2}}$
  * $(\operatorname{arctg} x)' = \frac{1}{1+x^2}, \quad (\operatorname{arccotg} x)' = -\frac{1}{1+x^2}$

#### l'Hospitalovo pravidlo a vyšetření průběhu funkcí:
* **l'Hospitalovo pravidlo:**
  Nechť $a \in \mathbb{R}^*$, funkce $f, g$ mají na prstencovém okolí $P(a, \delta)$ vlastní derivaci a $g'(x) \ne 0$.
  Jestliže platí jedna z podmínek:
  1. $\lim_{x \to a} f(x) = \lim_{x \to a} g(x) = 0$ (typ $\frac{0}{0}$), **nebo**
  2. $\lim_{x \to a} |g(x)| = +\infty$ (typ $\frac{\text{cokoliv}}{\pm\infty}$),
  potom platí:
  $$\lim_{x \to a} \frac{f'(x)}{g'(x)} = A \in \mathbb{R}^* \implies \lim_{x \to a} \frac{f(x)}{g(x)} = A$$
  *(Platí i pro jednostranné limity).*
  * **Kdy a jak l'Hospitala používat v praxi:**
    * **Přímé použití:** Pouze u podílů typu $\frac{0}{0}$ a $\frac{\pm\infty}{\pm\infty}$, kde derivace čitatele a jmenovatele výraz zjednoduší (např. polynomy, goniometrie, $e^x, \ln x$).
    * **Převod ostatních neurčitých výrazů na podíl:**
      * Typ $0 \cdot \infty$: přepíšeme jako zlomek $f \cdot g = \frac{f}{1/g}$ (tím vznikne $\frac{0}{0}$ nebo $\frac{\infty}{\infty}$).
      * Typ $\infty - \infty$: převedeme na společného jmenovatele do jednoho zlomku.
      * Typy $1^\infty, \infty^0, 0^0$: přepíšeme přes exponenciálu $f(x)^{g(x)} = e^{g(x) \ln f(x)}$ a l'Hospitala aplikujeme na exponent $g(x) \ln f(x)$ (typ $0 \cdot \infty$).
  * **Kdy l'Hospitala NEPOUŽÍVAT (časté chyby):**
    1. **Není splněn typ $\frac{0}{0}$ ani $\frac{\text{cokoliv}}{\pm\infty}$:** Pokud má zlomek nenulový jmenovatel, l'Hospital dá **zcela špatný výsledek** (např. $\lim_{x \to 0} \frac{x+1}{x+2} = \frac{1}{2}$, ale l'Hospital by dal $\frac{1}{1} = 1$).
    2. **Cyklení derivací:** Když derivování výraz nezjednodušuje, ale točí v kruhu (např. podíly s odmocninami $\frac{x}{\sqrt{x^2+1}}$ nebo $e^x \pm e^{-x}$).
    3. **Limita podílu derivací $\lim \frac{f'}{g'}$ neexistuje:** Např. $\lim_{x \to \infty} \frac{x + \sin x}{x} = 1$, ale derivace $\frac{1 + \cos x}{1}$ v nekonečnu osciluje $\implies$ l'Hospital nelze použít, ale původní limita existuje!
    4. **Složitější rozdíly:** Kde by bylo nutné derivovat 3× a vícekrát po sobě, je často mnohem rychlejší a méně náchylný k chybám **Taylorův polynom**.
* **Monotonie a extrémy (1. derivace):**
  * **Monotonie:** Je-li $f'(x) > 0$ na intervalu, je $f$ **rostoucí**; je-li $f'(x) < 0$, je $f$ **klesající**.
  * **Nutná podmínka pro lokální extrém (Fermatova věta):** Má-li $f$ v bodě $a$ lokální extrém a existuje $f'(a)$, pak $f'(a) = 0$ (**stacionární bod**).
  * **Hledání lokálních extrémů:** Extrém může nastat **pouze** ve stacionárních bodech ($f'(a) = 0$) nebo v bodech, kde derivace neexistuje.
  * **Postačující podmínka:** Mění-li $f'$ v bodě $a$ znaménko z $+$ na $-$, jde o **lokální maximum**; z $-$ na $+$, jde o **lokální minimum** (případně test 2. derivací: $f'(a) = 0$ a $f''(a) > 0 \implies$ lokální minimum; $f''(a) < 0 \implies$ lokální maximum).
* **Konvexita, konkavita a inflexní body (2. derivace):**
  * **Konvexita:** Graf leží pod sečnou (prohnutý jako „U“, leží nad tečnami): $f(x) \le f(a) + (x-a)\frac{f(b)-f(a)}{b-a}$ pro $a < x < b$.
    * Kritérium: $f''(x) > 0$ na intervalu $\implies f$ je **ryze konvexní**.
  * **Konkavita:** Graf leží nad sečnou (tvar kopce, leží pod tečnami):
    * Kritérium: $f''(x) < 0$ na intervalu $\implies f$ je **ryze konkávní**.
  * **Inflexní bod:** Bod, v němž funkce přechází z konvexní na konkávní (nebo naopak) a existuje v něm tečna.
    * Nutná podmínka: $f''(x_0) = 0$ nebo $f''(x_0)$ neexistuje. Postačující podmínka: $f''$ mění v $x_0$ znaménko.
* **Systematický postup vyšetření průběhu funkce v praxi:**
  1. **Definiční obor $D(f)$, spojitost, symetrie:** Určit $D(f)$, nulové body ($f(x) = 0$), průsečík s osou $y$, sudost ($f(-x) = f(x)$), lichost ($f(-x) = -f(x)$) a periodicitu.
  2. **Limity v krajních bodech a asymptoty:** Spočíst limity v krajích $D(f)$ (včetně bodů nespojitosti $\implies$ svislé asymptoty $x = x_0$).
     * *Asymptoty v $\pm\infty$ ($y = kx + q$):* $k = \lim_{x \to \pm\infty} \frac{f(x)}{x}$, $q = \lim_{x \to \pm\infty} (f(x) - kx)$ (pokud jsou obě limity vlastní).
  3. **1. derivace (Monotonie a extrémy):** Spočíst $f'(x)$, nalézt stacionární body ($f'(x) = 0$) a body neexistence derivace, určit intervaly růstu a poklesu, vyčíslit funkční hodnoty v lokálních extrémech.
  4. **2. derivace (Konvexita, konkavita, inflexe):** Spočíst $f''(x)$, nalézt body, kde $f''(x) = 0$, určit intervaly konvexity ($f'' > 0$) a konkavity ($f'' < 0$), určit inflexní body.
  5. **Obor hodnot $H(f)$ a náčrt grafu:** Zanést všechny klíčové body (průsečíky, extrémy, inflexní body) a asymptoty do kartézské soustavy a načrtnout křivku.

#### Taylorův polynom (limitní forma):
* **Definice Taylorova polynomu:**
  Nechť $f$ má v bodě $a \in \mathbb{R}$ vlastní $n$-tou derivaci ($n \in \mathbb{N}_0$). **Taylorův polynom stupně $n$** funkce $f$ v bodě $a$ je:
  $$T_n^{f, a}(x) = \sum_{k=0}^n \frac{f^{(k)}(a)}{k!} (x - a)^k = f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \dots + \frac{f^{(n)}(a)}{n!}(x-a)^n$$
  *(Pro střed $a = 0$ se nazývá **Maclaurinův polynom**).*
* **Taylorova věta s Peanovým tvarem zbytku (Limitní forma):**
  Nechť $f$ má v bodě $a$ vlastní $n$-tou derivaci. Potom:
  $$f(x) - T_n^{f, a}(x) = o((x - a)^n) \quad \text{pro } x \to a$$
  což znamená, že chyba aproximace klesá k nule rychleji než $(x - a)^n$:
  $$\lim_{x \to a} \frac{f(x) - T_n^{f, a}(x)}{(x - a)^n} = 0$$
  * *Význam:* $T_n^{f, a}(x)$ je **jediný polynom stupně $\le n$**, který má v bodě $a$ stejnou funkční hodnotu i všechny derivace až do řádu $n$ jako funkce $f$. Slouží k přesné aproximaci funkcí v okolí bodu $a$ a k rychlému výpočtu limit typu $\frac{0}{0}$.
* **Jak v praxi použít Taylorův polynom na výpočet limit (v krocích):**
  1. **Zvolíme střed rozvoje:** Obvykle počítáme limitu pro $x \to 0$ (pokud $x \to x_0 \ne 0$, posuneme substitucí $t = x - x_0 \to 0$).
  2. **Určíme řád rozvoje $n$ podle jmenovatele:** Zjistíme, jakou mocninu $x^n$ má jmenovatel (např. pro $x^3$ musíme čitatel rozvinout do řádu alespoň $n = 3$, aby se členy nevyrušily do nuly).
  3. **Nahradíme funkce jejich Maclaurinovými polynomy:** Dosadíme známé rozvoje se zbytkem $+ o(x^n)$.
  4. **Algebraicky sloučíme členy:** Konstanty a nižší mocniny se odečtou (vyruší neurčitost).
  5. **Vytkneme $x^n$ a pokrátíme:** Protože $\frac{o(x^n)}{x^n} \to 0$ pro $x \to 0$, rovnou zbude výsledná hodnota limity.
  * *Příklad (proč je lepší než l'Hospital):* $\lim_{x \to 0} \frac{x - \sin x}{x^3} = \lim_{x \to 0} \frac{x - (x - \frac{x^3}{6} + o(x^3))}{x^3} = \lim_{x \to 0} \frac{\frac{x^3}{6} + o(x^3)}{x^3} = \frac{1}{6}$ (na 2 řádky bez nutnosti 3× po sobě derivovat l'Hospitalem!).
* **Základní Maclaurinovy polynomy v bodě $a = 0$:**
  * $e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots + \frac{x^n}{n!} + o(x^n)$
  * $\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots + (-1)^k \frac{x^{2k+1}}{(2k+1)!} + o(x^{2k+2})$
  * $\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots + (-1)^k \frac{x^{2k}}{(2k)!} + o(x^{2k+1})$
  * $\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \dots + (-1)^{n-1} \frac{x^n}{n} + o(x^n)$
  * $\frac{1}{1 - x} = 1 + x + x^2 + \dots + x^n + o(x^n)$

#### Integrály a jejich aplikace:
* **Primitivní funkce (Neurčitý integrál):**
  * **Definice:** Nechť $I \subseteq \mathbb{R}$ je otevřený interval a $f: I \to \mathbb{R}$. Funkce $F: I \to \mathbb{R}$ je **primitivní funkcí** k $f$ na intervalu $I$, pokud pro všechna $x \in I$ platí:
    $$F'(x) = f(x)$$
    Množinu všech primitivních funkcí k $f$ značíme neurčitým integrálem $\int f(x) \, dx = F(x) + c$ ($c \in \mathbb{R}$ je integrační konstanta).
  * *Vlastnost:* Každé dvě primitivní funkce $F_1, F_2$ k téže funkci $f$ na intervalu $I$ se liší pouze o aditivní konstantu: $F_1(x) - F_2(x) = c$.
  * *Existence:* Každá spojitá funkce na intervalu $I$ má na $I$ primitivní funkci.
* **Metody výpočtu primitivní funkce:**
  1. **Integrace per partes (podle částí):**
     $$\int u'(x) v(x) \, dx = u(x) v(x) - \int u(x) v'(x) \, dx$$
     * *Kdy použít:* U součinu dvou různých typů funkcí:
       * polynom $\times$ exponenciála/goniometrie (např. $x e^x, x \sin x$): derivujeme polynom $v = x \implies v' = 1$, integrujeme $u' = e^x \implies u = e^x$.
       * polynom $\times$ logaritmus/cyklometrie (např. $x \ln x, 1 \cdot \operatorname{arctg} x$): integrujeme polynom $u' = x \implies u = \frac{x^2}{2}$, derivujeme $v = \ln x \implies v' = \frac{1}{x}$.
       * cyklický per partes (např. $e^x \sin x$): po dvou integracích per partes vyjádříme původní integrál jako neznámou z rovnice.
  2. **Substituční metoda:**
     * *1. věta o substituci (zjednodušení vnitřní funkce):*
       $$\int f(\varphi(t)) \cdot \varphi'(t) \, dt = \int f(u) \, du = F(u) + c = F(\varphi(t)) + c \quad (\text{substituce } u = \varphi(t), \, du = \varphi'(t) dt)$$
       *Kdy použít:* Když je v integrálu přítomen výraz $\varphi(t)$ a zároveň vedle něj jeho derivace $\varphi'(t)$ (např. $\int \sin^3(x) \cos(x) dx \to \text{sub } u = \sin x, du = \cos x dx \implies \int u^3 du = \frac{u^4}{4}$).
     * *Speciální případ (logaritmická integrace):* $\int \frac{f'(x)}{f(x)} \, dx = \ln |f(x)| + c$.
     * *2. věta o substituci (odstranění odmocnin):* $\int f(x) dx = \int f(\varphi(t)) \varphi'(t) dt$, kde $x = \varphi(t)$ je ryze monotónní s $\varphi' \ne 0$, po integraci dosadíme zpět $t = \varphi^{-1}(x)$.
* **Souhrn vzorců základních neurčitých integrálů:**
  * $\int x^n \, dx = \frac{x^{n+1}}{n+1} + c \quad (n \ne -1)$
  * $\int \frac{1}{x} \, dx = \ln |x| + c$
  * $\int e^x \, dx = e^x + c, \quad \int a^x \, dx = \frac{a^x}{\ln a} + c$
  * $\int \sin x \, dx = -\cos x + c, \quad \int \cos x \, dx = \sin x + c$
  * $\int \frac{1}{\cos^2 x} \, dx = \operatorname{tg} x + c, \quad \int \frac{1}{\sin^2 x} \, dx = -\operatorname{cotg} x + c$
  * $\int \frac{1}{1 + x^2} \, dx = \operatorname{arctg} x + c, \quad \int \frac{1}{\sqrt{1 - x^2}} \, dx = \arcsin x + c$
* **Riemannův integrál (Kompaktní definice):**
  * Pro omezenou funkci $f$ na $[a, b]$ a dělení $D = (a = x_0 < x_1 < \dots < x_n = b)$ definujeme:
    * **Dolní součet:** $s(f, D) = \sum_{i=0}^{n-1} \inf_{x \in I_i} f(x) \cdot (x_{i+1} - x_i)$ (součet vepsaných obdélníků pod grafem).
    * **Horní součet:** $S(f, D) = \sum_{i=0}^{n-1} \sup_{x \in I_i} f(x) \cdot (x_{i+1} - x_i)$ (součet opsaných obdélníků nad grafem).
  * **Dolní a horní integrál:** $\underline{\int_a^b} f = \sup_D s(f, D)$ a $\overline{\int_a^b} f = \inf_D S(f, D)$ (přes **všechna** možná dělení $D$).
  * *Kde je v definici schované „$n \to \infty$“:* Uvažujeme množinu **všech možných dělení $D$**. Přidáním dělících bodů (zjemněním dělení) se dolní součet zvětšuje ($s(f, D) \le s(f, D')$). Abychom dosáhli **suprema** $\sup_D$, bereme stále jemnější a jemnější dělení z této množiny všech dělení, kde počet dílků roste do nekonečna ($n \to \infty$).
  * **Definice Riemannova integrálu:** Funkce $f$ je riemannovsky integrovatelná ($f \in \mathcal{R}[a, b]$), pokud se dolní a horní integrál **rovnají a jsou konečné**:
    $$\int_a^b f(x) \, dx = \underline{\int_a^b} f = \overline{\int_a^b} f \in \mathbb{R}$$
  * *Které funkce jsou integrovatelné:* Každá **spojitá** funkce na $[a, b]$ a každá **monotónní** omezená funkce na $[a, b]$.
* **Souvislost s primitivní funkcí a Newtonovým integrálem:**
  * **1. základní věta analýzy (Integrál jako funkce horní meze):** Je-li $f \in \mathcal{R}[a, b]$, pak funkce $F(x) = \int_a^x f(t) \, dt$ je spojitá na $[a, b]$ a v každém bodě spojitosti $x_0$ funkce $f$ platí $F'(x_0) = f(x_0)$ (tj. $F$ je primitivní funkcí k $f$!).
  * **2. základní věta analýzy (Newtonova-Leibnizova formule):** Má-li $f$ na intervalu $(a, b)$ primitivní funkci $F$ spojitou na $[a, b]$, potom:
    $$\int_a^b f(x) \, dx = [F(x)]_a^b = F(b) - F(a)$$
    *(Pro spojité funkce na $[a, b]$ se tedy Riemannův integrál přesně rovná Newtonovu integrálu).*
* **Aplikace určitého integrálu v geometrii a analýze:**
  1. **Obsahy rovinných útvarů:**
     * Plocha pod grafem nezáporné funkce $f(x) \ge 0$ na $[a, b]$: $S = \int_a^b f(x) \, dx$.
     * Plocha mezi dvěma křivkami $f(x) \ge g(x)$ na $[a, b]$:
       $$S = \int_a^b (f(x) - g(x)) \, dx$$
       *(V praxi nejprve najdeme průsečíky $f(x) = g(x)$, které určí meze integrace $a, b$, a integrujeme horní křivku mínus dolní).*
  2. **Délka křivky:**
     * Délka grafu hladké funkce $y = f(x)$ pro $x \in [a, b]$:
       $$L = \int_a^b \sqrt{1 + (f'(x))^2} \, dx$$
  3. **Objemy a povrchy rotačních těles (Rotace kolem osy $x$ pro $x \in [a, b]$):**
     * **Objem rotačního tělesa:** Vzniklé rotací plochy pod grafem $f(x) \ge 0$:
       $$V = \pi \int_a^b f(x)^2 \, dx$$
       *(Intuice: součet objemů tenkých válcových disků o poloměru $r = f(x)$ a výšce $dx$, kde $dV = \pi r^2 dx$).*
     * **Povrch (plášť) rotačního tělesa:**
       $$S_{pl} = 2\pi \int_a^b f(x) \sqrt{1 + (f'(x))^2} \, dx$$
       *(Intuice: obvod podstavy $2\pi f(x)$ krát délka elementu křivky $dL = \sqrt{1 + (f')^2} dx$).*
  4. **Odhady součtu řad (konečných i nekonečných):**
     * **Integrální odhad konečného součtu:** Pro neklesající funkci $f$ na $[1, n]$:
       $$\sum_{k=1}^{n-1} f(k) \le \int_1^n f(x) \, dx \le \sum_{k=2}^n f(k)$$
     * **Integrální kritérium konvergence nekonečných řad:** Nechť $f$ je kladná a nerostoucí na $[1, \infty)$ t.ž. $a_n = f(n)$. Potom:
       $$\sum_{n=1}^\infty a_n \text{ konverguje} \iff \int_1^\infty f(x) \, dx < \infty$$
       *(Příklad použití: pro řadu $\sum_{n=1}^\infty \frac{1}{n^s}$ spočteme $\int_1^\infty \frac{1}{x^s} dx = [\frac{x^{1-s}}{1-s}]_1^\infty$, což konverguje právě pro $s > 1$).*

### Lingebra
#### Algebraické struktury (Grupy, permutace a tělesa):
* **Grupa $(G, \circ)$:** Množina $G$ s binární operací $\circ: G \times G \to G$ splňující:
  1. **Asociativita:** $\forall a, b, c \in G: a \circ (b \circ c) = (a \circ b) \circ c$.
  2. **Neutrální prvek:** $\exists e \in G \ \forall a \in G: a \circ e = e \circ a = a$.
  3. **Inverzní prvek:** $\forall a \in G \ \exists a^{-1} \in G: a \circ a^{-1} = a^{-1} \circ a = e$.
  * **Abelovská (komutativní) grupa:** Navíc platí $\forall a, b \in G: a \circ b = b \circ a$.
* **Podgrupa ($H \le G$):** Podmnožina $H \subseteq G$, která je sama grupou se zúženou operací (ekvivalentně: $e \in H$ a $\forall a, b \in H: a \circ b^{-1} \in H$).
* **Permutace a symetrická grupa $S_n$:** Permutace množiny $[n]$ je bijekce $p: [n] \to [n]$.
  * **Inverze v permutaci:** Dvojice indexů $(i, j)$ taková, že $i < j$, ale $p(i) > p(j)$.
  * **Znaménko permutace:** $\operatorname{sgn}(p) = (-1)^{\#\text{inverzí}} \in \{+1, -1\}$ (sudá vs. lichá permutace; pro transpozici je $-1$).
  * **Rychlý výpočet znaménka z počtu cyklů:** Každou permutaci $p \in S_n$ lze jednoznačně rozložit na disjunktní cykly. Znaménko se bleskově spočte jako:
    $$\operatorname{sgn}(p) = (-1)^{n - c}$$
    kde $n$ je celkový počet prvků a $c$ je celkový počet cyklů (včetně cyklů délky 1 = pevných bodů!).
    * *Princip / Parita:* Cyklus délky $k$ odpovídá $k - 1$ transpozicím $\implies$ jeho znaménko je $(-1)^{k-1}$ (cyklus sudé délky je lichá permutace, cyklus liché délky je sudá).
* **Těleso $(\mathbb{K}, +, \cdot)$:** Množina $\mathbb{K}$ se dvěma operacemi:
  1. $(\mathbb{K}, +)$ tvoří Abelovskou grupu s neutrálním prvkem $0$.
  2. $(\mathbb{K} \setminus \{0\}, \cdot)$ tvoří Abelovskou grupu s neutrálním prvkem $1$.
  3. **Distributivita:** $\forall a, b, c \in \mathbb{K}: a \cdot (b + c) = a \cdot b + a \cdot c$.
* **Charakteristika tělesa:** Nejmenší $n \in \mathbb{N}$ takové, že $\sum_{i=1}^n 1 = 0$ v $\mathbb{K}$. Pokud takové $n$ neexistuje, $\operatorname{char}(\mathbb{K}) = 0$ (např. $\mathbb{Q}, \mathbb{R}, \mathbb{C}$). Charakteristika je vždy $0$ nebo prvočíslo $p$.
* **Konečná tělesa ($GF(p^n)$ / Galois Fields):** Konečné těleso existuje právě tehdy, když má mohutnost $q = p^n$ ($p$ je prvočíslo, $n \ge 1$). Pro $n=1$ je to těleso zbytkových tříd $\mathbb{Z}_p = (\{0, \dots, p-1\}, +_p, \cdot_p)$.

#### Soustavy lineárních rovnic a eliminace:
* **Maticový zápis:** Soustava $m$ rovnic o $n$ neznámých: $Ax = b$, kde $A \in \mathbb{K}^{m \times n}$ je matice soustavy, $x \in \mathbb{K}^n$ vektor neznámých, $b \in \mathbb{K}^m$ vektor pravých stran. Rozšířená matice soustavy: $(A \mid b) \in \mathbb{K}^{m \times (n+1)}$.
* **Elementární řádkové úpravy (EŘÚ):** Nemění množinu řešení soustavy:
  1. Vynásobení řádku nenulovým skalárem $t \in \mathbb{K} \setminus \{0\}$.
  2. Přičtení $t$-násobku jednoho řádku k jinému řádku.
  3. Záměna (prohození) dvou řádků.
* **Odstupňovaný tvar matice (REF – Row Echelon Form):**
  * Nulové řádky jsou umístěny pod všemi nenulovými řádky.
  * První nenulový prvek každého nenulového řádku se nazývá **pivot**.
  * Pivot v každém nižším řádku leží ve sloupci přísně více vpravo než pivot v předchozím řádku ($j(1) < j(2) < \dots < j(r)$).
* **Redukovaný odstupňovaný tvar (RREF):** Matice je v REF a navíc:
  1. Všechny pivoty jsou rovny $1$.
  2. Nad každým pivotem jsou samé nuly (pivot je jediným nenulovým prvkem ve svém sloupci).
* **Gaussova a Gauss-Jordanova eliminace (Idea):**
  * **Gaussova eliminace:** Převod matice na REF pomocí EŘÚ přímým chodem (shora dolů) eliminací prvků pod pivoty $\to$ následné nalezení řešení zpětnou substitucí.
  * **Gauss-Jordanova eliminace:** Rozšíření o zpětný chod (zdola nahoru) – eliminace i prvků nad pivoty a normalizace pivotů na $1 \to$ vzniká RREF (řešení lze přímo vyčíst).
* **Popis množiny řešení soustavy:**
  * **Frobeniova věta:** Soustava $Ax = b$ je řešitelná $\iff \operatorname{rank}(A) = \operatorname{rank}(A \mid b)$.
  * **Struktura řešení:** Množina všech řešení tvoří afinní podprostor:
    $$x = x_p + x_h = x_p + \operatorname{Ker}(A)$$
    kde $x_p$ je libovolné **partikulární řešení** ($Ax_p = b$) a $x_h \in \operatorname{Ker}(A)$ je obecné řešení homogenní soustavy ($Ax = 0$).
  * **Parametry (volné neznámé):** Proměnné ve sloupcích bez pivotů se volí jako nezávislé parametry. Počet parametrů je $n - \operatorname{rank}(A) = \dim(\operatorname{Ker}(A))$.

#### Matice, hodnost a regulární matice:
* **Operace s maticemi:**
  * **Násobení matic:** Pro $A \in \mathbb{K}^{m \times p}$ a $B \in \mathbb{K}^{p \times n}$ je $AB \in \mathbb{K}^{m \times n}$, kde $(AB)_{i, j} = \sum_{k=1}^p A_{i, k} B_{k, j}$. (Asociativní, nekomutativní).
  * **Transpozice matice:** Pro $A \in \mathbb{K}^{m \times n}$ je transponovaná matice $A^T \in \mathbb{K}^{n \times m}$ definována $(A^T)_{i, j} = A_{j, i}$ (překlopení podle hlavní diagonály). Platí $(AB)^T = B^T A^T$ a $(A^T)^T = A$.
  * **Symetrická matice:** Čtvercová matice splňující $A = A^T$ ($A_{i, j} = A_{j, i}$).
* **Hodnost matice $\operatorname{rank}(A)$:** Počet lineárně nezávislých řádků (sloupců), což odpovídá počtu pivotů v libovolném REF tvaru matice. Platí $\operatorname{rank}(A) = \operatorname{rank}(A^T) \le \min(m, n)$.
* **Inverzní matice $A^{-1}$:** K čtvercové matici $A \in \mathbb{K}^{n \times n}$ je to matice splňující $A \cdot A^{-1} = A^{-1} \cdot A = I_n$ (počítá se eliminací $(A \mid I_n) \sim (I_n \mid A^{-1})$).
* **Ekvivalentní charakteristiky regulární matice (Zkouškový přehled):**
  Pro čtvercovou matici $A \in \mathbb{K}^{n \times n}$ jsou následující tvrzení ekvivalentní:
  1. $A$ je **regulární** (existuje inverzní matice $A^{-1}$).
  2. $\det(A) \ne 0$ (matice s $\det(A) = 0$ je **singulární**).
  3. $\operatorname{rank}(A) = n$ (plná hodnost).
  4. $\operatorname{Ker}(A) = \{0\}$ (homogenní soustava $Ax = 0$ má pouze triviální nulové řešení).
  5. Soustava $Ax = b$ má pro každou pravou stranu $b$ právě jedno řešení ($x = A^{-1}b$).
  6. Řádky (resp. sloupce) matice $A$ jsou lineárně nezávislé a tvoří bázi $\mathbb{K}^n$.
  7. RREF tvar matice $A$ je jednotková matice $I_n$.
  8. $0$ není vlastním číslem matice $A$.

#### Vektorové prostory a podprostory:
* **Vektorový prostor $(V, +, \cdot)$ nad tělesem $\mathbb{K}$:** Množina vektorů $V$ s operacemi sčítání $+: V \times V \to V$ a násobení skalárem $\cdot: \mathbb{K} \times V \to V$, kde $(V, +)$ je Abelovská grupa a pro skaláry platí:
  1. $1 \cdot v = v$, $\quad (a \cdot b) \cdot v = a \cdot (b \cdot v)$,
  2. $(a + b) \cdot v = a \cdot v + b \cdot v$, $\quad a \cdot (u + v) = a \cdot u + a \cdot v$.
* **Lineární kombinace a nezávislost:**
  * **Lineární kombinace:** Vektor $\sum_{i=1}^k a_i v_i$ pro $a_i \in \mathbb{K}, v_i \in V$.
  * **Lineární nezávislost (LN):** Množina vektorů $\{v_1, \dots, v_k\}$ je LN $\iff \sum_{i=1}^k a_i v_i = 0$ nastává pouze pro triviální volbu $a_1 = \dots = a_k = 0$. (Lineárně závislá: jeden vektor lze vyjádřit jako lin. kombinaci ostatních).
* **Lineární obal a systém generátorů:**
  * **Lineární obal $\operatorname{span}(X) = \mathcal{L}(X)$:** Množina všech konečných lineárních kombinací vektorů z $X$ (nejmenší podprostor obsahující $X$).
  * **Systém generátorů:** Množina $X \subseteq V$ generuje $V$, pokud $\mathcal{L}(X) = V$.
* **Steinitzova věta o výměně:**
  Nechť $X$ je konečná lineárně nezávislá množina ve $V$ a $Y$ je systém generátorů $V$. Potom:
  1. $|X| \le |Y|$ (žádná lineárně nezávislá množina nemůže mít více prvků než systém generátorů).
  2. Existuje podmnožina $Z \subseteq Y$ o velikosti $|Z| = |Y| - |X|$ taková, že $\mathcal{L}(X \cup Z) = V$ (vektory z $X$ lze doplnit vhodnými vektory z $Y$ na systém generátorů).
* **Báze, dimenze a souřadnice:**
  * **Báze $B$:** Lineárně nezávislý systém generátorů prostoru $V$ (minimální systém generátorů / maximální LN množina).
  * **Dimenze $\dim(V)$:** Počet prvků libovolné báze prostoru $V$ (dle Steinitzovy věty mají všechny báze stejnou mohutnost).
  * **Vektor souřadnic $[u]_B$:** Pro uspořádanou bázi $B = (v_1, \dots, v_n)$ jsou souřadnice vektoru $u \in V$ jednoznačně určené skaláry $(a_1, \dots, a_n)^T \in \mathbb{K}^n$ takové, že $u = \sum_{i=1}^n a_i v_i$.
* **Maticové podprostory (pro matici $A \in \mathbb{K}^{m \times n}$):**
  * **Jádro (nulový prostor):** $\operatorname{Ker}(A) = \{x \in \mathbb{K}^n \mid Ax = 0\} \le \mathbb{K}^n$.
  * **Řádkový prostor:** $\operatorname{Row}(A) = \mathcal{L}(\text{řádky } A) = \{A^T y \mid y \in \mathbb{K}^m\} \le \mathbb{K}^n$.
  * **Sloupcový prostor (obraz):** $\operatorname{Col}(A) = \mathcal{L}(\text{sloupce } A) = \{Ax \mid x \in \mathbb{K}^n\} \le \mathbb{K}^m$.
  * **Věta o dimenzích (Rank-Nullity teorém):**
    $$\dim(\operatorname{Row}(A)) = \dim(\operatorname{Col}(A)) = \operatorname{rank}(A), \quad \dim(\operatorname{Ker}(A)) = n - \operatorname{rank}(A)$$
  * **Ortogonalita řádkového prostoru a jádra:**
    $$\operatorname{Row}(A) \perp \operatorname{Ker}(A) \quad (\text{v } \mathbb{R}^n \text{ platí } \operatorname{Ker}(A) = (\operatorname{Row}(A))^\perp \text{ a } \operatorname{Row}(A) = (\operatorname{Ker}(A))^\perp)$$
    Pro symetrické matice ($A = A^T$) navíc platí $\operatorname{Row}(A) = \operatorname{Col}(A)$.

#### Lineární zobrazení a isomorfismus:
* **Lineární zobrazení $f: U \to V$ (mezi prostory nad stejným tělesem $\mathbb{K}$):**
  Zobrazení zachovávající operace sčítání vektorů a násobení skalárem:
  1. $f(u + v) = f(u) + f(v)$ pro všechny $u, v \in U$.
  2. $f(a \cdot u) = a \cdot f(u)$ pro všechny $a \in \mathbb{K}, u \in U$.
* **Jádro a obraz zobrazení:**
  * **Jádro $\operatorname{Ker}(f) = \{u \in U \mid f(u) = 0\} \le U$.** Zobrazení $f$ je **prosté (injektivní)** $\iff \operatorname{Ker}(f) = \{0\}$.
  * **Obraz $\operatorname{Im}(f) = f(U) = \{f(u) \mid u \in U\} \le V$.** Zobrazení $f$ je **na (surjektivní)** $\iff \operatorname{Im}(f) = V$.
  * **Věta o dimenzi jádra a obrazu:** $\dim(U) = \dim(\operatorname{Ker}(f)) + \dim(\operatorname{Im}(f))$.
* **Maticová reprezentace zobrazení vůči bázím:**
  Nechť $B_U = (u_1, \dots, u_n)$ je báze $U$ a $B_V = (v_1, \dots, v_m)$ báze $V$. Matice zobrazení $_{B_V}[f]_{B_U} \in \mathbb{K}^{m \times n}$ má ve sloupcích souřadnice obrazů bázových vektorů vzoru vyjádřené v bázi cíle:
  $$_{B_V}[f]_{B_U} = \begin{pmatrix} \mid & & \mid \\ [f(u_1)]_{B_V} & \dots & [f(u_n)]_{B_V} \\ \mid & & \mid \end{pmatrix}$$
  * **Přepočet souřadnic obrazu:** $[f(x)]_{B_V} = {_{B_V}[f]_{B_U}} \cdot [x]_{B_U}$.
  * **Matice složeného zobrazení:** Pro $f: U \to V$ a $g: V \to W$ platí:
    $$_{B_W}[g \circ f]_{B_U} = {_{B_W}[g]_{B_V}} \cdot {_{B_V}[f]_{B_U}}$$
* **Isomorfismus vektorových prostorů:**
  * **Definice:** Bijektivní lineární zobrazení $f: U \to V$ (prostory $U, V$ jsou pak isomorfní, $U \cong V$).
  * **Věta o isomorfismu:** Dva konečně-dimenzionální prostory $U, V$ nad stejným tělesem $\mathbb{K}$ jsou isomorfní $\iff \dim(U) = \dim(V)$.
  * Každý prostor $V$ dimenze $n$ nad $\mathbb{K}$ je isomorfní prostoru aritmetických vektorů $\mathbb{K}^n$ (isomorfismus zprostředkovává zobrazení souřadnic $u \mapsto [u]_B$).

#### Skalární součin, ortogonalita a projekce:
* **Skalární součin:** Zobrazení $\langle \cdot \mid \cdot \rangle: V \times V \to \mathbb{C}$ (resp. $\mathbb{R}$), které dvojici vektorů přiřadí skalár a splňuje 3 základní vlastnosti:
  1. **Pozitivní definitnost:** $\forall u \in V: \langle u \mid u \rangle \in \mathbb{R}_0^+$ (vždy reálné nezáporné číslo $\ge 0$) a zároveň platí rovnost $\langle u \mid u \rangle = 0 \iff u = 0$.
  2. **Konjugovaná symetrie:** $\forall u, v \in V: \langle v \mid u \rangle = \overline{\langle u \mid v \rangle}$ (pro reálné prostory $\mathbb{R}$ je to čistá symetrie $\langle u \mid v \rangle = \langle v \mid u \rangle$).
  3. **Linearita v 1. složce:** $\forall u, v, w \in V, \forall a \in \mathbb{C}$:
     * *Aditivita:* $\langle u + v \mid w \rangle = \langle u \mid w \rangle + \langle v \mid w \rangle$,
     * *Homogenita:* $\langle a u \mid v \rangle = a \langle u \mid v \rangle$ (ve 2. složce z toho plyne antilinearita: $\langle u \mid a v \rangle = \overline{a} \langle u \mid v \rangle$).
  * *Standardní skalární součin v $\mathbb{R}^n$:* $\langle x \mid y \rangle = x^T y = \sum_{i=1}^n x_i y_i$. Geometricky vyjadřuje míru, jak moc jde jeden vektor ve směru druhého ($\langle x \mid y \rangle = \|x\| \|y\| \cos \varphi$).
* **Norma indukovaná skalárním součinem:** Délka (velikost) vektoru: $\|u\| = \sqrt{\langle u \mid u \rangle}$.
* **Základní věty a nerovnosti:**
  * **Pythagorova věta:** Jsou-li $u \perp v$ ($\langle u \mid v \rangle = 0$), potom $\|u + v\|^2 = \|u\|^2 + \|v\|^2$.
  * **Cauchyho-Schwarzova nerovnost:** Pro libovolné vektory $u, v \in V$ platí:
    $$|\langle u \mid v \rangle| \le \|u\| \cdot \|v\|$$
    (Rovnost nastává právě tehdy, když jsou $u, v$ lineárně závislé).
  * **Trojúhelníková nerovnost:** Pro každou indukovanou normu platí $\|u + v\| \le \|u\| + \|v\|$.
* **Ortonormální (ON) systémy a Fourierovy koeficienty:**
  * **Ortogonální systém:** $\forall i \ne j: \langle v_i \mid v_j \rangle = 0$.
  * **Ortonormální systém / báze (ON báze):** Ortogonální systém normovaných vektorů: $\forall i, j: \langle v_i \mid v_j \rangle = \delta_{ij}$ (kde $\delta_{ij} = 1$ pro $i = j$ a $0$ jinak). Každý ON systém je lineárně nezávislý.
  * **Fourierovy koeficienty:** Má-li $V$ ortonormální bázi $Z = (v_1, \dots, v_n)$, pak pro každý vektor $u \in V$ platí:
    $$u = \sum_{i=1}^n \langle u \mid v_i \rangle v_i$$
    kde skaláry $\alpha_i = \langle u \mid v_i \rangle$ jsou **Fourierovy koeficienty** (velikost kolmého průmětu $u$ na bázový vektor $v_i$).
* **Gramova-Schmidtova ortogonalizace (Jak v praxi najít ON bázi):**
  * Vezmeme libovolnou známou bázi $(x_1, \dots, x_n)$ prostoru $V$ (např. bázové vektory řešení homogenní soustavy či sloupců) a algoritmem z ní vytvoříme ortonormální bázi $(z_1, \dots, z_n)$:
  * Pro $k = 1, \dots, n$:
    1. Odečti průměty do předchozích vektorů: $y_k = x_k - \sum_{j=1}^{k-1} \langle x_k \mid z_j \rangle z_j$.
    2. Znormalizuj vektor na jednotkovou délku: $z_k = \frac{y_k}{\|y_k\|}$.
* **Ortogonální doplněk a ortogonální projekce:**
  * **Ortogonální doplněk podmnožiny $V \le W$:** Množina všech vektorů kolmých na celý podprostor $V$:
    $$V^\perp = \{u \in W \mid \forall v \in V: \langle u \mid v \rangle = 0\}$$
    Platí: $(V^\perp)^\perp = V$ a $\dim(V) + \dim(V^\perp) = \dim(W)$ (pro konečně-dimenzionální prostory).
  * **Ortogonální projekce:** Je-li $(v_1, \dots, v_k)$ ON báze podprostoru $V \le W$, pak zobrazení $p_V: W \to V$:
    $$p_V(u) = \sum_{i=1}^k \langle u \mid v_i \rangle v_i$$
    je **lineární zobrazení**, splňuje $u - p_V(u) \in V^\perp$ a vektor $p_V(u)$ je **nejlepší aproximací** vektoru $u$ v podprostoru $V$ (minimalizuje vzdálenost $\|u - v\|$ pro $v \in V$).
* **Ortogonální matice ($Q \in \mathbb{R}^{n \times n}$):**
  * Pro čtvercovou reálnou matici $Q$ jsou ekvivalentní vlastnosti:
    1. $Q^T Q = Q Q^T = I_n$ (inverzní matice se rovná transponované: $Q^{-1} = Q^T$).
    2. Sloupce matice $Q$ tvoří ortonormální bázi $\mathbb{R}^n$.
    3. Řádky matice $Q$ tvoří ortonormální bázi $\mathbb{R}^n$.
    4. $Q$ zachovává skalární součin: $\langle Qx \mid Qy \rangle = \langle x \mid y \rangle$ (izometrie: zachovává délky $\|Qx\| = \|x\|$ i úhly).
    5. $|\det(Q)| = 1$ (tedy $\det(Q) \in \{+1, -1\}$; rotační matice mají $\det = +1$).

#### Determinanty:
* **Definice determinantu (Leibnizova formule):**
  Pro čtvercovou matici $A \in \mathbb{K}^{n \times n}$:
  $$\det(A) = \sum_{p \in S_n} \operatorname{sgn}(p) \prod_{i=1}^n a_{i, p(i)}$$
* **Rychlý výpočet malých determinantů:**
  * **Matice $2 \times 2$:** $\det \begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$.
  * **Matice $3 \times 3$ (Sarrusovo pravidlo):**
    $$\det \begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix} = (aei + bfg + cdh) - (ceg + afh + bdi)$$
    *(Pozor: Sarrusovo pravidlo platí POUZE pro $3 \times 3$, pro $4 \times 4$ a větší neplatí!)*
* **Jak v praxi počítat determinanty větších matic ($4 \times 4$ a více):**
  1. **Převod na horní trojúhelníkový tvar pomocí EŘÚ (Gaussova eliminace – nejrychlejší):** Upravujeme matici do REF. Přičtení násobku řádku hodnotu nemění; hlídáme si prohození řádků (mění znaménko na opačné) a vytknutí skaláru z celého řádku. Výsledný determinant je součin prvků na hlavní diagonále $\prod a_{ii}$.
  2. **Kombinace s Laplaceovým rozvojem:** Pokud má řádek či sloupec hodně nul, rozvineme podle něj (ideálně nejprve pomocí EŘÚ vyrobíme v jednom sloupci nuly všude kromě jediné pozice a pak rozvineme).
* **Základní vlastnosti determinantu:**
  * **Multiplikativnost:** $\det(AB) = \det(A) \cdot \det(B)$.
  * **Determinant transponované matice:** $\det(A^T) = \det(A)$.
  * **Vztah s regularitou:** $A$ je regulární $\iff \det(A) \ne 0$. Pro regulární matici platí $\det(A^{-1}) = \frac{1}{\det(A)}$.
  * **Vztah s vlastními čísly:** Determinant je roven součinu všech vlastních čísel matice (včetně algebraických násobností): $\det(A) = \prod_{i=1}^n \lambda_i$.
  * **Trojúhelníková matice:** Je-li $A$ horní či dolní trojúhelníková (např. v REF tvaru), determinant je součin prvků na hlavní diagonále: $\det(A) = \prod_{i=1}^n a_{ii}$.
  * **Vliv elementárních úprav (EŘÚ):**
    * Prohození dvou řádků/sloupců: násobí determinant $-1$.
    * Vynásobení řádku/sloupce skalárem $c$: násobí determinant číslem $c$ (platí $\det(c \cdot A) = c^n \det(A)$ pro $n \times n$).
    * Přičtení násobku jiného řádku k danému: **nemění** hodnotu determinantu.
* **Laplaceův rozvoj determinantu:**
  * **Rozvoj podle $i$-tého řádku:** $\det(A) = \sum_{j=1}^n a_{ij} (-1)^{i+j} \det(A^{ij})$.
  * **Rozvoj podle $j$-tého sloupce:** $\det(A) = \sum_{i=1}^n a_{ij} (-1)^{i+j} \det(A^{ij})$,
    kde $A^{ij}$ je podmatice vzniklá z $A$ vyškrtnutím $i$-tého řádku a $j$-tého sloupce (člen $(-1)^{i+j} \det(A^{ij})$ je tzv. **algebraický doplněk**).
* **Geometrická interpretace determinantu:**
  * **Objem rovnoběžnostěnu:** Absolutní hodnota $|\det(A)|$ se přesně rovná objemu $n$-rozměrného rovnoběžnostěnu určeného sloupcovými (či řádkovými) vektory matice $A$ (v $\mathbb{R}^2$ plocha rovnoběžníku, v $\mathbb{R}^3$ objem rovnoběžnostěnu).
  * **Znaménko $\operatorname{sgn}(\det(A))$:** Udává, zda transformace zachovává orientaci prostoru ($\det > 0$: zachovává pravotočivost báze, $\det < 0$: mění orientaci / zrcadlí).

#### Vlastní čísla, vlastní vektory a diagonalizace:
* **Vlastní číslo a vlastní vektor:**
  * Pro čtvercovou matici $A \in \mathbb{K}^{n \times n}$ (či operátor $f: V \to V$) je $\lambda \in \mathbb{K}$ **vlastní číslo** a $v \in V \setminus \{0\}$ jemu odpovídající **vlastní vektor**, pokud platí:
    $$A v = \lambda v \quad (\iff (A - \lambda I_n)v = 0)$$
  * **Geometrický význam:** Lineární transformace $A$ vektor $v$ pouze **škáluje (natahuje/zkracuje či obrací)** faktorem $\lambda$, ale nemění jeho směr (přímka $\operatorname{span}\{v\}$ je invariantní).
* **Charakteristický polynom a jak v praxi spočíst vlastní čísla:**
  * **Charakteristický polynom:** $p_A(\lambda) = \det(A - \lambda I_n)$ (polynom stupně $n$).
  * **Výpočet v praxi (2 kroky):**
    1. **Nalezení vlastních čísel:** Vyřešíme charakteristickou rovnici $\det(A - \lambda I_n) = 0$. Její kořeny jsou právě vlastní čísla $\lambda_1, \dots, \lambda_n$.
    2. **Nalezení vlastních vektorů:** Pro každé nalezené $\lambda$ dosadíme do rovnice $(A - \lambda I_n)v = 0$ a najdeme bázi jádra $\operatorname{Ker}(A - \lambda I_n)$ pomocí Gaussovy eliminace.
* **Násobnost vlastních čísel:**
  * **Algebraická násobnost:** Násobnost čísla $\lambda$ jako kořene charakteristického polynomu $p_A$.
  * **Geometrická násobnost:** Dimenze podprostoru vlastních vektorů $\dim(\operatorname{Ker}(A - \lambda I_n))$.
  * Platí nerovnost: $1 \le \text{geometrická násobnost} \le \text{algebraická násobnost}$.
* **Základní vlastnosti vlastních čísel:**
  * **Stopa matice $\operatorname{trace}(A)$:** Součet prvků na hlavní diagonále je roven součtu vlastních čísel: $\operatorname{trace}(A) = \sum_{i=1}^n a_{ii} = \sum_{i=1}^n \lambda_i$.
  * **Determinant:** Součin vlastních čísel: $\det(A) = \prod_{i=1}^n \lambda_i$.
  * $A$ je regulární $\iff 0$ není vlastním číslem $A$.
  * Vlastní čísla $A^{-1}$ jsou $\lambda_i^{-1}$, matice $A^k$ má vlastní čísla $\lambda_i^k$, matice $\alpha A$ má $\alpha \lambda_i$, a $A + \alpha I$ má $\lambda_i + \alpha$ (pro stejné vlastní vektory). $A^T$ má stejná vlastní čísla jako $A$.
* **Podobnost matic ($A \sim B$):**
  * Matice $A, B \in \mathbb{K}^{n \times n}$ jsou si podobné, pokud existuje regulární matice $R$ taková, že $A = R^{-1} B R$ (odpovídá témuž operátoru vyjádřenému v různých bázích, $R$ je matice přechodu).
  * *Invarianty podobnosti:* Podobné matice mají stejný charakteristický polynom, stejná vlastní čísla (včetně násobností), stejný determinant, stopu i hodnost.
* **Diagonalizovatelnost a spektrální rozklad:**
  * Matice $A$ je **diagonalizovatelná**, pokud je podobná diagonální matici $\Lambda = \operatorname{diag}(\lambda_1, \dots, \lambda_n)$, tj. existuje regulární matice $S$ taková, že:
    $$A = S \Lambda S^{-1} \quad (\iff S^{-1} A S = \Lambda)$$
  * **Podmínka diagonalizovatelnosti:** Matice $A \in \mathbb{K}^{n \times n}$ je diagonalizovatelná $\iff$:
    1. Prostor $\mathbb{K}^n$ má bázi tvořenou vlastními vektory matice $A$ ($n$ lineárně nezávislých vlastních vektorů).
    2. Pro každé vlastní číslo se jeho **algebraická násobnost rovná geometrické násobnosti** (pokud má nějaké vícenásobné $\lambda$ méně vlastních vektorů než svou násobnost, matice diagonalizovatelná není!).
  * **Jak v praxi matici diagonalizovat (Sestrojení $S$ a $\Lambda$):**
    1. Spočteme vlastní čísla $\lambda_1, \dots, \lambda_n$ $\implies$ položíme je na hlavní diagonálu matice $\Lambda$.
    2. Pro každé $\lambda_i$ vyřešíme soustavu $(A - \lambda_i I_n)v = 0 \implies$ získáme vlastní vektory $v_i$.
    3. Vlastní vektory poskládáme do **sloupců matice $S = (v_1 \mid v_2 \mid \dots \mid v_n)$** ve stejném pořadí, v jakém jsou vlastní čísla na diagonále $\Lambda$ ($j$-tý sloupec v $S$ odpovídá číslu $\lambda_j$).

#### Symetrické matice, pozitivní definitnost a Choleského rozklad:
* **Vlastnosti reálných symetrických matic ($A = A^T$):**
  * Všechna vlastní čísla reálné symetrické matice jsou **reálná** ($\lambda_i \in \mathbb{R}$).
  * Vlastní vektory příslušné různým vlastním číslům jsou navzájem **ortogonální** ($u \perp v$).
  * **Spektrální věta pro symetrické matice:** Každá reálná symetrická matice je **ortogonálně diagonalizovatelná**: existuje **ortogonální matice $Q$** ($Q^{-1} = Q^T$) a diagonální $\Lambda$ tak, že:
    $$A = Q \Lambda Q^T = \sum_{i=1}^n \lambda_i q_i q_i^T$$
    kde sloupce $q_i$ tvoří ortonormální bázi vlastních vektorů $\mathbb{R}^n$.
* **Pozitivně definitní (PD) a semidefinitní (PSD) matice:**
  * Symetrická matice $A \in \mathbb{R}^{n \times n}$ se nazývá:
    * **Pozitivně definitní (PD):** $\forall x \in \mathbb{R}^n \setminus \{0\}: x^T A x > 0$.
    * **Pozitivně semidefinitní (PSD):** $\forall x \in \mathbb{R}^n: x^T A x \ge 0$.
* **Ekvivalentní charakterizace pozitivní definitnosti (Zkouškový přehled):**
  Pro symetrickou matici $A \in \mathbb{R}^{n \times n}$ jsou následující tvrzení ekvivalentní:
  1. $A$ je PD ($\forall x \ne 0: x^T A x > 0$).
  2. **Vlastní čísla:** Všechna vlastní čísla jsou **ostře kladná**: $\lambda_i > 0$ pro všechna $i$ (pro PSD platí $\lambda_i \ge 0$).
  3. **Sylvestrovo kritérium:** Determinanty všech hlavních vedoucích podmatic jsou kladné: $\det(A_k) > 0$ pro $k = 1, \dots, n$ (kde $A_k$ je podmatice prvních $k$ řádků a sloupců).
  4. **Choleského rozklad:** Existuje regulární horní trojúhelníková matice $U$ s kladnou diagonálou t.ž. $A = U^T U$ (v dolním tvaru $A = L L^T$).
  5. **Gramova matice:** $A$ je Gramovou maticí nějaké lineárně nezávislé báze: $a_{ij} = \langle b_i \mid b_j \rangle$.
* **Vztah se skalárním součinem:**
  Každý skalární součin na $\mathbb{R}^n$ lze vyjádřit pomocí pozitivně definitní matice $A$ vztahem $\langle x \mid y \rangle = x^T A y$, a naopak každá PD matice definuje skalární součin.
* **Choleského rozklad:**
  * **Věta o Choleského rozkladu:** Pro každou reálnou symetrickou pozitivně definitní matici $A$ existuje **jediná horní trojúhelníková matice $U$ s kladnými prvky na diagonále** ($u_{ii} > 0$) taková, že:
    $$A = U^T U \quad (\text{resp. } A = L L^T \text{ pro dolní trojúhelníkovou } L = U^T)$$
  * **Praktické použití:**
    1. **Řešení soustav rovnic $Ax = b$:** Rozložíme $A = L L^T \implies$ řešíme dvě trojúhelníkové soustavy přímou a zpětnou substitucí: $L y = b$ a následně $L^T x = y$. Vyžaduje pouze $O(n^2)$ operací (po rozkladu) a spotřebuje poloviční čas i paměť oproti LU rozkladu, navíc je numericky stabilní bez nutnosti pivotizace.
    2. **Ověření pozitivní definitnosti:** Pokud při algoritmu Choleského rozkladu narazíme na odmocninu ze záporného čísla nebo nuly, matice není pozitivně definitní.

### Grafy
#### Základní pojmy teorie grafů:
* **Graf $G = (V, E)$:** Uspořádaná dvojice, kde $V$ je konečná neprázdná množina **vrcholů** ($|V| = n$) a $E \subseteq \binom{V}{2}$ je množina **hran** ($|E| = m$, dvouprvkové podmnožiny $\{u, v\}$, bez smyček a násobných hran).
* **Izomorfismus grafů ($G \cong H$):** Grafy $G=(V_G, E_G)$ a $H=(V_H, E_H)$ jsou izomorfní, pokud existuje **bijekce** $f: V_G \to V_H$ zachovávající hrany:
  $$\forall u, v \in V_G: \{u, v\} \in E_G \iff \{f(u), f(v)\} \in E_H$$
  * *Grafové invarianty* (nutné podmínky pro $G \cong H$): stejný počet vrcholů $n$, hran $m$, stejné skóre stupňů, délka nejkratší kružnice (girth), klikovost $\omega(G)$, nezávislost $\alpha(G)$, bipartitnost.
* **Podgraf a indukovaný podgraf:**
  * **Podgraf ($H \subseteq G$):** $V_H \subseteq V_G$ a $E_H \subseteq E_G \cap \binom{V_H}{2}$ (vznikne odebráním některých vrcholů a/nebo hran).
  * **Indukovaný podgraf ($G[U]$ pro $U \subseteq V_G$):** $V_H = U$ a $E_H = E_G \cap \binom{U}{2}$ (obsahuje *všechny* původní hrany mezi vrcholy podmnožiny $U$).
* **Okolí a stupeň vrcholu:**
  * **Otevřené okolí $N_G(v)$:** Množina sousedů: $N(v) = \{u \in V \mid \{u, v\} \in E\}$.
  * **Stupeň vrcholu $\deg_G(v)$:** Počet incidentních hran: $\deg(v) = |N(v)|$. Minimální stupeň $\delta(G)$, maximální stupeň $\Delta(G)$.
  * **Princip sudosti (Handshaking lemma):** Součet stupňů všech vrcholů je roven dvojnásobku počtu hran:
    $$\sum_{v \in V} \deg(v) = 2|E| \implies \text{počet vrcholů lichého stupně je vždy sudý}$$
  * **$k$-regulární graf:** Všechny vrcholy mají stejný stupeň: $\forall v \in V: \deg(v) = k$ (platí $k \cdot n = 2m$).
  * **Skóre grafu:** Posloupnost stupňů všech vrcholů (obvykle uspořádaná nerostoucí či neklesající).
* **Doplněk grafu ($\overline{G}$):** Graf na stejné množině vrcholů $V$, kde hrany tvoří právě ty dvojice, které v $G$ nejsou:
  $$\overline{G} = \left(V, \binom{V}{2} \setminus E\right), \quad |E(G)| + |E(\overline{G})| = \binom{n}{2} = \frac{n(n-1)}{2}$$
* **Bipartitní graf:** Graf $G=(V, E)$, jehož vrcholy lze rozdělit na dvě disjunktní partity $V = V_1 \cup V_2$ ($V_1 \cap V_2 = \emptyset$) tak, že každá hrana spojuje vrchol z $V_1$ s vrcholem z $V_2$ ($\forall e \in E: |e \cap V_1| = 1$, hrany nikdy nevedou uvnitř stejné partity).
  * **Charakterizační věta:** Graf $G$ je bipartitní $\iff$ **neobsahuje žádnou lichou kružnici** ($\iff$ je 2-obarvitelný, $\chi(G) \le 2$).

#### Základní příklady grafů, průchody a Eulerovské tahy:
* **Úplný graf $K_n$:** $V = [n]$, $E = \binom{V}{2}$, počet hran $\binom{n}{2} = \frac{n(n-1)}{2}$, každý vrchol má stupeň $n-1$.
* **Úplný bipartitní graf $K_{n, m}$:** Partity o velikostech $n$ a $m$ ($V = \{u_1, \dots, u_n\} \cup \{v_1, \dots, v_m\}$), $E = \{\{u_i, v_j\}\}$; počet hran $|E| = n \cdot m$.
* **Cesta $P_n$:** Graf na $n$ vrcholech spojených za sebou: $V = [n]$, $E = \{\{i, i+1\} \mid 1 \le i \le n-1\}$. Má $n$ vrcholů a délku $n-1$ hran.
* **Kružnice $C_n$ ($n \ge 3$):** Cyklus na $n$ vrcholech: $V = [n]$, $E = \{\{i, i+1\} \mid 1 \le i \le n-1\} \cup \{\{1, n\}\}$. Má $n$ vrcholů a $n$ hran (2-regulární).
* **Průchody grafem (Sled, Tah, Cesta):**
  * **Sled:** Sled z $v_0$ do $v_n$ je posloupnost $(v_0, e_1, v_1, e_2, \dots, e_n, v_n)$, pokud $\forall i$ platí $e_i = \{v_{i-1}, v_i\}$ (kde $v$ jsou vrcholy a $e$ hrany). **Mohou se opakovat vrcholy i hrany**.
  * **Tah:** Sled, kde $e$ jsou navzájem různé hrany. **Mohou se opakovat vrcholy, ale NE hrany**.
  * **Cesta:** Tah s navzájem různými vrcholy. **Neopakují se vrcholy ani hrany**.
* **Eulerovský graf a Eulerovský tah:**
  * **Eulerovský tah:** Tah, který projde **každou hranou grafu právě jednou**.
  * **Otevřený Eulerovský tah** (začíná a končí v různých vrcholech) existuje $\iff$ graf $G$ je souvislý a má **právě 2 vrcholy lichého stupně** (v jednom začíná, ve druhém končí).
  * **Uzavřený Eulerovský tah / Eulerovský graf** (končí ve stejném vrcholu) existuje $\iff$ graf $G$ je souvislý a **každý vrchol má sudý stupeň** ($\forall v \in V: \deg(v) \text{ je sudý}$).

#### Souvislost grafů, komponenty souvislosti a vzdálenost:
* **Souvislý graf:** Graf $G$ je souvislý, pokud $\forall u, v \in V$ existuje v $G$ cesta mezi $u$ a $v$.
* **Relace dosažitelnosti ($\sim$):** Ekvivalence na $V$ ($u \sim v \iff$ existuje cesta mezi $u$ a $v$).
  * *Reflexivní* ($u \sim u$ přes cestu délky 0), *symetrická* (neorientované hrany lze projít obousměrně), *tranzitivní* (napojení cest).
* **Komponenty souvislosti:** Podgrafy indukované jednotlivými rozkladovými třídami ekvivalence $\sim$ (maximální souvislé podgrafy).
* **Vzdálenost v grafu $d_G(u, v)$:** Délka (počet hran) nejkratší cesty mezi $u$ a $v$ ($d(u, v) = \infty$, pokud cesta neexistuje).
  * **Vlastnosti metriky na souvislém grafu ($\forall u, v, w \in V$):**
    1. **Nezápornost:** $d(u, v) \ge 0$ (délka cesty je nezáporná).
    2. **Identita nerozlišitelných:** $d(u, v) = 0 \iff u = v$.
    3. **Symetrie:** $d(u, v) = d(v, u)$.
    4. **Trojúhelníková nerovnost:** $d(u, w) \le d(u, v) + d(v, w)$ (napojení nejkratších cest $u \to v$ a $v \to w$ dává sled délky $d(u,v)+d(v,w)$, nejkratší cesta nemůže být delší).

#### Stromy (Definice, vlastnosti a ekvivalentní charakteristiky):
* **Definice stromu:** Souvislý acyklický graf (graf bez kružnic).
* **Les:** Acyklický graf (jeho komponenty souvislosti jsou stromy).
* **List:** Vrchol stupně 1 ($\deg(v) = 1$).
* **Základní vlastnosti stromů:**
  * Každý strom s alespoň dvěma vrcholy ($|V| \ge 2$) má **alespoň dva listy**.
  * Pro graf $G$ s listem $v$ platí: **$G$ je strom $\iff G - v$ je strom**.
  * Počet hran každého stromu s $n$ vrcholy je roven **$|E| = |V| - 1 = n - 1$** (pro les s $k$ komponentami platí $|E| = |V| - k$).
* **Ekvivalentní charakteristiky stromu (pro graf $G=(V, E)$ s $|V| = n$):**
  1. $G$ je souvislý a acyklický (= strom).
  2. $\forall u, v \in V(G)$ existuje **právě jedna cesta** mezi $u$ a $v$ (jednoznačná souvislost).
  3. $G$ je souvislý a $\forall e \in E(G): G - e$ není souvislý (minimální souvislost / každá hrana je most).
  4. $G$ je acyklický a $\forall e \in \binom{V}{2} \setminus E: G + e$ obsahuje kružnici (maximální acykličnost).
  5. $G$ je souvislý a $|E| = |V| - 1$ (Eulerova formule pro stromy).
  6. $G$ je acyklický a $|E| = |V| - 1$.
* **Kostra grafu:** Podgraf $T \subseteq G$, který je stromem a obsahuje všechny vrcholy $V(T) = V(G)$. Graf má kostru $\iff$ je souvislý.

#### Rovinné grafy (Nakreslení, Eulerova formule a vlastnosti):
* **Rovinný graf a nakreslení:**
  * **Rovinný graf:** Graf, pro který existuje rovinné nakreslení v ploše $\mathbb{R}^2$.
  * **Rovinné nakreslení:** Přiřazení různých bodů vrcholům a jednoduchých spojitých křivek (oblouků) hranám tak, že žádné dva oblouky nesdílí vnitřní bod (protínají se nanejvýš ve společném koncovém vrcholu).
* **Stěny (Faces, $F$):** Souvislé komponenty otevřené množiny $\mathbb{R}^2 \setminus (\text{nakreslení } G)$. Právě jedna stěna je neomezená (vnější stěna).
  * **Stupeň stěny $\deg(f)$:** Délka hraničního sledu stěny $f$.
  * **Princip sudosti pro stěny:**
    $$\sum_{f \in F} \deg(f) = 2|E|$$
* **Eulerova formule:** Pro každý **souvislý rovinný graf** s $v = |V|$ vrcholy, $e = |E|$ hranami a $f = |F|$ stěnami platí:
  $$v - e + f = 2 \quad (\text{neboli } v + f = e + 2)$$
  * **Důkaz indukcí podle počtu hran $e$ (při pevném $v$):**
    1. *Báze ($e = v - 1$):* Graf je strom, nemá žádné kružnice $\implies$ má pouze $f = 1$ stěnu (vnější). Dosazení: $v + 1 = (v - 1) + 2 = v + 1$ (platí).
    2. *Indukční krok ($e - 1 \to e$):* Mějme graf s $e \ge v$ hranami. Graf obsahuje kružnici; zvolme hranu $\lambda$ na kružnici a odebereme ji: $G' = G - \lambda$. V $G'$ ubude 1 hrana a spojí se 2 sousední stěny do jedné ($v' = v$, $e' = e - 1$, $f' = f - 1$). Z indukčního předpokladu pro $G'$ platí $v' + f' = e' + 2 \implies v + (f - 1) = (e - 1) + 2 \implies v + f = e + 2$ $\square$.
* **Maximální počet hran rovinného grafu:**
  * V každém rovinném grafu s alespoň 3 vrcholy ($v \ge 3$) platí:
    $$|E| \le 3|V| - 6$$
    * *Důkaz:* Každá stěna je ohraničena alespoň 3 hranami ($\deg(f) \ge 3$). Z principu sudosti pro stěny: $2e = \sum \deg(f) \ge 3f \implies f \le \frac{2}{3}e$. Dosazením do Eulerovy formule: $2 = v - e + f \le v - e + \frac{2}{3}e = v - \frac{1}{3}e \implies \frac{1}{3}e \le v - 2 \implies e \le 3v - 6$ $\square$.
  * **Pro rovinné grafy bez trojúhelníků (např. bipartitní, $\deg(f) \ge 4$):**
    $$|E| \le 2|V| - 4$$
    *(Důkaz: $2e \ge 4f \implies f \le \frac{e}{2} \implies 2 \le v - \frac{e}{2} \implies e \le 2v - 4$).*
* **Existence vrcholu malého stupně:** V každém rovinném grafu existuje vrchol stupně **nejvýše 5** ($\delta(G) \le 5$).
  * *Důkaz sporem:* Kdyby $\forall v \in V: \deg(v) \ge 6 \implies 2e = \sum \deg(v) \ge 6v \implies e \ge 3v$, což je spor s $e \le 3v - 6$.
* **Kuratowského věta:** Graf $G$ je rovinný $\iff$ neobsahuje podgraf izomorfní **dělení grafu $K_5$ ani $K_{3,3}$** (dělení hrany = přidání vrcholů na hrany $K_5$ či $K_{3,3}$).

#### Barevnost grafů:
* **Dobré $k$-obarvení vrcholů:** Zobrazení $c: V(G) \to \{1, \dots, k\}$ takové, že:
  $$\forall \{u, v\} \in E(G): c(u) \ne c(v) \quad (\text{žádné dva sousední vrcholy nemají stejnou barvu})$$
* **Barevnost (Chromatické číslo) $\chi(G)$:** Nejmenší $k$, pro které existuje dobré $k$-obarvení grafu $G$.
  * **Charakterizace 2-obarvitelnosti:** $\chi(G) \le 2 \iff G$ je bipartitní $\iff G$ nemá lichou kružnici.
* **Klika a klikovost $\omega(G)$:**
  * **Klika:** Podmnožina vrcholů, které jsou navzájem všechny propojené hranou (indukují úplný podgraf $K_k$).
  * **Klikovost $\omega(G)$:** Velikost největší kliky v grafu $G$.
* **Vztah barevnosti a klikovosti:**
  $$\chi(G) \ge \omega(G)$$
  * *Důvod:* Každý z $\omega(G)$ vrcholů kliky musí mít navzájem různou barvu.
  * *Pozor (Obrácená nerovnost neplatí!):* Existují grafy s libovolně vysokou barevností bez trojúhelníků ($\omega=2$, např. Mycielského konstrukce).
* **Dobré hranové obarvení:** Zobrazení $\varphi: E(G) \to \{1, \dots, k\}$ takové, že každé dvě hrany $e_1, e_2$ incidentní se stejným vrcholem mají různou barvu ($\varphi(e_1) \ne \varphi(e_2)$).
  * **Hranová barevnost (Chromatický index) $\chi'(G)$:** Nejmenší počet barev pro hranové obarvení.

#### Hranová a vrcholová souvislost grafů:
* **Hranový řez a Hranová souvislost:**
  * **Hranový řez:** Množina hran $F \subseteq E$, pro kterou je graf $G \setminus F$ nesouvislý.
  * **Hranová $k$-souvislost:** Graf $G$ je hranově $k$-souvislý, pokud neobsahuje žádný hranový řez velikosti menší než $k$ (k rozpojení grafu je třeba odebrat alespoň $k$ hran).
  * **Hranová souvislost $k_e(G)$ (či $\lambda(G)$):** Největší $k$ takové, že $G$ je hranově $k$-souvislý.
* **Vrcholový řez a Vrcholová souvislost:**
  * **Vrcholový řez:** Množina vrcholů $U \subseteq V$, pro kterou je indukovaný podgraf $G[V \setminus U]$ nesouvislý (nebo triviální).
  * **Vrcholová $k$-souvislost:** Graf $G$ je vrcholově $k$-souvislý, pokud má alespoň $k + 1$ vrcholů ($|V| \ge k + 1$) a neobsahuje žádný vrcholový řez velikosti $< k$.
  * **Vrcholová souvislost $k_v(G)$ (či $\kappa(G)$):** Největší $k$ takové, že $G$ je vrcholově $k$-souvislý.
  * **Vztah souvislostí:** Pro každý netriviální graf platí $k_v(G) \le k_e(G) \le \delta(G)$.
* **Mengerova věta (Všechny 4 varianty):**
  * **1. Hranová $xy$-verze (lokální):** Pro dva různé vrcholy $x, y \in V$:
    $$G \text{ obsahuje } k \text{ hranově disjunktních cest mezi } x, y \iff G \text{ neobsahuje hranový } xy\text{-řez velikosti } < k$$
  * **2. Vrcholová $xy$-verze (lokální):** Pro dva různé **nesousední** vrcholy $x, y \in V$:
    $$G \text{ obsahuje } k \text{ vrcholově disjunktních cest mezi } x, y \iff G \text{ neobsahuje vrcholový } xy\text{-řez velikosti } < k$$
  * **3. Globální hranová verze:**
    $$G \text{ je hranově } k\text{-souvislý} \iff \text{mezi každými dvěma různými vrcholy existuje alespoň } k \text{ hranově disjunktních cest}$$
  * **4. Globální vrcholová verze:**
    $$G \text{ je vrcholově } k\text{-souvislý} \iff \text{mezi každými dvěma různými vrcholy existuje alespoň } k \text{ vrcholově disjunktních cest}$$

#### Orientované grafy, silná a slabá souvislost:
* **Orientovaný graf (Digraf) $G = (V, E)$:** Uspořádaná dvojice, kde $E \subseteq V^2 \setminus \{(x, x) \mid x \in V\}$ je množina orientovaných hran (uspořádaných dvojic $(u, v)$, bez smyček).
* **Podkladový graf $H = (V, F)$:** Neorientovaný graf na stejných vrcholech, kde zahodíme šipky:
  $$F = \left\{\{u, v\} \in \binom{V}{2} \;\middle|\; (u, v) \in E \vee (v, u) \in E\right\}$$
* **Stupně vrcholů:** Vstupní stupeň $\deg^-(v) = |\{u \in V \mid (u, v) \in E\}|$, výstupní stupeň $\deg^+(v) = |\{u \in V \mid (v, u) \in E\}|$. Graf je **vyvážený**, pokud $\forall v \in V: \deg^+(v) = \deg^-(v)$.
* **Typy souvislosti orientovaného grafu:**
  * **Slabá souvislost:** Podkladový neorientovaný graf $H$ je souvislý.
  * **Silná souvislost:** Pro každé dva vrcholy $u, v \in V$ existuje orientovaná cesta z $u$ do $v$ (i z $v$ do $u$).
* **Eulerovský orientovaný graf (Ekvivalence):** Pro orientovaný graf $G$ jsou následující tvrzení ekvivalentní:
  1. $G$ je vyvážený a slabě souvislý.
  2. $G$ má uzavřený eulerovský tah (projde každou orientovanou hranu právě jednou a skončí v počátku).
  3. $G$ je vyvážený a silně souvislý.

#### Toky v sítích (Definice, vlastnosti a Ford-Fulkerson):
* **Toková síť:** Pětice $(V, E, z, s, c)$, kde:
  * $V$ je konečná množina vrcholů, $E \subseteq V \times V$ množina orientovaných hran.
  * $z \in V$ je **zdroj** (source), $s \in V \setminus \{z\}$ je **stok** (sink / spotřebič).
  * $c: E \to [0, +\infty)$ je **kapacita** hran ($c(e)$ udává maximální propustnost).
* **Tok v síti:** Funkce $f: E \to [0, +\infty)$ splňující dvě podmínky:
  1. **Kapacitní omezení:** $\forall e \in E: 0 \le f(e) \le c(e)$ (tok nepřekročí kapacitu).
  2. **Kirchhoffův zákon (zachování toku):** Pro každý vnitřní uzel $u \in V \setminus \{z, s\}$ platí:
     $$\sum_{v: (v, u) \in E} f(v, u) = \sum_{v: (u, v) \in E} f(u, v) \quad (\text{neboli } f_{in}(u) = f_{out}(u))$$
* **Velikost toku $w(f)$:** Čistý odtok ze zdroje $z$ (rovná se čistému přítoku do stoku $s$):
  $$w(f) = f(Out(z)) - f(In(z)) = \sum_{v: (z, v) \in E} f(z, v) - \sum_{v: (v, z) \in E} f(v, z)$$
* **Existence maximálního toku (Fakt):** V každé síti **existuje maximální tok** (množina všech přípustných toků tvoří uzavřenou a omezenou podmnožinu $\mathbb{R}^{|E|}$, je tedy kompaktní; velikost toku $w(f)$ je spojitá funkce, a spojitá funkce na kompaktu vždy nabývá svého maxima).
* **Řez v síti a jeho kapacita:**
  * **Řez v síti:** Množina hran $R \subseteq E$ taková, že každá orientovaná cesta ze $z$ do $s$ má neprázdný průnik s $R$ (odebráním $R$ se přeruší všechna spojení ze $z$ do $s$). Často definován rozkladem $V = A \cup B$ ($z \in A, s \in B, A \cap B = \emptyset$), řez jsou hrany vedoucí z $A$ do $B$.
  * **Kapacita řezu:** $c(R) = \sum_{e \in R} c(e)$.
  * **Minimální řez:** Řez s nejmenší celkovou kapacitou mezi všemi řezy sítě.
* **Věta o maximálním toku a minimálním řezu (Max-Flow Min-Cut / Minimax):**
  Pro každý tok $f$ a každý řez $R$ platí $w(f) \le c(R)$. Zejména pro maximální tok $f_{max}$ a minimální řez $R_{min}$ platí rovnost:
  $$w(f_{max}) = c(R_{min})$$
  * **Ekvivalentní charakteristiky maximálního toku:** Pro tok $f$ je ekvivalentní:
    1. $f$ je maximální tok.
    2. V síti neexistuje žádná zlepšující (nenasycená) cesta ze $z$ do $s$.
    3. Existuje řez $R$ takový, že $w(f) = c(R)$.
* **Hledání maximálního toku (Ford-Fulkersonův algoritmus):**
  * **Zlepšující (nenasycená) cesta $P$:** Neorientovaná cesta ze $z$ do $s$, kde:
    * Pro každou **dopřednou hranu** $e = (x_i, x_{i+1}) \in E$ je rezerva $r(e) = c(e) - f(e) > 0$ (lze přilít).
    * Pro každou **zpětnou hranu** $e = (x_{i+1}, x_i) \in E$ je rezerva $r(e) = f(e) > 0$ (lze ubrat / přesměrovat).
  * **Algoritmus pro celočíselné kapacity ($c(e) \in \mathbb{N}_0$):**
    1. Nastav $f(e) = 0$ pro všechny hrany (nulový tok).
    2. Dokud existuje zlepšující cesta $P$ ze $z$ do $s$:
       * Spočti úzké hrdlo cesty: $\varepsilon = \min_{e \in P} r(e)$ (minimální rezerva podél cesty).
       * Zvětši tok podél $P$ o $\varepsilon$: na dopředných hranách $f(e) \leftarrow f(e) + \varepsilon$, na zpětných $f(e) \leftarrow f(e) - \varepsilon$.
    3. Vrať maximální tok $f$.
  * **Konečnost a celočíselnost:** Jsou-li kapacity celá čísla, je v každém kroku $\varepsilon \ge 1$ celé číslo $\implies$ v každém kroku vzroste velikost toku alespoň o 1. Protože je velikost toku shora omezena kapacitou libovolného řezu, algoritmus **zaručeně skončí v konečném počtu kroků** v čase $\mathcal{O}(|E| \cdot w(f_{max}))$. Výsledný tok je celočíselný.

### Diskrétka
#### Relace a jejich vlastnosti:
* **Binární relace na množině $X$:** $R \subseteq X \times X$ (obecně mezi $X$ a $Y$: $R \subseteq X \times Y$)
* **Reflexivita:** $\forall x \in X: (x, x) \in R$
* **Symetrie:** $\forall x, y \in X: (x, y) \in R \implies (y, x) \in R$
* **Antisymetrie:** $\forall x, y \in X: ((x, y) \in R \wedge (y, x) \in R) \implies x = y$
* **Tranzitivita:** $\forall x, y, z \in X: ((x, y) \in R \wedge (y, z) \in R) \implies (x, z) \in R$

#### Ekvivalence a rozklad množiny:
* **Ekvivalence ($\sim$ nebo $\equiv$):** Relace, která je současně **reflexivní**, **symetrická** a **tranzitivní**.
* **Rozkladová třída prvku $x$:** $[x]_\sim = \{y \in X \mid y \sim x\}$ rozsekají množinu $X$ na vzájemně **disjunktní neprázdné podmnožiny**

#### Částečné uspořádání (Poset), extrémy, řetězce:
* **Částečné uspořádání ($\le$):** Relace, která je současně **reflexivní**, **antisymetrická** a **tranzitivní** (pokud jsou každé dva prvky porovnatelné $\implies$ **lineární / úplné**).
* **Nejmenší prvek $a$:** $\forall x \in X: a \le x$ (je menší nebo roven všem prvkům, existuje nejvýše jeden).
* **Minimální prvek $a$:** $\neg\exists x \in X: x \le a \wedge x \ne a$ (neexistuje žádný ostře menší prvek; může jich být více i žádný). *Obdobně pro **největší** ($\forall x \in X: x \le a$) a **maximální** ($\neg\exists x \in X: a \le x \wedge x \ne a$).*
* **Řetězec (Chain):** Podmnožina $C \subseteq X$, kde jsou každé dva prvky navzájem porovnatelné ($\forall x, y \in C: x \le y \vee y \le x$).
* **Antiřetězec (Antichain):** Podmnožina $A \subseteq X$, kde žádné dva různé prvky nejsou porovnatelné ($\forall x, y \in A, x \ne y: x \not\le y \wedge y \not\le x$).
* **Výška a šířka posetu:**
  * **Výška posetu:** Velikost nejdelšího řetězce v $(X, \le)$.
  * **Šířka posetu:** Velikost největšího antiřetězce v $(X, \le)$.
* **Věta o dlouhém a širokém (posetu):** Každá konečná částečně uspořádaná množina s alespoň $n \cdot m + 1$ prvky obsahuje **buď řetězec délky alespoň $n+1$**, **nebo antiřetězec velikosti alespoň $m+1$** (platí $|X| \le \text{výška} \cdot \text{šířka}$).

#### Funkce (Zobrazení) $f: X \to Y$ ($|X| = n, |Y| = m$):
* **Typy funkcí:**
  * **Injekce (prostá):** $\forall x_1, x_2 \in X: f(x_1) = f(x_2) \implies x_1 = x_2$ (každý cíl má nejvýše 1 vzor; nutně $n \le m$).
  * **Surjekce (na):** $\forall y \in Y \; \exists x \in X: f(x) = y$ (každý cíl má alespoň 1 vzor; nutně $n \ge m$).
  * **Bijekce (vzájemně jednoznačná):** Současně injekce i surjekce (dokonalé spárování 1:1, existuje inverzní $f^{-1}$; nutně $n = m$).
* **Počty různých funkcí z $X$ do $Y$:**
  * **Všechna zobrazení:** $m^n$
  * **Injekce (prostá):** $\frac{m!}{(m-n)!} = m(m-1)\cdots(m-n+1)$ pro $n \le m$ (jinak $0$).
  * **Bijekce:** $n!$ pro $n = m$ (jinak $0$).
  * **Surjekce (na):** $\sum_{k=0}^m (-1)^k \binom{m}{k} (m-k)^n = m! \cdot S(n, m)$ pro $n \ge m$ (přes PIE; pro $n < m$ je $0$).
* **Skládání $(f \circ g)(x) = f(g(x))$:** První se aplikuje vnitřní funkce $g$. ($f \circ g$ je injekce $\implies g$ je injekce; $f \circ g$ je surjekce $\implies f$ je surjekce).

#### Permutace a jejich vlastnosti ($S_n$ pro $|X| = n$):
* **Permutace:** Každá bijekce $\pi: X \to X$. Množina všech permutací se značí $S_n$, celkový počet je **$|S_n| = n!$**.
* **Pevný bod:** Prvek $x \in X$ splňující $\pi(x) = x$ (prvek se permutací nezmění, v cyklovém zápisu odpovídá cyklu délky 1).

#### Kombinační čísla a Binomická věta:
* **Kombinační číslo $\binom{n}{k}$:** Počet $k$-prvkových podmnožin $n$-prvkové množiny: $\binom{n}{k} = \frac{n!}{k!(n-k)!}$ (pro $0 \le k \le n$).
* **Základní vztahy a identity:**
  * **Symetrie:** $\binom{n}{k} = \binom{n}{n-k}$
  * **Pascalovo pravidlo:** $\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$
  * **Výběr s podvýborem:** $\binom{n}{k} \binom{k}{m} = \binom{n}{m} \binom{n-m}{k-m}$ (speciálně pro $m=1$: $k \binom{n}{k} = n \binom{n-1}{k-1}$)
* **Binomická věta:**
  $$(x + y)^n = \sum_{k=0}^n \binom{n}{k} x^{n-k} y^k$$
* **Aplikace a důsledky (speciální dosazení):**
  * **Součet všech podmnožin ($x=1, y=1$):** $\sum_{k=0}^n \binom{n}{k} = (1+1)^n = 2^n$
  * **Alternující součet ($x=1, y=-1$):** $\sum_{k=0}^n (-1)^k \binom{n}{k} = (1-1)^n = 0 \implies \sum_{k \text{ sudé}} \binom{n}{k} = \sum_{k \text{ liché}} \binom{n}{k} = 2^{n-1}$

#### Princip inkluze a exkluze (PIE):
* **Obecná formulace vzorce:**
  $$\left|\bigcup_{i=1}^n A_i\right| = \sum_{i=1}^n |A_i| - \sum_{1 \le i < j \le n} |A_i \cap A_j| + \sum_{1 \le i < j < k \le n} |A_i \cap A_j \cap A_k| - \dots + (-1)^{n+1} |A_1 \cap \dots \cap A_n|$$
* **Důkaz (zkrácený postup):**
  * **Cíl:** Ukázat, že libovolný prvek $x$, který leží v celém sjednocení (v právě $k \ge 1$ množinách), se na pravé straně po všech odčítáních a přičítáních započítá nakonec **přesně jednou**.
  * **Příspěvek prvku $x$:** $S = \binom{k}{1} - \binom{k}{2} + \binom{k}{3} - \dots + (-1)^{k-1} \binom{k}{k}$.
  * **Využití binomické věty:** $0 = (1 - 1)^k = \binom{k}{0} - \binom{k}{1} + \binom{k}{2} - \dots = \binom{k}{0} - S \implies S = \binom{k}{0} = 1$.
* **Hlavní aplikace PIE (univerzum $U$ minus sjednocení špatných vlastností):**
  * **Problém šatnářky ($D_n$):** Počet permutací bez pevného bodu ($|U| = n!$, špatná vl. $A_i: \pi(i) = i$, $|A_i| = (n-1)!$):
    $$D_n = n! - \binom{n}{1}(n-1)! + \binom{n}{2}(n-2)! - \dots = n! \sum_{k=0}^n \frac{(-1)^k}{k!} \approx \frac{n!}{e}$$
  * **Počet surjekcí z $N$ do $M$ ($|N|=n, |M|=m$):** ($|U| = m^n$, špatná vl. $A_i$: cíl $i$ není zasažen, $|A_i| = (m-1)^n$):
    $$Surj(n, m) = m^n - \binom{m}{1}(m-1)^n + \binom{m}{2}(m-2)^n - \dots = \sum_{k=0}^m (-1)^k \binom{m}{k} (m - k)^n$$
  * **Eulerova funkce $\varphi(n)$:** Počet čísel $1 \le k \le n$ nesoudělných s $n$ ($n = p_1^{a_1} \cdots p_r^{a_r}$, špatná vl. $A_{p_i}$: dělitelnost $p_i$, $|A_{p_i}| = \frac{n}{p_i}$):
    $$\varphi(n) = n - \left(\sum_i \frac{n}{p_i} - \sum_{i < j} \frac{n}{p_i p_j} + \sum_{i < j < k} \frac{n}{p_i p_j p_k} - \dots\right) = n \cdot \left(1 - \sum_i \frac{1}{p_i} + \sum_{i < j} \frac{1}{p_i p_j} - \dots\right) = n \prod_{i=1}^r \left(1 - \frac{1}{p_i}\right)$$

#### Hallova věta o SRR a párování v bipartitním grafu:
* **Systém různých reprezentantů (SRR):** Pro systém množin $\mathcal{M} = \{M_1, \dots, M_n\}$ je SRR výběr $n$ navzájem různých prvků $x_1 \in M_1, \dots, x_n \in M_n$ ($x_i \ne x_j$ pro $i \ne j$).
* **Vztah k bipartitním grafům:** Bipartitní graf $G = (A \cup B, E)$, kde $A = \{M_1, \dots, M_n\}$ (množiny), $B = \bigcup M_i$ (prvky) a hrana $\{M_i, x\} \in E \iff x \in M_i$. SRR odpovídá **párování nasycujícímu celou partitu $A$** ($|M| = n$).
* **Hallova věta (podmínka pro existenci SRR):** SRR existuje $\iff$ platí **Hallova podmínka**:
  $$\forall I \subseteq \{1, \dots, n\}: \left|\bigcup_{i \in I} M_i\right| \ge |I| \quad (\text{grafově } \forall S \subseteq A: |N(S)| \ge |S|)$$
* **Střídavá a zlepšující cesta:**
  * **Střídavá cesta:** Cesta v grafu, která pravidelně střídá hrany ležící v párování $M$ a hrany mimo $M$.
  * **Zlepšující cesta:** Střídavá cesta začínající i končící ve **volném (nenasyceném)** vrcholu. Její překlopení zvětší párování o 1 (Bergeovo lemma: párování je maximální $\iff$ neexistuje zlepšující cesta).
* **Princip důkazu (sporem přes střídavé cesty):** Pokud maximální párování nenasytí celou partitu $A$, z nenasyceného vrcholu v $A$ prohledáme všechny střídavé cesty (začínáme z vrcholu hranou co je mimo párování, vracíme tou co je v párování). Množina dosažených levých vrcholů $S \subseteq A$ má sousedy $N(S)$ pouze v již spárovaných pravých vrcholech $\implies |N(S)| < |S|$ (spor s Hallovou podmínkou).
* **Algoritmické aspekty (polynomiální nalezení SRR):**
  * **Metoda střídavých cest:** Začneme s prázdným párováním. Opakovaně pomocí BFS hledáme zlepšující cestu a překlápíme na ní hrany dokud cesta existuje.
  * **Složitost:** Maximálně $|V|$ zvětšení, každé BFS v $O(|E|) \implies$ celková složitost **$O(|V| \cdot |E|)$** (Hopcroft-Karp: $O(|E|\sqrt{|V|})$).

### Logika
#### Syntaxe výrokové a predikátové logiky:
* **Jazyk:**
  * **Výroková logika (VL):** Množina prvovýroků $\mathbb{P}$, logické spojky $(\neg, \wedge, \vee, \to, \leftrightarrow)$ a závorky.
  * **Predikátová logika (PL):** Množina proměnných $Var$, funkční symboly $f$ s aritou (0-ární jsou konstanty), predikátové/relační symboly $P$ s aritou, kvantifikátory $(\forall, \exists)$, logické spojky, případně rovnost $=$.
* **Termy (v PL):** Každá proměnná i konstanta je term. Jsou-li $t_1, \dots, t_n$ termy a $f$ je $n$-ární funkční symbol, pak $f(t_1, \dots, t_n)$ je term.
* **Výrok (Výroková formule ve VL, množina $VF_\mathbb{P}$):** Nejmenší množina formulí splňující induktivní definici:
  1. Každý prvovýrok $p \in \mathbb{P}$ je výrok ($p \in VF_\mathbb{P}$).
  2. Jsou-li $\varphi, \psi \in VF_\mathbb{P}$, pak i $(\neg\varphi), (\varphi \wedge \psi), (\varphi \vee \psi), (\varphi \to \psi), (\varphi \leftrightarrow \psi) \in VF_\mathbb{P}$.
* **Formule v predikátové logice (PL):**
  * **Atomická formule:** $P(t_1, \dots, t_n)$ nebo rovnost $t_1 = t_2$ (kde $t_i$ jsou termy).
  * **Složená formule:** Vzniká induktivně z atomických formulí pomocí logických spojek a kvantifikátorů $((\forall x)\varphi, (\exists x)\varphi)$.
* **Proměnné ve formuli (PL):**
  * **Vázaný výskyt proměnné:** Leží v podformuli tvaru $(\forall x)\psi$ nebo $(\exists x)\psi$.
  * **Volný výskyt proměnné:** Není vázaný žádným kvantifikátorem. Všechny volné výskyty téže proměnné $x$ v téže formuli (např. $P(x) \wedge Q(x)$) označují **vždy tentýž prvek** (daný týmž ohodnocením $e(x)$).
  * **Otevřená formule:** Neobsahuje **žádný kvantifikátor** ($\forall, \exists$).
  * **Uzavřená formule (Sentence):** Nemá **žádnou volnou proměnnou** (všechny výskyty proměnných jsou vázané).
  * **Instance formule $\varphi(x/t)$:** Vznikne nahrazením všech volných výskytů proměnné $x$ termem $t$ (term $t$ musí být za $x$ *substituovatelný*, tj. žádná proměnná v $t$ se po dosazení nesmí stát vázanou).
* **Sémantika volných vs. vázaných proměnných (Generální uzávěr):**
  * **Volná proměnná (libovolné dosazení):** Za volné $x$ lze ohodnocením $e(x)$ dosadit libovolný prvek univerza, ale dosadí se do **všech volných výskytů $x$ naráz** (v $P(x) \wedge Q(x)$ mají obě $x$ tutéž hodnotu $e(x)$).
  * **Platnost otevřené formule = „pro všechna“ (Generální uzávěr):** Otevřená formule $\varphi(x)$ platí ve struktuře $\mathcal{A}$ ($\mathcal{A} \models \varphi$), právě když platí pro **každé** ohodnocení $e$ $\iff \mathcal{A} \models (\forall x)\varphi(x)$. Proto se u vět v matematice i při Skolemizaci univerzální kvantifikátory vynechávají (volné proměnné automaticky znamenají „pro jakékoliv $x$“).
  * **Vázaná proměnná (zamčená v dosahu):** Ve formuli $(\forall x)\big(P(x) \wedge Q(x)\big)$ řídí obě $x$ přímo kvantifikátor, který pro každý prvek domény testuje $P(d) \wedge Q(d)$. Z vnějšku za $x$ nelze nic dosadit — formule je uzavřená (sentence) s pevnou hodnotou 0/1.

#### Normální tvary formulí (CNF, DNF, PNF) a algoritmy:
* **Normální tvary výrokových formulí:**
  * **Literál $\ell$:** Prvovýrok $p$ (pozitivní) nebo jeho negace $\neg p$ (negativní). Značení: $p^1 = p$, $p^0 = \neg p$.
  * **Klauzule:** Disjunkce literálů $C = \ell_1 \vee \ell_2 \vee \dots \vee \ell_k$. Prázdná klauzule $\square$ je $\bot$.
  * **CNF (Konjunktivní normální forma):** Konjunkce klauzulí: $\bigwedge_i C_i = \bigwedge_i \bigvee_j \ell_{i, j}$. Prázdná CNF je $\top$.
  * **Elementární konjunkce:** Konjunkce literálů $E = \ell_1 \wedge \ell_2 \wedge \dots \wedge \ell_k$. Prázdná je $\top$.
  * **DNF (Disjunktivní normální forma):** Disjunkce elementárních konjunkcí: $\bigvee_i E_i = \bigvee_i \bigwedge_j \ell_{i, j}$. Prázdná DNF je $\bot$.
* **Sémantický převod přes tabulku modelů:**
  * **Do DNF:** Sjednocení modelů (řádků s hodnotou 1): $\varphi_{DNF} = \bigvee_{v \models \varphi} \bigwedge_{p \in \mathbb{P}} p^{v(p)}$.
  * **Do CNF:** Zakázání nemodelů (řádků s hodnotou 0): $\varphi_{CNF} = \bigwedge_{v \not\models \varphi} \bigvee_{p \in \mathbb{P}} p^{1 - v(p)}$.
* **Prenexní normální forma (PNF v PL):**
  * Formule je v PNF, má-li tvar:
    $$(Q_1 x_1)(Q_2 x_2)\dots(Q_n x_n)\,\varphi'$$
    kde $Q_i \in \{\forall, \exists\}$ je **kvantifikátorový prefix** a $\varphi'$ je **otevřená formule** (otevřené jádro).
  * **Pravidla převodu do PNF (vytýkání):**
    1. **Dosah kvantifikátoru a přejmenování vázaných proměnných (substituce):**
       * *Dosah (Scope):* Kvantifikátor má vyšší prioritu než $\wedge, \vee, \to$. Ve formuli $(\forall x)P(x, y) \wedge Q(x)$ končí dosah $\forall x$ na $P(x, y)$, tj. $\big((\forall x)P(x, y)\big) \wedge Q(x)$. Proměnná $x$ v $Q(x)$ je proto **volná**.
       * *Zápis substituce s lomítkem:* V podformuli $(\forall x)P(x, y)$ nahradíme $x$ novou proměnnou $z$ formálním zápisem **$(\forall z) P(x/z, y)$**:
         $$(\forall x) P(x, y) \wedge Q(x) \ \sim \ (\forall z) P(x/z, y) \wedge Q(x) \ = \ (\forall z) P(z, y) \wedge Q(x) \ \sim \ (\forall z)\big(P(z, y) \wedge Q(x)\big)$$
    2. Odstranit spojky $\to, \leftrightarrow$ (převést na $\neg, \wedge, \vee$).
    3. Posunout negace dovnitř: $\neg(\forall x)\varphi \sim (\exists x)\neg\varphi$ a $\neg(\exists x)\varphi \sim (\forall x)\neg\varphi$.
    4. Vytknout kvantifikátory ven (pro $x$ nevolnou ve $\psi$):
       * $((Q x)\varphi \wedge \psi) \sim (Q x)(\varphi \wedge \psi)$, $\quad ((Q x)\varphi \vee \psi) \sim (Q x)(\varphi \vee \psi)$
       * $((Q x)\varphi \to \psi) \sim (\overline{Q} x)(\varphi \to \psi)$ *(pozor: v předpokladu implikace se kvantifikátor obrací $\forall \leftrightarrow \exists$!)*
       * $(\psi \to (Q x)\varphi) \sim (Q x)(\psi \to \varphi)$
* **Použití pro algoritmy (SAT a Rezoluce):**
  * **SAT:** Rozhodnout splnitelnost CNF formule. $k$-SAT má v každé klauzuli $\le k$ literálů (2-SAT je polynomiální v P, 3-SAT je NP-úplný).
  * **Výroková rezoluce:** Zamítací procedura na množině klauzulí $S$ v CNF.
    * **Rezoluční pravidlo:** Z klauzulí $C_1 \vee \ell$ a $C_2 \vee \overline{\ell}$ odvoď **rezolventu** $C_1 \vee C_2$.
    * **Rezoluční zamítnutí:** Odvození prázdné klauzule $\square$ (spor). Platí: $S \vdash_R \square \iff S$ je nesplnitelná.

#### Sémantika výrokové a predikátové logiky:
* **Model a teorie ve výrokové logice (VL):**
  * **Model formule:** Pravdivostní ohodnocení $v: \mathbb{P} \to \{0, 1\}$. Platnost: $v \models \varphi \iff$ hodnota formule $\varphi$ při ohodnocení $v$ je 1. Množina modelů formule je $M(\varphi)$.
  * **Model teorie $T$ ve VL:** Ohodnocení $v$, ve kterém platí všechny axiomy teorie $T$. Množina všech modelů teorie je $M(T) = \bigcap_{\alpha \in T} M(\alpha)$.
* **Model a teorie v predikátové logice (PL):**
* **Struktura jazyka $L$ (v predikátové logice):** Trojice $\mathcal{A} = \langle A, \mathcal{R}^\mathcal{A}, \mathcal{F}^\mathcal{A} \rangle$, kde:
  * $A$ je neprázdná množina (**doména / univerzum**).
  * $\mathcal{R}^\mathcal{A}$ je soubor realizací relačních symbolů (realizací $n$-árního relačního symbolu $R$ je nějaká $n$-ární relace $R^\mathcal{A} \subseteq A^n$).
  * $\mathcal{F}^\mathcal{A}$ je soubor realizací funkčních symbolů (realizací $n$-árního funkčního symbolu $f$ je nějaká $n$-ární funkce $f^\mathcal{A}: A^n \to A$, přičemž realizací konstantního symbolu $c$ je přímo prvek $c^\mathcal{A} \in A$).
  * **Model teorie $T$ v PL:** Struktura $\mathcal{A}$ jazyka $L$, ve které platí všechny axiomy teorie $T$ (značíme $\mathcal{A} \models T$).
* **Základní sémantické vztahy (vzhledem k teorii $T$):**
  * **Pravdivá v $T$ (důsledek $T$, tautologie v $T$):** $T \models \varphi \iff \varphi$ platí v každém modelu $T$ ($M(T) \subseteq M(\varphi)$).
  * **Lživá v $T$ (sporná v $T$):** $T \models \neg\varphi \iff \varphi$ neplatí v žádném modelu $T$ ($M(T) \cap M(\varphi) = \emptyset$).
  * **Nezávislá v $T$:** Platí v nějakém modelu $T$ a v jiném neplatí ($\emptyset \subsetneq M(T) \cap M(\varphi) \subsetneq M(T)$).
  * **Splnitelná (konzistentní) v $T$:** Platí alespoň v jednom modelu $T$ ($M(T) \cap M(\varphi) \ne \emptyset$).
  * **Bezesporná (splnitelná) teorie:** Má alespoň jeden model ($M(T) \ne \emptyset$).
  * **Sporná teorie:** Nemá žádný model ($M(T) = \emptyset \implies T \models \bot$, vyplývá z ní vše).
  * **Kompletní teorie:** Je bezesporná a každá sentence je v ní buď pravdivá, nebo lživá (nemá žádné nezávislé sentence).
* **Analýza výrokových teorií nad $n$ prvovýroky ($|\mathbb{P}| = n$):**
  * Jazyk má právě $2^n$ modelů (ohodnocení).
  * Počet neekvivalentních teorií odpovídá počtu podmnožin modelů: $2^{2^n}$.
  * Počet neekvivalentních kompletních teorií je roven počtu modelů: $2^n$ (kompletní teorie má právě 1 model).

#### Extenze teorií a Skolemizace:
* **Extenze teorie:** Mějme teorii $T$ v jazyce $L$ a teorii $T'$ v jazyce $L'$:
  * **Extenze ($T \subseteq T'$ sémanticky):** $L \subseteq L'$ a každý důsledek $T$ je důsledkem $T'$ ($Csq_L(T) \subseteq Csq_{L'}(T')$).
  * **Jednoduchá extenze:** $L' = L$ (nerozšiřuje jazyk, pouze přidává axiomy v původním jazyce).
  * **Konzervativní extenze:** $T'$ nedokazuje v původním jazyce $L$ žádné nové formule:
    $$Csq_L(T) = Csq_{L'}(T') \cap VF_L \quad (\forall \varphi \in VF_L: T' \models \varphi \iff T \models \varphi)$$
    * *Sémantické kritérium:* Každý model $\mathcal{M} \models T$ lze expandovat na model $\mathcal{M}' \models T'$ (přidáním interpretace nových symbolů bez změny univerza a starých relací).
* **Skolemizace (převod na otevřenou teorii):**
  * Odstranění existenčních kvantifikátorů $\exists$ ze sentence v PNF při zachování splnitelnosti (vzniklá teorie je ekvisplnitelná a je konzervativní extenzí):
  * **Pravidlo pro existenční kvantifikátor $(\exists y)$:**
    * Pokud mu v prefixu **nepředchází žádné $\forall$:** nahradíme $y$ novou **Skolemovou konstantou** $c_0$.
    * Pokud mu v prefixu **předchází $(\forall x_1)\dots(\forall x_k)$:** nahradíme $y$ novou **Skolemovou funkcí** $f(x_1, \dots, x_k)$ arity $k$.
  * Po odstranění všech $\exists$ a zahození zbylých $\forall$ získáme **otevřenou formuli (Skolemovu variantu)**.

#### Dokazatelnost a formální systémy:
* **Pojem formálního důkazu:** Syntaktický proces odvozování z axiomů pomocí odvozovacích pravidel. Značení: $T \vdash \varphi$ ($\varphi$ je dokazatelná z $T$).
  * **Korektnost (Soundness):** $T \vdash \varphi \implies T \models \varphi$ (dokazatelné je pravdivé).
  * **Úplnost (Completeness):** $T \models \varphi \implies T \vdash \varphi$ (pravdivé je dokazatelné).
  * **Zamítnutí (Refutace):** Důkaz sporu $T \cup \{\neg\varphi\} \vdash \bot$.
* **1. Tablo metoda (Důkaz sporem s označkovanými formulemi $T\psi, F\psi$):**
  * **Začátek důkazu formule $\varphi$ z teorie $T$:** Kořen stromu tvoří sporný předpoklad **$F\varphi$**. Kdykoliv lze na konec větve připojit axiom teorie jako **$T\alpha$** ($\alpha \in T$).
  * **Pravidla rozvoje (Atomická tabla pro spojky):**
    * **Konjunkce ($\wedge$):** $T(\varphi \wedge \psi) \implies$ pod sebe $T\varphi, T\psi$; $\quad F(\varphi \wedge \psi) \implies$ větví na $F\varphi \mid F\psi$.
    * **Disjunkce ($\vee$):** $T(\varphi \vee \psi) \implies$ větví na $T\varphi \mid T\psi$; $\quad F(\varphi \vee \psi) \implies$ pod sebe $F\varphi, F\psi$.
    * **Implikace ($\to$):** $T(\varphi \to \psi) \implies$ větví na $F\varphi \mid T\psi$; $\quad F(\varphi \to \psi) \implies$ pod sebe $T\varphi, F\psi$.
    * **Negace ($\neg$):** $T(\neg\varphi) \implies F\varphi$; $\quad F(\neg\varphi) \implies T\varphi$.
    * **Ekvivalence ($\leftrightarrow$):** $T(\varphi \leftrightarrow \psi) \implies (T\varphi, T\psi) \mid (F\varphi, F\psi)$; $\quad F(\varphi \leftrightarrow \psi) \implies (T\varphi, F\psi) \mid (F\varphi, T\psi)$.
  * **Pravidla pro kvantifikátory (PL):**
    * **Typ Svědek ($T(\exists x)\psi, F(\forall x)\psi$):** Zavedeme **nový** konstantní symbol $c$, který na dané větvi dosud není. *Aplikujeme VŽDY jako první*, abychom si vyrobili konstanty!
    * **Typ Všichni ($T(\forall x)\psi, F(\exists x)\psi$):** Dosadíme **libovolný již zavedený** term/konstantu z větve (pokud žádná není, vymyslíme si libovolnou $c_0$). *Aplikujeme až poté*, do již existujících konstant.
    * **Zanořené kvantifikátory (loupání cibule vs. volba pořadí):**
      * *Různé formule na větvi:* Lze volit pořadí $\implies$ vždy nejdřív Svědek, až pak Všichni.
      * *Zanořené v sobě (např. $T(\forall x)(\exists y)R(x, y)$):* Vnitřní kvantifikátor je zamčený — musíme jít od vnějšího k vnitřnímu: nejprve $\forall x$ (Všichni pro $c$) $\implies T(\exists y)R(c, y)$, a až poté $\exists y$ (Svědek zavede nové $d$) $\implies TR(c, d)$.
      * *Důvod nerozhodnutelnosti PL:* Střídání $\forall\exists$ může do nekonečna plodit nové konstanty ($c \to d \to e \dots$), takže větev tabla nikdy neskončí.
  * **Sporná větev:** Obsahuje položku $T\psi$ i $F\psi$ pro stejnou formuli $\psi$.
  * **Tablo důkaz:** Konečné tablo, jehož **každá větev je sporná** (uzavřená) $\implies T \vdash \varphi$.
* **2. Rezoluce (v PL):**
  * Formule převedeme do Skolemovy normální formy (otevřené klauzule).
  * Při rezoluci se pro vyhledání odpovídajícího literálu $\ell$ a $\overline{\ell}$ aplikuje **nejobecnější unifikátor (MGU)** termů.
* **3. Hilbertovský kalkul:**
  * Přímý deduktivní systém s axiomy tautologií a odvozovacím pravidlem **Modus Ponens**:
    $$\frac{\varphi, \quad \varphi \to \psi}{\psi}$$

#### Věty o kompaktnosti a úplnosti (Význam a důsledky):
* **Gödelova věta o úplnosti (pro VL i PL):**
  Pro každou teorii $T$ a sentenci $\varphi$ platí:
  $$T \models \varphi \iff T \vdash \varphi$$
  * *Význam:* Sémantická pravdivost v modelech je ekvivalentní syntaktické dokazatelnosti formálním kalkulem (např. tablem).
  * *Důsledek:* Teorie $T$ má model ($T \not\models \bot$) $\iff$ teorie $T$ je syntakticky bezesporná ($T \not\vdash \bot$).
* **Věta o kompaktnosti (pro VL i PL):**
  Teorie $T$ má model právě tehdy, když **každá její konečná podmnožina $T' \subseteq_{fin} T$ má model**:
  $$T \text{ má model} \iff \forall T' \subseteq_{fin} T: T' \text{ má model}$$
  * *Alternativní znění přes důsledek:* $T \models \varphi \iff \exists T' \subseteq_{fin} T: T' \models \varphi$.
  * *Význam:* Umožňuje převádět tvrzení o nekonečných objektech a nekonečných teoriích na vlastnosti jejich konečných částí.
* **Aplikace a příklady použití věty o kompaktnosti:**
  1. **Barevnost a bipartitnost nekonečných grafů (De Bruijn-Erdős):** Spočetně nekonečný graf $G$ je $k$-obarvitelný (resp. bipartitní) $\iff$ každý jeho konečný podgraf je $k$-obarvitelný (resp. bipartitní).
  2. **Nestandardní modely aritmetiky:** K teorii přirozených čísel $\text{Th}(\mathbb{N})$ přidáme novou konstantu $c$ a nekonečnou sadu axiomů $\{c > \underline{0}, c > \underline{1}, c > \underline{2}, \dots\}$. Každá konečná podmnožina má model v $\mathbb{N}$ (stačí zvolit $c$ větší než maximum čísel v ní). Dle kompaktnosti má celá teorie model $\implies$ existuje nestandardní model aritmetiky obsahující „nekonečně velké přirozené číslo $c$“.
  3. **Existence nekonečných modelů:** Pokud má teorie $T$ libovolně velké konečné modely (tj. pro každé $n \in \mathbb{N}$ má model s alespoň $n$ prvky), potom má $T$ i **nekonečný model**.

#### Rozhodnutelnost a kompletnost teorií:
* **Kompletní teorie:**
  * **Definice:** Bezesporná teorie $T$, ve které je každá sentence buď dokazatelná, nebo vyvratitelná ($T \vdash \varphi$ nebo $T \vdash \neg\varphi$, nemá žádné nezávislé sentence).
  * **Sémantická kritéria kompletnosti:**
    * Ve VL: Má právě jeden model ($|M(T)| = 1$).
    * V PL: Má právě jeden model až na **elementární ekvivalenci** ($\mathcal{A} \equiv \mathcal{B} \iff$ v obou strukturách platí přesně tytéž sentence). Teorie každé struktury $\text{Th}(\mathcal{A})$ je vždy kompletní.
  * **Łoś-Vaughtovo kritérium (test kompletnosti):** Je-li $T$ bezesporná teorie bez konečných modelů v spočetném jazyce a je $\kappa$-kategorická pro nějaké nespočetné $\kappa$ (všechny její modely velikosti $\kappa$ jsou izomorfní), pak $T$ je **kompletní**.
* **Pojmy rozhodnutelnosti:**
  * **Rekurzivně axiomatizovaná teorie:** Existuje algoritmus, který pro libovolnou formuli $\varphi$ rozhodne, zda $\varphi \in T$ (vstupní axiomy lze algoritmicky rozpoznat; každá konečně axiomatizovaná teorie je rekurzivní).
  * **Rozhodnutelná teorie:** Existuje algoritmus, který pro libovolnou sentenci $\varphi$ rozhodne, zda $T \models \varphi$.
  * **Částečně rozhodnutelná teorie:** Algoritmus odpoví „ano“, pokud $T \models \varphi$ (pro $T \not\models \varphi$ nemusí zastavit).
* **Vztah kompletnosti a rozhodnutelnosti (Zlatá věta):**
  * Každá rekurzivně axiomatizovaná teorie je **částečně rozhodnutelná** (lze systematicky prohledávat strom formálních důkazů).
  * Je-li rekurzivně axiomatizovaná teorie navíc **kompletní**, potom je **ROZHODNUTELNÁ**.
    * *Algoritmus:* Současně prohledáváme důkazy pro $\varphi$ a důkazy pro $\neg\varphi$. Protože $T$ je kompletní, právě jeden z důkazů $T \vdash \varphi$ nebo $T \vdash \neg\varphi$ existuje $\implies$ algoritmus vždy v konečném čase zastaví a odpoví.
* **Příklady rozhodnutelných a nerozhodnutelných teorií:**
  * *Hranice rozhodnutelnosti:* Leží přesně tam, kde je jazyk natolik silný, že v něm lze zakódovat chod počítačového programu (Turingův stroj). Jakmile to jde, narážíme na paradoxy (Gödelova věta) a neřešitelný problém zastavení programů – teorie se stává nerozhodnutelnou (neexistuje univerzální algoritmus na ověření pravdy).
  * **Rozhodnutelné teorie (Bezpečné zóny):** Algoritmus na ověření pravdivosti výroků zde existuje, protože prostředí neumožňuje vznik paradoxů (ani simulaci počítače):
    * **Presburgerova aritmetika $\text{Th}(\mathbb{N}, +, 0)$:** Obsahuje pouze sčítání. Je příliš „hloupá“ – nedá se v ní vyjádřit násobení, a tedy v ní neexistují prvočísla ani dělitelnost. Bez prvočísel nelze kódovat programy.
    * **Algebraicky uzavřená tělesa (např. $\text{Th}(\mathbb{C}, +, \cdot, 0, 1)$):** Přestože mají násobení, jsou bezpečná. Jde o prostředí, kde lze vše (kromě 0) beze zbytku vydělit a každý polynom má kořen. Ztrácí se zde diskrétní kroky a prvočísla. Nůž násobení tu nemá co řezat, nelze tu postavit mechanismus počítače (logika zde umí řešit jen vlastnosti rovnic).
    * **Teorie lineárních uspořádání:**
      * $\text{Th}(\mathbb{Q}, \le)$ – DeLO (husté uspořádání bez konců): Mezi dvěma body je vždy další bod, nedají se definovat oddělené diskrétní kroky.
      * $\text{Th}(\mathbb{Z}, \le)$ – diskrétní uspořádání bez konců: Obyčejný nekonečný řetízek bez dalších operací.
  * **Nerozhodnutelné teorie (Turingovsky úplné):** Tyto systémy jsou tak mocné, že dokážou simulovat samy sebe / běh algoritmů, čímž vznikají neřešitelné paradoxy:
    * **Predikátová logika 1. řádu s alespoň 1 binárním predikátem (Church-Turing):** Jakmile umíte popsat vztah mezi dvěma objekty (např. binární relací si uděláte „šipku z uzlu A do uzlu B“), dokážete z těchto šipek postavit strukturu jakéhokoliv algoritmu (Turingův stroj). Logika s pouhými unárními predikáty (jen izolované vlastnosti věcí) by naproti tomu rozhodnutelná byla.
    * **Peanova aritmetika $\text{Th}(\mathbb{N}, +, \cdot, 0, S, \le)$:** Přidáním násobení do prostředí přirozených čísel vzniká průšvih. Objevují se prvočísla, díky nimž lze (přes tzv. Gödelovo číslování) zakódovat jakoukoliv větu do jednoho obrovského čísla. Systém pak dokáže formulovat lhářské věty typu „Tato věta se zde nedá dokázat“ (1. Gödelova věta o neúplnosti). Systém se zavaří a je algoritmicky nerozhodnutelný.
    * *(Pozn.: Teorie grup a obecná teorie těles jsou rovněž nerozhodnutelné).*

### Past
#### Pravděpodobnostní prostor:
Trojice $(\Omega, \mathcal{F}, P)$:
* $\Omega$ = Prostor elementárních jevů (množina všech možných výsledků $\omega$).
* $\mathcal{F}$ = Prostor jevů (prvkem je náhodný jev), obsahuje prázdnou množinu a celé $\Omega$, je uzavřený na doplňky a na spočetná sjednocení.
* $P$ = Pravděpodobnostní míra, Funkce $P: \mathcal{F} \to [0, 1]$.

#### Podmíněná pravděpodobnost a nezávislost jevů:
* **Podmíněná pravděpodobnost:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$ pro $P(B) > 0$
* **Nezávislost jevů:** $P(A \cap B) = P(A) \cdot P(B)$

#### Bayesův vzorec a věta o úplné pravděpodobnosti:
$$P(B_j|A) = \frac{P(B_j \cap A)}{P(A)} = \frac{P(A|B_j) \cdot P(B_j)}{\sum_i P(A|B_i) \cdot P(B_i)}$$
* $P(B_j)$ = **apriorní pravděpodobnost** (víra před provedením testu/experimentu).
* $P(B_j|A)$ = **aposteriorní pravděpodobnost** (upravená víra po zjištění výsledku $A$).

#### Náhodná veličina a Distribuční funkce (CDF):
* **Náhodná veličina:** Funkce $X: \Omega \to \mathbb{R}$
* **Distribuční funkce:** $F_X(x) = P(X \le x)$
* **Pravděpodobnost intervalu:** $P(a < X \le b) = F_X(b) - F_X(a)$

#### Diskrétní rozdělení a pravděpodobnostní funkce (PMF):
* **Pravděpodobnostní funkce:** $p_X(x) = P(X = x)$
* **Bernoulliho $Ber(p)$:** $P(X=1) = p, \; P(X=0) = 1-p$ (indikátor $I_A$)
* **Binomické $Bin(n, p)$:** $p_X(k) = \binom{n}{k} p^k (1-p)^{n-k}$ pro $k \in \{0, \dots, n\}$ ($X = \sum_{i=1}^n I_i$)
* **Geometrické $Geom(p)$:** $p_X(k) = (1-p)^{k-1} p$ pro $k \in \{1, 2, \dots\}$ (bez paměti: $P(X > s+t \mid X > s) = P(X > t)$)
* **Poissonovo $Pois(\lambda)$:** $p_X(k) = \frac{\lambda^k}{k!} e^{-\lambda}$ pro $k \in \{0, 1, 2, \dots\}$ (použít, pokud je $n$ obrovské a $p$ malinké $\implies \lambda = np$)

#### Spojitá rozdělení a Hustota pravděpodobnosti (PDF):
* **Hustota pravděpodobnosti:** Funkce $f_X: \mathbb{R} \to [0, \infty)$ splňující $f_X(x) \ge 0$ a $\int_{-\infty}^\infty f_X(x) dx = 1$.
* **Pravděpodobnost intervalu:** $P(a \le X \le b) = \int_a^b f_X(x) dx$
* **Vztah s CDF:** $F_X(x) = \int_{-\infty}^x f_X(t) dt \iff f_X(x) = F_X'(x)$
* **Uniformní $U(a, b)$:** $f_X(x) = \frac{1}{b-a}, \; F_X(x) = \frac{x-a}{b-a}$ pro $x \in [a, b]$
* **Exponenciální $Exp(\lambda)$:** Spojitý ekvivalent geometrického (také bez paměti), $\lambda$ je počet událostí za jednotku času, průměrné čekání je $\frac{1}{\lambda}$, $f_X(x) = \lambda e^{-\lambda x}, \; F_X(x) = 1 - e^{-\lambda x}$ pro $x \ge 0$, stačí si pamatovat tu distribuční funkci a zderivovat jí
* **Normální (Gaussovo) $N(\mu, \sigma^2)$:** $f_X(x) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
  * **Standardizace na $N(0, 1)$:** $Z = \frac{X - \mu}{\sigma} \sim N(0, 1)$
  * **Výpočet pravděpodobnosti přes $\Phi$:** $P(X \le x) = \Phi\left(\frac{x - \mu}{\sigma}\right)$

#### Střední hodnota $\mathbb{E}[X]$:
* **Diskrétní:** $\mathbb{E}[X] = \sum_{x \in \operatorname{Im}(X)} x \cdot P(X = x)$
* **Spojitá:** $\mathbb{E}[X] = \int_{-\infty}^\infty x \cdot f_X(x) \, dx$
* **Diskrétní PNS:** $\mathbb{E}[g(X)] = \sum_x g(x) \cdot P(X = x)$
* **Spojité PNS:** $\mathbb{E}[g(X)] = \int_{-\infty}^\infty g(x) \cdot f_X(x) \, dx$
* **Linearita střední hodnoty (platí VŽDY, i pro ZÁVISLÉ veličiny!):**
  $$\mathbb{E}[aX + bY + c] = a\mathbb{E}[X] + b\mathbb{E}[Y] + c$$
* **Součin (platí POUZE pro NEZÁVISLÉ veličiny!):**
  $$\mathbb{E}[X \cdot Y] = \mathbb{E}[X] \cdot \mathbb{E}[Y]$$
* **Indikátorová veličina $I_A$:** $I_A \in \{0, 1\}, \; \mathbb{E}[I_A] = P(A)$ (rozklad složité veličiny na součet indikátorů $X = \sum I_{A_i} \implies \mathbb{E}[X] = \sum P(A_i)$)

#### Rozptyl $\operatorname{var}(X)$ a Kovariance $\operatorname{cov}(X, Y)$:
* **Definice rozptylu:** $\operatorname{var}(X) = \mathbb{E}\left[(X - \mathbb{E}[X])^2\right]$
* **Výpočetní vzorec:** $\operatorname{var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$
* **Vlastnosti rozptylu:**
  * $\operatorname{var}(X + b) = \operatorname{var}(X)$ (posun nemění rozptyl)
  * $\operatorname{var}(aX) = a^2 \operatorname{var}(X)$ (škálování se umocňuje)
* **Kovariance:** $\operatorname{cov}(X, Y) = \mathbb{E}\left[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])\right] = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]$
  * $X, Y$ rostou spolu $\implies \operatorname{cov} > 0$; jdou proti sobě $\implies \operatorname{cov} < 0$.
  * **Nezávislost:** Pokud jsou $X, Y$ nezávislé $\implies \operatorname{cov}(X, Y) = 0$ (opačně neplatí!).
  * **Rozptyl součtu:** $\operatorname{var}(X + Y) = \operatorname{var}(X) + \operatorname{var}(Y) + 2\operatorname{cov}(X, Y)$ (pro nezávislé/nekorelované platí $\operatorname{var}(X + Y) = \operatorname{var}(X) + \operatorname{var}(Y)$).

#### Markovova nerovnost:
* **Předpoklady:** $X \ge 0$ (nezáporná veličina) a $a > 0$.
* **Vzorec:**
  $$P(X \ge a) \le \frac{\mathbb{E}[X]}{a}$$

#### Slabý zákon velkých čísel (WLLN):
* **Předpoklady:** $X_1, X_2, \dots$ jsou stejně rozdělené nezávislé náhodné veličiny se střední hodnotou $\mu$ a konečným rozptylem $\sigma^2$.
* **Výběrový průměr:** $\overline{X_n} = \frac{1}{n}\sum_{i=1}^n X_i \implies \mathbb{E}[\overline{X_n}] = \mu, \; \operatorname{var}(\overline{X_n}) = \frac{\sigma^2}{n}$.
* **Tvrzení (konvergence v pravděpodobnosti $\overline{X_n} \xrightarrow{P} \mu$):**
  $$\forall \varepsilon > 0: \lim_{n \to \infty} P\left(|\overline{X_n} - \mu| > \varepsilon\right) = 0$$

#### Centrální limitní věta (CLV):
* **Předpoklady:** $X_1, X_2, \dots$ jsou stejně rozdělené nezávislé náhodné veličiny se střední hodnotou $\mu$ a konečným rozptylem $\sigma^2$.
* **Standardizovaná veličina:**
  $$Y_n = \frac{\sum_{i=1}^n X_i - n\mu}{\sqrt{n}\sigma} = \frac{\overline{X_n} - \mu}{\sigma / \sqrt{n}}$$
* **Tvrzení (konvergence v distribuci $Y_n \xrightarrow{d} N(0, 1)$):**
  $$\lim_{n \to \infty} P(Y_n \le x) = \Phi(x) \quad \text{pro každé } x \in \mathbb{R}$$

#### Statistika a Bodové odhady parametrů $\theta$:
* **Statistika:** Libovolná funkce dat $T(X_1, \dots, X_n)$ (je to náhodná veličina).
* **Bodový odhad $\widehat{\theta}_n$:** Statistika použitá k odhadu neznámého parametru $\theta$.
* **Vlastnosti odhadů:**
  * **Nestrannost / Nevychýlenost (Unbiasedness):** $\mathbb{E}[\widehat{\theta}_n] = \theta$ (vychýlení $\operatorname{bias}(\widehat{\theta}_n) = \mathbb{E}[\widehat{\theta}_n] - \theta$).
  * **Konzistence (Consistency):** $\widehat{\theta}_n \xrightarrow{P} \theta$ pro $n \to \infty$.
  * **Střední kvadratická chyba (MSE):**
    $$\operatorname{MSE}(\widehat{\theta}_n) = \mathbb{E}\left[(\widehat{\theta}_n - \theta)^2\right] = \operatorname{var}(\widehat{\theta}_n) + \operatorname{bias}^2(\widehat{\theta}_n)$$
* **Metoda momentů (MME):**
  * Položíme teoretickou střední hodnotu $\mathbb{E}[X] = f(\theta)$ rovnu výběrovému průměru $\overline{X_n}$ a vyjádříme $\widehat{\theta}$.
  * *Příklad ($Exp(\lambda)$):* $\mathbb{E}[X] = \frac{1}{\lambda} \implies \overline{X_n} = \frac{1}{\lambda} \implies \widehat{\lambda} = \frac{1}{\overline{X_n}}$.

#### Intervaly spolehlivosti:
* **Definice $(1-\alpha)$ intervalu spolehlivosti:** $P(D \le \theta \le H) = 1 - \alpha$ (meze $D, H$ jsou náhodné statistiky, $\theta$ je pevný neznámý parametr; pro $\alpha = 0.05 \implies 95\%$ interval).
* **Konstrukce pro $\mu$ při známém $\sigma$:**
  $$\overline{X_n} \pm z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}$$
  * **Standardní chyba průměru (Standard Error - SE):** $SE = \frac{\sigma}{\sqrt{n}}$ (směrodatná odchylka výběrového průměru $\overline{X_n}$).
  * Pro $95\%$ interval ($\alpha = 0.05$): $z_{0.025} = \Phi^{-1}(0.975) \approx 1.96 \implies \overline{X_n} \pm 1.96 \cdot \frac{\sigma}{\sqrt{n}}$.

#### Testování hypotéz:
* **Základní princip:** Nulová hypotéza $H_0$ (výchozí stav, např. $\mu = \mu_0$) vs. Alternativní hypotéza $H_1$ (např. $\mu \ne \mu_0$).
* **Chyby a hladina významnosti:**
  * **Hladina významnosti $\alpha$:** Maximální povolená pravděpodobnost chyby 1. druhu (typicky $\alpha = 0.05$).
  * **Chyba 1. druhu (Falešný poplach):** Zamítneme $H_0$, ačkoliv ve skutečnosti **platí** ($P(\text{Chyba I}) \le \alpha$).
  * **Chyba 2. druhu (Přehlédnutí):** Nezamítneme $H_0$, ačkoliv ve skutečnosti **neplatí** ($P(\text{Chyba II}) = \beta$; síla testu je $1 - \beta$).
* **Z-test (jednovýběrový test střední hodnoty při známém $\sigma$):**
  * Testová statistika: $Z = \frac{\overline{X_n} - \mu_0}{\sigma / \sqrt{n}}$
  * **Kritický obor (pro $H_1: \mu \ne \mu_0$):** Zamítáme $H_0$ na hladině $\alpha$, pokud $|Z| \ge z_{\alpha/2}$ (pro $\alpha = 0.05$ pokud $|Z| \ge 1.96$), resp. pokud $p\text{-hodnota} < \alpha$.

## Informatika

### Automaty a gramatiky
#### Základní pojmy a notace:
* **Abeceda $\Sigma$:** Konečná neprázdná množina symbolů (znaků, např. $\Sigma = \{0, 1\}$ či $\{a, b\}$).
* **Slovo (řetězec) $w \in \Sigma^*$:** Konečná posloupnost symbolů z abecedy $\Sigma$.
  * **Prázdné slovo:** Značíme $\varepsilon$ (či $\lambda$), platí délka $|\varepsilon| = 0$.
  * **Délka slova $|w|$:** Počet symbolů ve slově (např. $|auto| = 4$). Počet výskytů znaku $a$ značíme $|w|_a$.
  * **Zřetězení slov $u \cdot v$ (či $uv$):** Spojení slov za sebe. Neutrální prvek je $\varepsilon$ ($u \varepsilon = \varepsilon u = u$).
  * **Mocnina slova $u^n$:** $u^0 = \varepsilon$, $u^{n+1} = u^n \cdot u$ (např. $(ab)^2 = abab$).
  * **Množina všech slov $\Sigma^*$:** Kleeneho uzávěr abecedy (všechna konečná slova včetně $\varepsilon$).
  * **Množina neprázdných slov $\Sigma^+$:** $\Sigma^+ = \Sigma^* \setminus \{\varepsilon\}$.
* **Formální jazyk $L$:** Libovolná podmnožina slov nad abecedou $\Sigma$, tj. $L \subseteq \Sigma^*$.

#### Deterministický konečný automat (DFA):
* **Definice DFA:** Pětice $A = (Q, \Sigma, \delta, q_0, F)$, kde:
  * $Q$ je konečná neprázdná množina **stavů**.
  * $\Sigma$ je konečná neprázdná **vstupní abeceda**.
  * $\delta: Q \times \Sigma \to Q$ je **přechodová funkce** (v klasické definici totální).
  * $q_0 \in Q$ je **počáteční stav**.
  * $F \subseteq Q$ je množina **koncových (přijímajících) stavů**.
* **Úmluva o totální přechodové funkci (Dead state):** Pokud pro některý stav a písmeno není přechod definován, automat doplníme o nový „pekelný/odpadní stav“ $q_{dead} \notin F$, do kterého vedou všechny chybějící přechody a z nějž vedou smyčky pod všemi písmeny $\delta(q_{dead}, a) = q_{dead}$.
* **Rozšířená přechodová funkce $\delta^*: Q \times \Sigma^* \to Q$ (Tranzitivní uzávěr):**
  Definuje stav, do kterého automat přejde po přečtení celého slova. Induktivní definice:
  1. **Báze:** $\delta^*(q, \varepsilon) = q$ (přečtení prázdného slova stav nezmění).
  2. **Indukční krok:** $\forall w \in \Sigma^*, x \in \Sigma: \delta^*(q, w x) = \delta(\delta^*(q, w), x)$.
* **Jazyk přijímaný DFA:**
  Jazyk rozpoznávaný automatem $A$ je množina všech slov, která převedou automat z počátečního stavu do některého koncového stavu:
  $$L(A) = \{w \in \Sigma^* \mid \delta^*(q_0, w) \in F\}$$
  Třídu všech jazyků přijímaných DFA nazýváme **regulární jazyky** ($\mathcal{R}$).

#### Nedeterministický konečný automat (NFA a $\varepsilon$-NFA):
* **Definice $\varepsilon$-NFA:** Pětice $A = (Q, \Sigma, \delta, q_0, F)$, kde přechodová funkce:
  $$\delta: Q \times (\Sigma \cup \{\varepsilon\}) \to \mathcal{P}(Q)$$
  přiřazuje dvojici (stav, symbol nebo $\varepsilon$) **množinu** možných následujících stavů (může být prázdná $\emptyset$).
* **$\varepsilon$-uzávěr ($\varepsilon\text{-closure}(q)$):** Množina všech stavů dosažitelných ze stavu $q$ po nula či více $\varepsilon$-přechodech. Pro množinu $S \subseteq Q$ je $\varepsilon\text{-closure}(S) = \bigcup_{q \in S} \varepsilon\text{-closure}(q)$.
* **Rozšířená přechodová funkce pro NFA $\delta^*: Q \times \Sigma^* \to \mathcal{P}(Q)$:**
  1. $\delta^*(q, \varepsilon) = \varepsilon\text{-closure}(\{q\})$
  2. $\delta^*(q, w a) = \varepsilon\text{-closure}\left(\bigcup_{p \in \delta^*(q, w)} \delta(p, a)\right)$ pro $a \in \Sigma$.
* **Jazyk přijímaný NFA:** Slovo $w$ je přijato, pokud **alespoň jedna** větev výpočtu skončí v koncovém stavu:
  $$L(A) = \{w \in \Sigma^* \mid \delta^*(q_0, w) \cap F \ne \emptyset\}$$
* **Podmnožinová konstrukce (Převod NFA na ekvivalentní DFA):**
  * Každý nedeterministický automat lze převést na DFA přijímající stejný jazyk ($L(DFA) = L(NFA)$).
  * Stavy nového DFA jsou **podmnožiny stavů původního NFA**: $Q_{DFA} \subseteq \mathcal{P}(Q_{NFA})$.
  * Počáteční stav DFA: $S_0 = \varepsilon\text{-closure}(\{q_0\})$.
  * Přechodová funkce DFA: pro stav $S \subseteq Q_{NFA}$ a $a \in \Sigma$:
    $$\delta_{DFA}(S, a) = \varepsilon\text{-closure}\left(\bigcup_{q \in S} \delta_{NFA}(q, a)\right)$$
  * Koncové stavy DFA: všechny podmnožiny obsahující alespoň jeden koncový stav NFA:
    $$F_{DFA} = \{S \subseteq Q_{NFA} \mid S \cap F_{NFA} \ne \emptyset\}$$
  * *Složitost:* Původní NFA s $n$ stavy může vést na DFA s až $2^n$ stavy (exponenciální nárůst v nejhorším případě).
* **Minimalizace DFA (Tabulková vyškrtávací metoda / Table-Filling):**
  * *Kdy použít:* K **nalezení minimálního DFA** (sloučení nerozlišitelných stavů do reduktu) a k **ověření ekvivalence dvou DFA** ($L(A_1) = L(A_2)$ spojením jejich stavů do jedné tabulky).
  * *Jak funguje:* V trojúhelníkové tabulce všech neuspořádaných dvojic $\{p, q\}$ nejprve vyškrtneme dvojice koncový–nekoncový ($p \in F \land q \notin F$), a pak iterativně vyškrtáváme $\{p, q\}$, pokud pro nějaký symbol $a \in \Sigma$ je dvojice následníků $\{\delta(p, a), \delta(q, a)\}$ již vyškrtnutá; políčka, která zůstanou nevyškrtnutá, představují nerozlišitelné stavy ($p \sim q$), které sloučíme.

#### Regulární gramatiky (Chomského typ 3):
* **Formální definice gramatiky:** Čtveřice $G = (V, T, P, S)$, kde:
  * $V$ je konečná množina **neterminálů** (proměnných).
  * $T$ je konečná množina **terminálů** (abeceda výsledných slov), přičemž $V \cap T = \emptyset$.
  * $S \in V$ je **startovací (počáteční) neterminál**.
  * $P$ je konečná množina přepisovacích pravidel.
* **Pravidla regulární (pravé lineární) gramatiky:**
  Všechna pravidla v $P$ mají **pouze tvar**:
  $$A \to w B \quad \text{nebo} \quad A \to w \quad (A, B \in V, \, w \in T^*)$$
  (ve zkrácené standardní formě $A \to a B$, $A \to a$, $A \to \varepsilon$ pro $a \in T$).
  * *(Levá lineární gramatika má tvar $A \to B w \mid w$. Pozor: pravidla pravá a levá se v jedné gramatice NESMÍ míchat, jinak by gramatika nebyla regulární!).*
* **Jazyk generovaný gramatikou:** $L(G) = \{w \in T^* \mid S \Rightarrow^* w\}$ (množina všech terminálních slov odvoditelných ze startovacího symbolu).
* **Ekvivalence s konečnými automaty:**
  * Jazyk je generovatelný regulární gramatikou $\iff$ je přijímaný konečným automatem.
  * *Převod gramatiky na NFA:* neterminály $V$ odpovídají stavům, $S$ je počáteční stav $q_0$. Pravidlo $A \to a B$ dává přechod $\delta(A, a) \ni B$, pravidlo $A \to a$ dává přechod do koncového stavu $\delta(A, a) \ni q_{final}$, pravidlo $A \to \varepsilon \implies A \in F$.

#### Regulární výrazy (RegEx) a Kleeneho věta:
* **Přehled operátorů a symbolů v regulárních výrazech:**
  * **Základní konstanty:**
    * $\emptyset$: **Prázdný jazyk** ($L(\emptyset) = \emptyset$, nepřijímá žádné slovo).
    * $\varepsilon$ (či $\lambda$): **Prázdné slovo** ($L(\varepsilon) = \{\varepsilon\}$, slovo nulové délky; platí lemma $\emptyset^* = \{\varepsilon\}$).
    * $a \in \Sigma$: **Jednotlivý znak abecedy** ($L(a) = \{a\}$).
  * **Základní teoretické operace (induktivní definice):**
    * **$+$ (Alternativa / Sjednocení):** $\alpha + \beta$ (v programování $\alpha \mid \beta$) znamená „buď $\alpha$, nebo $\beta$“; $L(\alpha + \beta) = L(\alpha) \cup L(\beta)$.
    * **$\cdot$ (Zřetězení / Konkatenace):** $\alpha \beta$ (či $\alpha \cdot \beta$) znamená „za slovo z $\alpha$ připoj slovo z $\beta$“; $L(\alpha \beta) = L(\alpha) \cdot L(\beta)$.
    * **$*$ (Kleeneho hvězdička / Iterace):** $\alpha^*$ znamená **0 nebo více opakování** $\alpha$; $L(\alpha^*) = \bigcup_{i=0}^\infty (L(\alpha))^i = \{\varepsilon\} \cup L(\alpha) \cup L(\alpha)^2 \cup \dots$.
    * **$()$ (Závorky):** $(\alpha)$ slouží ke změně priority vyhodnocování ($L((\alpha)) = L(\alpha)$).
  * **Odvozené zkratky:**
    * **$+$ (Pozitivní iterace jako exponent):** $\alpha^+ = \alpha \cdot \alpha^*$ znamená **1 nebo více opakování** (vylučuje nultou mocninu $\varepsilon$, pokud ji neobsahuje samotné $\alpha$).
    * **$?$ (Volitelný výskyt):** $\alpha? = (\alpha + \varepsilon)$ znamená 0 nebo 1 výskyt.
  * **Priorita operátorů (od nejvyšší k nejnižší):**
    1. **Iterace:** $*$ a $+$ (vážou nejpevněji, např. $a b^* = a(b^*)$).
    2. **Zřetězení:** $\cdot$ (váže pevněji než sjednocení, např. $a b + c = (a b) + c$).
    3. **Alternativa (sjednocení):** $+$ (či $\mid$, má nejnižší prioritu).
* **Kleeneho věta (Základní ekvivalence regulárních reprezentací):**
  Následující tvrzení jsou ekvivalentní pro každý jazyk $L \subseteq \Sigma^*$:
  1. $L$ je rozpoznatelný deterministickým konečným automatem (DFA).
  2. $L$ je rozpoznatelný nedeterministickým konečným automatem (NFA / $\varepsilon$-NFA).
  3. $L$ je popsatelný regulárním výrazem (RegEx).
  4. $L$ je generovatelný regulární (pravou lineární) gramatikou.
* **Převod konečného automatu na RegEx (Metoda eliminace stavů):**
  1. **Normalizace:** Přidáme nový počáteční stav $q_{start}$ ($\varepsilon$-přechod do původního $q_0$) a nový jediný koncový stav $q_{end}$ ($\varepsilon$-přechody ze všech původních koncových stavů). Původní stavy již nejsou počáteční ani koncové.
  2. **Postupná eliminace:** Vybereme libovolný vnitřní stav $q$ k odstranění. Pro každou dvojici stavů $p$ (vstupující do $q$) a $r$ (vystupující z $q$) s přechody $p \xrightarrow{\alpha} q$, smyčkou $q \xrightarrow{\gamma} q$ a $q \xrightarrow{\beta} r$ přidáme k přímé hraně $p \xrightarrow{\delta} r$ novou větev:
     $$p \xrightarrow{\delta + \alpha \gamma^* \beta} r$$
  3. Stav $q$ a všechny jeho incidentní hrany smažeme.
  4. Opakujeme, dokud nezbudou jen stavy $q_{start}$ a $q_{end}$. Výraz na jediné zbývající hraně $q_{start} \to q_{end}$ je hledaný regulární výraz.

#### Pumping lemma pro regulární jazyky (Důkaz neregularity):
* **Znění věty (Pumping lemma / Iterační lemma):**
  Nechť $L$ je regulární jazyk. Potom existuje přirozené číslo $p \ge 1$ (pumpovací délka) takové, že každé slovo $w \in L$ o délce $|w| \ge p$ lze rozdělit na tři části $w = x y z$ splňující:
  1. $|x y| \le p$ (pumpovací část leží v prvních $p$ znacích).
  2. $|y| \ge 1$ (pumpovací část $y$ je neprázdná, $y \ne \varepsilon$).
  3. $\forall i \ge 0: x y^i z \in L$ (slovo lze libovolně „napumpovat“ i vyfouknout pro $i = 0$).
* **Použití Pumping lemmatu (Důkaz sporem, že jazyk $L$ NENÍ regulární):**
  * Hra s oponentem:
    1. Předpokládáme sporem, že $L$ je regulární $\implies$ existuje $p \ge 1$.
    2. My zvolíme zákeřné slovo $w \in L$ splňující $|w| \ge p$ (zapsané pomocí parametru $p$).
    3. Oponent ho rozdělí na $w = x y z$ splňující $|xy| \le p$ a $|y| \ge 1$. Z toho odvodíme, jak přesně $y$ musí vypadat.
    4. My zvolíme mocninu $i \ge 0$ a dokážeme, že slovo $x y^i z \notin L$, což je spor s Pumping lemmatem $\implies L$ není regulární.
  * *Klasické příklady neregulárních jazyků:*
    * $L = \{0^n 1^n \mid n \ge 0\}$ (vyžaduje neomezenou paměť na počítání nul a jedniček; zvolíme $w = 0^p 1^p \implies y = 0^k, k \ge 1 \implies x y^2 z = 0^{p+k} 1^p \notin L$).
    * $L = \{w w^R \mid w \in \{0, 1\}^*\}$ (jazyk palindromů).
    * $L = \{a^{p} \mid p \text{ je prvočíslo}\}$ nebo $\{a^{n^2} \mid n \ge 0\}$.

#### Uzávěrové vlastnosti regulárních jazyků:
* **Konstrukce součinového automatu ($A_1 \times A_2$ pro paralelní běh):** Stavy jsou dvojice $(p, q) \in Q_1 \times Q_2$, počáteční stav je $(q_{01}, q_{02})$, a přechodová funkce provádí krok v obou automatech současně: $\delta((p, q), a) = (\delta_1(p, a), \delta_2(q, a))$. Jednotlivé operace se liší pouze volbou koncových stavů:
  * **Průnik ($L_1 \cap L_2$):** $F = F_1 \times F_2$ (oba stavy musí být koncové: $p \in F_1 \land q \in F_2$).
  * **Sjednocení ($L_1 \cup L_2$):** $F = (F_1 \times Q_2) \cup (Q_1 \times F_2)$ (alespoň jeden je koncový: $p \in F_1 \lor q \in F_2$).
  * **Rozdíl ($L_1 \setminus L_2 = L_1 \cap \overline{L_2}$):** $F = F_1 \times (Q_2 \setminus F_2)$ (první je koncový a druhý ne: $p \in F_1 \land q \notin F_2$).
Třída regulárních jazyků je **uzavřená** na všechny základní operace:
1. **Sjednocení, průnik, rozdíl:** Viz součinová konstrukce výše (popř. sjednocení přes nový počáteční stav s $\varepsilon$-přechody v NFA).
4. **Doplněk (Komplement $\overline{L} = \Sigma^* \setminus L$):**
   * Vezmeme automat pro $L$, **musí být deterministický a totální!** (pokud není, nejprve determinizujeme a doplníme dead state).
   * Prohodíme koncové a nekoncové stavy: $F_{new} = Q \setminus F$.
5. **Zřetězení ($L_1 \cdot L_2$):** Propojíme koncové stavy $A_1$ pomocí $\varepsilon$-přechodů s počátečním stavem $A_2$.
6. **Kleeneho iterace ($L^*$):** Přidáme $\varepsilon$-přechody z koncových stavů zpět do počátečního stavu a nový počáteční koncový stav pro slovo $\varepsilon$.
7. **Reverze (Zrcadlení $L^R = \{w^R \mid w \in L\}$):** Všechny orientované hrany v automatu obrátíme do protisměru, z koncových stavů uděláme počáteční a z původního počátečního stavu uděláme koncový (vytvoříme NFA s novým počátečním stavem přes $\varepsilon$).

#### Bezkontextové jazyky (Chomského typ 2):
* **Bezkontextová gramatika (CFG):**
  * **Definice:** Čtveřice $G = (V, T, P, S)$, kde $V$ jsou neterminály, $T$ terminály ($V \cap T = \emptyset$), $S \in V$ startovací symbol a $P$ konečná množina pravidel tvaru:
    $$A \to \alpha \quad (A \in V, \, \alpha \in (V \cup T)^*)$$
    *(Na levé straně pravidla stojí **právě jeden neterminál bez okolního kontextu**).*
  * **Derivace a jazyk gramatiky:**
    * Krok přímé derivace: $\beta A \gamma \Rightarrow \beta \alpha \gamma$ (přepsání neterminálu $A$ podle pravidla $A \to \alpha$).
    * Reflexivně tranzitivní uzávěr $\Rightarrow^*$.
    * **Jazyk generovaný gramatikou:** $L(G) = \{w \in T^* \mid S \Rightarrow^* w\}$. Třída těchto jazyků tvoří **bezkontextové jazyky (CFL)**.
  * **Víceznačnost (Ambiguity):** Gramatika $G$ je víceznačná, pokud pro nějaké slovo $w \in L(G)$ existují alespoň dva různé derivační stromy (ekvivalentně dvě různé levé derivace).
  * **Chomského normální forma (ChNF):** Každou bezkontextovou gramatiku (bez $\varepsilon$) lze převést na ekvivalentní gramatiku s pravidly pouze ve tvaru:
    $$A \to B C \quad \text{nebo} \quad A \to a \quad (A, B, C \in V, \, a \in T)$$
    *(Je-li $\varepsilon \in L$, povoluje se navíc $S \to \varepsilon$, přičemž $S$ se pak nesmí vyskytovat na pravé straně žádného pravidla. V ChNF má derivační strom binární strukturu a slovo délky $n \ge 1$ se odvodí v přesně $2n - 1$ krocích).*
  * **Postup převodu libovolné CFG do ChNF (5 kroků):**
    1. **Odstranění $\varepsilon$-pravidel ($A \to \varepsilon$):** Najdeme nulovatelné neterminály ($A \Rightarrow^* \varepsilon$). V každém pravidle vygenerujeme všechny kombinace s vynecháním těchto neterminálů (pokud $\varepsilon \in L$, zavedeme nový start $S_0 \to S \mid \varepsilon$).
    2. **Odstranění jednotkových pravidel ($A \to B$):** Pro každý neterminál spočteme tranzitivně dosažitelné neterminály a pravidla $A \to B$ nahradíme všemi nejednotkovými pravidly z $B$.
    3. **Odstranění zbytečných symbolů (Redukce gramatiky):**
       * Nejprve odstraníme **neproduktivní symboly** (které nedokážou vygenerovat terminální slovo $A \not\Rightarrow^* w \in T^*$).
       * Poté odstraníme **nedostupné symboly** (které nelze dosáhnout ze startovacího $S$). *(Pořadí je nutné dodržet!).*
    4. **Izolace terminálů:** V pravidlech délky $\ge 2$ nahradíme každý terminál $a$ novým neterminálem $T_a$ s pravidlem $T_a \to a$.
    5. **Kaskádovité zkrácení dlouhých pravidel:** Pravidla $A \to B_1 B_2 \dots B_k$ ($k \ge 3$) rozsekáme pomocí pomocných neterminálů na dvojice: $A \to B_1 C_1, C_1 \to B_2 C_2, \dots, C_{k-2} \to B_{k-1} B_k$.
* **Zásobníkový automat (PDA – Pushdown Automaton):**
  * **Definice (Sedmice):** $P = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$, kde:
    * $Q$ je konečná množina **stavů**.
    * $\Sigma$ je konečná **vstupní abeceda**.
    * $\Gamma$ je konečná **zásobníková abeceda**.
    * $\delta: Q \times (\Sigma \cup \{\varepsilon\}) \times \Gamma \to \mathcal{P}_{FIN}(Q \times \Gamma^*)$ je **přechodová funkce**.
    * $q_0 \in Q$ je **počáteční stav**.
    * $Z_0 \in \Gamma$ je **počáteční symbol na zásobníku** (na začátku je v zásobníku právě jen $Z_0$).
    * $F \subseteq Q$ je množina **koncových stavů** (při přijímání prázdným zásobníkem může být prázdná).
  * **Anotace hrany v přechodovém diagramu a krok automatu:**
    $$\text{Hrana z } p \text{ do } q \text{ s návěstím: } \mathbf{a, X \to \gamma} \iff (q, \gamma) \in \delta(p, a, X)$$
    * Význam: Je-li automat ve stavu $p$, přečte ze vstupu symbol $a$ (nebo $\varepsilon$), z vrcholu zásobníku **vyjme (POP)** symbol $X$ a na jeho místo **uloží (PUSH)** řetězec $\gamma \in \Gamma^*$.
    * **DŮLEŽITÉ – Pořadí ukládání na zásobník (Zprava doleva):**
      Pro řetězec $\gamma = Y_1 Y_2 \dots Y_k$ (např. $\gamma = A B C$) je **první symbol zleva ($Y_1 = A$) na SAMÉM VRCHOLU ZÁSOBNÍKU**, a poslední symbol ($Y_k = C$) je nejhlouběji!
      *(Představujeme si, že na zásobník se symboly sypou zprava doleva: nejprve $C$, pak $B$, a navrch $A$. V diagramu to odpovídá: $a, Z_0 \to A Z_0$ nechá $Z_0$ dole a nad něj položí $A$).*
    * **Základní operace na hraně:**
      * $a, X \to \varepsilon$: **POP** (odebrání $X$ z vrcholu bez náhrady).
      * $a, X \to X$: **Čtení bez změny** (vrchol $X$ zůstává).
      * $a, X \to Y X$: **PUSH $Y$** (ponechání $X$ a vložení nového symbolu $Y$ nad něj).
* **Způsoby přijímání slov a třída jazyků PDA:**
  * **Dva způsoby přijímání:**
    1. **Přijetí koncovým stavem:** $L(P) = \{w \in \Sigma^* \mid (q_0, w, Z_0) \vdash^* (q_f, \varepsilon, \gamma), \, q_f \in F, \, \gamma \in \Gamma^*\}$.
    2. **Přijetí prázdným zásobníkem:** $L_\varepsilon(P) = \{w \in \Sigma^* \mid (q_0, w, Z_0) \vdash^* (q, \varepsilon, \varepsilon), \, q \in Q\}$.
    * *Ekvivalence:* Obě definice přijímání jsou navzájem převoditelné a rozpoznávají **přesně stejnou třídu jazyků** ($\mathcal{L}(PDA_F) = \mathcal{L}(PDA_\varepsilon)$).
  * **Ekvivalence PDA a CFG a konstrukce 1-stavového PDA (Top-down analýza):**
    * Třída jazyků přijímaných nedeterministickými PDA je přesně třída **bezkontextových jazyků**: $\mathcal{L}(\text{PDA}) = \mathcal{L}(\text{CFG}) = \text{CFL}$.
    * **Konstrukce PDA z libovolné CFG (přijímá prázdným zásobníkem):** Sestrojíme automat $P = (\{q\}, T, V \cup T, \delta, q, S, \emptyset)$ s jediným stavem $q$, kde všechny přechody jsou smyčky $q \to q$:
      1. **Expanze neterminálu (uhodnutí pravidla):** Pro každé pravidlo $A \to \alpha \in P$:
         $$\delta(q, \varepsilon, A) \ni (q, \alpha) \quad (\text{hrana: } \varepsilon, A \to \alpha)$$
      2. **Porovnání terminálu se vstupem (Match):** Pro každý terminál $a \in T$:
         $$\delta(q, a, a) = \{(q, \varepsilon)\} \quad (\text{hrana: } a, a \to \varepsilon)$$
      *(Automat simuluje levou sentenciální formu: neterminál na vrcholu zásobníku nahradí pravou stranou pravidla, a jakmile je na vrcholu terminál, porovná ho se vstupem a smaže. Po přečtení slova zůstane zásobník prázdný).*
  * **Deterministické PDA (DPDA) a deterministické bezkontextové jazyky (DCFL):**
    * DPDA má v každé konfiguraci nejvýše jeden možný přechod (pokud je definován $\varepsilon$-krok pro $(q, \varepsilon, X)$, nesmí pro tentýž stav a vrchol zásobníku existovat krok pod žádným $a \in \Sigma$).
    * **Nedeterminismus u PDA zvyšuje sílu:**
      $$\text{Regulární (RL)} \subsetneq \text{DCFL} \subsetneq \text{CFL}$$
    * Jazyky z $\text{CFL} \setminus \text{DCFL}$ (např. symetrické palindromy sudé délky $\{w w^R \mid w \in \{0, 1\}^*\}$) vyžadují nedeterminismus pro uhodnutí středu slova.
* **Uzávěrové vlastnosti CFL:**
  * **CFL JE uzavřená na:**
    * **Sjednocení** ($L_1 \cup L_2$), **zřetězení** ($L_1 \cdot L_2$), **Kleeneho iteraci** ($L^*$).
    * **Průnik s regulárním jazykem:** Je-li $L \in \text{CFL}$ a $R \in \text{REG}$, pak $L \cap R \in \text{CFL}$ (konstrukce synchronního součinu PDA $\times$ DFA).
  * **CFL NENÍ uzavřená na:**
    * **Průnik:** Např. $L_1 = \{a^n b^n c^m \mid n, m \ge 0\} \in \text{CFL}$ a $L_2 = \{a^m b^n c^n \mid n, m \ge 0\} \in \text{CFL}$, ale jejich průnik $L_1 \cap L_2 = \{a^n b^n c^n \mid n \ge 0\} \notin \text{CFL}$!
    * **Doplněk (Komplement):** Kdyby byla uzavřená na doplněk, z De Morgana $L_1 \cap L_2 = \overline{\overline{L_1} \cup \overline{L_2}}$ by musela být uzavřená i na průnik (spor).
* **Pumping lemma pro bezkontextové jazyky (uvwxy lemma):**
  * **Znění:** Nechť $L \in \text{CFL}$. Pak existuje $p \ge 1$ takové, že každé slovo $z \in L$ o délce $|z| \ge p$ lze rozdělit na 5 částí $z = u v w x y$ splňující:
    1. $|v w x| \le p$ (pumpovací úsek je omezen délkou $p$).
    2. $|v x| \ge 1$ (alespoň jedno ze slov $v, x$ je neprázdné).
    3. $\forall i \ge 0: u v^i w x^i y \in L$ (obě části $v$ a $x$ se pumpují současně stejnou mocninou).
  * *Použití:* Důkaz sporem, že jazyk není bezkontextový (např. pro $L = \{a^n b^n c^n \mid n \ge 0\}$ zvolíme $z = a^p b^p c^p$; úsek $vwx$ o délce $\le p$ nemůže zasáhnout symboly $a$ i $c$ zároveň, napumpováním se poruší rovnost počtů $a, b, c$).

#### Rekurzivně spočetné jazyky, gramatiky typu 0 a Turingovy stroje:
* **Gramatika typu 0 (Neomezená gramatika):**
  * Pravidla mají zcela obecný tvar:
    $$\alpha \to \omega \quad (\alpha, \omega \in (V \cup T)^*, \, |\alpha|_V \ge 1)$$
    *(Jediná podmínka: levá strana $\alpha$ musí obsahovat alespoň jeden neterminál. Na rozdíl od kontextových gramatik zde pravidla mohou libovolně zkracovat řetězce).*
  * **Jazyky generované gramatikami typu 0** jsou právě **rekurzivně spočetné jazyky** ($\mathcal{L}_0$ / RE – Recursively Enumerable).
* **Turingův stroj (TM – Turing Machine):**
  * **Formální definice (Sedmice):** $M = (Q, \Sigma, \Gamma, \delta, q_0, B, F)$, kde:
    * $Q$ je konečná množina **stavů**.
    * $\Sigma$ je konečná neprázdná množina **vstupních symbolů** ($B \notin \Sigma$).
    * $\Gamma$ je konečná množina **páskových symbolů**, přičemž $\Gamma \supseteq \Sigma$ a $Q \cap \Gamma = \emptyset$.
    * $\delta: (Q \setminus F) \times \Gamma \to Q \times \Gamma \times \{L, R\}$ je (částečná) **přechodová funkce**.
      *(Je-li stroj ve stavu $q \in Q \setminus F$ a čte symbol $X \in \Gamma$, pak $\delta(q, X) = (p, Y, D)$ znamená: přejde do stavu $p \in Q$, na pásku zapíše symbol $Y \in \Gamma$ [přepíše $X$] a posune čtecí/zápisovou hlavu ve směru $D \in \{L, R\}$ [doleva či doprava]).*
    * $q_0 \in Q$ je **počáteční stav**.
    * $B \in \Gamma \setminus \Sigma$ je **prázdný symbol (Blank)**. Na začátku výpočtu je na pásce zapsáno vstupní slovo $w \in \Sigma^*$ a všechny ostatní buňky pásky (do nekonečna vpravo i vlevo) obsahují symbol $B$.
    * $F \subseteq Q$ je množina **koncových (přijímajících) stavů**. Jakmile stroj vstoupí do stavu z $F$, výpočet končí přijetím.
  * **Konfigurace TM a krok výpočtu:**
    * Konfigurace se zapisuje řetězcem $\alpha q \beta$ ($\alpha, \beta \in \Gamma^*, q \in Q$): hlava čte první symbol slova $\beta$, slovo $\alpha$ leží vlevo od hlavy a zbytek $\beta$ vpravo.
    * Počáteční konfigurace pro vstup $w \in \Sigma^*$: $q_0 w$ (pro $w = \varepsilon$ je to $q_0 B$).
    * Krok výpočtu značíme $\vdash$.
  * **Jazyk přijímaný Turingovým strojem:**
    $$L(M) = \{w \in \Sigma^* \mid q_0 w \vdash^* \alpha q_f \beta, \, q_f \in F, \, \alpha, \beta \in \Gamma^*\}$$
    * **Chování pro slova mimo jazyk ($w \notin L(M)$):** Stroj buď po konečném počtu kroků **zastaví v nekoncovém stavu** (nedefinovaný přechod), NEBO se **zacyklí (běží do nekonečna)**.
  * **Ekvivalence výpočetních modelů TM (Churchova-Turingova teze):**
    * *Vícepáskový TM:* má $k$ nezávislých pásek s vlastními hlavami. Lze nasimulovat 1-páskovým TM se stopami (Tracks) s kvadratickým časovým zpomalením $O(T^2)$.
    * *Nedeterministický TM (NTM):* $\delta(q, X) \subseteq Q \times \Gamma \times \{L, R\}$. Lze nasimulovat deterministickým TM (prohledáváním stromu konfigurací do šířky BFS) s exponenciálním zpomalením $O(2^{c \cdot T})$.
    * *Obousměrně nekonečná páska:* ekvivalentní jednosměrně nekonečné pásce (pásku rozdělíme na horní a dolní stopu).
    * *Závěr:* Žádná z těchto modifikací **nezvyšuje třídu rozpoznatelných jazyků**, definují přesně tutéž třídu $\mathcal{L}_0$.

#### Algoritmická rozhodnutelnost a nerozhodnutelné problémy:
* **Rozhodnutelnost vs. Rekurzivní spočetnost:**
  * **Rozhodnutelný problém (Rekurzivní jazyk $\mathcal{R}$):** Existuje algoritmus (TM), který se pro **každý** vstup v konečném čase zastaví a řekne ANO / NE.
  * **Částečně rozhodnutelný (Rekurzivně spočetný jazyk $\mathcal{L}_0$ / RE):** Pro ANO se TM v konečném čase zastaví a přijme; pro NE se ale může **zacyklit (běžet do nekonečna)**.
  * **Postova věta:** Jazyk $L$ je rozhodnutelný právě tehdy, když je on i jeho doplněk rekurzivně spočetný:
    $$L \in \mathcal{R} \iff L \in \mathcal{L}_0 \ \land \ \overline{L} \in \mathcal{L}_0$$
    *(Běží-li paralelně TM pro $L$ i TM pro $\overline{L}$, jeden z nich musí pro libovolný vstup zastavit).*

* **Přehled hlavních nerozhodnutelných problémů:**
  * **1. Problém zastavení (Halting Problem – $H$):**
    * *Otázka:* Zastaví zadaný Turingův stroj $M$ na vstupu $w$?
    * *Výsledek:* Je částečně rozhodnutelný ($H \in \mathcal{L}_0$), ale **algoritmicky nerozhodnutelný** ($H \notin \mathcal{R}$).
    * *Intuice důkazu (Paradox lháře v kódu / Cantorova diagonalizace):*
      Kdyby existoval univerzální analyzátor `Halt(M, w)`, napíšeme program `Rebel(P)`: zeptá se analyzátoru na `Halt(P, P)` a **udělá naschvál přesný opak** (pokud `Halt` předpoví, že $P$ zastaví, `Rebel` se schválně zacyklí; pokud předpoví, že poběží navždy, `Rebel` ihned skončí).
      Co se stane, když programu předložíme jeho vlastní kód `Rebel(Rebel)`?
      $$\text{Rebel se zastaví} \iff \text{Halt předpověděl zacyklení} \iff \text{Rebel se nezastaví}$$
      Ať `Halt` odpoví cokoliv, lže (obdoba věty *„Tato věta je lež“*). Protože samotný kód `Rebel` je triviální, jediná neexistující věc je samotný analyzátor `Halt` $\implies$ univerzální algoritmus pro detekci zastavení nemůže existovat.
    * *Doplněk $\overline{H}$ (stroje, co nezastaví):* Není ani rekurzivně spočetný ($\overline{H} \notin \mathcal{L}_0$).
  * **2. Diagonální jazyk ($L_d$):**
    * Jazyk kódů strojů, které nepřijmou svůj vlastní kód: $L_d = \{w_i \mid M_i \text{ nepřijme } w_i\}$.
    * **Není ani rekurzivně spočetný** ($L_d \notin \mathcal{L}_0$) – dokazuje se Cantorovým sporem na diagonále matice strojů a slov.
  * **3. Postův korespondenční problém (PCP – skládání domina):**
    * *Zadání:* Máme domino kostky s horním a dolním slovem $\left[\frac{w_i}{x_i}\right]$ (seznamy $A, B$).
    * *Otázka:* Lze za sebe poskládat řadu kostek (s opakováním) tak, aby horní slovo bylo stejné jako dolní? ($w_{i_1}\dots w_{i_m} = x_{i_1}\dots x_{i_m}$).
    * *Výsledek:* PCP je **algoritmicky nerozhodnutelný**.
    * *Využití (redukce na bezkontextové gramatiky):* Z PCP se dokazuje nerozhodnutelnost klíčových otázek o CFG:
      * **Ekvivalence:** Zda $L(G_1) = L(G_2)$? $\implies$ **nerozhodnutelné!**
      * **Disjunktnost (Prázdnost průniku):** Zda $L(G_1) \cap L(G_2) = \emptyset$? $\implies$ **nerozhodnutelné!**
      * **Univerzalita:** Zda $L(G) = \Sigma^*$? $\implies$ **nerozhodnutelné!**
      * **Víceznačnost:** Zda je daná CFG víceznačná? $\implies$ **nerozhodnutelné!**
      *(POZOR na zkouškový chyták: Samotná prázdnost $L(G) = \emptyset$ a konečnost $L(G)$ jsou pro CFG ROZHODNUTELNÉ odstraněním neproduktivních symbolů).*
  * **4. Riceova věta:**
    * *Každá netriviální sémantická vlastnost rekurzivně spočetných jazyků je nerozhodnutelná.*
    * *Lidsky:* Z pouhého zdrojového kódu Turingova stroje nelze algoritmicky zjistit **žádnou vlastnost jeho chování** (např. zda přijímá prázdný jazyk $L(M) = \emptyset$, zda je jazyk konečný, regulární, nebo zda přijímá konkrétní slovo).
  * **5. Algoritmická redukce ($A \le B$):**
    * Převod vstupu $w \in A \iff f(w) \in B$ pomocí algoritmu $f$, který vždy zastaví.
    * *Princip:* Pokud víme, že $A$ je nerozhodnutelný a svedeme $A \le B$, pak je i **$B$ nutně nerozhodnutelný** (řešení $B$ by vyřešilo i $A$).

#### Chomského hierarchie a zařazení konkrétního jazyka:
* **Přehledná tabulka Chomského hierarchie:**

| Typ | Třída jazyků | Tvar přepisovacích pravidel gramatiky | Rozpoznávací automat | Uzávěrové vlastnosti |
| :--- | :--- | :--- | :--- | :--- |
| **Typ 3** | **Regulární (RL)** | $A \to w B \mid w$ ($A, B \in V, w \in T^*$) | **DFA, NFA** (Konečný automat) | $\cup, \cap, \overline{L}, \cdot, *$ (vše) |
| **Typ 2** | **Bezkontextové (CFL)** | $A \to \alpha$ ($A \in V, \alpha \in (V \cup T)^*$) | **PDA** (Zásobníkový automat) | $\cup, \cdot, *$, průnik s REG<br>*(NENÍ na $\cap, \overline{L}$)* |
| **Typ 1** | **Kontextové (CSL)** | $\gamma A \beta \to \gamma \omega \beta$ ($\omega \ne \varepsilon$) nebo monotónní $\|\alpha\| \le \|\beta\|$ *(výjimka $S \to \varepsilon$)* | **LBA** (Lineárně ohraničený automat) | $\cup, \cap, \overline{L}, \cdot, *$ (vše včetně doplňku) |
| — | **Rekurzivní ($\mathcal{R}$)** | *(nemá přirozenou generativní gramatiku)* | **Úplný TM** (vždy zastaví – algoritmus) | $\cup, \cap, \overline{L}, \cdot, *$ (vše včetně doplňku) |
| **Typ 0** | **Rekurzivně spočetné (RE)** | $\alpha \to \beta$ ($\alpha, \beta \in (V \cup T)^*, \|\alpha\|_V \ge 1$) | **Turingův stroj (TM)** | $\cup, \cap, \cdot, *$ *(NENÍ na doplněk $\overline{L}$)* |

* **Vztah tříd (Ostrá hierarchie):**
  $$\mathcal{L}_3 \subsetneq \mathcal{L}_2 \subsetneq \mathcal{L}_1 \subsetneq \mathcal{R} \subsetneq \mathcal{L}_0$$

* **Metodika zařazení konkrétního jazyka do Chomského hierarchie na zkoušce:**
  Pro určení *nejnižší* vrstvy $\mathcal{L}_k$, do které jazyk $L$ patří, musíme provést dva kroky:
  1. **Krok 1 (Důkaz, že $L \in \mathcal{L}_k$):**
     * Pro $\mathcal{L}_3$: Napíšeme regulární výraz, regulární gramatiku, nebo nakreslíme DFA/NFA.
     * Pro $\mathcal{L}_2$: Zkonstruujeme bezkontextovou gramatiku (CFG) nebo navrhneme PDA (využití LIFO zásobníku k párování 1 dvojice počtů).
     * Pro $\mathcal{L}_1$: Sestrojíme lineárně ohraničený automat LBA (pracuje pouze v prostoru délky vstupního slova, např. metoda Ping-Pong se škrtáním symbolů) nebo monotónní gramatiku.
     * Pro $\mathcal{R}$: Navrhneme Turingův stroj (algoritmus), který pro každé slovo garantovaně zastaví.
     * Pro $\mathcal{L}_0$: Sestrojíme TM, který pro slova z $L$ zastaví a přijme.
  2. **Krok 2 (Důkaz, že $L \notin \mathcal{L}_{k+1}$ – nepatří do nižší třídy):**
     * Pro vyvrácení regularity ($L \notin \mathcal{L}_3$): použijeme **Pumping lemma pro RL** (sporem) nebo Myhillovu-Nerodovu větu (nekonečně mnoho prefixů s různými residui).
     * Pro vyvrácení bezkontextovosti ($L \notin \mathcal{L}_2$): použijeme **Pumping lemma pro CFL ($uvwxy$)** nebo uzávěrové vlastnosti (např. $L \cap R \notin \text{CFL}$ pro $R \in \text{REG}$).
     * Pro vyvrácení rozhodnutelnosti ($L \notin \mathcal{R}$): použijeme **algoritmickou redukci** z problému zastavení ($H \le L$) nebo **Riceovu větu**.
     * Pro vyvrácení rekurzivní spočetnosti ($L \notin \mathcal{L}_0$): použijeme redukci z doplňku halting problému ($\overline{H} \le L$) nebo diagonálního jazyka ($L_d \le L$).

* **Kanonické příklady jazyků pro jednotlivá patra hierarchie:**
  * **Typ 3 (Regulární):**
    * $L = \{a^n b^m \mid n, m \ge 0\}$ (RegEx: $a^* b^*$, 2 stavy).
    * $L = \{w \in \{a, b\}^* \mid |w|_a \equiv 0 \pmod 2\}$ (konečná paměť na paritu).
  * **Typ 2, ale ne Typ 3 (Bezkontextové neregulární):**
    * $L = \{a^n b^n \mid n \ge 0\}$ (CFG: $S \to a S b \mid \varepsilon$; vyžaduje čítání jedné závislosti do neomezené hloubky).
    * $L = \{w w^R \mid w \in \{a, b\}^*\}$ (symetrické palindromy; zásobník ověřuje inverzní pořadí).
    * Dyckův jazyk správného uzávorkování: $S \to (S) S \mid \varepsilon$.
  * **Typ 1, ale ne Typ 2 (Kontextové nebezkontextové):**
    * $L = \{a^n b^n c^n \mid n \ge 1\}$ (tři vzájemně vázané počty; PDA zvládne porovnat jen 2, LBA škrtá trojice $a, b, c$ sem a tam v prostoru délky slova).
    * $L = \{a^n b^m c^n d^m \mid n, m \ge 1\}$ (křížové závislosti).
    * $L = \{w w \mid w \in \{a, b\}^*\}$ (opakování stejného slova v přímém pořadí; vyžaduje netriviální porovnání dvou polovin, LBA zvládne, PDA ne).
  * **Rekurzivní, ale ne Typ 1 ($\mathcal{R} \setminus \mathcal{L}_1$):**
    * Jazyky vyžadující prostor rostoucí rychleji než lineárně (např. paměť $2^n$ nebo čas Ackermannovy funkce).
  * **Typ 0, ale ne Rekurzivní ($\mathcal{L}_0 \setminus \mathcal{R}$):**
    * Problém zastavení $H = \{\langle M, w \rangle \mid M \text{ zastaví na } w\}$.
    * Univerzální jazyk $L_u = \{\langle M, w \rangle \mid M \text{ přijme } w\}$.
    * Jazyk dvojic kódů CFG s neprázdným průnikem $\{\langle G_1, G_2 \rangle \mid L(G_1) \cap L(G_2) \ne \emptyset\}$.
  * **Mimo Typ 0 (Nerekurzivně spočetné, $\notin \mathcal{L}_0$):**
    * Diagonální jazyk $L_d = \{w_i \mid M_i \text{ nepřijme } w_i\}$.
    * Doplněk problému zastavení $\overline{H} = \{\langle M, w \rangle \mid M \text{ nezastaví na } w\}$.
    * Jazyk všech kódů TM, které nepřijímají žádné slovo: $L_{empty} = \{\langle M \rangle \mid L(M) = \emptyset\}$.

### Ads

#### Časová a prostorová složitost algoritmů:
* **Časová a prostorová složitost (Model RAM):**
  * **Časová složitost $T(n)$:** Celkový počet elementárních kroků/instrukcí RAMu provedených během výpočtu jako funkce velikosti vstupu $n = |x|$ ($T: \mathbb{N} \to \mathbb{R}$).
  * **Prostorová složitost $S(n)$:** Rozsah indexů (maximální počet) použitých buněk paměti RAMu během výpočtu jako funkce velikosti vstupu ($S: \mathbb{N} \to \mathbb{R}$).
* **Měření velikosti dat a cenové modely RAMu:**
  * **Jednotková cena (Uniform cost):** Každá operace a přístup k libovolné buňce stojí $\mathcal{O}(1)$.
    * *Problém neomezených čísel:* Pokud by buňky mohly obsahovat libovolně velká čísla bez penalizace, lze prostorovou a časovou složitost hackovat (do jednoho obřího čísla zakódujeme celou paměť a bitovými posuny/násobením provádíme paralelní výpočty).
    * *Řešení v teorii i praxi:* Omezení velikosti čísel konstantou nebo polynomem / velikostí slova $c \cdot \log n$ bitů (do buňky se vejde právě adresa/pointer na $n$-prvkový vstup).
  * **Logaritmická cena (Logarithmic cost):** Cena operace a přístupu k buňce odpovídá počtu bitů čísel: přístup k číslu $x$ stojí $\mathcal{O}(\log |x|)$ a operace nad $x, y$ stojí $\mathcal{O}(\log |x| + \log |y|)$. Fyzikálně a matematicky věrnější, ale pracná na výpočet.
  * **Poměrná logaritmická cena:** Cena operace je poměr logaritmů velikosti vstupu a velikosti čísel (pro polynomem omezená čísla je cena operace konstantní $\mathcal{O}(1)$).
* **Složitost v nejlepším, nejhorším a průměrném případě:**
  * **Nejhorší případ (Worst-case) $T_{worst}(n) = \max_{|x|=n} T(x)$:** Maximum přes všechny možné vstupy velikosti $n$. Nejpoužívanější přístup – poskytuje **garantovanou horní mez** (algoritmus nikdy nepoběží déle).
  * **Nejlepší případ (Best-case) $T_{best}(n) = \min_{|x|=n} T(x)$:** Minimum přes všechny vstupy velikosti $n$ (např. InsertSort na seřazeném poli provede jen $n-1$ porovnání $\implies \mathcal{O}(n)$).
  * **Průměrný případ (Average-case) $T_{avg}(n) = \sum_{|x|=n} P(x) \cdot T(x)$:** Střední hodnota času přes všechny vstupy při daném pravděpodobnostním rozdělení $P(x)$ (typicky rovnoměrném). Dobře vystihuje reálné chování (např. Quicksort má v průměru $\mathcal{O}(n \log n)$, i když v nejhorším případě $\mathcal{O}(n^2)$), ale je matematicky obtížná na odvození.
* **Asymptotická notace (Landauovy symboly):**
  * **Horní mez ($\mathcal{O}$):** $f \in \mathcal{O}(g) \iff \exists c > 0, n_0 \in \mathbb{N} \ \forall n \ge n_0: f(n) \le c \cdot g(n)$.
  * **Dolní mez ($\Omega$):** $f \in \Omega(g) \iff \exists c > 0, n_0 \in \mathbb{N} \ \forall n \ge n_0: f(n) \ge c \cdot g(n)$.
  * **Těsná mez ($\Theta$):** $f \in \Theta(g) \iff f \in \mathcal{O}(g) \land f \in \Omega(g)$ ($\exists c_1, c_2 > 0, n_0: c_1 g(n) \le f(n) \le c_2 g(n)$).
  * **Ostrá horní mez ($o$):** $f \in o(g) \iff \lim_{n \to \infty} \frac{f(n)}{g(n)} = 0$.
  * **Ostrá dolní mez ($\omega$):** $f \in \omega(g) \iff \lim_{n \to \infty} \frac{f(n)}{g(n)} = \infty$.

#### Třídy složitosti (P, NP, převoditelnost a NP-úplnost):
* **Rozhodovací problémy:**
  * Problém kódovaný jako funkce $P: \{0, 1\}^* \to \{0, 1\}$ s odpovědí $\{\text{ANO}, \text{NE}\}$, odpovídající jazyku $L = \{x \in \{0, 1\}^* \mid P(x) = 1\}$.
* **Třídy P a NP:**
  * **Třída P (Polynomiální čas):**
    Problémy řešitelné deterministickým algoritmem v polynomiálním čase vzhledem k délce vstupu:
    $$L \in \text{P} \iff \exists \text{ deterministický algoritmus } A, \exists \text{ polynom } p: \forall x \in \{0, 1\}^*: A(x) \text{ doběhne do } p(|x|) \text{ kroků} \land A(x) = L(x)$$
    *(Třída prakticky a efektivně zvládnutelných problémů – např. 2-SAT, nejkratší cesty, minimální kostra, párování v bipartitním grafu).*
  * **Třída NP (Nedeterministický polynomiální čas / Polynomiální verifikace):**
    Problémy, kde kladnou odpověď (svědka/certifikát) lze **v polynomiálním čase zkontrolovat**:
    $$L \in \text{NP} \iff \exists \text{ deterministický verifikátor } V \in \text{P}, \exists \text{ polynom } g: \forall x: L(x) = 1 \iff \exists y \text{ (certifikát)}, |y| \le g(|x|) \land V(x, y) = 1$$
    *(Např. pro problém Kliky velikosti $k$ je certifikátem seznam $k$ vrcholů; verifikátor v čase $\mathcal{O}(k^2)$ ověří, že mezi všemi dvojicemi vede hrana).*
    *Ekvivalentní definice:* Jazyky přijímané nedeterministickým Turingovým strojem v polynomiálním čase.
  * **Vztah P a NP:**
    $$\text{P} \subseteq \text{NP}$$
    *(Zda $\text{P} = \text{NP}$, nebo $\text{P} \subsetneq \text{NP}$, je nejvýznamnější otevřený problém informatiky; všeobecně se předpokládá $\text{P} \ne \text{NP}$).*
* **Převoditelnost problémů (Karpova polynomiální redukce $A \le_P B$ neboli $A \to B$):**
  * Problém $A$ je polynomiálně převoditelný na problém $B$ ($A \le_P B$), pokud existuje funkce $f: \{0, 1\}^* \to \{0, 1\}^*$ vyčíslitelná v polynomiálním čase taková, že:
    $$\forall x \in \{0, 1\}^*: x \in A \iff f(x) \in B$$
  * **Vlastnosti převoditelnosti:**
    * *Reflexivní:* $A \le_P A$ ($f$ je identita).
    * *Tranzitivní:* $A \le_P B \land B \le_P C \implies A \le_P C$ (složení dvou polynomiálních funkcí $f \circ g$ je opět polynomiální).
    * *Není antisymetrická:* Např. problém „vstup má sudou délku“ a „vstup má lichou délku“ lze převádět oběma směry, ale nejsou to totožné problémy.
    * *Existují vzájemně nepřevoditelné problémy:* Mezi triviálním problémem „vždy odpověz 0“ a „vždy odpověz 1“ převod neexistuje.
    * Převoditelnost tvoří **částečné kvaziuspořádání** na množině problémů.
  * **Klíčové věty o převodu:**
    1. Pokud $A \le_P B$ a $B \in \text{P}$, pak $A \in \text{P}$ *(pokud umíme $B$ řešit rychle, umíme i $A$)*.
    2. Pokud $A \le_P B$ a $A \notin \text{P}$, pak $B \notin \text{P}$ *(těžkost se přenáší dopředu)*.
* **NP-těžkost a NP-úplnost:**
  * **NP-těžký problém (NP-hard):** Problém $L$ je NP-těžký, pokud je na něj polynomiálně převoditelný **každý** problém z NP:
    $$\forall K \in \text{NP}: K \le_P L$$
    *(NP-těžký problém nemusí sám ležet v NP; může být klidně nerozhodnutelný, např. Halting problem je NP-těžký).*
  * **NP-úplný problém (NP-complete / NPC):** Problém $L$ je NP-úplný, pokud:
    1. $L \in \text{NP}$ (leží v NP – má polynomiální verifikátor), a zároveň
    2. $L$ je NP-těžký ($\forall K \in \text{NP}: K \le_P L$).
  * **Věta o dokazování NP-úplnosti:**
    Pokud je problém $A$ NP-úplný, problém $B \in \text{NP}$ a platí **$A \le_P B$**, pak je **$B$ také NP-úplný**!
    *(POZOR na směr převodu: redukujeme ZE známého NP-úplného problému NA nový zkoumaný problém!).*
  * **Cook-Levinova věta:** Problém SAT (splnitelnost Booleovských formulí) je **NP-úplný** (historicky první dokázaný NP-úplný problém, přímo simuluje kroky libovolného NTM pomocí logického obvodu/formule).
* **Katalog NP-úplných problémů:**
  * **Logické:**
    * **SAT:** Splnitelnost CNF formule ($\exists$ pravdivostní ohodnocení proměnných?).
    * **3-SAT:** SAT, kde každá klauzule obsahuje nejvýše 3 literály.
    * **3,3-SAT:** 3-SAT, kde se navíc každá proměnná vyskytuje v celé formuli nejvýše 3krát.
    * **Circuit-SAT:** Splnitelnost Booleovského obvodu s hradly AND, OR, NOT.
    *(Pozor: 2-SAT $\in \text{P}$ přes silně souvislé komponenty implikačního grafu; Horn-SAT $\in \text{P}$).*
  * **Grafové:**
    * **Klika (Clique):** Existuje v $G$ úplný podgraf na alespoň $k$ vrcholech?
    * **Nezávislá množina (Independent Set):** Existuje v $G$ množina alespoň $k$ vrcholů, mezi nimiž nevede žádná hrana?
    * **Vrcholové pokrytí (Vertex Cover):** Existuje v $G$ množina nejvýše $k$ vrcholů, která pokrývá všechny hrany grafu?
    * **3D-párování (3D-Matching):** Mějme množiny $A, B, C$ stejné velikosti a trojice $T \subseteq A \times B \times C$. Existuje perfektní podmnožina trojic pokrývající každý prvek právě jednou? *(Pozor: 2D párování v bipartitním grafu $\in \text{P}$).*
    * **$k$-obarvitelnost:** Lze vrcholy obarvit $k$ barvami bez konfliktu sousedů? (Pro $k \ge 3$ je NP-úplné; pro $k = 2$ je v P – test bipartitnosti).
    * **Hamiltonovská kružnice / cesta:** Existuje kružnice procházející každý vrchol právě jednou? *(Pozor: Eulerovský tah procházející každou hranu právě jednou je v P!).*
    * **Problém obchodního cestujícího (TSP – rozhodovací):** Existuje hamiltonovská kružnice s délkou $\le K$?
  * **Číselné (slabě NP-úplné, mají pseudopolynomiální algoritmus přes dynamické programování):**
    * **Součet podmnožiny (Subset Sum):** Množina celých čísel $S$ a cíl $K$. Existuje podmnožina se součtem přesně $K$?
    * **Batoh (Knapsack – rozhodovací):** Lze vybrat věci s celkovou vahou $\le W$ a cenou $\ge C$?
    * **Dva loupežníci (Partition):** Lze rozdělit čísla na dvě hromádky se stejným součtem?
* **Konkrétní konstrukce polynomiálních převodů (zkouškové šablony):**
  * **1. Klika $\leftrightarrow$ Nezávislá množina:**
    * Vrcholy $S \subseteq V$ tvoří kliku v $G \iff$ tvoří nezávislou množinu v doplňkovém grafu $\overline{G} = (V, \binom{V}{2} \setminus E)$.
    * Převodní funkce: $f(G, k) = (\overline{G}, k)$. Spočtení doplňku trvá $\mathcal{O}(V^2)$, tedy v polynomiálním čase.
  * **2. SAT $\to$ 3-SAT (Štípání dlouhých klauzulí):**
    * Cíl: Nahradit klauzule délky $\ell > 3$ klauzulemi délky 3 při zachování ekvisplnitelnosti.
    * Klauzuli $(\alpha \lor \beta)$ s $|\alpha| = 2$ a $|\beta| = \ell - 2$ nahradíme pomocí nového pomocného literálu $z$:
      $$(\alpha \lor z) \land (\beta \lor \neg z)$$
    * První klauzule má délku 3, druhá délku $\ell - 1$. Tento krok opakujeme na druhou klauzuli, dokud nemá délku 3. Počet kroků i nových proměnných je lineární vzhledem k délce formule.
  * **3. 3-SAT $\to$ 3,3-SAT (Omezení počtu výskytů proměnné):**
    * Nechť proměnná $x$ má v formuli $k > 3$ výskytů.
    * Nahradíme její výskyty novými proměnnými $x_1, x_2, \dots, x_k$ (každá se vyskytne 1× v původních klauzulích).
    * Ekvivalenci všech $x_i$ vynutíme kružnicí implikací: $(x_1 \implies x_2) \land (x_2 \implies x_3) \land \dots \land (x_k \implies x_1)$, zapsaných jako 2-literálové klauzule:
      $$(\neg x_1 \lor x_2) \land (\neg x_2 \lor x_3) \land \dots \land (\neg x_k \lor x_1)$$
    * Každá proměnná $x_i$ se pak vyskytne v celé formuli celkem nejvýše 3krát (1× původně, 2× v kružnici).
  * **4. 3-SAT $\to$ Nezávislá množina:**
    * Mějme 3-CNF formuli s $m$ klauzulemi $C_1, \dots, C_m$.
    * **Konstrukce grafu:**
      1. Pro každou klauzuli $C_i = (\ell_{i,1} \lor \ell_{i,2} \lor \ell_{i,3})$ vytvoříme trojúhelník (kliku $K_3$) o 3 vrcholech odpovídajících literálům této klauzule (celkem $3m$ vrcholů).
      2. Spojíme hranami všechny dvojice vrcholů, které představují vzájemně konfliktní literály (např. vrchol $x$ a vrchol $\neg x$).
      3. Požadovanou velikost nezávislé množiny položíme $k = m$.
    * **Důkaz ekvivalence:**
      * $(\implies)$ Je-li formule splnitelná, v každé klauzuli vybereme alespoň 1 pravdivý literál (celkem $m$ vrcholů). Mezi nimi nevede žádná hrana z trojúhelníků (z každého bereme 1) ani žádná konfliktní hrana (žádný literál není zároveň $x$ i $\neg x$) $\implies$ tvoří nezávislou množinu velikosti $m$.
      * $(\impliedby)$ Z každého trojúhelníku $K_3$ může nezávislá množina obsahovat nejvýše 1 vrchol. Aby měla velikost $m$, musí obsahovat právě 1 vrchol z každého trojúhelníku. Protože v ní nevedou hrany, neobsahuje žádnou dvojici $x$ a $\neg x$. Nastavíme-li tyto vybrané literály na 1, získáme korektní splňující ohodnocení celé formule.

#### Metoda rozděl a panuj a Master theorem:
* **Princip paradigmatu Rozděl a panuj (Divide and Conquer):**
  1. **Rozděl (Divide):** Původní problém velikosti $n$ rozložíme na $a \ge 1$ menších podproblémů stejného typu, každý o velikosti $n / b$ ($b > 1$).
  2. **Panuj (Conquer):** Tyto podproblémy vyřešíme rekurzivním voláním algoritmu. (Dojdeme-li k bázovému případu konstantní velikosti, např. $n \le 1$, vyřešíme jej triviálně přímo v čase $\Theta(1)$).
  3. **Spoj (Combine):** Výsledky podproblémů sloučíme do celkového řešení původního problému.
  * **Sestavení rekurentní rovnice pro čas $T(n)$:**
    $$T(n) = a \cdot T\left(\frac{n}{b}\right) + f(n)$$
    kde $f(n) = \Theta(n^c)$ je režie na rozdělení a následné sloučení podproblémů v kořeni rekurze.

* **Master theorem (Kuchařková věta pro rekurence – bez důkazu):**
  * **Znění věty:** Mějme rekurentní rovnici $T(n) = a \cdot T(n/b) + \Theta(n^c)$, kde konstanty splňují $a \ge 1, b > 1, c \ge 0$. Porovnáme poměr $\frac{a}{b^c}$ (nebo ekvivalentně $c$ vůči $\log_b a$):
    1. **Případ 1 (Rovnováha, $\frac{a}{b^c} = 1 \iff c = \log_b a$):**
       $$T(n) = \Theta(n^c \log n) = \Theta(n^{\log_b a} \log n)$$
    2. **Případ 2 (Převládá kořen, $\frac{a}{b^c} < 1 \iff c > \log_b a$):**
       $$T(n) = \Theta(n^c)$$
    3. **Případ 3 (Převládají listy, $\frac{a}{b^c} > 1 \iff c < \log_b a$):**
       $$T(n) = \Theta(n^{\log_b a})$$

* **Kanonické aplikace Master Theoremu:**
  * **1. Mergesort (Třídění sléváním):**
    * Pole rozdělíme na 2 poloviny ($a=2, b=2$), po setřídění je slijeme v lineárním čase ($c=1$):
      $$T(n) = 2 T(n/2) + \Theta(n) \implies a=2, b=2, c=1 \implies \frac{a}{b^c} = \frac{2}{2^1} = 1 \implies T(n) = \Theta(n \log n)$$
  * **2. Karacubovo násobení dlouhých čísel:**
    * Chceme vynásobit dvě $n$-ciferná čísla $X, Y$. Rozdělíme je na poloviny o $n/2$ cifrách:
      $$X = A \cdot z^{n/2} + B, \quad Y = C \cdot z^{n/2} + D$$
      $$X \cdot Y = AC \cdot z^n + (AD + BC) \cdot z^{n/2} + BD$$
    * *Naivní přístup:* Vyžaduje 4 násobení ($AC, AD, BC, BD$) polovičních čísel $\implies T(n) = 4 T(n/2) + \Theta(n) \implies \Theta(n^{\log_2 4}) = \Theta(n^2)$.
    * *Karacubův trik:* Střední člen spočteme pomocí jednoho součinového členu a odečtení již známých $AC$ a $BD$:
      $$AD + BC = (A + B)(C + D) - AC - BD$$
    * Stačí **pouze 3 násobení** čísel poloviční délky ($AC, BD, (A+B)(C+D)$) a několik lineárních sčítání/posunů:
      $$T(n) = 3 T(n/2) + \Theta(n) \implies a=3, b=2, c=1$$
      $$\frac{a}{b^c} = \frac{3}{2^1} = 1.5 > 1 \implies T(n) = \Theta(n^{\log_2 3}) \approx \Theta(n^{1.585}) \quad (\text{výrazně rychlejší než } \mathcal{O}(n^2)!)$$
  * **3. Binární vyhledávání:**
    * Jeden podproblém poloviční velikosti, porovnání v čase $\mathcal{O}(1)$:
      $$T(n) = T(n/2) + \Theta(1) \implies a=1, b=2, c=0 \implies \frac{a}{b^c} = \frac{1}{1} = 1 \implies T(n) = \Theta(\log n)$$
  * **4. Strassenovo násobení matic:**
    * Matice $n \times n$ rozdělíme na bloky $n/2 \times n/2$. Namísto 8 násobení bloků použijeme důmyslnou algebraickou kombinaci se 7 násobeními:
      $$T(n) = 7 T(n/2) + \Theta(n^2) \implies a=7, b=2, c=2 \implies \frac{a}{b^c} = \frac{7}{4} > 1 \implies T(n) = \Theta(n^{\log_2 7}) \approx \Theta(n^{2.807})$$

#### Binární vyhledávací stromy (BVS) a AVL stromy:
* **Definice Binárního vyhledávacího stromu (BVS / BST):**
  * Zakořeněný binární strom, kde každý uzel $v$ nese unikátní klíč $k(v)$ z uspořádané množiny.
  * **Invariant BVS:** Pro každý uzel $v$ platí:
    * $\forall u \in L(v): k(u) < k(v)$ (všechny klíče v levém podstromu jsou menší),
    * $\forall w \in R(v): k(w) > k(v)$ (všechny klíče v pravém podstromu jsou větší).
  * *Vlastnost In-order průchodu:* Průchod stromem v pořadí (Levý podstrom, Kořen, Pravý podstrom) navštíví prvky v **přísně vzestupném seřazeném pořadí v čase $\Theta(n)$**.
* **Operace s nevyvažovaným BVS:**
  * **Find(x):** Porovnáme $x$ s $k(v)$. Pokud $x = k(v)$, uzel je nalezen; pokud $x < k(v)$, pokračujeme rekurzivně vlevo, jinak vpravo. Složitost: $\mathcal{O}(h)$, kde $h$ je hloubka stromu.
  * **Insert(x):** Provedeme vyhledání $x$. Skončíme-li v prázdném ukazateli (listu), připojíme sem nový uzel s klíčem $x$. Složitost: $\mathcal{O}(h)$.
  * **Delete(x):** Vyhledáme uzel $v$ s klíčem $x$. Rozlišujeme 3 případy podle počtu synů:
    1. *Uzel $v$ je list (0 synů):* Prostě jej smažeme a u jeho rodiče vynulujeme ukazatel.
    2. *Uzel $v$ má právě 1 syna:* Uzel $v$ vyjmeme a jeho jediného syna připojíme přímo na rodiče uzlu $v$.
    3. *Uzel $v$ má 2 syny:* V pravém podstromu $R(v)$ nalezneme **symetrického následníka** $s$ (nejlevější uzel v $R(v)$, tj. minimum z $R(v)$). Hodnotu $k(s)$ zkopírujeme do $v$ a uzel $s$ smažeme ze stromu (uzel $s$ má z definice nejvýše 1 pravého syna $\implies$ redukce na případ 1 nebo 2).
  * *Zásadní slabina nevyvažovaného BVS:* Závislost tvaru stromu na pořadí vkládání. Při vkládání již seřazených dat ($1, 2, 3, \dots, n$) strom zdegraduje na dlouhý jednostranný řetízek (spojový seznam) s hloubkou $h = \Theta(n)$ a operace trvají $\Theta(n)$!
* **AVL stromy (definice):**
  * **Definice AVL stromu:** Binární vyhledávací strom splňující **invariant hloubkového vyvážení**:
    Pro každý jeho vrchol $v$ platí, že hloubka (výška) levého a pravého podstromu se liší nejvýše o jedna:
    $$|h(L(v)) - h(R(v))| \le 1$$
  * **Věta o hloubce:** AVL strom na $n$ vrcholech má hloubku $\Theta(\log n)$ (přesněji $h < 1.44 \log_2(n+2)$).
  * *Poznámka k rotacím:* Invariant se při vkládání/mazání obnovuje lokálními rotacemi ukazatelů v čase $\mathcal{O}(1)$ (proto operace `Find`, `Insert`, `Delete` trvají $\mathcal{O}(\log n)$). **Jednoduchá rotace (L/R)** řeší přímé přetížení (LL/RR) povýšením syna na místo otce, zatímco **dvojitá rotace (LR/RL)** řeší zalomené přetížení „cik-cak“ vytažením prostřední hodnoty z nevyvážené trojice uzlů na pozici nového lokálního kořene.

#### Třídění (primitivní algoritmy, Quicksort a dolní mez):
* **Pojem inverze a dolní mez pro lokální výměny:**
  * **Inverze v poli $A$:** Dvojice indexů $(i, j)$ taková, že $i < j$ a zároveň $A[i] > A[j]$.
  * Počet inverzí udává míru „nesetříděnosti“ pole. Setříděné pole má 0 inverzí, reverzně setříděné pole má maximum $\binom{n}{2} = \frac{n(n-1)}{2}$ inverzí.
  * *Klíčový fakt:* Prohozením dvou sousedních prvků v poli se počet inverzí změní **nejvýše o 1**. Každý algoritmus prohazující pouze sousední prvky (Bubblesort, Insertsort) proto musí v nejhorším případě provést $\Omega(n^2)$ operací!
* **Primitivní třídicí algoritmy:**
  * **Bubblesort (Probublávání):**
    * Opakovaně prochází pole zleva doprava a porovnává sousedy $A[i], A[i+1]$. Jsou-li ve špatném pořadí, prohodí je. V každém průchodu největší zbývající prvek „probublá“ na svou finální pozici na konci.
    * Vlastnosti: In-place, stabilní.
    * Složitost: Nejhorší i průměrná $\Theta(n^2)$ ($\frac{n(n-1)}{2}$ porovnání/výměn). S bool příznakem (zda došlo k výměně) je nejlepší případ $\Theta(n)$ (již setříděné pole).
  * **Insertsort (Třídění vkládáním):**
    * Udržuje setříděný prefix $A[1 \dots i-1]$. V $i$-tém kroku vezme prvek $A[i]$ a zatřídí jej na správné místo v prefixu posunem větších prvků doprava.
    * Vlastnosti: In-place, stabilní, velmi nízká režie.
    * Složitost:
      * Nejhorší případ: $\Theta(n^2)$ (reverzně seřazené pole).
      * Nejlepší případ: $\Theta(n)$ (již seřazené pole – pro každý prvek provede jediné porovnání a žádný posun!).
      * Využití: Ideální pro malá pole ($n \le 16$, kde překonává Quicksort i Mergesort) a pro téměř setříděná data s malým počtem inverzí ($T(n) = \mathcal{O}(n + I)$).
* **Quicksort:**
  * **Princip algoritmu:**
    1. Zvolíme prvek $p$ (pivot).
    2. **Partition (Rozdělení pole):** Přeskládáme pole v čase $\mathcal{O}(n)$ na 3 úseky: prvky menší než $p$, prvky rovné $p$, prvky větší než $p$.
    3. Rekurzivně zavoláme Quicksort na levý a pravý úsek.
    4. Spojení je triviální $\mathcal{O}(1)$ – pole je setříděné přímo na místě (in-place).
  * **Složitost Quicksortu:**
    * **Nejhorší případ: $\Theta(n^2)$**
      Nastává při nejhorším možném dělení (např. pivot je pokaždé minimem nebo maximem, takže jeden podproblém má velikost $0$ a druhý $n-1$). Rekurence: $T(n) = T(n-1) + \Theta(n) \implies \Theta(n^2)$.
    * **Průměrný případ: $\Theta(n \log n)$**
      * **Zdůvodnění přes skoromedián a lemma o džbánu:**
        * Náhodně zvolený pivot padne s pravděpodobností $p = \frac{1}{2}$ do prostředních 50 % prvků (mezi 25. a 75. percentil) – tzv. **skoromedián**.
        * Když zvolíme skoromedián, oba podproblémy mají velikost nejvýše $\frac{3}{4} n$.
        * **Lemma o džbánu** (střední doba čekání na 1. úspěch v geometrickém rozdělení s $p = \frac{1}{2}$): v průměru potřebujeme $\frac{1}{p} = 2$ pokusy (kroky dělení), než trefíme skoromedián.
        * Hloubka stromu „úspěšných“ dělení je nejvýše $\log_{4/3} n = \mathcal{O}(\log n)$. Se započtením neúspěšných pokusů je očekávaná hloubka nejvýše $2 \log_{4/3} n = \mathcal{O}(\log n)$.
        * Na každé hladině stromu rekurze je součet velikostí podproblémů $\le n$ (prvky se nekopírují), takže práce na hladinu je $\mathcal{O}(n)$. Celkový očekávaný čas: $\mathcal{O}(n) \times \mathcal{O}(\log n) = \mathbf{\Theta(n \log n)}$.
      * **Lze použít Kuchařkovou větu (Master Theorem)?**
        * **Přímo pro průměrný případ NE:** Master Theorem striktně vyžaduje symetrické dělení na $a$ podproblémů **stejné** velikosti $n/b$ ($T(n) = a \cdot T(n/b) + f(n)$). Quicksort dělí pole asymetricky a náhodně: $T(n) = T(k) + T(n-1-k) + \Theta(n)$.
        * *(Master Theorem lze použít pouze v nejlepším případě dokonalého půlení mediánem: $T(n) = 2T(n/2) + \Theta(n) \implies a=2, b=2, c=1 \implies \frac{a}{b^c} = 1 \implies \Theta(n \log n)$).*
* **Dolní odhad složitosti porovnávacích třídicích algoritmů ($\Omega(n \log n)$):**
  * **Model rozhodovacího stromu (Decision Tree):**
    * Libovolný deterministický třídicí algoritmus založený na vzájemném porovnávání prvků lze reprezentovat jako binární rozhodovací strom:
      * *Vnitřní uzly:* Odpovídají dotazům na porovnání $A[i] \le A[j]$ se 2 výstupy (ANO / NE).
      * *Listy:* Reprezentují výsledné permutace prvků pole.
      * *Délka cesty od kořene k listu:* Počet porovnání provedených algoritmem pro daný vstup.
      * *Výška stromu $h$:* Počet porovnání v **nejhorším případě**.
  * **Matematické odvození meze:**
    1. Vstup o $n$ prvcích může mít $n!$ různých uspořádání (permutací).
    2. Aby algoritmus fungoval korektně pro každý možný vstup, musí mít rozhodovací strom alespoň $n!$ různých listů (jinak by dvě různé permutace skončily ve stejném listu, což by pro jednu z nich znamenalo chybné setřídění):
       $$\text{Počet listů } L \ge n!$$
    3. Binární strom s výškou $h$ má nejvýše $2^h$ listů ($L \le 2^h$).
    4. Z toho plyne dolní odhad na výšku stromu $h$:
       $$h \ge \lceil \log_2(n!) \rceil$$
    5. Odhad hodnoty $\log_2(n!)$:
       $$\log_2(n!) = \sum_{i=1}^n \log_2 i \ge \sum_{i=\lceil n/2 \rceil}^n \log_2 i \ge \frac{n}{2} \log_2\left(\frac{n}{2}\right) = \frac{n}{2} (\log_2 n - 1) = \Omega(n \log n)$$
#### Grafové algoritmy:
* **Prohledávání grafu do šířky (BFS) a do hloubky (DFS):**
  * **Prohledávání do šířky (BFS – Breadth-First Search):**
    * *Datová struktura:* Fronta (FIFO).
    * *Stavy vrcholů:* Nenavštívený (neviděný), Otevřený (vložený do fronty), Zavřený (vyjmutý a zpracovaný).
    * *Průběh:* Začíná v počátečním vrcholu $s$, vloží jej do fronty. Dokud fronta není prázdná, vyjme vrchol $v$, prohlédne všechny jeho sousedy; pokud je soused $w$ neviděný, označí jej jako otevřený a vloží do fronty. Po prohlédnutí všech sousedů se $v$ označí jako zavřený.
    * *Vlastnost:* Prochází graf po soustředných vlnách (hladinách) vzdálenosti od $s$. Nalezne cestu s **minimálním počtem hran** $\implies$ slouží k hledání nejkratších cest v neohodnocených grafech (resp. s jednotkovými délkami hran).
    * *Složitost:* $\Theta(n + m)$.
  * **Prohledávání do hloubky (DFS – Depth-First Search):**
    * *Datová struktura:* Zásobník (LIFO, typicky implicitně přes rekurzi).
    * *Časové známky:* `in[v]` (čas objevení / otevření) a `out[v]` (čas dokončení / opuštění / zavření).
    * *Průběh:* Funkce $DFS(v)$ označí $v$ jako otevřený (`in[v] = ++time`), pro každou hranu $vw \in E$ rekurzivně zavolá $DFS(w)$, pokud je $w$ neviděný. Po prozkoumání všech sousedů vrchol uzavře (`out[v] = ++time`).
    * *Opakované DFS:* Spustí se pro každý dosud neviděný vrchol $\implies$ projde všechny komponenty souvislosti.
    * *Klasifikace hran v orientovaném grafu:*
      * *Stromové:* hrany použité při prvním vstupu do neviděného vrcholu.
      * *Zpětné:* hrany vedoucí k otevřenému předkovi $\implies$ **orientovaný graf obsahuje cyklus $\iff$ DFS najde zpětnou hranu**!
      * *Dopředné:* hrany k zavřenému potomkovi mimo strom.
      * *Příčné:* hrany mezi větvemi stromu (vedou zprava doleva).
    * *Složitost:* $\Theta(n + m)$.

* **Topologické třídění orientovaných grafů:**
  * **Definice topologického uspořádání:**
    Lineární uspořádání $\le$ na množině vrcholů $V$ orientovaného grafu $G = (V, E)$ takové, že pro každou hranu $(u, v) \in E$ platí:
    $$u \le v \quad (\text{všechny hrany směřují zleva doprava})$$
  * **Věta o existenci:** Orientovaný graf má topologické uspořádání právě tehdy, když je **acyklický (DAG – Directed Acyclic Graph)**. (Může jich existovat více).
  * **Algoritmy konstrukce topologického uspořádání:**
    1. *Odtrháváním zdrojů (Kahnův algoritmus):*
       * Spočteme vstupní stupně `in-deg(v)` všech vrcholů. Vrcholy s `in-deg = 0` (zdroje) vložíme do fronty.
       * Opakovaně vyjmeme vrchol $u$, zařadíme jej do výstupního pořadí a pro všechny hrany $(u, w)$ snížíme `in-deg(w)--`. Pokud `in-deg(w)` klesne na 0, přidáme $w$ do fronty.
       * Složitost: $\Theta(n + m)$. Pokud na konci neobsahuje všechny vrcholy, graf má cyklus.
    2. *Pomocí DFS (zavírací časy):*
       * Spustíme opakované DFS. Vrcholy se zavírají v **přesně opačném pořadí**, než je topologické (uzel, z nějž už nevede žádná hrana, se zavře jako první).
       * Seřazením vrcholů podle **klesajícího času opuštění `out[v]`** (nebo vkládáním zavřených vrcholů na začátek spojového seznamu) získáme platné topologické uspořádání v čase $\Theta(n + m)$.

* **Nejkratší cesty v ohodnocených grafech (Dijkstra a Bellman-Ford):**
  * **Dijkstrův algoritmus:**
    * *Použití:* Nejkratší cesty z jednoho startovního vrcholu $s$ do všech ostatních v grafech s **nezápornými vahami hran ($w(e) \ge 0$)**.
    * *Princip (Hladový výběr + prioritní fronta):*
      * Nastavíme $h(s) = 0$, pro ostatní $h(v) = +\infty$.
      * Dokud existují otevřené vrcholy, vybereme otevřený vrchol $u$ s **minimálním $h(u)$**, označíme jej za zavřený (trvalý) a pro všechny jeho následníky $v$ provedeme relaxaci:
        $$\text{pokud } h(v) > h(u) + w(u, v) \implies h(v) = h(u) + w(u, v), \ P(v) = u$$
      * *Klíčová vlastnost:* Díky nezáporným vahám je každý vrchol vybrán a zavřen **právě jednou** (jeho vzdálenost se už nikdy nezmenší).
      * *Proč nefunguje pro záporné hrany:* Hladový předpoklad selže – do již zavřeného vrcholu by mohla vést ještě kratší cesta přes zápornou hranu objevenou později.
    * *Složitost podle datové struktury prioritní fronty:*
      * Pole (hledání minima průchodem): $\Theta(n^2)$ (vhodné pro velmi husté grafy $m \approx n^2$).
      * Binární halda: $n \times \text{ExtractMin} + m \times \text{DecreaseKey} \implies \mathcal{O}((n + m) \log n)$.
      * Fibonacciho halda: $\mathcal{O}(m + n \log n)$.
  * **Bellmanův-Fordův algoritmus:**
    * *Použití:* Grafy s libovolnými vahami hran (i zápornými), **bez záporných cyklů**. Dokáže detekovat záporný cyklus dosažitelný ze zdroje!
    * *Princip (Relaxace fázováním):*
      * Nejkratší jednoduchá cesta v grafu s $n$ vrcholy má nejvýše $n-1$ hran.
      * Algoritmus pracuje v $n-1$ fázích. V každé fázi provede relaxaci přes **všechny hrany grafu**:
        $$\forall (u, v) \in E: \text{pokud } h(v) > h(u) + w(u, v) \implies h(v) = h(u) + w(u, v), \ P(v) = u$$
      * *Invariant:* Na konci $i$-té fáze odpovídá $h(v)$ délce nejkratšího sledu z $s$ do $v$ o nejvýše $i$ hranách.
      * *Detekce záporného cyklu:* Provedeme $n$-tou fázi. Pokud se ještě v $n$-té fázi nějaké $h(v)$ zmenší, graf obsahuje záporný cyklus!
    * *Složitost:* $\mathcal{O}(n \cdot m)$ ($n$ fází, v každé projdeme $m$ hran).

* **Minimální kostra grafu (Jarník a Borůvka):**
  * **Zadání úlohy:** V neorientovaném souvislém grafu $G = (V, E, w)$ najít kostru $T \subseteq E$ s minimálním celkovým součtem vah $\sum_{e \in T} w(e)$.
  * **Řezové lemma (Cut lemma – základní kámen kostrových algoritmů):**
    Nechť $R$ je libovolný řez v grafu (množina hran mezi $S$ a $V \setminus S$, kde $\emptyset \subsetneq S \subsetneq V$). Nechť $e$ je **nejlehčí hrana tohoto řezu**. Pak hrana $e$ **leží v nějaké minimální kostře** (jsou-li váhy hran unikátní, leží v každé minimální kostře).
  * **Jarníkův algoritmus (Prim-Jarník):**
    * *Princip (Hladový růst jednoho stromu):* Začneme s libovolným vrcholem $v_0$ jako stromem $T$. V každém kroku uvažujeme řez mezi stromem $T$ a zbytkem grafu $V \setminus V(T)$, nalezneme nejlehčí hranu tohoto řezu a přidáme ji i s novým vrcholem do stromu $T$.
    * *Implementace:* Pomocí prioritní fronty (haldy) analogicky jako u Dijkstry. V haldě udržujeme aktivní hrany vedoucí ze stromu $T$ do jednotlivých vrcholů mimo $T$.
    * *Složitost:* $\mathcal{O}(m \log n)$ s binární haldou (případně $\mathcal{O}(m + n \log n)$ s Fibonacciho haldou).
  * **Borůvkův algoritmus:**
    * *Princip (Paralelní růst lesa):* Na začátku tvoří každý vrchol samostatnou komponentu (les izolovaných vrcholů).
    * V každé fázi: **pro každou komponentu** souvislosti nalezneme její nejlehčí incidentní hranu (spojující ji s jinou komponentou). Všechny tyto vybrané hrany naráz přidáme do kostry a komponenty sloučíme.
    * *Počet fází a složitost:*
      * V každé fázi se počet komponent zmenší alespoň na polovinu $\implies$ algoritmus provede **nejvýše $\lceil \log_2 n \rceil$ fází**.
      * V jedné fázi trvá nalezení nejlehčích hran pro všechny komponenty $\mathcal{O}(m)$ (pomocí BFS/DFS na komponentách).
      * Celková složitost: $\mathcal{O}(m \log n)$. (Pro rovinné grafy dokonce lineární $\mathcal{O}(n)$).

* **Toky v sítích (Ford-Fulkersonův algoritmus):**
  * **Definice sítě a toku:**
    * Síť: Orientovaný graf $G = (V, E)$, zdroj $s \in V$, stok $t \in V$, nezáporné kapacity hran $c: E \to \mathbb{R}_0^+$.
    * **Tok $f: E \to \mathbb{R}$** splňuje:
      1. *Kapacitní omezení:* $0 \le f(e) \le c(e)$ pro každou hranu $e \in E$.
      2. *Kirchhoffův zákon (zachování toku):* Pro každý vnitřní uzel $v \in V \setminus \{s, t\}$ platí:
         $$\sum_{e \in in(v)} f(e) = \sum_{e \in out(v)} f(e)$$
    * *Velikost toku $|f|$:* Čistý odtok ze zdroje $\sum_{e \in out(s)} f(e) - \sum_{e \in in(s)} f(e)$.
  * **Reziduální síť $G_f$ a zlepšující (nenasycená) cesta:**
    * Pro každou hranu $e = (u, v)$ evidujeme:
      * *Dopřednou hranu $(u, v)$* s reziduální kapacitou $r(u, v) = c(e) - f(e)$ (prostor pro navýšení toku).
      * *Zpětnou hranu $(v, u)$* s reziduální kapacitou $r(v, u) = f(e)$ (možnost vrátit / přesměrovat již poslaný tok).
    * **Zlepšující cesta (Augmenting path):** Orientovaná cesta z $s$ do $t$ v reziduální síti $G_f$, na které mají všechny hrany kladnou reziduální kapacitu ($r > 0$).
  * **Ford-Fulkersonův algoritmus:**
    1. Začneme s nulovým tokem $f(e) = 0$ pro všechna $e \in E$.
    2. Dokud v reziduální síti $G_f$ existuje zlepšující cesta $P$ z $s$ do $t$:
       * Spočteme rezervu celé cesty: $\varepsilon = \min_{e \in P} r(e) > 0$.
       * Podél cesty $P$ upravíme tok:
         - pro dopředné hrany: $f(e) \gets f(e) + \varepsilon$,
         - pro zpětné hrany: $f(e) \gets f(e) - \varepsilon$.
    3. Jakmile žádná zlepšující cesta z $s$ do $t$ neexistuje, tok $f$ je **maximální**.
  * **Konvergence a složitost:**
    * *Celočíselné kapacity:* V každém kroku vzroste velikost toku alespoň o celočíselnou $1 \implies$ algoritmus garantovaně skončí v čase $\mathcal{O}(m \cdot |f_{max}|)$ a vrátí celočíselný maximální tok.
    * *Racionální kapacity:* Vynásobením společným jmenovatelem převedeme na celočíselné $\implies$ algoritmus zastaví.
    * *Iracionální kapacity:* Obecný Ford-Fulkerson se může zacyklit a konvergovat k nesprávné hodnotě!
    * *Edmonds-Karpův algoritmus (polynomiální varianta):* Zlepšující cestu hledá pomocí **BFS (nejkratší podle počtu hran)**. Garantuje polynomiální čas $\mathcal{O}(n \cdot m^2)$ pro libovolné kapacity.
  * **Věta o maximálním toku a minimálním řezu (Max-Flow Min-Cut Theorem):**
    $$\text{Velikost maximálního toku } |f_{max}| = \text{Kapacita minimálního } s\text{-}t \text{ řezu } c(A, B)$$
    *(Minimální řez tvoří množina vrcholů $A$ dosažitelných ze zdroje $s$ v reziduální síti $G_f$ po skončení algoritmu a $B = V \setminus A$).*

### Architektura počítačů, OS a Programovací jazyky

#### 1. Reprezentace dat v paměti, hardware a čtení C / C++:
* **Reprezentace celých čísel (Dvojkový doplněk – Two's Complement):**
  * Kladná čísla začínají bitem `0`, záporná čísla začínají bitem `1`.
  * **Pravidlo pro negaci čísla:** Invertuj všechny bity (NOT / `~`) a přičti 1:
    $$-x = \sim x + 1$$
    *(Příklad na 4 bitech: $+3 = 0011_2 \implies \sim(0011_2) = 1100_2 \implies +1 = 1101_2 = -3$).*
  * **Rozsah na $k$ bitech:** Od $-2^{k-1}$ do $+2^{k-1} - 1$. (Asymetrie: záporných je o 1 více, $0$ má jediný kód, nejmenší záporné číslo nelze znegovat bez přetečení!).
* **Reprezentace reálných čísel s plovoucí řádovou čárkou (IEEE 754):**
  * Každé číslo je uloženo ve 3 složkách: **Znaménko $s$** (1 bit), **Exponent $E$** (posunutý o bias $B$), **Mantisa $M$** (normalizovaná, implicitní jednička před čárkou $1.M$):
    $$x = (-1)^s \cdot (1 + M) \cdot 2^{E - B}$$
  * **Typy a velikosti:**
    * `float` (32 bitů): $s = 1\text{b}$, $E = 8\text{b}$ (bias $B = 127$), $M = 23\text{b}$.
    * `double` (64 bitů): $s = 1\text{b}$, $E = 11\text{b}$ (bias $B = 1023$), $M = 52\text{b}$.
  * **Speciální hodnoty:**
    * *Exponent samé 1 a mantisa 0:* $\pm \infty$ (při dělení nenulového čísla nulou).
    * *Exponent samé 1 a mantisa $\ne 0$:* $\text{NaN}$ (Not a Number, např. $0/0$, $\sqrt{-1}$, neplatí ani $\text{NaN} == \text{NaN}$).
    * *Exponent samé 0:* Denormalizovaná čísla (umožňují postupný podtékání k nule) a $\pm 0$.
* **Endianita (Pořadí ukládání bajtů v paměti):**
  * Mějme 4bajtové číslo `0x12345678` uložené na paměťové adrese `0x100`:
    * **Little-Endian (x86, x86-64, ARM):** *Nejméně významný bajt (LSB = `0x78`) je na nejnižší adrese:*
      `[0x100] = 0x78`, `[0x101] = 0x56`, `[0x102] = 0x34`, `[0x103] = 0x12`.
    * **Big-Endian (Síťový pořádek / Network Byte Order):** *Nejvíce významný bajt (MSB = `0x12`) je na nejnižší adrese:*
      `[0x100] = 0x12`, `[0x101] = 0x34`, `[0x102] = 0x56`, `[0x103] = 0x78`.
* **Bitové operace a masky v C# (POZOR na přetypování!):**
  * Operátory: `&` (AND), `|` (OR), `^` (XOR), `~` (bitová negace NOT), `<<` (posun vlevo), `>>` (posun vpravo).
  * **Zkouškový chyták v C#:** Bitové operace nad menšími typy (`byte`, `short`) kompilátor **automaticky povyšuje na `int`**! Výsledek je nutné explicitně přetypovat:
    ```csharp
    byte b = 0b0000_1111;
    byte mask = (byte)(~b); // BEZ (byte) CHYBA PŘEKLADU: Cannot implicitly convert 'int' to 'byte'
    ```
  * **Základní triky s maskami na $k$-tém bitu:**
    * *Test bitu:* `bool isSet = (val & (1 << k)) != 0;`
    * *Nastavení bitu na 1:* `val |= (1 << k);`
    * *Vynulování bitu na 0:* `val &= ~(1 << k);`
    * *Přepnutí bitu (Toggle):* `val ^= (1 << k);`
* **Zarovnání dat v paměti (Data Alignment & Padding):**
  * **Pravidlo hardwaru:** $k$-bajtový primitivní typ (např. 4B `int`, 8B `double`) musí v paměti začínat na **adrese dělitelné $k$** (jinak procesor potřebuje 2 paměťové cykly nebo vyvolá výjimku).
  * Kompilátor proto mezi položky struktur vkládá neviditelné výplňové bajty (**padding**).
  * **Celková velikost struktury `sizeof`** je navíc zarovnána na násobek velikosti **jejího největšího primitivního členu**:
    ```c
    struct Priklad {
        char a;     // 1 byte  + 3 bajty padding (aby int ležel na adrese dělitelné 4)
        int b;      // 4 bajty
        short c;    // 2 bajty + 2 bajty padding na konci (aby pole struktur bylo zarovnané)
    }; // sizeof(struct Priklad) = 12 bajtů (nikoliv 7!).
    ```
* **Jak číst a chápat C / C++ kód v zadání (Pointery, Reference, Dereference):**
  * **Adresa `&` vs. Dereference `*`:**
    * `int x = 42;`
    * `int* ptr = &x;` $\implies$ `ptr` obsahuje adresu buňky paměti, kde leží `x` (např. `0x7fff00`).
    * `*ptr = 100;` $\implies$ **dereference**: zápis na adresu, na kterou pointer ukazuje $\implies$ hodnota `x` je nyní `100`.
  * **Šipka `->` vs. Tečka `.`:**
    * Máme-li instanci přímo: `mojeStruktura.polozka`
    * Máme-li pointer: `(*ptr).polozka` je syntakticky ekvivalentní zápisu **`ptr->polozka`** (šipka provede dereferenci a přístup ke členu v jednom kroku).
  * **Pravidlo čtení `const` pointerů (Čti zprava doleva):**
    * `const int* p;` *(nebo `int const* p;`)* $\implies$ pointer na konstantní int. **Hodnotu `*p` nelze měnit**, ale samotný ukazatel `p` lze přepojit na jinou proměnnou.
    * `int* const p = &x;` $\implies$ konstantní pointer na int. **Hodnotu `*p` lze měnit**, ale ukazatel `p` je přilepen k `x` a nelze jej přepojit.
    * `const int* const p = &x;` $\implies$ konstantní pointer na konstantní int (zamčeno obojí).
  * **Reference v C++ (`int& ref = x;`):**
    * Pouhý alias (přezdívka) pro existující proměnnou. Na rozdíl od pointeru **nemůže být `NULL`**, musí být inicializována ihned a nelze ji přepojit na jinou paměť. Změna `ref` přímo mění `x`.
  * **Pointerová aritmetika a pole:**
    * Název pole `arr` v C funguje jako pointer na nultý prvek `&arr[0]`.
    * Přičtení čísla $i$ k pointeru `T* ptr` posune adresu o **$i \times \text{sizeof}(T)$ bajtů**!
    * Indexace `arr[i]` je přesně definována jako dereference `*(arr + i)`.
  * **Klíčové slovo `volatile` (Kritické pro Memory-Mapped I/O a hardware):**
    * Říká kompilátoru: *„Tato paměťová buňka se může změnit zásahem hardwaru nebo jiného vlákna bez vědomí tohoto kódu.“*
    * Kompilátor **nesmí hodnotu kešovat v registru procesoru** a při každém čtení i zápisu musí provést skutečnou instrukci na paměťovou sběrnici!
    * Typické použití u registrů zařízení: `typedef volatile struct { uint32_t status; ... } disk_regs_t;`. Bez `volatile` by smyčka `while (regs->status & BUSY);` skončila nekonečným cyklem, protože by si kompilátor načetl stav do registru jen jednou!
    * **Vícevláknové aplikace (kdy netřeba a co neřeší):** Není potřeba uvnitř `lock`u (ten sám tvoří plnou paměťovou bariéru) ani pro samotný objekt zámku (`readonly`). Zásadně **neřeší atomicitu** složených operací (`counter++` stále vyžaduje `lock` nebo `Interlocked`, jinak hrozí race condition / lost update!).

#### 2. Procesor, registry, instrukční sada RISC a běhové režimy:
* **Klíčové registry procesoru:**
  * `PC` (Program Counter / Instruction Pointer): adresa právě prováděné instrukce.
  * `SP` (Stack Pointer): adresa vrcholu zásobníku (zásobník roste směrem dolů k nižším adresám!).
  * `BP` / `FP` (Base / Frame Pointer): bázový ukazatel na počátek stack framu aktuální funkce (přístup k lokálním proměnným a parametrům přes relativní offsety jako `[BP - 4]`, `[BP + 8]`).
  * Stavový registr příznaků: drží výsledkové bity operací (Zero, Carry, Overflow, Sign) a stavový bit režimu procesoru.
* **Uživatelský (User) vs. Privilegovaný (Kernel) režim procesoru:**
  * *User mode:* Běžný kód procesů. Zákaz přímého I/O, zákaz změny stránkovacích tabulek a zákaz vypnutí přerušení.
  * *Kernel mode:* Neomezený přístup k veškerému hardwaru a instrukcím procesoru.
  * *Přechod z User do Kernel mode probíhá výhradně 3 způsoby:*
    1. **Systémové volání (Syscall):** Synchronní požadavek procesu na službu OS (např. čtení ze souboru).
    2. **Hardwarové přerušení (Interrupt):** Asynchronní událost z vnějšího hardwaru (řadič disku, časovač).
    3. **Výjimka procesoru (Exception):** Chyba při vykonání instrukce (dělení nulou, Page Fault).
* **RISC architektura a překlad konstrukcí (Load/Store model):**
  * Žádná instrukce neoperuje přímo s RAM – data se musí nejdřív načíst do registru (`LOAD`), spočítat a zapsat zpět (`STORE`), může být např. po `LOAD` přerušena a++ tedy není atomické.
  * **Ukázka překladu cyklu `while (a < b) a += 2;` do RISC instrukcí:**
    ```text
    loop_start:
        LOAD R1, [a]        ; načti proměnnou a do registru R1
        LOAD R2, [b]        ; načti proměnnou b do registru R2
        CMP R1, R2          ; porovnej R1 a R2
        BGE loop_end        ; pokud a >= b, vyskoč z cyklu (Branch if Greater or Equal)
        ADD R1, R1, 2       ; a += 2 (přičti konstantu 2 k registru R1)
        STORE [a], R1       ; ulož novou hodnotu a zpět do RAM
        JMP loop_start      ; skoč zpět na začátek cyklu
    loop_end:
    ```
  * **Překlad volání funkce (Stack Frame, CALL a RET):**
    * *Volající:* Předá parametry (v registrech nebo na stack přes `PUSH`) a zavolá `CALL cil` (instrukce automaticky uloží návratovou adresu `PC` na stack a skočí na cíl).
    * *Prolog funkce (vytvoření stack framu):* `PUSH BP` (ulož starý base pointer), `MOV BP, SP` (nastav nový rámec), `SUB SP, N` (alokuj $N$ bajtů pro lokální proměnné). Lokální proměnné jsou na záporném offsetu `[BP - 4]`, parametry na kladném `[BP + 8]`.
    * *Epilog funkce a návrat:* `MOV SP, BP` (uvolni lokální proměnné), `POP BP` (obnov starý base pointer), `RET` (vyzvedne návratovou adresu ze stacku do `PC`).

#### 3. Vstup/Výstup, řadiče periférií, přerušení a ovladač disku (C vs. C#):
* **Řadič zařízení (Device Controller):**
  * Hardware rozhraní mezi sběrnicí a mechanickým zařízením. Registry: `Status` (stav: bit `BUSY`, bit `ERR`), `Command` (akce: 1=čtení, 2=zápis), `Data` / `LBA` / `DMA` (parametry).
  * **PMIO vs. MMIO:**
    * *PMIO (Port-Mapped I/O):* Oddělený adresní prostor pro porty, vyžaduje speciální instrukce procesoru (`IN`/`OUT`).
    * *MMIO (Memory-Mapped I/O):* Registry leží přímo na adresách fyzické paměti RAM $\implies$ přístup běžnými instrukcemi pro práci s pamětí (`volatile` ukazatele).
* **Způsoby obsluhy zařízení (PIO vs. Přerušení vs. DMA):**
  * **PIO (Programmed I/O):** Aktivní čekání (Polling) `while (status & BUSY);` $\implies$ 100% zbytečné vytížení procesoru po celou dobu mechanické operace.
  * **Přerušení (Interrupts):** CPU zadá příkaz a věnuje se jiným procesům. Po dokončení pošle řadič žádost o přerušení:
    * *Hardware:* Uloží `PC` a stavový registr na zásobník, přepne do Kernel mode a skočí na kód obsluhy přerušení v jádře OS.
    * *Software (OS):* Uloží registry, přečte data ze zařízení, probudí čekající proces/vlákno (stav Ready) a vrátí se instrukcí `IRET` zpět do přerušeného programu.
  * **DMA (Direct Memory Access):** Řadič přenáší bloky dat (sektory) přímo do RAM bez asistence CPU $\implies$ po přenesení celého bloku vyvolá jediné přerušení.
    * **Zkouškový chyták:** **DMA pracuje výhradně s FYZICKÝMI adresami RAM!** (Řadič nezná stránkování MMU, proto mu OS musí předat fyzickou adresu bufferu).
* **Praktická ukázka ovladače disku: C vs. C# (Zadání Jaro 2024):**
  * *V jazyce C (Nízkoúrovňový ovladač v jádře OS):*
    ```c
    typedef volatile struct {
        uint32_t status;  // bit 0: ERR (1=chyba), bit 1: BUSY (1=zařízení pracuje)
        uint32_t size;    // velikost disku v blocích
        uint32_t command; // 1 = čtení, 2 = zápis
        uint32_t lba;     // logická adresa bloku
        uint32_t dma;     // FYZICKÁ adresa v RAM pro uložení dat
    } disk_regs_t;

    typedef struct {
        disk_regs_t *ctl;
        mutex_t mutex;    // ošetření souběžného volání z více procesů
    } disk_t;

    bool disk_read_block(disk_t *disk, uint32_t lba, uint32_t phys_addr) {
        mutex_lock(&disk->mutex);
        while (disk->ctl->status & 2); // aktivní čekání na !BUSY
        
        disk->ctl->lba = lba;
        disk->ctl->dma = phys_addr;
        disk->ctl->command = 1;        // spustit čtení
        
        while (disk->ctl->status & 2); // čekání na dokončení
        bool ok = (disk->ctl->status & 1) == 0; // kontrola bitu ERR
        mutex_unlock(&disk->mutex);
        return ok;
    }
    ```
  * *V jazyce C# (Reprezentace řadiče přes `class` a `volatile`):*
    * **Proč v C# `class` a v C++ `struct`?** V C/C++ je `struct` pouhá šablona rozložení paměti, na kterou se přímo ukáže pointerem `disk_regs_t* ctl = (disk_regs_t*)addr`. V C# je však `struct` hodnotový typ (Value Type) – při předání do ovladače by se celý zkopíroval po hodnotě a zápisy by šly do lokální kopie místo do hardwaru! Proto v C# volíme `class` (referenční typ), kde se předává odkaz na stejnou instanci registrů.
    * Proměnné označíme klíčovým slovem **`volatile` přímo v definici třídy** (nativní C# klíčové slovo, které zakáže kešování v registrech CPU a vynutí přímý přístup do paměti):
    ```csharp
    public class DiskRegisters {
        public volatile uint Status;  // bit 0: ERR, bit 1: BUSY
        public uint Size;
        public volatile uint Command; // 1 = čtení, 2 = zápis
        public volatile uint Lba;
        public volatile uint Dma;     // fyzická adresa v RAM
    }

    public class DiskDriver {
        private readonly DiskRegisters regs;
        private readonly object lockObj = new object(); // zámek pro kritickou sekci

        public DiskDriver(DiskRegisters registers) {
            this.regs = registers;
        }

        public bool ReadBlock(uint lba, uint physAddr) {
            lock (lockObj) { // lock chrání souběžný přístup z více vláken
                // 1. Aktivní čekání, dokud zařízení neukončí předchozí práci (!BUSY)
                while ((regs.Status & 2) != 0) { }

                // 2. Zadání parametrů a příkazu
                regs.Lba = lba;
                regs.Dma = physAddr;
                regs.Command = 1; // 1 = čtení

                // 3. Aktivní čekání na dokončení čtení
                while ((regs.Status & 2) != 0) { }

                // 4. Úspěch, pokud bit ERR (bit 0) je 0
                return (regs.Status & 1) == 0;
            }
        }
    }
    ```

#### 4. Virtuální paměť, stránkování, TLB, cache a mmap:
* **Proč virtuální paměť:**
  1. *Ochrana paměti:* Proces nemůže číst ani přepsat paměť jiného procesu ani jádra OS.
  2. *Iluze souvislého adresního prostoru:* Program vidí souvislý prostor od adresy `0`, i když fyzická RAM je fragmentovaná.
* **Stránkování (Paging) – Stránka vs. Rámec:**
  * Virtuální adresní prostor je rozdělen na **stránky (Pages)** (typicky 4 KB).
  * Fyzická paměť RAM je rozdělena na stejně velké **rámce (Frames)**.
  * **Zkouškový chyták (12 spodních bitů se nepřekládá!):**
    * Velikost stránky 4 KB znamená $4096 = 2^{12}$ bajtů.
    * **Spodních 12 bitů virtuální adresy tvoří offset (posun)** uvnitř stránky i rámce a zůstává zcela beze změny!
    * Jednotka MMU překládá pouze **horních 20 bitů** (číslo virtuální stránky $\to$ číslo fyzického rámce) pomocí stránkovací tabulky.
* **Ochranné a stavové bity ve stránkovací tabulce:**
  * `Present bit (P)`: 1 = rámec je v RAM; 0 = stránka není v RAM $\implies$ vyvolá hardwarovou výjimku **Page Fault (výpadek stránky)**, jádro OS stránku načte ze swapu/disku a obnoví instrukci.
  * `User / Supervisor bit (U/S)`: 0 = Supervisor only (jádro OS je namapováno v horní polovině adresního prostoru s tímto bitem $\implies$ uživatelský kód tam nesmí přistoupit).
  * `Read / Write bit (R/W)`: 0 = Read-only (kód programu `.text`), 1 = Read-Write (halda, zásobník).
  * `No-Execute bit (NX)`: Zákaz spouštění kódu ze zásobníku a haldy (ochrana proti spuštění škodlivého kódu).
* **Hardwarová akcelerace překladu a přístupu (TLB a Cache):**
  * **TLB (Translation Lookaside Buffer):** Rychlá asociativní cache uvnitř MMU, která si pamatuje nedávné překlady: *číslo virtuální stránky $\to$ číslo rámce*. (TLB Hit = 1 cyklus; TLB Miss = pomalé čtení tabulky z RAM).
  * **Cache paměť procesoru (L1, L2, L3):** Načítá se vždy po celých blocích (**Cache Line = 64 B**) $\implies$ sekvenční procházení paměti je mnohonásobně rychlejší než náhodné skákání.
* **Paměťové mapování souborů (`mmap` v OS / `MemoryMappedFile` v C#):**
  * Mapuje soubor z disku přímo do virtuálního adresního prostoru procesu $\implies$ přístup k souboru jako k poli v paměti RAM bez nutnosti volat `read()` a `write()` (Zero-Copy).
  * **Líné načítání (Lazy loading via Page Fault):** Fyzické načtení z disku do RAM proběhne až při prvním skutečném sáhnutí na danou adresu vyvoláním hardwarového výpadku stránky (Page Fault).
  * **Využití:** Maximální rychlost I/O a nejrychlejší sdílená paměť pro meziprocesovou komunikaci (IPC).

#### 5. Procesy, vlákna, plánování a souborový systém:
* **Proces (PCB) vs. Vlákno (TCB) – Co je vlastní a co sdílené:**
  * **Proces:** Nezávislá jednotka alokace zdrojů (drží deskriptor procesu PCB). Má vlastní virtuální adresní prostor, tabulku otevřených souborů, oprávnění a PID.
  * **Vlákno:** Jednotka plánování běhu na CPU (drží deskriptor vlákna TCB):
    * *Vlastní kontext vlákna:* Program Counter (`PC`), registry CPU, vlastní zásobník (Stack) a Stack Pointer (`SP`), stav vlákna.
    * *Sdílené v rámci procesu mezi všemi jeho vlákny:* Celý virtuální adresní prostor (halda, globální data, kód `.text`), tabulka otevřených souborů/socketů.
* **Stavy vlákna a preemptivní multitasking:**
  * **Stavy vlákna:** *Running* (vykonává se na CPU), *Ready* (čeká ve frontě na přidělení CPU), *Blocked / Waiting* (čeká na I/O, zámek nebo časovač).
  * **Preemptivní přepínání kontextu:** Periodické přerušení od hardwarového časovače (timer tick) předá řízení OS $\implies$ jádro vyčerpalo-li vlákno časové kvantum, uloží jeho registry do TCB (přepne do Ready) a obnoví registry jiného vlákna (přepne do Running).
* **Soubor jako abstrakce úložného prostoru (analogie s adresovým prostorem):**
  * Soubor je z pohledu aplikace lineární pole bajtů indexované offsetem $0$ až $N-1$, což je přímá analogie k virtuálnímu adresovému prostoru ($0$ až $2^k-1$).
  * Obě abstrakce překládají logický offset na fyzická data (stránkovací tabulka mapuje virtuální stránku na rámec v RAM; i-node mapuje offset souboru na diskové bloky). Systémové volání `mmap` tyto dva světy přímo propojuje.
* **Soubory, deskriptor a i-node:**
  * **Souborový deskriptor (File Descriptor / Handle):** Malé celé číslo (0 = stdin, 1 = stdout, 2 = stderr), index do per-proces tabulky otevřených souborů.
  * **i-node na disku:** Datová struktura reprezentující soubor. Obsahuje metadata (velikost, vlastník, přístupová práva, časová razítka) a ukazatele na datové bloky na disku (přímé ukazatele + nepřímé bloky pro velké soubory).
  * **Zkouškový chyták:** **i-node NEOBSAHUJE název souboru!** Název je uložen v adresáři jako mapování: `název souboru -> číslo i-nodu`. Proto může existovat více názvů (Hard Linků) ukazujících na tentýž soubor.
  * **Správa zdrojů OS v C# (`using` a `IDisposable`):**
    * *Problém:* Otevřený soubor alokuje v jádře OS deskriptor (*unmanaged resource*). Garbage Collector spravuje pouze paměť na haldě, ale neuzavírá systémové handly včas!
    * *Řešení v C#:* Blok `using` garantuje volání `Dispose()` a uzavření deskriptoru i při vyhození výjimky:
    ```csharp
    // 1. Zápis pomocí using (od C# 8 stačí using deklarace):
    using var reader = new StreamReader("data.txt");
    while (!reader.EndOfStream) {
        string? line = reader.ReadLine();
    }

    // 2. Co kompilátor reálně vygeneruje pod kapotou (ekvivalent):
    StreamReader r = new StreamReader("data.txt");
    try {
        while (!r.EndOfStream) {
            string? line = r.ReadLine();
        }
    }
    finally {
        if (r != null) ((IDisposable)r).Dispose(); // zavře OS deskriptor i při výjimce!
    }
    ```

#### 6. Synchronizace, kritická sekce a synchronizační primitiva (OS & C#):
* **Race Condition (Souběh) a Kritická sekce:**
  * *Race condition:* Chyba, kdy výsledek programu závisí na náhodném pořadí přepínání vláken plánovačem.
  * *Příčina:* Ani jednoduchá operace `x++` není na procesoru atomická! V assembleru jde o 3 instrukce (`LOAD`, `ADD`, `STORE`). Přepne-li časovač vlákno uprostřed, dojde ke ztrátě zápisu (*Lost Update*).
  * *Kritická sekce:* Úsek kódu přistupující ke sdíleným datům, kde smí v libovolný okamžik běžet nanejvýš jedno vlákno (**Vzájemné vyloučení / Mutual Exclusion**).
* **Hardwarová atomická primitiva (Aktivní čekání / Spinlock):**
  * **Test-and-Set:** HW instrukce, která atomicky zapíše `1` do proměnné a vrátí její původní hodnotu:
    ```c
    // Spinlock: aktivní točení v cyklu (Busy-waiting):
    while (test_and_set(&lock) == 1); // toč se, dokud je zamčeno
    // ... kritická sekce ...
    lock = 0; // uvolnění zámku
    ```
  * **Compare-and-Swap (CAS / `Interlocked.CompareExchange` v C#):** Atomicky provede: *„Pokud paměť obsahuje očekávanou hodnotu, přepiš ji novou.“* Základ pro lock-free datové struktury.
  * *Spinlock vs. Mutex:* Spinlock neuspává vlákno (žere 100 % CPU, vhodný jen na mikrosekundy u vícejádrových systémů). Mutex při neúspěchu uspí vlákno v jádře OS (stav Blocked $\implies$ nulové vytížení CPU).
* **Rozdíl: `lock` (`Monitor`) vs. `Mutex` a meziprocesová synchronizace:**
  * **`lock (obj)` / `Monitor.Enter` (In-Process / User-mode):**
    * Bleskový (~20–50 ns), žije výhradně v runtime CLR a zamyká na hlavičce objektu na haldě (`SyncBlockIndex`).
    * **Funguje POUZE uvnitř 1 procesu** (procesy mají oddělené virtuální paměti, nemohou sdílet C# objekt).
  * **`System.Threading.Mutex` a `Semaphore` (Cross-Process / Kernel Objects):**
    * **Garantuje je přímo jádro operačního systému (Kernel Objects)!**
    * **Doba trvání:** Jsou pomalejší (~1–2 mikrosekundy), protože každé volání `WaitOne()` a `Release()` vyžaduje přechod do jádra OS (*syscall*). Naproti tomu odlehčený in-process `SemaphoreSlim` trvá jen desítky nanosekund (~20–50 nanosekund).
    * **Jak se v C# udělá synchronizace mezi procesy?** Předáním systémového jména s prefixem `Global\`:
    ```csharp
    // 1. Pojmenovaný Mutex (Typické použití: Single-Instance aplikace):
    using var mutex = new Mutex(true, "Global\\MojeAplikace_ID", out bool isNewInstance);
    if (!isNewInstance) {
        Console.WriteLine("Aplikace již běží v jiném procesu!");
        return; // ukončit druhou instanci
    }
    // Běžná vzájemně vylučující kritická sekce mezi procesy:
    mutex.WaitOne(); // čeká v jádře OS (~1-2 mikrosekundy)
    try { /* zápis do sdíleného souboru */ }
    finally { mutex.ReleaseMutex(); }

    // 2. Pojmenovaný Semafor (Omezení na max 3 procesy současně přistupující ke zdroji):
    using var sem = new Semaphore(initialCount: 3, maximumCount: 3, "Global\\MujSdilenySemafor");
    sem.WaitOne(); // sníží čítač v jádře OS (~1-2 mikrosekundy), při 0 uspí proces
    try { /* práce se sdíleným hardwarem/databází */ }
    finally { sem.Release(); } // zvýší čítač v jádře OS
    ```
* **Mutex vs. Semafor:**
  * **Mutex (Mutual Exclusion):** Má **vlastníka** (odemknout ho smí POUZE vlákno, které ho zamklo). Slouží k ochraně kritické sekce (binární 0/1).
  * **Semafor (Čítačový semafor):** **NEMÁ vlastníka!**
    * Drží celočíselný čítač volných zdrojů $S \ge 0$.
    * `Wait()` / `P()`: pokud $S > 0$, sníží $S \gets S - 1$; pokud $S == 0$, vlákno se zablokuje.
    * `Signal()` / `Release()`: zvýší $S \gets S + 1$ a probudí jedno čekající vlákno (může ho zavolat libovolné jiné vlákno!).
    * **Využití:** Signalizace mezi vlákny/procesy a problém Producent-Konzument (často se používají 2 semafory: `volno` o kapacitě $N$ a `obsazeno` s počátkem 0). V C# existuje rychlý in-process `SemaphoreSlim` (~20–50 nanosekund) a meziprocesový `Semaphore("Global\\...")` garantovaný OS (~1–2 mikrosekundy).
* **Monitor v C# (`lock`, `Monitor.Wait` a `Monitor.Pulse`):**
  * Klíčové slovo `lock (lockObj)` je v C# syntaktický cukr pro `Monitor.Enter(lockObj)` a `Monitor.Exit(lockObj)` v bloku `try-finally`.
  * **Zkouškový chyták – Zamykání je KOOPERATIVNÍ (Advisory):**
    * Samotná data (proměnná, pole, list) **nejsou hardwarem v paměti RAM nijak zamknutá!**
    * Zámek `lock (syncRoot)` je pouze „dohoda mezi ukázněnými vlákny“, která se před sáhnutím na data zeptají.
    * *Co se stane, když vlákno `lock` NEZAVOLÁ?* **VŮBEC SE NEUSPÍ!** Operační systém ani CPU o žádném zámku neví, procesor provede zápis do paměti i v okamžiku, kdy jiné vlákno zrovna uvnitř svého locku manipuluje s daty $\implies$ paměťová korupce.
    ```csharp
    public class SharedCounter {
        private int count = 0;
        private readonly object syncRoot = new object(); // vyhrazený zámek

        // SPRÁVNĚ (kooperativní volání):
        public void SafeIncrement() {
            lock (syncRoot) { 
                // Pokud jiný drží syncRoot, OS toto vlákno ZASTAVÍ a USPÍ (stav Blocked -> 0 % CPU).
                count++; 
            }
        }

        // ŠPATNĚ (zkouškový chyták - chybějící lock):
        public void RogueIncrement() {
            // ZDE CHYBÍ lock(syncRoot)! Vlákno se VŮBEC NEUSPÍ!
            // CPU natvrdo zapíše do RAM uprostřed běhu cizího locku -> Race Condition / Lost Update!
            count++; 
        }
    }
    ```
  * **Klíčový rozdíl: `Monitor.Enter` (`lock`) vs. `Monitor.Wait`:**
    * **`Monitor.Enter` (vstup do `lock`):** Slouží k **získání zámku**. Pokud je obsazený, vlákno čeká před vchodem. Když projde, **zámek drží**.
    * **`Monitor.Wait`:** Volá se **uvnitř** kritické sekce, když vlákno zjistí, že nemůže pokračovat (např. prázdná fronta). Udělá atomický trojkrok:
      1. **DOČASNĚ UVOLNÍ zámek `lockObj`** (aby producent mohl vstoupit a data doplnit – kdyby zámek neuvolnil, nastane okamžitý Deadlock!).
      2. **Uspí toto vlákno** do stavu `Blocked` (0 % CPU).
      3. Až producent zavolá `Monitor.Pulse`, vlákno se probudí, ale **nejprve si automaticky znovu ZÍSKÁ zámek `lockObj`**, než pokračuje dál!
  * **Zkouškový chyták:** **`Monitor.Wait` se VŽDY musí volat v cyklu `while (!podminka)`**, NIKDY v pouhém `if`!
    *(Důvody: 1. Falešné probuzení / Spurious wakeup ze strany OS; 2. Než se probuzené vlákno dostane k běhu a znovu získá zámek, jiné vlákno mohlo podmínku opět zneplatnit!).*
  * *Vzorová blokující fronta s vyznačením `Enter`, `Wait` a `Exit`:*
    ```csharp
    public class BlockingQueue<T> {
        private readonly Queue<T> q = new Queue<T>();
        private readonly int capacity;
        private readonly object lockObj = new object();

        public BlockingQueue(int cap) => capacity = cap;

        public void Enqueue(T item) {
            lock (lockObj) { // 1. Monitor.Enter: získám zámek (nebo čekám před vchodem)
                while (q.Count >= capacity) // VŽDY while!
                    Monitor.Wait(lockObj);  // 2. Monitor.Wait: DOČASNĚ uvolním zámek a usnu
                q.Enqueue(item);
                Monitor.PulseAll(lockObj);  // probuď čekající konzumenty
            } // 3. Monitor.Exit: definitivně uvolním zámek
        }

        public T Dequeue() {
            lock (lockObj) { // 1. Monitor.Enter: získám zámek
                while (q.Count == 0)        // VŽDY while!
                    Monitor.Wait(lockObj);  // 2. Monitor.Wait: DOČASNĚ uvolním zámek, aby producent mohl vložit data!
                T item = q.Dequeue();
                Monitor.PulseAll(lockObj);  // probuď čekající producenty
                return item;
            } // 3. Monitor.Exit: definitivně uvolním zámek
        }
    }
    ```
* **Čtenářsko-písařský zámek (Reader-Writer Lock):**
  * Povoluje souběžné čtení více čtenářům (`EnterReadLock`), ale zápis je striktně exkluzivní (`EnterWriteLock`).
  * V C# realizováno třídou `ReaderWriterLockSlim`.
* **Vlákna, Tasky, Delegáti, Lambdy a Asynchronie (C# Concurrency Stack):**
  * **Delegát:** Typově bezpečný objektový ukazatel na metodu:
    * `Action<T1, T2>`: Delegát pro metodu nevracející hodnotu (`void`).
    * `Func<T1, T2, TResult>`: Delegát pro metodu vracející hodnotu (poslední typ v závorkách je návratový typ!).
  * **Lambda výraz a uzávěr (Closure):** `(x) => x * 2` (anonymní funkce schopná zachytit proměnné z okolního kontextu).
  * **`Thread` vs. `ThreadPool` vs. `Task`:**
    * *`Thread`:* Těžké vlákno OS s vlastním 1MB zásobníkem (drahý vznik, `Start()`, blokující `Join()`).
    * *`ThreadPool`:* Fond předvytvořených systémových vláken pro krátké úlohy bez režie alokace nového vlákna.
    * *`Task` / `Task<T>`:* Slib budoucího výsledku běžící na ThreadPoolu (`Task.Run`).
  * **Blokující vs. Neblokující čekání na Task:**
    * **Blokující čekání (`task.Result` / `task.Wait()` / `thread.Join()`):** Volající vlákno se **fyzicky zastaví a zamrzne** (OS ho uspí do stavu Blocked). Vlákno nemůže dělat nic jiného (v UI zamrzne okno, na serveru hrozí vyčerpání vláken ThreadPoolu nebo Deadlock).
    * **Neblokující čekání (`await task`):** Vlákno se **VŮBEC NEBLOKUJE**. Metoda se pozastaví, ale aktuální vlákno se **ihned uvolní zpět do ThreadPoolu** a může obsluhovat jiné požadavky. Po dokončení Tasku se pokračování metody naplánuje na libovolné volné vlákno přes generovaný stavový automat (*State Machine*).
  * *Propojená ukázka: Delegáti, Lambdy, Thread, Task a async/await v akci:*
    ```csharp
    public class ConcurrencyDemo {
        // 1. Delegát Func s lambdou a uzávěrem (closure):
        private Func<int, int> multiplier = (x) => x * 2;

        public async Task RunDemoAsync() {
            // 2. Thread (těžké OS vlákno) s delegátem Action:
            Thread t = new Thread(() => Console.WriteLine("Běží na dedikovaném OS vlákně"));
            t.Start();
            t.Join(); // BLOKUJÍCÍ čekání: volající vlákno zamrzne a čeká na konec t

            // 3. Task naplánovaný na ThreadPool s delegátem Func:
            Task<int> task = Task.Run(() => multiplier(21));

            // --- ROZDÍL: BLOKUJÍCÍ vs. NEBLOKUJÍCÍ ČEKÁNÍ ---
            // A) BLOKUJÍCÍ: int r = task.Result; (vlákno spí, nic jiného nemůže dělat)
            // B) NEBLOKUJÍCÍ (asynchronní):
            int result = await task; // Vlákno se IHNED uvolní! Kód dál pokračuje až po dokončení.
        }

        // 4. Asynchronní I/O metoda (neblokující síťový požadavek):
        public async Task<string> FetchUrlAsync(string url) {
            using var client = new HttpClient();
            // await UVOLNÍ aktuální vlákno do ThreadPoolu po celou dobu čekání na síťový paket!
            string html = await client.GetStringAsync(url);
            return html.Trim(); // po příchodu paketu se dokončí na libovolném volném vlákně
        }
    }
    ```

#### 7. Programovací jazyk C# a Objektově orientované koncepty:

* **Typový systém, Paměť, Pole a Předávání parametrů (`ref`, `out`, `in`, `Span<T>`):**
  * **`class` vs. `struct`:**
    * *`class` (Referenční typ):* Alokace na haldě, spravováno GC, předává se referencí, výchozí hodnota `null`.
    * *`struct` (Hodnotový typ):* Alokace na zásobníku (nebo inline v objektu), předává se kopií hodnoty, výchozí hodnota je paměť s nulami, nepodporuje dědičnost.
  * **Boxing a Unboxing:**
    * *Boxing:* Zabalení hodnotového typu (`int`, `struct`) do referenčního typu (`object` na haldě). Vytvoří se nová instance s hlavičkou objektu $\implies$ alokace na haldě, režie a zátěž pro GC.
    * *Unboxing:* Explicitní vybalení hodnoty z objektu zpět na zásobník `int x = (int)obj;` (při neshodě typu vyhodí `InvalidCastException`).
    * *Výhoda generik:* `List<int>` ukládá prvky přímo v poli primitiv bez boxingu (oproti starému `ArrayList`).
  * **Interní reprezentace objektu na haldě (.NET Object Header):**
    * Každý objekt na haldě zabírá navíc 8 B (na 32b) / 16 B (na 64b) pro pevnou hlavičku:
      1. **SyncBlockIndex (4/8 B):** Index pro zamykání (`lock (obj)`), hash code a interní příznaky GC.
      2. **MethodTable pointer (4/8 B):** Ukazatel na metadata typu a tabulku virtuálních metod (`vtable`) pro dynamický polymorfismus.
      3. **Datová pole instance:** Samotné proměnné třídy zarovnané na hranice slov.
  * **Předávání parametrů funkcí:**
    * *`ref`:* Obousměrná reference. Proměnná **musí být inicializována** před voláním. Umožňuje přepsat proměnnou volajícího.
    * *`out`:* Výstupní reference. Proměnná nemusí být inicializována, ale metoda do ní **musí zapsat** před návratem.
    * *`in`:* Reference **jen pro čtení**. Zabraňuje kopírování velkých structů, kompilátor zakazuje změnu.
  * **Pole v C# (3 různé druhy!):**
    * 1D pole: `int[] a = new int[5];` (souvislý blok paměti).
    * 2D obdélníkové: `int[,] m = new int[3, 4];` (jediný souvislý blok paměti alokovaný na haldě).
    * Zubaté (Jagged): `int[][] j = new int[3][];` (pole referencí na samostatná 1D pole různých délek).
  * **`Span<T>` a `ref struct` (Zkouškový hit pro zero-allocation kód):**
    * `Span<T>` je typově bezpečný pohled na libovolnou souvislou paměť (pole, stack, nativní paměť) **zcela bez alokace paměti na haldě**.
    * Je definován jako **`ref struct`** $\implies$ **smí existovat VÝHRADNĚ NA STACKU**! Nesmí být polem běžné třídy ani boxován $\implies$ GC o něm nemusí vědět.
    * *Využití:* Substring bez alokace (`str.AsSpan(0, 5)` nealokuje nový string, drží jen ukazatel a délku).
  * *Propojená ukázka: Struct, Parametry in/ref/out, Pole a Span<T>:*
    ```csharp
    public readonly struct BigPoint { // immutable hodnotový typ na stacku
        public readonly double X, Y;
        public BigPoint(double x, double y) => (X, Y) = (x, y);
    }

    public class MemoryAndParametersDemo {
        // in: reference bez kopírování paměti; ref: obousměrná; out: povinný zápis
        public void Transform(in BigPoint pt, ref double scale, out double length) {
            scale *= 2;
            length = Math.Sqrt(pt.X * pt.X + pt.Y * pt.Y) * scale;
        }

        public void ArraysAndSpan() {
            int[] arr1D = new int[5];                 // 1D pole
            int[,] rect2D = new int[2, 3];            // 2D obdélníkové (1 blok v RAM)
            int[][] jagged = new int[2][] { new int[2], new int[4] }; // zubaté pole

            // Zero-allocation parsing pomocí ReadOnlySpan<char>:
            string text = "12345,67890";
            ReadOnlySpan<char> span = text.AsSpan();
            ReadOnlySpan<char> firstNum = span.Slice(0, 5); // ŽÁDNÁ ALOKACE nového stringu!
            int parsed = int.Parse(firstNum);
        }
    }
    ```

* **Vlastnosti (Properties), Zapouzdření a Neměnnost (`get`, `set`, `init`, `required`):**
  * **Princip vlastností:** Slouží k **zapouzdření dat** (*encapsulation*). Navenek se chovají jako proměnné (`obj.X = 10;`), ale kompilátor je pod kapotou překládá na volání metod (`get_X()`, `set_X(value)`).
  * **Plná vlastnost vs. Automatická:**
    * *Plná vlastnost:* Má explicitní privátní proměnnou (**backing field**), používá se při potřebě logiky/validace při čtení či zápisu (`value` je klíčové slovo pro přiřazovanou hodnotu).
    * *Automatická vlastnost (`{ get; set; }`):* Backing field vygeneruje kompilátor pod kapotou sám.
  * **Omezení zápisu (`private set`):** Čtení je veřejné, ale měnit hodnotu smí pouze samotná třída zevnitř (zapouzdření stavu).
  * **Vlastnosti pouze pro čtení (`{ get; }`) vs. `readonly` pole:**
    * Klíčové slovo **`readonly`** se v C# píše před **pole** (proměnné): `private readonly int _id;`.
    * U **vlastností** se pro neměnnost vynechá `set`: `public int Id { get; }`. Kompilátor pro ni vygeneruje privátní `readonly` backing field $\implies$ lze nastavit pouze při deklaraci nebo v konstruktoru třídy, poté již nikdy (ani samotná třída ji nemůže změnit).
  * **`init` (C# 9+) – Neměnnost + Objektový inicializátor:**
    * Get-only (`get;`) vyžaduje konstruktor se všemi parametry a neumožňuje objektový inicializátor (`new Uzivatel { Jmeno = "Petr" }`).
    * **`init` (Init-only setter):** Umožňuje nastavení v konstruktoru **nebo v objektovém inicializátoru při vytváření instance**. Jakmile je objekt vytvořen, hodnota je trvale neměnná (*immutable* – základní stavební kámen např. pro `record`).
  * **`required` (C# 11+) – Povinná inicializace:**
    * Vynucuje, aby vlastnost v objektovém inicializátoru **musela** být vyplněna (zabraňuje vytvoření neúplného objektu `new Uzivatel()`).
  * **Počítané vlastnosti (`=>`):**
    * Výrazový zápis (*expression-bodied property*): nemá žádný uložený stav (žádný backing field), hodnotu dynamicky počítá při každém čtení.
  * *Jedna propojená ukázka (všechny formy vlastností v praxi):*
    ```csharp
    public class BankovniUcet {
        // 1. Plná vlastnost s privátním backing fieldem a validační logikou:
        private decimal _zustatek;
        public decimal Zustatek {
            get => _zustatek;
            set {
                if (value < 0) throw new ArgumentException("Zůstatek nesmí být záporný!");
                _zustatek = value; // 'value' je klíčové slovo představující přiřazovanou hodnotu
            }
        }

        // 2. Automatická vlastnost (kompilátor vygeneruje privátní pole sám):
        public string Poznamka { get; set; } = "Bez poznámky";

        // 3. Omezení zápisu: čtení je public, zápis smí provést jen třída zevnitř:
        public int PocetTransakci { get; private set; }

        // 4. Get-only vlastnost (pod kapotou readonly) - nastavitelná jen při definici či v konstruktoru:
        public int CisloUctu { get; }

        // 5. Init-only + required (C# 9/11+) - v inicializátoru povinné, po vytvoření neměnné (immutable):
        public required string Majitel { get; init; }

        // 6. Počítaná vlastnost (expression-bodied) - nemá žádné uložené pole, jen getter:
        public bool JeAktivni => Zustatek > 0;

        public BankovniUcet(int cisloUctu) {
            CisloUctu = cisloUctu; // OK - v konstruktoru lze get-only nastavit
        }

        public void PripisUrok(decimal urok) {
            Zustatek += urok;
            PocetTransakci++; // OK - jsme uvnitř třídy, private set povolen
        }
    }

    // --- Použití v kódu a chování kompilátoru ---
    var ucet = new BankovniUcet(123456) {
        Majitel = "Jan Novák", // OK: required + init v objektovém inicializátoru
        Zustatek = 1500        // OK: projde validačním setterem
    };

    // ucet.Majitel = "Karel";    // CHYBA KOMPILACE! 'init' nelze po vytvoření instance měnit.
    // ucet.CisloUctu = 999;      // CHYBA KOMPILACE! get-only vlastnost nemá setter.
    // ucet.PocetTransakci = 10;  // CHYBA KOMPILACE! setter je 'private'.
    // var chybny = new BankovniUcet(1); // CHYBA KOMPILACE! 'Majitel' je 'required' a chybí v inicializátoru.
    ```
  * *Přehledové shrnutí (Cheat Sheet vlastností):*
    | Zápis | Kdy a odkud lze nastavit / změnit? | Účel a chování |
    | :--- | :--- | :--- |
    | `get; set;` | Kdykoliv a odkudkoliv | Plně modifikovatelná automatická vlastnost. |
    | `get; private set;` | Číst kdokoliv, měnit jen kód dané třídy | Zapouzdření interního stavu. |
    | `get; }` | Jen při deklaraci nebo v konstruktoru třídy | Neměnná (get-only) vlastnost (kompilátor vygeneruje `readonly` pole). |
    | `get; init;` | V konstruktoru **nebo** v objektovém inicializátoru `{ Prop = x }` | Neměnnost (*immutability*) vhodná pro inicializátory a recordy (C# 9+). |
    | `required ... get; init;` | Povinně v objektovém inicializátoru | Vynucená inicializace při vytváření instance (C# 11+). |
    | `=> hodnota;` | Pouze getter (čtení za běhu) | Čistě počítaná hodnota bez vlastního backing fieldu (*expression-bodied*). |

* **Dědičnost, Polymorfismus, `vtable`, Rozhraní a Explicitní implementace:**
  * **Dynamický vs. Statický polymorfismus:**
    * *Dynamický:* Řešen za běhu přes virtuální tabulku metod (**`vtable` / MethodTable**). Každý objekt na haldě má v hlavičce ukazatel na MethodTable; volání virtuální metody je skok přes fixní index v tabulce (1 paměťová dereference navíc).
    * *Statický:* Řešen v době kompilace (přetěžování metod a operátorů).
  * **`virtual` / `override` vs. `new` (shadowing):**
    * `override` přepisuje virtuální metodu v `vtable` $\implies$ volá se i přes referenci bázové třídy.
    * `new` pouze skryje bázovou metodu $\implies$ při volání přes bázovou referenci se zavolá původní kód!
    * `base`: Explicitní vyvolání implementace bázové třídy (`base.Vypocet()`).
  * **Jednoduchá dědičnost vs. Vícenásobná a Diamantový problém (Diamond Problem):**
    * *Diamantový problém:* Pokud třída $D$ dědí z $B$ i $C$ a obě dědí z $A$, vzniká konflikt (dvojí instance datových polí z $A$, nejednoznačnost při volání metod).
    * *Řešení v C#:* U tříd je povolena **pouze jednoduchá dědičnost** (žádný diamantový problém u stavu). Je však povolena **vícenásobná implementace rozhraní** (interfaces), kde ke konfliktu datového stavu nedochází.
  * **Rozhraní a Explicitní implementace rozhraní (`void IFoo.Metoda()`):**
    * Metoda je přístupná **výhradně po přetypování na dané rozhraní** `((IFoo)obj).Metoda()`.
    * *Využití:* Řeší kolizi, pokud dvě různá rozhraní vyžadují metodu se stejným názvem a signaturou.
    * *Defaultní metody rozhraní (C# 8+):* Rozhraní smí mít výchozí tělo metody. Třída ji však nezdědí do svého veřejného API – lze ji zavolat VÝHRADNĚ po přetypování na dané rozhraní `((ILogger)obj).LogInfo(...)`.
  * *Propojená ukázka: Polymorfismus, vtable, Shadowing, Base, Explicitní Interface a Defaultní metoda:*
    ```csharp
    public interface IPrinter { void Print(); }
    public interface ILogger {
        void Print(); // kolize se stejným názvem!
        // Defaultní metoda rozhraní s tělem (C# 8+):
        void LogInfo(string msg) => Console.WriteLine($"[INFO] {msg}");
    }

    public class BaseDocument {
        public virtual void Render() => Console.WriteLine("Bázový render");
    }

    public class Report : BaseDocument, IPrinter, ILogger {
        // 1. Dynamický polymorfismus přes override (přepíše záznam ve vtable):
        public override void Render() {
            base.Render(); // explicitní volání bázové metody
            Console.WriteLine("Rozšířený render reportu");
        }

        // 2. Explicitní implementace rozhraní (vyřešení kolize dvou metod Print):
        void IPrinter.Print() => Console.WriteLine("Tisk na tiskárnu");
        void ILogger.Print()  => Console.WriteLine("Zápis do logu");

        // 3. Defaultní metodu LogInfo() třída implementovat NEMUSÍ, použije se tělo z rozhraní.
    }

    public class SealedReport : Report {
        // 4. Stínění (shadowing) přes new - NEMĚNÍ vtable polymorfismu:
        public new void Render() => Console.WriteLine("Skrytý render");
    }

    // --- POUŽITÍ: Zkouškový chyták na volání defaultní metody ---
    // Report r = new Report();
    // r.LogInfo("Ahoj");            // CHYBA PŘEKLADU! Třída defaultní metodu nezdědila do svého API.
    // ((ILogger)r).LogInfo("Ahoj"); // SPRÁVNĚ: Volání defaultní metody VÝHRADNĚ přes referenci rozhraní!
    ```

* **Rozhodovací pravidla pro OOP návrh u zkoušky (Interface vs. Abstraktní třída vs. Enum):**
  * **Kdy `interface`:**
    * Kontrakt o **chování a schopnostech** (role CAN-DO: `IComparable`, `IDisposable`), které implementují různé nesouvisející třídy.
    * **V interface NIKDY nesmí být proměnné (*fields*)!** Interface definuje chování, ne paměťový stav (`string name;` je chyba), jsou tam jen properties u kterých se ten `{ get; či set; }` překládá na metodu get_NazevProperty.
    * **Vlastnosti VŽDY jen s `{ get; }`** (`string Name { get; }`). Dává se pouze getter (read-only kontrakt); třída si pak sama určí implementaci (`init`, `private set`, get-only). Pokud napíšeme `{ get; set; }`, nutíme každou třídu mít veřejný setter!
  * **Kdy `abstraktní třídu` (hierarchii tříd):**
    * Vztah **„JE NĚČÍM“ (IS-A)** a sdílení **vnitřního stavu a kódu** (společný `Name`, bázový konstruktor `base(name)`).
    * Stromové hierarchie a návrhový vzor **Composite** (např. prvky IDE: `abstract class IdeElement`, ze kterého dědí `FieldElement`, `MethodElement`, `TypeElement`).
    * Disjunktní polymorfismus pro pattern matching (prvek je garantovaně právě jednoho konkrétního typu), používat `sealed`.
    * *Ukázka: Disjunktní hierarchie se `sealed record` a switch výrazem:*
      ```csharp
      public abstract record StavPlatby;

      public sealed record CekaSeNaPlatbu : StavPlatby;
      public sealed record Zaplaceno(DateTime Kdy) : StavPlatby;
      public sealed record Selhalo(string Duvod) : StavPlatby;

      // Díky sealed:
      // 1. Kompilátor ví, že větve jsou vzájemně výlučné (objekt nemůže být zároveň Zaplaceno i něco jiného).
      // 2. Žádná cizí knihovna vám do této hierarchie nemůže podstrčit nečekaného potomka.
      string zprava = stav switch
      {
          CekaSeNaPlatbu => "Čekáme...",
          Zaplaceno z => $"Uhrazeno: {z.Kdy}",
          Selhalo s => $"Chyba: {s.Duvod}"
      };
      ```
  * **Kdy `enum` (Zkouškový reflex):**
    * Kdykoliv zadání žádá **„druh / typ / variantu“ z pevné sady hodnot** (např. druh typu: `enum TypeKind { Class, Struct, Interface, Enum }`, barva, stav).
    * Nevymýšlet na to další hierarchii tříd ani textové řetězce (`string`)! `enum` je v C# nejrychlejší, typově bezpečný a ideální pro switch/pattern matching.

* **Pattern Matching, Generika (`where`), Výjimky (`throw;`) a Přetížení operátorů:**
  * **Generika a omezení (`where` constraints):**
    * Typová bezpečnost bez nutnosti boxingu a přetypovávání: `where T : class, struct, new(), IComparable<T>, notnull`.
  * **Operátory přetypování `is` a `as`:**
    * `as`: Bezpečné přetypování referenčního/nullable typu (`var s = obj as string;`). Pokud objekt neodpovídá typu, **vrátí `null`** (nevyhodí výjimku `InvalidCastException`).
    * `is`: Test na typ a pattern matching deklarace (`if (obj is Circle c && c.Radius > 0)`).
  * **Pattern Matching a `switch`:**
    * Moderní přepínač s testem na typ (`Kruh k`), dekonstrukci vlastností a dodatečné podmínky `when`.
  * **Obsluha výjimek a zkouškový chyták (`throw;` vs. `throw ex;`):**
    * `finally` se provede **vždy** (i při `return` uvnitř `try`).
    * **`throw;`** $\implies$ **Správně.** Přepošle výjimku dál a **zcela zachová původní Stack Trace**.
    * **`throw ex;`** $\implies$ **Chyba!** Přepíše Stack Trace na aktuální řádek $\implies$ ztratí se místo, kde chyba reálně vznikla!
  * **Statický polymorfismus (Přetížení operátorů):** Deklarován jako `public static operator +(...)`.
  * *Propojená ukázka: Generika where, Switch Pattern Matching, korektní throw a Operátory:*
    ```csharp
    public record Shape;
    public record Circle(double Radius) : Shape;
    public record Rectangle(double Width, double Height) : Shape;

    public struct Complex {
        public double Re, Im;
        // Přetížení operátoru + (statický polymorfismus):
        public static Complex operator +(Complex a, Complex b) =>
            new Complex { Re = a.Re + b.Re, Im = a.Im + b.Im };
    }

    public class GenericProcessor<T> where T : class, new() {
        // Pattern matching switch výraz:
        public string DescribeShape(Shape shape) => shape switch {
            Circle c when c.Radius > 10 => $"Velký kruh r={c.Radius}",
            Circle c                    => $"Malý kruh r={c.Radius}",
            Rectangle { Width: var w, Height: var h } => $"Obdélník {w}x{h}",
            null                        => "Null hodnota",
            _                           => "Neznámý tvar"
        };

        public void SafeExecute() {
            try {
                // riziková operace
            }
            catch (Exception ex) {
                // Logování...
                throw; // SPRÁVNĚ: Zachová původní stack trace! (throw ex; by ho přemazal)
            }
            finally {
                // Provede se VŽDY, i při chybě i při returnu!
            }
        }
    }
    ```

* **Běhové prostředí, kompilace a linkování:**
  * **Compiler (Kompilátor) vs. Linker:**
    * *Compiler:* Překládá zdrojový text v C/C++ do binárních objektových souborů (`.obj`).
    * *Linker:* Propojí objektové soubory a knihovny do výsledného spustitelného souboru (`.exe`, `.so`), vyřeší externí symboly a adresy skoků.
  * **Statické vs. Dynamické knihovny:**
    * *Statická knihovna (`.lib`, `.a`):* Kód knihovny se v době linkování celý nakopíruje do výsledné binárky $\implies$ samostatný soubor, ale větší velikost na disku i v RAM.
    * *Dynamická knihovna (`.dll`, `.so`):* Kód zůstává v externím souboru. Načte se do RAM až při spuštění programu $\implies$ menší binárka, kód knihovny může sdílet více procesů v RAM současně.
  * **Reprezentace programu v .NET (CIL, JIT a AOT):**
    * C# kompilátor (`csc`) nepřekládá do strojového kódu CPU, ale do mezikódu **CIL (Common Intermediate Language)** / Bytecode uloženého v `.dll` sestavení.
    * Běhové prostředí **CLR (Common Language Runtime)** obsahuje virtuální stroj, který CIL spouští a spravuje paměť (Garbage Collector).
    * **JIT (Just-In-Time) kompilátor:** Překládá jednotlivé CIL metody do nativního strojového kódu procesoru **až za běhu aplikace při jejich prvním zavolání**.
    * **AOT (Ahead-Of-Time) kompilace:** Překládá C# kód do nativního strojového kódu procesoru **předem ještě před spuštěním** $\implies$ bleskový start programu bez zahřívání JITu a menší nároky na RAM.
  * **Správa paměti a Generační Garbage Collector (.NET GC):**
    * *Generační hypotéza:* Většina objektů zaniká krátce po svém vytvoření. Paměť haldy je rozdělena na:
      * **Gen 0:** Nové krátce žijící objekty (alokace je pouhý posun pointeru, sbírá se nejčastěji a bleskově).
      * **Gen 1:** Přeživší z Gen 0 (nárazníkové pásmo).
      * **Gen 2:** Dlouho žijící objekty (plný sběr Full GC, nejdražší fáze).
      * **LOH (Large Object Heap):** Objekty $> 85\text{ KB}$ (např. velká pole); nedefragmentují se, aby se nekopírovaly obří bloky RAM.
  * **Běhové prostředí a vazba na operační systém (Co to reálně je):**
    * Aplikace v C# neběží izolovaně, CLR přímo mapuje své abstrakce na funkce a jádro OS:
      1. *Vlákna:* Každý `new Thread()` v C# je přímo **1:1 mapované nativní vlákno jádra OS** (Kernel thread).
      2. *Systémová volání (Syscalls):* Třídy pro I/O (`FileStream`, `Socket`) interně volají systémová volání OS (`read`, `write`, `epoll`, resp. Win32 `CreateFile`, `IOCP`).
      3. *P/Invoke (`[DllImport]`):* Umožňuje z C# volat nativní C funkce z OS knihoven (`kernel32.dll`, `libc.so`).
      4. *Správa OS handlů (`SafeHandle`, `IDisposable`):* Objekty drží nativní deskriptory OS; jejich uzavření garantuje `using` a `Dispose()`.
      5. *Meziprocesní synchronizace:* Třídy `Mutex` a `Semaphore` s prefixem `"Global\\..."` vytvářejí reálné pojmenované objekty v jádře OS (*Kernel Objects*).

## Web


### Databáze

#### 1. Architektury databázových systémů a Návrh relací:
* **Tříúrovňová architektura ANSI/SPARC:**
  1. **Konceptuální úroveň:** Logická struktura celé databáze nezávislá na konkrétním DBMS (např. konceptuální ER diagram nebo UML diagram tříd – entity, atributy, vztahy, kardinality).
  2. **Logická (implementační) úroveň:** Transformace konceptuálního modelu do konkrétního datového modelu (např. relační schéma – tabulky, primární klíče `PK`, cizí klíče `FK`, datové typy sloupců).
  3. **Fyzická (interní) úroveň:** Fyzické uložení dat na paměťových médiích (soubory na disku, stránky paměti, diskové bloky, uspořádání záznamů, B-stromové a hash indexy).
* **Funkční závislosti a klíče:**
  * **Funkční závislost ($X \to Y$):** V relaci $R$ platí, že pokud se dva řádky shodují v atributech $X$, musí se nutně shodovat i v atributech $Y$.
  * **Uzávěr atributů ($X^+$):** Množina všech atributů, které jsou funkčně závislé na $X$.
  * **Klíč relace (Kandidátní klíč):** Minimální množina atributů $K$, pro kterou platí $K^+ = R$ (žádná vlastní podmnožina $K$ není klíčem). **Nadklíč:** Libovolná nadmnožina klíče.
* **Normalizace relací (Normální formy – proč normalizujeme):**
  * **Cíl:** Odstranění redundance (duplicitních dat) a eliminace **anomálií** při manipulaci s daty:
    * *Anomálie při vkládání (Insertion anomaly):* Nelze vložit informaci o jedné entitě bez existence druhé entity.
    * *Anomálie při mazání (Deletion anomaly):* Smazáním jednoho faktu nechtěně smažeme i jiný nesouvisející fakt.
    * *Anomálie při aktualizaci (Update anomaly):* Změna jednoho údaje vyžaduje přepis mnoha řádků (riziko nekonzistence).
  * **1. Normální forma (1NF):** Všechny atributy obsahují pouze **atomické (nedělitelné)** hodnoty (žádná pole, vnořené relace, seznamy).
  * **2. Normální forma (2NF):** Je v 1NF a žádný neklíčový atribut není **částečně závislý** na složeném primárním klíči (všechny neklíčové atributy jsou plně funkčně závislé na celém primárním klíči).
  * **3. Normální forma (3NF):** Je ve 2NF a žádný neklíčový atribut není **tranzitivně závislý** na primárním klíči (neexistuje závislost $Klíč \to X \to Nezklicovy$). Formálně: pro každou netriviální $X \to Y$ je $X$ nadklíč nebo $Y$ je součástí nějakého kandidátního klíče.
  * **Boyce-Coddova normální forma (BCNF):** Zpřísnění 3NF: Pro **každou** netriviální funkční závislost $X \to Y$ musí být množina atributů $X$ **nadklíčem**.
  * **Dekompozice relací:** Rozdělení původní tabulky na menší. Musí být:
    1. **Bezeztrátová (Lossless-join):** Přirozené spojení dekomponovaných tabulek $R_1 \bowtie R_2$ musí přesně zrekonstruovat původní $R$ (platí právě tehdy, když $R_1 \cap R_2 \to R_1$ nebo $R_1 \cap R_2 \to R_2$).
    2. **Se zachováním funkčních závislostí:** Všechny původní závislosti lze ověřit v rámci jednotlivých tabulek bez nutnosti provádět JOIN. *(3NF vždy zaručuje obojí, BCNF zaručuje bezeztrátovost, ale nemusí zachovat všechny závislosti).*
  * **Názorný postupný příklad normalizace (1NF $\to$ 2NF $\to$ 3NF $\to$ BCNF na jednom scénáři):**
    1. **Ne-1NF $\to$ 1NF (Atomické hodnoty):**
       * *Výchozí stav:* `Student(StudentID, Jmeno, Fakulta, MestoFakulty, Predmety[Kod, Nazev])` $\implies$ atribut `Predmety` je pole/seznam (neatomický).
       * *Převod do 1NF:* Rozbalení do atomických řádků se složeným klíčem:  
         `R(`$\underline{\mathbf{StudentID, Kod}}$, `Jmeno, Fakulta, MestoFakulty, Nazev)`.
    2. **1NF $\to$ 2NF (Odstranění částečných závislostí na složeném klíči):**
       * *Problém v 1NF:* Neklíčové atributy závisí jen na *části* klíče: `Kod -> Nazev` a `StudentID -> (Jmeno, Fakulta, MestoFakulty)`.
       * *Dekompozice do 2NF:* Vyčlenění tabulek s plnou závislostí na celém svém klíči:
         * `Predmet(`$\underline{\mathbf{Kod}}$, `Nazev)`
         * `Zapis(`$\underline{\mathbf{StudentID, Kod}}$)
         * `Student(`$\underline{\mathbf{StudentID}}$, `Jmeno, Fakulta, MestoFakulty)`
    3. **2NF $\to$ 3NF (Odstranění tranzitivních závislostí neklíčových atributů):**
       * *Problém v `Student`:* Platí tranzitivní závislost `StudentID -> Fakulta -> MestoFakulty` (`MestoFakulty` závisí na `Fakulta`, což není klíč/nadklíč).
       * *Dekompozice do 3NF:*
         * `Student(`$\underline{\mathbf{StudentID}}$, `Jmeno, Fakulta)`
         * `Fakulta(`$\underline{\mathbf{Fakulta}}$, `MestoFakulty)`
    4. **3NF $\to$ BCNF (Každý determinant musí být nadklíčem):**
       * *Mějme tabulku cvičení:* `Cviceni(`$\underline{\mathbf{Student, Predmet}}$, `Cvicici)` s pravidly:
         * `(Student, Predmet) -> Cvicici` (student má pro předmět 1 cvičícího)
         * `Cvicici -> Predmet` (cvičící učí pouze 1 předmět)
       * *Kandidátní klíče:* `(Student, Predmet)` i `(Student, Cvicici)`. Všechny atributy jsou primární (součástí klíče) $\implies$ **relace je ve 3NF!**
       * *Problém (porušení BCNF):* V závislosti `Cvicici -> Predmet` není determinant `Cvicici` nadklíčem.
       * *Dekompozice do BCNF:*
         * `Uvazek(`$\underline{\mathbf{Cvicici}}$, `Predmet)`
         * `ZapisCviceni(`$\underline{\mathbf{Student, Cvicici}}$)
         * *(Důležitý postřeh: Dekompozice je bezeztrátová, ale ztratila se funkční závislost $(Student, Predmet) \to Cvicici$ – nelze ji hlídat bez JOINu tabulek, proto se v praxi často zůstává u 3NF).*
* **Převod konceptuálního modelu (ER/UML) na relační model:**
  * **Entita $\implies$ Relační tabulka** (atributy se stanou sloupci, identifikátor primárním klíčem `PK`).
  * **Vztah 1:N $\implies$ Cizí klíč (`FK`):** Primární klíč strany 1 se vloží jako cizí klíč do tabulky na straně N.
  * **Vztah M:N $\implies$ Samostatná asociační (vazební) tabulka:** Obsahuje cizí klíče na obě zúčastněné tabulky, jejichž kombinace tvoří složený primární klíč asociační tabulky.
* **Konceptuální modelování (UML / ER) – Zkouškový vzor kreslení na papír:**
  * **Entity:** Obdélník se jménem nahoře, pod čarou atributy se znaménky (např. `- Cislo`, `- Jmeno`, `- Typ`).
  * **Vztahy (Asociace):** Spojnice se jménem vztahu a kardinalitami na obou koncích ve formátu $(min, max)$, např. $(0, 1)$, $(0, *)$, $1$ (což znamená $(1, 1)$).
  * **Zkouškový vzor: Učitel a Student v jedné entitě `Osoba` a vztahy k `DiplomovaPrace`:**
    ```text
    +---------------+                  +------------------+
    | Osoba         |                  | DiplomovaPrace   |
    +---------------+ (0,1) Resi (0,1) +------------------+
    | - Cislo       |------------------| - Nazev          |
    | - Jmeno       |                  | - StudijniObor   |
    | - Prijmeni    | 1    Vede (0,*)  | - NazevFakulty   |
    | - Typ         |------------------|                  |
    +---------------+                  +------------------+
    ```
    * *Vysvětlení kardinalit:*
      * `Resi (0,1) ... (0,1)`: Student může řešit nejvýše 1 práci (nebo 0); práce má nejvýše 1 řešitele (nebo 0 = volné téma).
      * `Vede 1 ... (0,*)`: Práce musí mít právě 1 vedoucího; učitel může vést libovolně mnoho prací $(0, *)$.
    * *Alternativa přes ISA dědičnost:* Nadtřída `Osoba` $\to$ trojúhelník (generalizace) $\to$ podtřídy `Student` (vstupuje do `Resi`) a `Ucitel` (vstupuje do `Vede`).

* **Co znamená „Vlnka“ ($\sim\sim$) a jak kreslit netriviální prvky v ER a UML (Zkouškový přehled):**
  * **1. Co znamená vlnka / podtržení vlnovkou:**
    * **V konceptuálním ER diagramu (Chen / MFF):** Značí **částečný klíč / diskriminátor slabé entity** ($\underline{\sim\text{CisloPolozky}\sim}$). Atribut je v elipse podtržen vlnovkou. Sám o sobě nestačí k jednoznačné identifikaci v celém systému, je unikátní pouze v rámci nadřazené silné entity (vlastníka).
    * **V relačním schématu (prof. Pokorný):** Plná čára značí primární klíč ($\underline{\mathbf{ID}}$), zatímco **vlnovka pod názvem sloupce** ($\underset{\sim}{\text{VlastnikID}}$) značí **cizí klíč (FK)**.
  * **2. Slabá entita & Identifikační vztah vs. Kompozice:**
    * **ER:** Slabá entita = **dvojitý obdélník**, identifikační vztah = **dvojitý kosočtverec**, diskriminátor = elipsa s **vlnovkou**.
    * **UML:** Modeluje se jako **Kompozice** – **plný černý kosočtverec** ($\blacklozenge$) na straně vlastníka (`Faktura` $1 \blacklozenge$--- $1..*$ `PolozkaFaktury`). Kardinalita na straně vlastníka je povinně $1$ ($1..1$). Životní cyklus komponenty je vázán na vlastník.
    * **Převod do SQL:** Složený PK = PK vlastníka + diskriminátor. Cizí klíč má kaskádní integritu:
      `PRIMARY KEY (FakturaID, CisloPolozky)`, `FOREIGN KEY (FakturaID) REFERENCES Faktura(ID) ON DELETE CASCADE`.
  * **3. Agregace vs. Kompozice v UML:**
    * **Agregace ($\lozenge$ prázdný kosočtverec):** Vztah „celek - část“ s nezávislým životním cyklem. Komponenta může existovat bez celku a být sdílena (např. `Univerzita` $\lozenge$--- `Profesor`).
    * **Kompozice ($\blacklozenge$ plný černý kosočtverec):** Výhradní vlastnictví se sdíleným životním cyklem. Zánik celku znamená zánik komponenty (např. `Dokument` $\blacklozenge$--- `Odstavec`).
  * **4. Asociační třída (UML) vs. Atributy vztahu (ER):**
    * **Situace:** Vztah M:N nese vlastní atributy (např. vztah mezi `Student` a `Predmet` nese `Znamka`, `DatumZkousky`, `Termin`).
    * **ER:** Elipsy s atributy vedou přímo z kosočtverce vztahu.
    * **UML:** **Asociační třída** – samostatný obdélník třídy spojený **čárkovanou spojnicí** přímo s asociační čárou mezi třídami.
    * **Převod do SQL:** Vždy samostatná propojovací tabulka s vlastními sloupci:
      `Zapis(`$\underline{\mathbf{StudentID, PredmetID}}$, `Datum, Znamka)`.
  * **5. N-ární (Ternární) vztahy a určení klíčů:**
    * **Příklad:** Lékař předepisuje Lék Pacientovi (`Lekar`, `Pacient`, `Lek`).
    * **ER:** Kosočtverec spojující 3 (či více) entit. **UML:** Kosočtverec/diamant $\lozenge$ na křižovatce spojnic mezi 3 třídami.
    * **Pravidlo pro určení PK v relačním modelu (Kritická zkoušková past!):**
      * Pokud je vazba obecná $M:N:P$: Primárním klíčem je trojice všech klíčů $\underline{\mathbf{(LekarID, PacientID, LekID)}}$.
      * Pokud platí omezení kardinality $1$ (např. pro danou dvojici Pacient a Lék existuje právě jeden ošetřující Lékař, tj. $Pacient \times Lek \to Lekar$): PK tvoří **pouze** dvojice $\underline{\mathbf{(PacientID, LekID)}}$ a `LekarID` je v tabulce pouze běžným cizím klíčem!
  * **6. Rekurzivní (unární) vztahy a ROLE:**
    * Vztah entity sama se sebou (např. `Zamestnanec` řídí jiné `Zamestnance`, nebo `Dil` se skládá z jiných `Dilu`).
    * **Povinnost u zkoušky:** U obou konců smyčky **musí být explicitně uvedena jména rolí** (např. role `vedouci (0,1)` vs role `podrizeny (0,*)`). Bez rolí je diagram chybný!
    * **Převod do SQL:** Cizí klíč v téže tabulce: `NadrizenyID INT REFERENCES Zamestnanec(ZamestnanecID)`.
  * **7. ISA hierarchie (Dědičnost / Specializace) a integritní omezení:**
    * **ER:** Trojúhelník `ISA` (špička k nadtypu). **UML:** Prázdná trojúhelníková šipka $\vartriangle$ směřující k nadtřídě.
    * **Dvě ortogonální dimenze omezení (Zkouškový standard):**
      1. **Disjunktnost podtříd:**
         * `{disjoint}` (disjunktní): Instance může patřit nejvýše do jednoho podtypu (např. `Auto` vs. `Nakladak`).
         * `{overlapping}` (překrývající se): Instance může patřit do více podtypů současně (např. `Student` i `Zamestnanec`).
      2. **Úplnost pokrytí:**
         * `{complete / total}` (úplná): Každá instance nadtypu musí patřit alespoň do jednoho podtypu (nadtřída je abstraktní).
         * `{incomplete / partial}` (částečná): Mohou existovat instance nadtypu nepatřící do žádné podtřídy.
    * **3 přístupy k mapování ISA do SQL tabulek:**
      * *A. Single Table (Jedna tabulka pro celou hierarchii):* `Osoba(ID, Typ, Jmeno, Obor, Plat)` + diskriminátor `Typ`. Sloupce specifické pro podtřídy musí povolit `NULL`. Žádný JOIN, ale plýtvá místem.
      * *B. Joined Table / Class Table Inheritance (Tabulka pro nadtřídu i každou podtřídu):* `Osoba(`$\underline{\mathbf{ID}}$, `Jmeno)`, `Student(`$\underline{\mathbf{ID}}$, `Obor)`, `Ucitel(`$\underline{\mathbf{ID}}$, `Katedra)`. Klíč podtřídy je současně PK i FK odkazující do `Osoba(ID)`. Čistá normalizace, ale vyžaduje JOIN.
      * *C. Concrete Table per Class (Tabulky pouze pro listové podtřídy):* `Student(`$\underline{\mathbf{ID}}$, `Jmeno, Obor)`, `Ucitel(`$\underline{\mathbf{ID}}$, `Jmeno, Katedra)`. Tabulka `Osoba` neexistuje. Vhodné pouze pro `{disjoint, complete}`.
  * **8. Speciální atributy v ER:**
    * **Vícehodnotový (Multivalued):** **Dvojitá elipsa** (např. `TelefonniCisla`). V UML jako atribut s kardinalitou `telefon: string[0..*]`.
      * $\implies$ V SQL relačním modelu se **musí** vyčlenit do samostatné tabulky se složeným klíčem: `Telefon(`$\underline{\mathbf{OsobaID, Cislo}}$`)`.
    * **Složený (Composite):** Strom elips větvící se z elipsy (např. `Adresa` $\to$ `Ulice`, `Mesto`, `PSC`).
      * $\implies$ V relačním modelu se "rozbalí" na samostatné atomické sloupce: `Ulice, Mesto, PSC` (splnění 1NF).
    * **Odvozený (Derived):** **Čárkovaná elipsa**, v UML se značí lomítkem `/vek`.
      * $\implies$ V relační databázi se standardně neukládá (porušení redundance), počítá se ve `VIEW` nebo `GENERATED ALWAYS AS (...)`.
  * **9. Výčtový typ (Enum / Číselník) v ER, UML a SQL (Zkouškové standardy):**
    * **V UML:** Samostatný obdélník se stereotypem `«enumeration»`:
      ```text
      +--------------------+
      |   «enumeration»    |
      |        Stav        |
      +--------------------+
      | NOVY               |
      | ZAPLACENO          |
      | STORNO             |
      +--------------------+
      ```
      Použití ve třídě: `- stav: Stav` (nebo zkráceně přímo v atributu: `- stav: {NOVY, ZAPLACENO, STORNO}`).
    * **V ER diagramu:** Běžná elipsa atributu s vypsanou doménou povolených hodnot: `Stav {NOVY, ZAPLACENO, STORNO}`. (Pokud má stav nést další údaje jako popis či sazbu, modeluje se jako plnohodnotná entita spojená vztahem 1:N).
    * **Převod do SQL (3 přístupy):**
      1. *Omezení `CHECK` (univerzální standardní SQL):*  
         `stav VARCHAR(20) NOT NULL CHECK (stav IN ('NOVY', 'ZAPLACENO', 'STORNO'))`
      2. *Nativní `ENUM` typ (PostgreSQL / MySQL):*  
         `CREATE TYPE stav_t AS ENUM ('NOVY', 'ZAPLACENO', 'STORNO');` a sloupec `stav stav_t NOT NULL;`
      3. *Číselníková tabulka (Lookup Table – pro dynamické výčty):*  
         `StavCiselnik(`$\underline{\mathbf{Kod}}$, `Popis)` + cizí klíč v cílové tabulce `StavKod REFERENCES StavCiselnik(Kod)`.



* **Vzorový zápis relačního schématu (Formální MFF notace na zkoušce):**
  * **Zápis relace:** `NazevRelace(Atribut1, Atribut2, ...)`
  * **Primární klíč (`PK`):** **Tučně a podtrženě** $\underline{\mathbf{OsobaID}}$.
  * **Kandidátní klíč (alternativní unikátní identifikátor):** Podtrženě $\underline{Cislo}$.
  * **Cizí klíč (`FK`) a referenční integrita:** Zapisuje se jako **inkluze množin**:
    $$\text{AtributFK} \subseteq \text{CilovaTabulka}.\text{CilovyAtributPK}$$
  * **Pravidla pro klíče vztahových tabulek (Zlaté pravidlo MFF):**
    * *„Kardinalita vztahů se projeví v rozdílné definici klíčů vztahových tabulek.“*
    * **Vztah 1:N (`Vede`):** Cizí klíč se vloží přímo do tabulky na straně N:
      `DiplomovaPrace(`$\underline{\mathbf{DiplomovaPraceID}}$, `Nazev, StudijniObor, NazevFakulty, VedouciID)`
      `VedouciID` $\subseteq$ `Osoba.OsobaID`
    * **Vztah (0,1) : (0,1) (`Resi`):** Samostatná vztahová tabulka (nebo cizí klíč s `UNIQUE`):
      `Resi(`$\underline{\mathbf{OsobaID}}$, `DiplomovaPraceID)`  *(klíčem může být buď OsobaID nebo DiplomovaPraceID – oba jsou kandidátní klíče!)*
      `OsobaID` $\subseteq$ `Osoba.OsobaID`
      `DiplomovaPraceID` $\subseteq$ `DiplomovaPrace.DiplomovaPraceID`
    * **Vztah M:N (např. kniha a více autorů):** Klíčem je složený klíč obou $\underline{\mathbf{(AutorID, KnihaID)}}$.

* **Příklad na dekompozici a převod do 3NF (Zkouškový vzor ze zadání):**
  * *Původní tabulka:* `DiplomovaPrace(`$\underline{\mathbf{DiplomovaPraceID}}$, `Nazev, StudijniObor, NazevFakulty)`
  * *Tranzitivní funkční závislost:* $DiplomovaPraceID \to StudijniObor \to NazevFakulty$.
  * *Proč porušuje 3NF:* Pro závislost $StudijniObor \to NazevFakulty$ platí, že $StudijniObor$ **není nadklíč** a $NazevFakulty$ **není součástí žádného kandidátního klíče**.
  * *Oprava (Dekompozice podle $StudijniObor \to NazevFakulty$):*
    * `Obor(`$\underline{\mathbf{StudijniObor}}$, `NazevFakulty)`
    * `DiplomovaPrace(`$\underline{\mathbf{DiplomovaPraceID}}$, `Nazev, StudijniObor)`
      `StudijniObor` $\subseteq$ `Obor.StudijniObor`

---

#### 2. Transakční zpracování, ACID, Rozvrhy a Zamykání:
* **Vlastnosti transakcí (ACID):**
  * **A (Atomicity – Nedělitelnost):** Všechno nebo nic. Transakce proběhne celá (úspěšný `COMMIT`), nebo se při chybě/pádu vrátí do výchozího stavu (`ROLLBACK`).
  * **C (Consistency – Konzistence):** Transakce převádí databázi z jednoho konzistentního stavu do jiného (narušení integrity $\implies$ zrušení transakce).
  * **I (Isolation – Izolovanost):** Souběžně běžící transakce se navzájem neovlivňují; mezistavy neuložené transakce nejsou viditelné pro ostatní.
  * **D (Durability – Trvalost):** Změny potvrzené transakce (`COMMIT`) jsou trvalé a přežijí i výpadek napájení a restart systému (zajištěno transakčním deníkem **WAL – Write-Ahead Logging**, kde se log zapíše na disk před samotným zápisem dat).
* **Anomálie při souběhu transakcí:**
  * *Dirty Read (Čtení špinavých dat):* $T_2$ přečte neuložená data zapsaná $T_1$, která následně provede `ROLLBACK`.
  * *Non-repeatable Read (Neopakovatelné čtení):* $T_1$ přečte řádek, $T_2$ ho přepíše a potvrdí, $T_1$ ho přečte znovu a vidí jinou hodnotu.
  * *Phantom Read (Fantomové čtení):* $T_1$ provede dotaz s podmínkou (např. věk $> 18$), $T_2$ vloží nový řádek splňující podmínku, $T_1$ dotaz zopakuje a vidí řádek navíc.
* **Rozvrhy (Schedules) a Konfliktová uspořádatelnost (Conflict Serializability):**
  * **Konfliktní operace:** Dvě operace jsou v konfliktu $\iff$ patří různým transakcím ($i \neq j$), přistupují ke **stejné položce $x$** a alespoň jedna z nich je zápis ($w$). Konfliktní dvojice: $r_i(x) - w_j(x)$, $w_i(x) - r_j(x)$, $w_i(x) - w_j(x)$. Dvě čtení $r_i(x) - r_j(x)$ v konfliktu **nejsou**!
  * **Postup vyšetření konfliktové uspořádatelnosti (Krok za krokem na zkoušce):**
    1. *Nakresli uzly:* Pro každou transakci $T_1, T_2, \dots, T_k$ v rozvrhu vytvoř uzel grafu.
    2. *Hledej konfliktní hrany (zleva doprava v čase):* Projdi rozvrh a pro každou položku (např. $A, B$) najdi operace přistupující ke stejné položce:
       * Kdykoliv předchází $o_i(x)$ před $o_j(x)$ (kde $i \neq j$) a jsou v konfliktu, přidej orientovanou hranu $T_i \to T_j$.
    3. *Vyhodnocení grafu předcházení (Precedence Graph / Konfliktový graf):*
       * **Graf je acyklický (DAG):** Rozvrh **JE konfliktově uspořádatelný**. Ekvivalentní sériové pořadí určíš **topologickým uspořádáním** grafu (např. $T_1 \to T_3 \to T_2$).
       * **Graf obsahuje cyklus (např. $T_1 \to T_2$ i $T_2 \to T_1$):** Rozvrh **NENÍ konfliktově uspořádatelný** (nelze jej sériově seřadit).

* **Zotavitelnost (REC) a Vyvarování se kaskádních rollbacků (ACA) – Postup vyšetření:**
  * **1. Krok: Najdi všechny relace „kdo od koho čte“ (Read-From):**
    * $T_j$ čte od $T_i$ ($T_i \xrightarrow{\text{čte}} T_j$), pokud $T_i$ zapsala do položky $x$ ($w_i(x)$), následně $T_j$ přečetla tutéž položku $x$ ($r_j(x)$) a mezitím žádná jiná transakce do $x$ nezapsala.
  * **2. Krok: Test na Zotavitelnost (REC – Recoverable):**
    * *Pravidlo:* Pro každou dvojici, kde $T_j$ čte od $T_i$, musí platit, že $T_i$ potvrdí **dříve** než $T_j$:
      $$c_i < c_j$$
    * *Zdůvodnění:* Pokud by $T_j$ potvrdila dříve než $T_i$ ($c_j < c_i$), a $T_i$ by následně zhavarovala (`ROLLBACK`), databáze by obsahovala potvrzená neplatná data, která již nelze vzít zpět $\implies$ **NEZOTAVITELNÝ rozvrh**.
  * **3. Krok: Test na Vyvarování se kaskádních rollbacků (ACA – Avoids Cascading Aborts):**
    * *Pravidlo (Přísnější):* Každá transakce smí číst data **pouze od transakcí, které již potvrdily**!
      $$w_i(x) \dots c_i \dots r_j(x)$$
    * *Zdůvodnění:* Pokud $T_j$ čte data zapsaná $T_i$ ještě předtím, než se $T_i$ commitne ($w_i(x) \dots r_j(x) \dots c_i$), pak při abortu $T_i$ musí systém kaskádově abortovat i $T_j$ $\implies$ **NENÍ ACA** (i kdyby rozvrh byl zotavitelný díky $c_i < c_j$).
  * **4. Shrnutí hierarchie rozvrhů:**
    $$\text{Sériový} \subset \text{Striktní (ST)} \subset \text{Bez kaskádových rollbacků (ACA)} \subset \text{Zotavitelný (REC)}$$
    *(Platí: Každý ACA rozvrh je automaticky zotavitelný! Striktní rozvrh navíc zakazuje přepis $w_j(x)$ před $c_i$).*
* **Zamykací protokoly (Locking Protocols):**
  * Zámky: **Sdílený $S$** (pro čtení – více transakcí může držet $S$ současně), **Výhradní $X$** (pro zápis – drží pouze jediná transakce, vylučuje $S$ i $X$).
  * **Dvoufázové zamykání (2PL – Two-Phase Locking):**
    1. *Fáze růstu:* Transakce zámky pouze získává, žádný neuvolňuje.
    2. *Fáze smršťování:* Jakmile transakce uvolní první zámek, nesmí už žádný nový zámek získat.
    * *Vlastnost:* **2PL zaručuje konfliktovou uspořádatelnost!** Nezabraňuje však deadlocku ani kaskádovým rollbackům.
  * **Striktní 2PL (Strict 2PL / S2PL):** Všechny **výhradní zámky $X$** se drží až do konce transakce (až po `COMMIT` / `ROLLBACK`).
    * *Vlastnost:* **Garantuje uspořádatelnost + zamezuje kaskádovým rollbackům (je ACA i zotavitelný)!** Nejčastěji používaný v komerčních RDBMS.
  * **Rigidní (Silné) 2PL (SS2PL):** Všechny zámky ($S$ i $X$) se drží až do konce transakce.
* **Zablokování (Deadlock):**
  * Situace cyklického čekání, kdy $T_1$ čeká na zámek držený $T_2$ a $T_2$ čeká na zámek držený $T_1$.
  * **Detekce deadlocku:** Údržba grafu čekání (**Wait-for Graph**). Pravidelně se hledají cykly $\implies$ při detekci se vybere „oběť“ (victim), která se přeruší (`ROLLBACK`) a zámky se uvolní.
  * **Prevence pomocí časových razítek (Timestamp ordering – transakce má čas vzniku $TS(T)$):**
    * *WAIT-DIE (ne-preemptivní):* Starší transakce smí čekat na mladší ($TS(T_i) < TS(T_j)$). Pokud mladší transakce žádá o zámek držený starší, mladší okamžitě „zemře“ (abort + restart se stejným timestampem).
    * *WOUND-WAIT (preemptivní):* Starší transakce okamžitě „zraní“ (abortne) mladší transakci držící zámek a zámek jí sebere. Mladší transakce na starší smí čekat.

---

#### 3. Přehled jazyka SQL a Pokročilé dotazování:
* **Logické pořadí vyhodnocování SQL dotazu:**
  $$\text{FROM} \to \text{ON} \to \text{JOIN} \to \text{WHERE} \to \text{GROUP BY} \to \text{HAVING} \to \text{SELECT} \to \text{DISTINCT} \to \text{ORDER BY} \to \text{LIMIT}$$
  *(Důležité: Aliasy definované v `SELECT` nelze použít ve `WHERE`, protože `WHERE` se vyhodnocuje dříve!).*
* **Typy spojení tabulek (JOIN):**
  * `INNER JOIN`: Vrátí pouze řádky, které mají shodu v obou tabulkách.
  * `LEFT (OUTER) JOIN`: Vrátí všechny řádky z levé tabulky; pokud v pravé není shoda, doplní hodnoty `NULL`.
  * `FULL (OUTER) JOIN`: Vrátí všechny řádky z obou tabulek, chybějící protějšky doplní `NULL`.
  * `CROSS JOIN`: Kartézský součin (každý řádek s každým).
* **Agregace a rozdíl `WHERE` vs. `HAVING`:**
  * `WHERE`: Filtruje **jednotlivé řádky ještě před seskupením** (nesmí obsahovat agregační funkce jako `SUM`, `AVG`).
  * `GROUP BY`: Seskupí řádky se stejnou hodnotou klíče do jedné skupiny.
  * `HAVING`: Filtruje **celé agregované skupiny po seskupení** (používá podmínky na agregační funkce, např. `HAVING COUNT(*) > 5`).
  * Agregační funkce: `COUNT(*)`, `COUNT(sloupec)` (spočte pouze **nenulové** hodnoty!), `SUM`, `AVG`, `MIN`, `MAX`.
* **Tříhodnotová logika (3VL) a `NULL` hodnoty:**
  * `NULL` reprezentuje chybějící nebo neznámou hodnotu.
  * Libovolné porovnání s `NULL` dává hodnotu **`UNKNOWN`** (např. `x = NULL` nebo `x <> NULL` je `UNKNOWN`, nikoliv `TRUE` ani `FALSE`!).
  * Klauzule `WHERE` propustí pouze řádky s výsledkem `TRUE` (řádky s `FALSE` i `UNKNOWN` jsou zahozeny).
  * **Správný test na NULL:** `sloupec IS NULL` nebo `sloupec IS NOT NULL`.
  * Ošetření v dotazech: `COALESCE(sloupec, výchozí_hodnota)` vrátí první nenulový argument.
* **Vnořené dotazy (Subqueries):**
  * *Nekorelovaný poddotaz:* Nezávislý na vnějším dotazu, vyhodnotí se pouze jednou (např. `WHERE plat > (SELECT AVG(plat) FROM zamestnanci)`).
  * *Korelovaný poddotaz:* Odkazuje na sloupce vnějšího dotazu, vyhodnocuje se znovu pro každý řádek vnějšího dotazu (např. s operátorem `EXISTS (SELECT 1 FROM objednavky WHERE zakaznik_id = z.id)`).
  * *Operátory:* `IN`, `NOT IN` *(pozor: pokud poddotaz v `NOT IN` vrátí jediný `NULL`, celý výraz je `UNKNOWN` a nevrátí nic!)*, `ANY / SOME`, `ALL`.
* **Tvorba tabulek (DDL `CREATE TABLE` s integritními omezeními) a vkládání (DML `INSERT`):**
  ```sql
  -- 1. Tvorba tabulek s PRIMARY KEY, UNIQUE, FOREIGN KEY, CHECK a NOT NULL:
  CREATE TABLE Osoba (
      OsobaID INT PRIMARY KEY,
      Cislo VARCHAR(20) UNIQUE NOT NULL,      -- kandidátní klíč
      Jmeno VARCHAR(50) NOT NULL,
      Prijmeni VARCHAR(50) NOT NULL,
      Typ VARCHAR(10) NOT NULL CHECK (Typ IN ('student', 'ucitel'))
  );

  CREATE TABLE Obor (
      StudijniObor VARCHAR(50) PRIMARY KEY,
      NazevFakulty VARCHAR(100) NOT NULL
  );

  CREATE TABLE DiplomovaPrace (
      DiplomovaPraceID INT PRIMARY KEY,
      Nazev VARCHAR(200) NOT NULL,
      StudijniObor VARCHAR(50) NOT NULL REFERENCES Obor(StudijniObor),
      VedouciID INT NOT NULL,
      FOREIGN KEY (VedouciID) REFERENCES Osoba(OsobaID) ON DELETE RESTRICT
  );

  CREATE TABLE Resi (
      OsobaID INT PRIMARY KEY REFERENCES Osoba(OsobaID),
      DiplomovaPraceID INT UNIQUE NOT NULL REFERENCES DiplomovaPrace(DiplomovaPraceID)
  );

  -- 2. Vkládání dat (INSERT INTO ... VALUES a INSERT INTO ... SELECT):
  INSERT INTO Osoba (OsobaID, Cislo, Jmeno, Prijmeni, Typ)
  VALUES (1, 's101', 'Jan', 'Novák', 'student'),
         (2, 'u202', 'Petr', 'Profesor', 'ucitel');

  INSERT INTO Obor VALUES ('Informatika', 'MFF'), ('Matematika', 'MFF');

  -- Vložení výsledků jiného dotazu (archivace):
  INSERT INTO ArchivPraci (ID, Nazev)
  SELECT DiplomovaPraceID, Nazev FROM DiplomovaPrace WHERE obhajeno = TRUE;
  ```

* **Zkouškové vzory dotazů (JOINy, Anti-Join, Vícenásobné reference a NOT EXISTS):**

  **1. Vícenásobný JOIN se dvěma aliasy na tutéž tabulku `Osoba` (Student i Vedoucí):**
  ```sql
  -- Vypiš název práce, fakultu, jméno studenta a jméno vedoucího:
  SELECT dp.Nazev, o.NazevFakulty,
         s.Jmeno || ' ' || s.Prijmeni AS Student,
         v.Jmeno || ' ' || v.Prijmeni AS Vedouci
  FROM DiplomovaPrace dp
  INNER JOIN Obor o ON dp.StudijniObor = o.StudijniObor
  INNER JOIN Osoba v ON dp.VedouciID = v.OsobaID               -- 1. odkaz na Osoba: Vedoucí (učitel)
  LEFT JOIN Resi r ON dp.DiplomovaPraceID = r.DiplomovaPraceID -- Volné téma nemusí mít řešitele!
  LEFT JOIN Osoba s ON r.OsobaID = s.OsobaID;                  -- 2. odkaz na Osoba: Student
  ```

  **2. `LEFT OUTER JOIN` – Vyhledání „prázdných“ vazeb (Anti-Join vzor `IS NULL`):**
  ```sql
  -- Najdi všechny učitele, kteří aktuálně NEVEDOU žádnou diplomovou práci:
  SELECT u.OsobaID, u.Jmeno, u.Prijmeni
  FROM Osoba u
  LEFT JOIN DiplomovaPrace dp ON u.OsobaID = dp.VedouciID
  WHERE u.Typ = 'ucitel' AND dp.DiplomovaPraceID IS NULL;
  ```

  **3. `FULL OUTER JOIN` (Zobrazení obou stran včetně nespárovaných):**
  ```sql
  -- Vypiš všechny studenty i všechny práce (včetně studentů bez práce a volných prací bez studenta):
  SELECT s.Jmeno, s.Prijmeni, dp.Nazev
  FROM Osoba s
  FULL OUTER JOIN Resi r ON s.OsobaID = r.OsobaID
  FULL OUTER JOIN DiplomovaPrace dp ON r.DiplomovaPraceID = dp.DiplomovaPraceID
  WHERE s.Typ = 'student' OR s.Typ IS NULL;
  ```

  **4. Zkouškový dotaz z minulých zadání (Knihy a vyloučení přátel přes `NOT EXISTS`):**
  ```sql
  -- „Které knihy napsal Dan Brown s někým, kdo nepatří do jeho přátel?“
  -- Tabulky: Autor(id, jmeno), Kniha(id, nazev), Napsal(id_autor, id_kniha), Pritel(id_autor1, id_autor2)
  SELECT DISTINCT k.nazev
  FROM Autor dan
  JOIN Napsal n1 ON dan.id = n1.id_autor
  JOIN Kniha k   ON n1.id_kniha = k.id
  JOIN Napsal n2 ON k.id = n2.id_kniha
  JOIN Autor spoluautor ON n2.id_autor = spoluautor.id
  WHERE dan.jmeno = 'Dan Brown'
    AND spoluautor.id <> dan.id
    AND NOT EXISTS (
        SELECT 1 FROM Pritel p
        WHERE (p.id_autor1 = dan.id AND p.id_autor2 = spoluautor.id)
           OR (p.id_autor2 = dan.id AND p.id_autor1 = spoluautor.id)
    );
  ```

  **5. Agregace s podmínkou nad skupinami (`HAVING` a `WHERE` současně):**
  ```sql
  -- Pro každého studenta spočti průměrnou známku ze zkoušek,
  -- ale uvažuj jen studenty, kteří mají alespoň 3 zkoušky a jejich průměr je lepší než 2.0:
  SELECT s.id, s.jmeno, COUNT(z.predmet_id) AS pocet_zkousek, AVG(z.znamka) AS prumer
  FROM Studenti s
  INNER JOIN Zkousky z ON s.id = z.student_id
  WHERE z.znamka IS NOT NULL
  GROUP BY s.id, s.jmeno
  HAVING COUNT(z.predmet_id) >= 3 AND AVG(z.znamka) < 2.0
  ORDER BY prumer ASC;
  ```

  **6. Skalární korelovaný poddotaz v `SELECT`:**
  ```sql
  -- Vypiš učitele a ke každému počet prací, které vede (bez nutnosti globálního GROUP BY a JOINu):
  SELECT u.OsobaID, u.Jmeno, u.Prijmeni,
         (SELECT COUNT(*) FROM DiplomovaPrace dp WHERE dp.VedouciID = u.OsobaID) AS PocetVedenychPraci
  FROM Osoba u
  WHERE u.Typ = 'ucitel';
  ```

  **7. Nekorelovaný poddotaz v klauzuli `HAVING` (Porovnání s globální hodnotou):**
  ```sql
  -- Najdi studenty, jejichž průměrná známka je lepší (menší) než celkový průměr všech studentů:
  SELECT s.OsobaID, s.Jmeno, s.Prijmeni, AVG(z.Znamka) AS PrumerStudenta
  FROM Osoba s
  JOIN Zapis z ON s.OsobaID = z.StudentID
  GROUP BY s.OsobaID, s.Jmeno, s.Prijmeni
  HAVING AVG(z.Znamka) < (
      SELECT AVG(Znamka) FROM Zapis  -- Jednorázově spočtený celkový průměr
  );
  ```

  **8. Relační dělení pomocí dvojitého `NOT EXISTS` (Klasická MFF otázka: „Kdo splnil VŠECHNY...“):**
  ```sql
  -- „Kteří studenti mají zapsané VŠECHNY povinné předměty?“
  -- Logika: Hledáme studenty, pro které NEEXISTUJE povinný předmět, který by si NEZAPSALI:
  SELECT s.OsobaID, s.Jmeno, s.Prijmeni
  FROM Osoba s
  WHERE s.Typ = 'student'
    AND NOT EXISTS (
        -- 1. Vyber všechny povinné předměty:
        SELECT p.PredmetID
        FROM Predmet p
        WHERE p.JePovinny = TRUE
          AND NOT EXISTS (
              -- 2. Ověř, zda si daný student tento předmět zapsal:
              SELECT 1
              FROM Zapis z
              WHERE z.StudentID = s.OsobaID AND z.PredmetID = p.PredmetID
          )
    );
  ```

  **9. Vnořený poddotaz s operátorem `> ALL`:**
  ```sql
  -- Najdi učitele, který vede VÍCE prací než KAŽDÝ (libovolný) učitel z Katedry softwaru:
  SELECT u.Jmeno, u.Prijmeni, COUNT(*) AS Pocet
  FROM Osoba u
  JOIN DiplomovaPrace dp ON u.OsobaID = dp.VedouciID
  GROUP BY u.OsobaID, u.Jmeno, u.Prijmeni
  HAVING COUNT(*) > ALL (
      SELECT COUNT(*)
      FROM DiplomovaPrace dp2
      JOIN Osoba u2 ON dp2.VedouciID = u2.OsobaID
      WHERE u2.Katedra = 'Katedra softwaru'
      GROUP BY u2.OsobaID
  );
  ```

  **10. Zkouškový chyták: Selhání `NOT IN` při výskytu `NULL` (proč vždy raději `NOT EXISTS`):**
  ```sql
  -- CHYBA: Pokud poddotaz vrátí byť jediný NULL, dotaz nevrátí ŽÁDNÝ řádek (prázdný výsledek)!
  SELECT * FROM Student 
  WHERE StudentID NOT IN (SELECT StudentID FROM Zapis);
  -- Důvod: x NOT IN (1, 2, NULL) se v SQL přeloží na (x <> 1 AND x <> 2 AND x <> NULL).
  -- Porovnání s NULL je vždy UNKNOWN -> TRUE AND UNKNOWN je UNKNOWN -> WHERE podmínka NIKDY není splněna!
  
  -- SPRÁVNĚ (dvouhodnotová logika existence, NULL ji nerozhodí):
  SELECT * FROM Student s 
  WHERE NOT EXISTS (SELECT 1 FROM Zapis z WHERE z.StudentID = s.StudentID);
  ```

---

#### 4. Moderní databázové systémy, NoSQL a Big Data:
* **Pojem Big Data a princip 4V:**
  1. **Volume (Objem):** Obrovské množství dat (terabyty až petabyty), které nelze efektivně uložit ani zpracovat na jednom serveru.
  2. **Velocity (Rychlost):** Vysoká frekvence generování a potřeba real-time zpracování (proudová data / streaming, senzory, logy).
  3. **Variety (Různorodost):** Heterogenní formáty – strukturovaná (tabulky), polostrukturovaná (JSON, XML) i nestrukturovaná (texty, audio, video).
  4. **Veracity (Věrohodnost/Kvalita):** Šum v datech, neúplnost, nejistota a potřeba čištění dat před analýzou.
  * *Výzvy pro tradiční RDBMS:* Špatná horizontální škálovatelnost (scale-out), nutnost fixního relačního schématu, režie ACID transakcí.
* **CAP teorém (Brewerova věta):**
  * V distribuovaném datovém úložišti lze současně zaručit **pouze 2 ze 3** následujících vlastností:
    * **C (Consistency – Silná konzistence):** Každé čtení vrátí nejnovější zapsanou hodnotu (všechny uzly vidí tatáž data současně).
    * **A (Availability – Dostupnost):** Každý nezhavarovaný uzel vrátí na libovolný požadavek platnou odpověď (bez chyby či timeoutu).
    * **P (Partition Tolerance – Odolnost proti rozpadu sítě):** Systém funguje dál i při ztrátě nebo zpoždění zpráv mezi uzly sítě.
  * *Důsledek pro distribuované systémy:* Síťové výpadky v reálném světě nastávají vždy $\implies$ **Partition tolerance je povinná**. Distribuované systémy proto volí kompromis:
    * **CP systémy (Konzistence + Partition tolerance):** Při výpadku sítě odmítnou obsloužit část požadavků, aby neporušily konzistenci (např. MongoDB, HBase).
    * **AP systémy (Dostupnost + Partition tolerance):** Při výpadku sítě odpoví všechny uzly, ale mohou vrátit zastaralá data (např. Apache Cassandra, CouchDB). Využívají model **BASE**: *Basically Available* (dostupný), *Soft state* (stav se může měnit i bez vstupu), *Eventual consistency* (data se nakonec sesynchronizují).
* **Základní třídy NoSQL databází (4 typy):**
  1. **Klíč – hodnota (Key-Value):**
     * *Příklady:* Redis, Memcached, Amazon DynamoDB.
     * *Model:* Asociativní pole; přístup výhradně přes unikátní klíč v čase $O(1)$. Hodnota je pro databázi netransparentní binární blob/string.
     * *Využití:* Session store, cache, nákupní košíky, bleskové čtení.
  2. **Dokumentové (Document Stores):**
     * *Příklady:* MongoDB, CouchDB.
     * *Model:* Ukládají polostrukturované dokumenty (typicky JSON / BSON). Každý dokument má unikátní `_id`, podporují sekundární indexy na libovolná vnitřní pole dokumentu a bohaté dotazy.
     * *Využití:* Uživatelské profily, katalogy produktů, CMS systémy s proměnlivým schématem.
  3. **Sloupcově orientované (Column-family / Wide-column):**
     * *Příklady:* Apache Cassandra, Google Bigtable, Apache HBase.
     * *Model:* Tabulka se skládá z řádků identifikovaných řádkovým klíčem, data jsou na disku fyzicky uspořádána po **rodinách sloupců (column families)**.
     * *Využití:* Analytika velkých objemů dat, časové řady (IoT metriky), logování, masivní škálovatelný zápis.
  4. **Grafové databáze (Graph Databases):**
     * *Příklady:* Neo4j.
     * *Model:* Labeled Property Graph (LPG) – uzly (nodes), orientované hrany (relationships) a vlastnosti (properties v klíč-hodnota).
     * *Index-free adjacency:* Každý uzel drží přímé paměťové ukazatele na sousední hrany $\implies$ průchod grafem je $O(1)$ na hranu bez drahých tabulkových spojení (JOINů).
     * *Využití:* Sociální sítě, doporučovací systémy, detekce finančních podvodů, znalostní grafy. Dotazovací jazyk **Cypher** (`MATCH (u:User)-[:FRIEND]->(f) WHERE ... RETURN f`).
* **Princip MapReduce (Distribuované paralelní zpracování):**
  * Programovací model pro paralelní dávkové zpracování masivních dat na klastru (Hadoop MapReduce).
  * **3 základní fáze (plus volitelný Combiner):**
    1. **Map:** Čte vstupní záznamy a generuje množinu mezilehlých dvojic `(klíč, hodnota)`.
    2. **Shuffle & Sort:** Framework automaticky seskupí a seřadí všechny hodnoty se stejným mezilehlým klíčem a rozešle je na příslušné uzly.
    3. **Reduce:** Zpracuje klíč a iterátor všech hodnot příslušejících k tomuto klíči a zapíše finální výsledek do distribuovaného filesystému (HDFS).
    * *(Volitelný krok Combiner):* Lokální „Mini-Reducer“ běžící přímo na mapovacím stroji, který mezivýsledky agreguje ještě před odesláním po síti (např. lokální mezisoučet slov), čímž dramaticky šetří síťové pásmo.
  * *Příklad: Počítání slov (WordCount) v pseudokódu:*
    ```text
    // 1. Fáze Map (spouští se paralelně pro každý blok textu):
    function map(document_id, text_content):
        for each word in tokenize(text_content):
            emit_intermediate(word.toLower(), 1)

    // 2. Fáze Shuffle (automaticky zajistí framework):
    // seskupí výstupy do dvojic: (word, [1, 1, 1, 1, ...])

    // 3. Fáze Reduce (spouští se pro každý unikátní klíč):
    function reduce(word, list_of_counts):
        int total_sum = 0
        for each count in list_of_counts:
            total_sum += count
        emit(word, total_sum)
    ```
  * *Výhody:* Automatické rozdělení práce, odolnost proti výpadku uzlu (fault-tolerance – při pádu uzlu se daný Map/Reduce spustí jinde), data locality (kód se posílá k datům).
  * *Nevýhody:* Zápis mezivýsledků na disk (vysoká I/O režie), nevhodné pro iterativní algoritmy (nahrazeno Apache Sparkem, který drží data v RAM).
  * *Alternativy k MapReduce:* **Apache Spark** (In-Memory DAG, mezivýsledky v RAM přes RDD $\implies$ 10–100× rychlejší u iterací), **Apache Flink / Kafka Streams** (proudové real-time zpracování po událostech, okna), **Google Pregel / Apache Giraph** (grafový model BSP – *„Think like a vertex“*), **Trino / Presto** (rychlé distribuované SQL nad Data Lake).

* **NoSQL – Vlastnosti, výhody/nevýhody a srovnání modelů na příkladu e-shopu:**
  * *Vlastnosti:* Horizontální škálovatelnost (scale-out, sharding), flexibilní schéma (*schema-on-read*), denormalizace (agregáty pospolu bez JOINů), model BASE místo ACID.
  * *Výhody:* Obrovská propustnost čtení/zápisu, snadné škálování na komoditním HW, agilní úpravy struktur.
  * *Nevýhody:* Ztráta plného ACID (transakce jen nad 1 dokumentem/klíčem), absence jednotného SQL, integrita dat se přenáší do aplikace, redundance dat.
  * *Srovnání modelů (E-shop: Zákazník Jan, Objednávka 101, Položky: 2× Kniha Algoritmy):*
    * **Relační (SQL):** 4 tabulky spojené cizími klíči $\implies$ detail objednávky vyžaduje **3× `JOIN`**.
    * **Klíč – hodnota (Key-Value):** Klíč `order:101` $\to$ hodnota je serializovaný JSON blob v $O(1)$; nelze se ptát dovnitř na produkt bez skenu všech klíčů.
    * **Dokumentové:** Jeden JSON dokument v `orders` s vnořeným polem položek $\implies$ **sekundární index na `items.product_id`** umožní bleskový dotaz na produkt v $O(\log N)$.
    * **Sloupcové (Wide-Column):** RowKey = `CustomerID`, sloupce = `OrderID_101` $\implies$ historie zákazníka leží na disku souvisle, bleskové čtení.
    * **Grafové:** Uzly `(:Customer)` a `(:Product)` propojené přes `(:Order)` hranami `[:ORDERED]` a `[:CONTAINS]` $\implies$ doporučovací dotazy bez JOINů.

* **Grafové databáze – Datový model a 4 třídy grafových dotazů:**
  * *Datový model LPG (Labeled Property Graph):* Uzly (entity se štítky), orientované typované hrany a vlastnosti (klíč-hodnota) na uzlech i hranách.
  * *Index-free adjacency:* Každý uzel drží přímé paměťové pointery na sousední hrany $\implies$ průchod hranou je **$O(1)$** nezávisle na celkové velikosti grafu.
  * *Příklad modelu:* `(:User {name: 'Alice'})-[:FRIEND]->(:User)-[:WATCHED {rating: 5}]->(:Movie {title: 'Matrix'})`.
  * *4 třídy grafových dotazů:*
    1. *Dotazy na sousedství (Neighborhood / k-hop):* `MATCH (u:User {name: 'Alice'})-[:FRIEND]->(f)-[:WATCHED]->(m) RETURN m.title`
    2. *Vyhledávání vzorů (Pattern matching):* `MATCH (a:Account)-[:TRANSFER]->(b)-[:TRANSFER]->(c)-[:TRANSFER]->(a) RETURN a,b,c` (detekce cyklů a podvodů)
    3. *Cestové dotazy (Reachability / Path finding):* `MATCH p = shortestPath((a:City {name:'Praha'})-[:ROAD*]-(b:City {name:'Brno'})) RETURN p`
    4. *Globální analytické dotazy:* PageRank (autorita uzlů), detekce komunit (Louvain), Betweenness centrality (úzká hrdla sítě).

* **Multi-model databáze vs. Polystore architektura:**
  * **Multi-model databáze:**
    * *Princip:* Jediný integrovaný databázový stroj nativně podporuje více různých datových modelů současně (např. relační tabulky + JSON dokumenty + grafové vazby).
    * *Příklady:* PostgreSQL (relační tabulky, `JSONB` dokumenty, prostorová data PostGIS), ArangoDB (dokumenty, grafy, klíč-hodnota).
    * *Výhody:* Jednotná správa, společné transakční záruky (ACID napříč modely), žádná duplikace dat, nulová režie na synchronizaci.
  * **Polystore architektura:**
    * *Princip:* Zastřešující middleware vrstva nad několika samostatnými, fyzicky oddělenými heterogenními databázemi (např. systém BigDAWG – relační data v PostgreSQL, grafy v Neo4j, masivní matice ve SciDB).
    * *Výhody:* Každý dílčí dotaz běží na enginu, který je pro daný typ dat hardwarově i algoritmicky nejlépe optimalizovaný.
    * *Nevýhody / Problémy:* Chybí globální transakční podpora (distribuovaný 2-fázový commit je extrémně drahý), vysoká latence při síťovém přenosu a propojování mezivýsledků z různých databází, složitá optimalizace dotazů.

### Datový management
* **Datový model vs. Datový formát vs. Datové schéma:** *Model* = konceptuální rámec (relační, grafový LPG/RDF, hierarchický); *Formát* = syntax/serializace (JSON, XML, CSV, Turtle); *Schéma* = formální integrita a pravidla (XSD, JSON Schema, CSVW, SQL DDL).
* **W3C** – HTML, CSS, XML (XSD, XSLT), RDF, SPARQL, JSON-LD, CSVW, SKOS, DCAT, OWL | **IETF** – TCP/IP, HTTP, URI/URL, JSON (RFC 8259), CSV (RFC 4180) | **OGC** – WKT, GML, GeoSPARQL (prostorová data)

#### XML – Datový dokument (Well-formed a validní vůči schématu níže):
```xml
<?xml version='1.0' encoding='UTF-8'?>
<!-- Well-formed XML: 1 kořen, uzavřené tagy, uvozovky u atributů -->
<knihovna>
  <kniha isbn='978-80-200-0980-7'>
    <nazev>R.U.R.</nazev>
    <rok>1920</rok>
    <autori>
      <autor>Karel Čapek</autor>
    </autori>
  </kniha>
  <kniha isbn='978-80-748-3012-3'>
    <!-- Element rok je nepovinný, vnořených autorů může být více -->
    <nazev>Povídky malostranské</nazev>
    <autori>
      <autor>Jan Neruda</autor>
      <autor>Ilustrátor Neznámý</autor>
    </autori>
  </kniha>
</knihovna>
```

#### XML Schema (XSD) – Definice struktury, kardinality a atributů:
```xml
<?xml version='1.0' encoding='UTF-8'?>
<!-- Kořen schématu s W3C jmenným prostorem xs: -->
<xs:schema xmlns:xs='http://www.w3.org/2001/XMLSchema'>
  <xs:element name='knihovna'>
    <xs:complexType>
      <xs:sequence>
        <!-- maxOccurs='unbounded' = pole/opakování (1..N) -->
        <xs:element name='kniha' maxOccurs='unbounded'>
          <xs:complexType>
            <xs:sequence>
              <!-- Povinný textový element (výchozí minOccurs='1') -->
              <xs:element name='nazev' type='xs:string' />
              <!-- Nepovinný číselný element (0..1) -->
              <xs:element name='rok' type='xs:integer' minOccurs='0' />
              <!-- Vnořený stromový blok autorů -->
              <xs:element name='autori'>
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name='autor' type='xs:string' maxOccurs='unbounded' />
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
            </xs:sequence>
            <!-- Atribut se definuje UVNITŘ complexType, ale AŽ ZA sequence! -->
            <xs:attribute name='isbn' type='xs:string' use='required' />
          </xs:complexType>
        </xs:element>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

#### XSLT – Deklarativní transformace XML do HTML (Šablony, XPath, For-Each):
```xml
<?xml version='1.0' encoding='UTF-8'?>
<!-- Transformační stylesheet s jmenným prostorem xsl: -->
<xsl:stylesheet version='1.0' xmlns:xsl='http://www.w3.org/1999/XSL/Transform'>
  <xsl:output method='html' indent='yes' encoding='UTF-8' />

  <!-- 1. Hlavní šablona: match='/' zachytí kořenový uzel XML dokumentu -->
  <xsl:template match='/'>
    <html>
      <body>
        <h1>Katalog knih</h1>
        <ul>
          <!-- 2. Iterace přes všechny knihy (XPath: knihovna/kniha) -->
          <xsl:for-each select='knihovna/kniha'>
            <li>
              <!-- 3. Relativní XPath: vytažení hodnoty elementu a atributu (@) -->
              <strong><xsl:value-of select='nazev' /></strong>
              (ISBN: <xsl:value-of select='@isbn' />) - 
              <xsl:value-of select='rok' />: 
              <!-- Iterace vnořených autorů -->
              <xsl:for-each select='autori/autor'>
                <span><xsl:value-of select='.' /> </span>
              </xsl:for-each>
            </li>
          </xsl:for-each>
        </ul>
      </body>
    </html>
  </xsl:template>
</xsl:stylesheet>
```

#### JSON – Datový dokument (RFC 8259, striktně dvojité uvozovky):
```json
{
  "id": "ds-42",
  "title": "Katalog knihovny",
  "year": 1920,
  "isPublic": true,
  "authors": ["Karel Čapek"],
  "tags": ["drama", "sci-fi", 100]
}
```

#### JSON Schema – Validace struktury, typů a omezení (Draft 2020-12):
* **Otevřenost vs. Uzavřenost:** JSON Schema je ve výchozím stavu **otevřené** (extra klíče jsou povoleny, dokud není nastaveno `"additionalProperties": false`). XML Schema (XSD) je naopak ve výchozím stavu **uzavřené** (jakýkoliv neznámý tag/atribut způsobí chybu validace).
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "required": ["id", "title", "authors"],
  "properties": {
    "id": { "type": "string", "pattern": "^ds-[0-9]+$" },
    "title": { "type": "string", "minLength": 1 },
    "year": { "type": "integer", "minimum": 1500 },
    "isPublic": { "type": "boolean" },
    "authors": {
      "type": "array",
      "items": { "type": "string" },
      "minItems": 1
    },
    "tags": {
      "type": "array",
      "items": {
        "oneOf": [
          { "type": "string" },
          { "type": "number" }
        ]
      }
    }
  },
  "additionalProperties": false
}
```

#### JSON-LD – Sémantické obohacení JSONu o RDF (@context, @id, @type, Language Maps):
* **Struktura sémantiky:** V `@context` se definuje mapování lokálních klíčů na slovníky/ontologie (určuje význam **predikátů**). V těle JSONu se pak popisuje samotná entita (**subjekt**) přes globální IRI (`@id`), třídu (`@type`) a konkrétní data (**objekty**).
```json
{
  "@context": {
    "dcat": "http://www.w3.org/ns/dcat#",
    "dcterms": "http://purl.org/dc/terms/",
    "foaf": "http://xmlns.com/foaf/0.1/",
    
    "title": {
      "@id": "dcterms:title",
      "@container": "@language"
    },
    "year": "dcterms:issued",
    "authors": {
      "@id": "dcterms:creator",
      "@type": "@id"
    }
  },
  
  "@id": "https://data.mff.cuni.cz/dataset/42",
  "@type": "dcat:Dataset",
  
  "title": {
    "cs": "Katalog knihovny",
    "en": "Library Catalog"
  },
  "year": "1920",
  "authors": [
    "https://data.mff.cuni.cz/person/capek"
  ]
}
```

#### CSV (RFC 4180) a CSVW (JSON-LD metadatové mapování do RDF):
```csv
id,name,age
1234,"Novák, Karel",22
```

```json
{
  "@context": "http://www.w3.org/ns/csvw",
  "url": "studenti.csv",
  "tableSchema": {
    "aboutUrl": "http://example.org/student/{id}",
    "columns": [
      { "name": "id", "suppressOutput": true },
      { "name": "name", "propertyUrl": "http://schema.org/name" },
      { "name": "age", "propertyUrl": "http://schema.org/age", "datatype": "integer" }
    ]
  }
}
```

```turtle
# Výsledné RDF trojice vygenerované z řádku CSV (Subjekt Predikát Objekt .)
<http://example.org/student/1234> <http://schema.org/name> "Novák, Karel" .
<http://example.org/student/1234> <http://schema.org/age>  "22"^^<http://www.w3.org/2001/XMLSchema#integer> .
```

#### RDF a RDF Schema (RDFS) – Třídy, Vlastnosti, Hierarchie a OWA odvozování:
* **Blank Node (`[ ... ]` nebo `_:b1`):** Anonymní uzel bez globálního IRI (vnořený objekt).
* **Vlastnosti na hraně (N-ární vztahy):** V čistém RDF hrany nesmí nést data (na rozdíl od LPG v Neo4j). Pro atributy vztahu (např. platnost od–do) se vytvoří pomocný Blank Node.

```turtle
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .
@prefix ex:   <http://example.org/uni/> .

# 1. Definice tříd a hierarchie (rdfs:subClassOf)
ex:Osoba    rdf:type rdfs:Class .
ex:Profesor rdf:type rdfs:Class ;
            rdfs:subClassOf ex:Osoba .
ex:Student  rdf:type rdfs:Class ;
            rdfs:subClassOf ex:Osoba .
ex:Predmet  rdf:type rdfs:Class .

# 2. Definice vlastnosti s doménou (Subjekt) a oborem hodnot (Objekt)
ex:vyucuje  rdf:type rdf:Property ;
            rdfs:domain ex:Profesor ;
            rdfs:range  ex:Predmet .

# 3. Instance a Open World Assumption (OWA) odvozování:
# Pokud zapíšeme pouze tuto trojici, Reasoner sám odvodí:
# ex:Karel a ex:Profesor . a ex:Matematika a ex:Predmet . (není to SQL constraint!)
ex:Karel ex:vyucuje ex:Matematika .

# 4. Blank Node a N-ární vztahy (vlastnosti na hraně: platnost od-do):
# V čistém RDF hrany nemohou mít vlastnosti -> použijeme anonymní Blank Node [ ... ] s typu ex:Uvazek aby bylo možné se na úvazky dotazovat
ex:Karel ex:vyucujeKurz [
    a          ex:Uvazek ;
    ex:predmet ex:Matematika ;
    ex:od      "2020-10-01"^^xsd:date ;
    ex:do      "2026-06-30"^^xsd:date
] .
```

#### DCAT – Datové katalogy a distribuce (Catalog, Dataset, Distribution, DataService):
* **`dcat:Catalog` (Katalog):** Zastřešující kontejner pro publikované datasety (`dcat:dataset`).
* **`dcat:Dataset` (Datová sada):** Abstraktní logická kolekce dat (autor, téma, licence). Není to fyzický soubor!
* **`dcat:Distribution` (Distribuce):** Konkrétní fyzický soubor ke stažení jedním GET dotazem (`dcterms:format`, `dcat:downloadURL`).
* **`dcat:DataService` (Datová služba / API):** Interaktivní API endpoint (REST, SPARQL) pro dynamický přístup (`dcat:endpointURL`, `dcat:servesDataset`).

```turtle
@prefix dcat:    <http://www.w3.org/ns/dcat#> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix xsd:     <http://www.w3.org/2001/XMLSchema#> .
@prefix ex:      <http://mesto.cz/> .

# 1. Katalog (Zastřešující kontejner)
ex:Katalog a dcat:Catalog ;
    dcterms:title "Katalog otevřených dat města"@cs ;
    dcat:dataset  ex:JizdniRady .

# 2. Datová sada (Logická entita)
ex:JizdniRady a dcat:Dataset ;
    dcterms:title        "Jízdní řády MHD"@cs ;
    dcterms:publisher    <https://mesto.cz/dopravni-podnik> ;
    dcat:distribution    ex:JizdniRadyCSV ;
    dcat:distribution    ex:JizdniRadyAPI .

# 3. Distribuce jako statický soubor ke stažení (Download)
ex:JizdniRadyCSV a dcat:Distribution ;
    dcterms:title    "Jízdní řády v CSV"@cs ;
    dcterms:format   "text/csv" ;
    dcat:downloadURL <https://mesto.cz/data/jizdni_rady.csv> .

# 4. Datová služba / API endpoint pro dynamické dotazování
ex:JizdniRadyAPI a dcat:DataService ;
    dcterms:title      "REST API pro aktuální polohu a řády"@cs ;
    dcat:endpointURL   <https://api.mesto.cz/v1/mhd> ;
    dcat:servesDataset ex:JizdniRady .
```

#### SKOS a Dublin Core (DCMI) – Řízené slovníky, taxonomie a sémantický popis dat:
* **SKOS:** Odlehčená ontologie pro tezaury a hierarchické taxonomie (`skos:Concept`).
  * **Štítky:** `skos:prefLabel` (oficiální název, max 1 na jazyk), `skos:altLabel` (synonyma/zkratky), `skos:hiddenLabel` (překlepy pro vyhledávače).
  * **Vztahy:** `skos:broader` (nadřazený/širší), `skos:narrower` (podřazený/užší), `skos:related` (asociace).
* **Dublin Core (`dcterms:`):** Univerzální administrativní metadata (`title`, `creator`, `publisher`, `issued`, `modified`).
* **Sémantický popis dat:** Odkázáním vlastnosti `dcat:theme` na IRI konceptu namísto volného textu (např. `"Auta"`) umožníme strojové vyhledávání přes synonyma i nadřazené kategorie.

```turtle
@prefix dcat:    <http://www.w3.org/ns/dcat#> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix skos:    <http://www.w3.org/2004/02/skos/core#> .
@prefix xsd:     <http://www.w3.org/2001/XMLSchema#> .
@prefix ex:      <http://mojedata.cz/> .

# 1. Definice SKOS taxonomie (Pojmy, Štítky a Hierarchie)
ex:slovnik/Doprava a skos:Concept ;
    skos:prefLabel "Dopravní prostředek"@cs .

ex:slovnik/Auto a skos:Concept ;
    skos:prefLabel   "Osobní automobil"@cs ;
    skos:altLabel    "Auťák"@cs, "Osobák"@cs ;   # Synonyma
    skos:hiddenLabel "Aotomobil"@cs ;             # Zachycení překlepů
    skos:broader     ex:slovnik/Doprava .        # Hierarchická vazba nahoru

# 2. Sémantický popis datasetu pomocí Dublin Core a napojení na SKOS téma:
ex:RegistrVozidel a dcat:Dataset ;
    dcterms:title     "Registr vozidel ČR"@cs ;
    dcterms:creator   "Ministerstvo dopravy"@cs ;
    dcterms:issued    "2026-08-01"^^xsd:date ;
    dcterms:modified  "2026-08-31"^^xsd:date ;
    # Napojení na SKOS koncept (globální IRI interoperabilita)
    dcat:theme        ex:slovnik/Auto .
```

#### Data Provenance a ontologie PROV-O (Sledování původu a historie dat):
* **Data Provenance (Původ dat):** Záznam o tom, jaká data, jakým procesem a kým byla vytvořena/změněna (auditovatelnost, důvěryhodnost a reprodukovatelnost).
* **PROV-O Trojúhelník (Základní entity a vztahy):**
  * **`prov:Entity`:** Datový artefakt/soubor (`surova_data.csv`, `cista_data.csv`).
  * **`prov:Activity`:** Proces, výpočet nebo transformace v čase (`ex:Agregace`).
  * **`prov:Agent`:** Hybatel zodpovědný za spuštění (člověk, organizace, software: `ex:Alice`).
* **Vztahy (Hrany grafu):**
  * `prov:used` (Aktivita $\to$ Vstupní Entity)
  * `prov:wasGeneratedBy` (Výstupní Entity $\to$ Aktivita)
  * `prov:wasAssociatedWith` (Aktivita $\to$ Agent)
  * `prov:wasDerivedFrom` (Výstupní Entity $\to$ Vstupní Entity, přímá zkratka)
  * `prov:wasAttributedTo` (Entity $\to$ Agent)

```turtle
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .
@prefix ex:   <http://example.org/pipeline/> .

# 1. Entity (Vstupní a výstupní data)
ex:SurovaData a prov:Entity .
ex:CistaData  a prov:Entity ;
    prov:wasGeneratedBy  ex:Agregace ;
    prov:wasDerivedFrom  ex:SurovaData ;
    prov:wasAttributedTo ex:Alice .

# 2. Agent (Zodpovědná osoba / organizace / software)
ex:Alice a prov:Agent ;
    prov:actedOnBehalfOf <https://firma.cz> .

# 3. Aktivita (Proces transformace dat)
ex:Agregace a prov:Activity ;
    prov:used              ex:SurovaData ;
    prov:wasAssociatedWith ex:Alice ;
    prov:startedAtTime     "2026-08-31T10:00:00Z"^^xsd:dateTime ;
    prov:endedAtTime       "2026-08-31T10:05:00Z"^^xsd:dateTime .
```

#### Datový model Wikidata a dotazování (WDQS / SPARQL):
* **Struktura Wikidat (Entity - Property - Statement):**
  * **Položky (Items `wd:Q...`):** Koncepty a reálné objekty grafu (např. `wd:Q42` Douglas Adams, `wd:Q213` ČR).
  * **Vlastnosti (Properties `wdt:P...`):** Typy vztahů a atributů (`wdt:P31` instance of, `wdt:P39` position held, `wdt:P569` date of birth).
  * **Reifikace výroků (Statements):** Protože v čistém RDF hrany nemohou mít vlastnosti (např. Havel byl prezidentem *od 1993 do 2003* s referencí na zdroj), tvrzení se reprezentuje mezilehlým uzlem (**Statement node**). Ten nese samotnou hodnotu (`ps:P...`), **Kvalifikátory** (Qualifiers `pq:P...`, např. platnost od-do) a **Reference** (zdroje tvrzení).
* **Způsob dotazování (SPARQL):**
  * **Truthy prefix `wdt:`:** Přímá zkratka Subjekt $\to$ Objekt (vrací aktuální/preferované tvrzení bez nutnosti reifikace).
  * **Label Service:** `SERVICE wikibase:label { bd:serviceParam wikibase:language "cs,en". }` pro automatické doplnění čitelných štítků (`?osobaLabel`).

```sparql
# Hledání prezidentů ČR (Q1914624) a jejich data narození
SELECT ?osoba ?osobaLabel ?datumNarozeni WHERE {
  # 1. Truthy trojice: osoba má funkci prezidenta ČR
  ?osoba wdt:P39 wd:Q1914624 .
  
  # 2. Volitelné datum narození (záznam se nezahodí, pokud datum chybí)
  OPTIONAL { ?osoba wdt:P569 ?datumNarozeni . }
  
  # 3. Magická služba pro získání lidsky čitelných štítků
  SERVICE wikibase:label { bd:serviceParam wikibase:language "cs,en". }
}
```

#### Procesy zpracování dat, kvalita a typologie metadat:
* **Základní datové operace (Data Operations):**
  * **Data Selection:** Horizontální filtrace záznamů podle podmínky (SQL `WHERE`, např. výběr studentů z Prahy).
  * **Data Projection:** Vertikální výběr konkrétních sloupců/atributů (SQL `SELECT col1, col2`, např. zahození rodného čísla).
  * **Data Summarization:** Agregace a souhrnné statistiky přes skupiny (SQL `GROUP BY` + `AVG`, `SUM`, např. průměrný plat na katedře).
  * **Data Reduction:** Zmenšení fyzického objemu dat při zachování podstaty (vzorkování / *sampling*, clustering, PCA, vyhlazení křivek GPS).
  * **Data Lifting (Zvedání dat):** Transformace nestrukturovaných / relačních dat (CSV, JSON, SQL) do sémantického RDF grafu obohacením o ontologie (CSVW, RML, Tarql). Umožňuje SPARQL dotazování a globální propojitelnost.
  * **Data Lowering (Srážení dat):** Transformace sémantických RDF grafů zpět do plochých formátů (CSV, JSON) pro klasické nástroje (BI, Pandas, ML matice), typicky přes `SPARQL SELECT`.
* **Problém datových sil (Data Silos):** Izolovaná data uvnitř jednotlivých oddělení/aplikací bez možnosti propojení. *Řešení:* Otevřená data, Linked Data, kontrolované slovníky, ontologie a DCAT katalogy.
* **Dimenze datové kvality ("Fitness for use", princip GIGO – Garbage In, Garbage Out):**
  * **Přesnost (Accuracy):** Míra shody dat s reálným stavem (např. rodné číslo neprochází modulo 11, chybná krevní skupina).
  * **Úplnost (Completeness):** Absence chybějících (NULL) hodnot v povinných atributech ($\frac{\text{vyplněné}}{\text{celkem}} \cdot 100\,\%$).
  * **Konzistence (Consistency):** Vzájemná nerozpornost dat napříč atributy či systémy (např. datum propuštění < datum přijetí).
  * **Včasnost (Timeliness):** Aktuálnost dat v momentě rozhodování (např. 15minutové zpoždění burzovních dat ničí jejich hodnotu).
* **Druhy metadat (Data o datech, principy FAIR – Findable, Accessible, Interoperable, Reusable):**
  * **Popisná (Descriptive):** Identifikace a vyhledání zdroje (`dcterms:title`, `creator`, `keywords`, abstrakt).
  * **Strukturální (Structural):** Vnitřní organizace, vazby a sémantika dat (schéma tabulek, počet kapitol, formát a relace).
  * **Administrativní (Administrative):** Správa, licencování, odkaz / URL pro stažení (distribuce), archivace a ochrana (datum vytvoření, práva CC, původ PROV-O).
* **Kontrolované slovníky (Hierarchie sémantické síly – od seznamu po ontologii):**
  1. **Kontrolovaný seznam (Controlled List):** Plochý výčet povolených hodnot bez vztahů (např. dny v týdnu, kódy států).
  2. **Klasifikační schéma (Classification Scheme):** Uspořádání do pevných kategorií pro archivaci/třídění (např. MDT – Mezinárodní desetinné třídění).
  3. **Taxonomie (Taxonomy):** Stromová hierarchie nadřazený/podřazený pojem (vztah rodič–potomek, např. Zvíře $\to$ Savec $\to$ Pes).
  4. **Tezaurus (Thesaurus):** Taxonomie doplněná o synonyma a asociace (`skos:prefLabel`, `altLabel`, `broader`, `related`).
  5. **Ontologie (Ontology):** Nejsilnější formální model s axiomy, pravidly a doménami (`rdfs:domain`/`range`, OWL) umožňující logické odvozování nových faktů (Inference / Reasoner).

#### Grafové databáze a jazyk Cypher (LPG – Labeled Property Graph v Neo4j):
* **Model LPG:** Uzly mají štítky `(:Autor)`, hrany mají směr a typ `[:NAPSAL]`. Obojí může nést **vlastnosti** (properties) ve formě klíč-hodnota.
* **ASCII-art syntaxe:** Uzly v `()`, hrany v `[]` se šipkou `-->` (nebo bez šipky pro obousměrný průchod).
* **Klauzule:** `MATCH` (vzor grafu), `WHERE` (filtry a negace `NOT ()--()`), `RETURN` (výpis), `CREATE` / `MERGE` (vložení/upsert).
* **Variable-Length Path:** `*5` (přesně 5 skoků), `*1..3` (1 až 3 skoky), `*` (tranzitivní uzávěr 1 až $\infty$).
* **Třídy grafových dotazů:**
  1. *Bodové dotazy / Filtry vlastností:* Hledání uzlů/hran splňujících konkrétní hodnoty atributů (`WHERE u.vek > 30`).
  2. *Dotazy na okolí a vzory (Pattern / Subgraph matching):* Vyhledání konkrétní struktury/podgrafu (`MATCH (u)-[:FRIEND]->(v)`).
  3. *Dosažitelnost a cesty (Reachability / Path queries):* Nejkratší cesta mezi dvěma uzly (`shortestPath`), tranzitivní uzávěr (`[:PRITEL*1..3]`).
  4. *Globální analytické dotazy:* Výpočty nad celým grafem – centrálnost (PageRank, Betweenness), detekce komunit (Louvain), komponenty souvislosti.

```cypher
// 1. Vyhledání spoluautorů Dana Browna s vyloučením přátel (negace vztahu)
MATCH (dan:Autor {jmeno: 'Dan Brown'})-[:NAPSAL]->(k:Kniha)<-[:NAPSAL]-(spoluautor:Autor)
WHERE dan <> spoluautor 
  AND NOT (dan)-[:PRITEL]-(spoluautor)
RETURN DISTINCT spoluautor.jmeno, k.nazev;

// 2. Hledání cest s proměnnou délkou (přátelé přes 1 až 3 skoky)
MATCH (a:Autor {jmeno: 'Dan Brown'})-[:PRITEL*1..3]-(znamy:Autor)
RETURN DISTINCT znamy.jmeno;
```

#### Prostorová data (Spatial Data) – CRS a formáty (WKT, GML, GeoJSON, GeoSPARQL):
* **Souřadnicový referenční systém (CRS / SRS):** Matematický model převádějící $(X,Y)$ čísla na reálný zemský geoid/elipsoid. Bez specifikace CRS jsou čísla bezvýznamná.
  * **WGS 84 (EPSG:4326):** Globální GPS standard (zeměpisná šířka / délka ve stupních). Výchozí pro GeoJSON.
  * **Web Mercator (EPSG:3857):** Standard webových map (Google Maps, OSM) v metrech.
  * **S-JTSK (EPSG:5514):** Křovákovo zobrazení pro ČR a SR (katastrální mapy).
* **Základní geometrie OGC:** `Point` (bod), `LineString` (lomená čára / cesta), `Polygon` (uzavřená plocha, vnější obvod + vnitřní díry).

##### A) WKT (Well-Known Text – textový standard OGC, souřadnice odděleny mezerou, body čárkou):
```wkt
POINT(14.42 50.08)
LINESTRING(14.4 50.0, 14.5 50.1, 14.6 50.2)
POLYGON((14.0 50.0, 14.5 50.0, 14.5 50.5, 14.0 50.5, 14.0 50.0))
```

##### B) GeoJSON (RFC 7946 – JSON pro webové mapy, striktně WGS 84, pořadí `[Longitude, Latitude]`):
```json
// 1. Samostatný bod (Point)
{
  "type": "Point",
  "coordinates": [14.4208, 50.0878]
}

// 2. Kompletní objekt (Feature s Polygonem a atributy)
{
  "type": "Feature",
  "geometry": {
    "type": "Polygon",
    "coordinates": [
      [ [14.0, 50.0], [14.5, 50.0], [14.5, 50.5], [14.0, 50.5], [14.0, 50.0] ]
    ]
  },
  "properties": { "name": "Národní park", "area_km2": 150 }
}
```

##### C) GML (Geography Markup Language – XML standard OGC, explicitní `srsName`):
```xml
<!-- 1. Bod (Point se souřadnicí pos) -->
<gml:Point srsName="EPSG:4326" xmlns:gml="http://www.opengis.net/gml">
  <gml:pos>50.0878 14.4208</gml:pos>
</gml:Point>

<!-- 2. Plocha (Polygon s LinearRing a posList) -->
<gml:Polygon srsName="EPSG:4326" xmlns:gml="http://www.opengis.net/gml">
  <gml:exterior>
    <gml:LinearRing>
      <gml:posList>50.0 14.0 50.0 14.5 50.5 14.5 50.5 14.0 50.0 14.0</gml:posList>
    </gml:LinearRing>
  </gml:exterior>
</gml:Polygon>
```

##### D) GeoSPARQL (OGC rozšíření RDF/SPARQL, WKT literál s URI prefixem CRS):
```turtle
@prefix geo:  <http://www.opengis.net/ont/geosparql#> .
@prefix geof: <http://www.opengis.net/def/function/geosparql/> .
@prefix uom:  <http://www.opengis.net/def/uom/OGC/1.0/> .
@prefix ex:   <http://example.org/geo/> .

# Definice prostorového objektu (Feature) s geometrií a explicitním CRS:
ex:Praha a geo:Feature ;
    geo:hasGeometry [
        a geo:Geometry ;
        geo:asWKT "<http://www.opengis.net/def/crs/EPSG/0/4326> POINT(14.4208 50.0878)"^^geo:wktLiteral
    ] .
```

```sparql
# Prostorový dotaz: Nalezení prvků v okruhu 5 km od zadaného bodu
SELECT ?feature WHERE {
  ?feature geo:hasGeometry/geo:asWKT ?geom .
  FILTER(geof:distance(?geom, "POINT(14.42 50.08)"^^geo:wktLiteral, uom:metre) <= 5000)
}
```

#### Komprese dat a Teorie informace (Shannonova věta, RLE, Huffman, LZW, Aritmetika):
* **Informační entropie ($H$) a Shannonova věta o kódování zdrojů:**
  * **Vzorec entropie:** $H(X) = - \sum_{i=1}^n p(x_i) \log_2 p(x_i)$ (střední hodnota informace v bitech na symbol).
  * **Shannonova věta:** Žádný bezztrátový algoritmus nedokáže zakódovat zprávu tak, aby průměrná délka kódového slova byla menší než informační entropie $H(X)$ daného zdroje ($L \ge H(X)$).
* **Čtyři základní kompresní algoritmy:**
  1. **RLE (Run-Length Encoding):** Nahrazuje sekvence opakujících se stejných symbolů dvojicí `(počet, symbol)`, např. `AAAAABBB` $\to$ `5A3B`.
  2. **Huffmanovo kódování (Huffman Coding):** Entropické kódování stavěné **zdola nahoru (Bottom-Up)** slučováním dvou uzlů s nejmenší pravděpodobností do binárního stromu.
  3. **LZW (Lempel-Ziv-Welch):** Nahrazuje opakující se sekvence znaků indexy z **dynamicky budovaného slovníku frází**.
  4. **Aritmetické kódování (Arithmetic Coding):** Nekóduje symboly po jednom, ale celou zprávu namapuje na **jedno reálné číslo** v intervalu $[0, 1)$ postupným zmenšováním podintervalu podle pravděpodobností znaků.
* **Digitální certifikát & PKI (Public Key Infrastructure):** Certifikační autorita (CA) podepisuje veřejný klíč serveru (X.509 certifikát). Asymetrická kryptografie ověří identitu a bezpečně vymění symetrický klíč $\to$ rychlé symetrické šifrování dat (AES).

#### Fyzická organizace tabulek na disku (File Organization):
* **Logická tabulka vs. Fyzický soubor:** Logická tabulka v SQL je na disku (úložný stroj / Storage Engine) uložena jako soubor rozřezaný na bloky/stránky (Pages, např. 4–16 KB).
* **3 základní teoretické přístupy:**
  1. **Hromada (Heap File):** Řádky se sypou na konec posledního bloku bez řazení. Rychlý `INSERT` ($\mathcal{O}(1)$), pomalý `SELECT` (Full Table Scan $\mathcal{O}(N)$). Vyžaduje **hustý (dense) index** (odkaz na každý řádek / `TID`).
  2. **Sekvenční / Tříděný soubor (Sorted File):** Řádky jsou v blocích fyzicky seřazeny podle klíče. Rychlý `SELECT` (binární půlení $\mathcal{O}(\log N)$, range scan), drahý `INSERT`/`DELETE` ($\mathcal{O}(N)$ kvůli posouvání). Stačí **řídký (sparse) index** (1 ukazatel na blok).
  3. **Index-sekvenční soubor (ISAM):** Tříděná data s řídkým indexem a bloky přetečení (Overflow blocks). Odstranil posouvání, ale trpí degradací řetězců přetečení (nutnost offline reorganizace).
* **Co se používá v moderní praxi (2 hlavní tábory):**
  * **Tábor A – Heap File + B+ strom indexy (PostgreSQL, Oracle):** Data tabulky jsou v hromadě, každý řádek má diskovou adresu **TID (Tuple ID: blok + slot)**. Všechny indexy jsou samostatné **husté sekundární B+ stromy** ukazující na toto TID.
  * **Tábor B – Klusterovaný B+ strom (MySQL InnoDB, SQLite, MS SQL):** Samotná tabulka **JE** fyzicky jedním velkým B+ stromem (Index-Organized Table). Celá data řádků leží přímo v **listech B+ stromu** seřazená podle primárního klíče.
* **Indexování – Primární vs. Sekundární, Přímé vs. Nepřímé:**
  * **Primární index:** Vytvořený nad uspořádávacím klíčem souboru (může být řídký / *sparse*). **Sekundární index:** Nad jiným sloupcem (musí být hustý / *dense*).
  * **Přímé indexování (Direct):** Listový záznam indexu obsahuje přímo fyzickou adresu řádku na disku (`TID = blok + slot`, např. PostgreSQL). Rychlý skok na data, ale reorganizace tabulky nutí přepsat všechny indexy.
  * **Nepřímé indexování (Indirect):** List sekundárního indexu obsahuje hodnotu primárního klíče `PK` (např. MySQL InnoDB). Přesun řádku na disku nerozbije sekundární indexy, ale vyžaduje dohledání v primárním B+ stromu (*Bookmark Lookup*).

#### Dynamické hashování na vnější paměti (Fagin, Cormack, Larson & Kalja):
* **Faginovo rozšiřitelné hashování (Extendible Hashing – doporučená volba na papír):**
  * **Struktura:** Adresář v RAM velikosti $2^G$ s **Globální hloubkou ($G$)** a datové kbelíky na disku s kapacitou $B$ a **Lokální hloubkou ($L \le G$)**. Klíče se adresují binárním prefixem/suffixem hash kódu délky $G$.
  * **Pravidla štěpení při přeplnění kbelíku:**
    * **Případ A ($L < G$):** Kbelík se rozštěpí na dva s $L \to L+1$, data se přerozdělí podle $(L+1)$-tého bitu hashe, ukazatele v adresáři se přenastaví. **Adresář se nezvětšuje.**
    * **Případ B ($L = G$):** Adresář se **zdvojnásobí** ($G \to G+1$, každý původní slot se zdvojí), přeplněný kbelík se rozštěpí s $L \to L+1$ a adresář ukáže na nový kbelík.
  * **Složitost:** Zaručuje vyhledání na **1 diskový přístup** (pokud je adresář v RAM).
* **Alternativní přístupy (adresář neroste):**
  * **Cormack:** Adresář má pevnou velikost a ukazuje na souvislé oblasti bloků (**Chunky**). Při přeplnění se na disku alokuje větší chunk a najde se nová lokální hashovací funkce $h_i(x)$, která prvky rozptýlí do bloků v chunku bez kolizí (perfektní hashování).
  * **Larson & Kalja:** Řeší kolize pomocí bitových signatur záznamů a **tabulky separátorů držené trvale v RAM** (jedno malé číslo pro každý kbelík), čímž zjišťuje správný blok (primární vs. přetečení) ještě před sáhnutím na disk.

#### Hierarchické indexy (B-strom, B+ strom, B* strom):
* **B-strom (neredundantní):** $m$-árnost (řád $m$) udává **maximální počet potomků** uzlu $\implies$ uzel pojme maximálně **$m - 1$ klíčů** (při $m$ klíčích přeteče) a vnitřní uzel má minimálně $\lceil m/2 \rceil$ potomků. Každý klíč se v celém stromu vyskytuje **právě jednou** (data/ukazatele jsou v listech i vnitřních uzlech).
  * *Štěpení při přetečení ($m$ klíčů):* Medián **stoupá do rodiče a ze spodního patra ZMIZÍ**.
  * *Podtečení při mazání ($< \lceil m/2 \rceil - 1$ klíčů):* 
    1. **Rotace/výpůjčka:** Klíč od souseda jde do rodiče a dělící klíč z rodiče sjede do podtečeného uzlu.
    2. **Slití (Merge):** Dva uzly se sloučí a dělící klíč z rodiče **se stáhne dolů mezi ně**.
* **B+ strom (redundantní – standard pro SQL DB):** Všechna data leží **pouze v listech** propojených obousměrným spojovým seznamem (Linked List). Vnitřní uzly nesou jen navigační rozcestníky (kopie klíčů).
  * *Vkládání:* Při rozdělení listu medián **stoupá do rodiče a ZŮSTÁVÁ i dole v listu**.
  * *Konvence ($\le$ vlevo, $>$ vpravo):* Počátek intervalu najdeme vlevo a pak jednoduše čteme doprava přes spojový seznam listů.
  * *Mazání:* Smazaný klíč zmizí z listu, ale **ve vnitřních navigačních uzlech ZŮSTÁVÁ** (slouží jen jako rozcestník).
  * *Podtečení listu:* Při výpůjčce se v rodiči **jen upraví navigační hodnota**; při slití listů se navigační klíč v rodiči **smaže**.
* **B\*-strom (neredundantní, s odloženým štěpením při vkládání):** V původní definici (D. Knuth) je **neredundantní** (data v uzlech i listech bez duplikací). Při přetečení přelévá přebytečná data do volného souseda přes rodiče (přesný opak výpůjčky při podtečení); teprve když jsou oba sourozenci plní, štěpí 2 uzly na 3 (garance zaplnění $2/3 \approx 66\,\%$).

#### Výpočet pater a kapacity hierarchického indexu (Zkouškový vzorec):
* **Parametry:** $N$ záznamů celkem, kapacita indexového bloku $B$ položek (např. 64), kapacita datového bloku tabulky $D$ řádků (např. 10).
* **1. Hustý index (Dense – pro netříděný soubor / Heap):**
  * Index adresuje **každý jednotlivý záznam**:
  * 1. patro (listy): $L_1 = \lceil N / B \rceil$ bloků.
  * 2. patro: $L_2 = \lceil L_1 / B \rceil$ bloků $\dots$ až $L_k = 1$ (kořen).
  * *Příklad ($N=8192, B=64$):* $L_1 = 8192/64 = 128$ bloků $\to L_2 = 128/64 = 2$ bloky $\to L_3 = \lceil 2/64 \rceil = 1$ blok (kořen). **Výška = 3 patra.**
* **2. Řídký index (Sparse – pro tříděný soubor / Sorted File):**
  * Index adresuje **pouze datové bloky tabulky** ($K = \lceil N / D \rceil$ bloků dat):

#### Prostorové indexování (SFC, Quad-tree, k-d tree, R-strom):
* **Křivky vyplňující prostor (SFC – Z-křivka, Hilbert):** Redukují 2D/3D bod $[x, y]$ na **1D kód** pro uložení do klasického $B^+$ stromu.
  * **Z-křivka (Mortonův kód):** Střídavé prokládání bitů souřadnic ($Z = y_1 x_1 y_2 x_2 \dots$ pro tvar Z). Rychlé na CPU, ale trpí *skokovými anomáliemi* (roztrhané intervaly a False Positives).
  * **Hilbertova křivka:** Rotuje tvar 'U' $\implies$ dokonalé shlukování (málo 1D intervalů i False Positives), ale dražší výpočet na CPU.
* **Point Quad-tree (pro 2D body):** Každý uzel dělí prostor na **4 kvadranty** (NW, NE, SW, SE) křížem procházejícím daným bodem. *Nevýhoda:* Tvar závisí na pořadí vkládání (není vyvážený $\implies$ v nejhorším $\mathcal{O}(N)$).
* **k-d tree ($k$-dimenzionální strom pro body):** Binární strom, kde se v každém patře **cyklicky střídá dělící osa** (kořen dělí podle $X$, patro 1 podle $Y$, patro 2 podle $X\dots$). Dělící nadrovina prochází přímo bodem v uzlu.
* **R-strom (pro plochy a polygony):** Výškově vyvážený strom, data jsou **pouze v listech**, vnitřní uzly drží **MBR obálky**. MBR se mohou **překrývat (Overlap)** $\implies$ dotaz může prohledávat více větví současně.
  * *Guttmanovo štěpení při přetečení ($M+1$ objektů, $\mathcal{O}(M^2)$):*
    1. **PickSeeds:** Vybere 2 objekty s největším mrtvým prostorem jako základ skupin $G_1, G_2$.
    2. **PickNext:** Ze zbývajících vybere prvek s **maximálním rozdílem plošných nárůstů** $|\Delta Area_1 - \Delta Area_2|$ a přiřadí ho do skupiny s menším $\Delta Area$.
    3. **Minimální zaplnění ($m \approx 30\%\text{--}40\% M$):** Nižší limit než u B-stromu dává geometrickou volnost tvořit kompaktnější MBR s menším překryvem.
* **Varianty R-stromu (R+ vs. R\*):**
  * **R+ strom:** Zákaz překryvu MBR $\implies$ objekty na hranicích se **rozsekávají a duplikují** do více listů (garance $\mathcal{O}(\log_m N)$ pro bodové dotazy, ale růst paměti).
  * **R\* strom:** Standard v DB (PostGIS). Povoluje překryv, ale minimalizuje jej (plocha, překryv, obvod) + **Forced Re-insert** (při přeplnění vyjme $30\,\%$ okrajových prvků a znovu je vloží od kořene $\implies$ často předejde štěpení).
* **Prostorové spojení (Spatial Join – např. silnice protínající řeky):**
  * Naivní spojení je $\mathcal{O}(N \times M)$ (drahé na CPU).
  * **Filter & Refine:** 1. *Filter* (rychlé porovnání MBR např. pomocí **Plane-Sweep** v $\mathcal{O}(N \log N)$ nebo **synchronního průchodu dvěma R-stromy** s ořezáváním neprotínajících se větví) $\implies$ 2. *Refine* (přesný geometrický výpočet polygonů pouze nad kandidáty).

### Web
#### Serverové PHP – Backend API, Front Controller a Databázové JSON Endpointy:
```php
<?php
// 1. Spuštění serverové relace
session_start();

// 2. Front Controller – určení požadované akce (routing)
// Pozor: V $_GET jsou vždy parametry z URL adresy (Query Stringu),
// a to i když je samotný HTTP dotaz typu POST, PUT či DELETE!
$action = $_GET['action'] ?? 'home';

// A) REST JSON Endpoint pro příjem dat (POST s JSON tělem)
if ($action === 'create_item') {
    // Proč php://input? Pokud klient posílá Content-Type: application/json,
    // superglobální pole $_POST zůstane zcela prázdné!
    $rawInput = file_get_contents('php://input');
    $data = json_decode($rawInput, true);

    if (!$data || !isset($data['name'])) {
        http_response_code(400); // 400 Bad Request
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Neplatný JSON vstup']);
        exit;
    }
    http_response_code(201); // 201 Created
    header('Content-Type: application/json; charset=utf-8');
    echo json_encode(['status' => 'created', 'id' => 42]);
    exit;
}

// B) Databázový dotaz (GET) se sanitizací a ošetřením chyb (Zkouškový vzor)
if ($action === 'get_dataset') {
    /* filter_input(INPUT_GET, 'title') vs. $_GET['title']:
       - filter_input vrátí null bez varování 'Undefined array key', pokud klíč v URL chybí.
       - Čte přímo původní request nezávisle na případných mutacích superglobálního pole.
       - Umožňuje snadnou aplikaci typových filtrů (např. FILTER_VALIDATE_INT). */
    $title = filter_input(INPUT_GET, 'title');

    if ($title === null || trim($title) === '') {
        http_response_code(400); // 400 Bad Request
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Chybí povinný parametr title']);
        exit;
    }

    try {
        // 1. Připojení a Prepared Statement přes PDO (SQL Injection ochrana)
        $pdo = new PDO('mysql:host=localhost;dbname=katalog;charset=utf8', 'user', 'pass');
        $stmt = $pdo->prepare('SELECT id, title, format FROM dataset WHERE title = :title LIMIT 1');
        $stmt->execute(['title' => $title]);
        $dataset = $stmt->fetch(PDO::FETCH_ASSOC);
        $pdo = null; // Uzavření spojení

        /* Alternativa v mysqli:
        $mysqli = new mysqli('localhost', 'user', 'pass', 'katalog');
        $stmt = $mysqli->prepare('SELECT id, title, format FROM dataset WHERE title = ? LIMIT 1');
        $stmt->bind_param('s', $title);
        $stmt->execute();
        $dataset = $stmt->get_result()->fetch_assoc();
        $stmt->close();
        $mysqli->close(); // Uzavření spojení */

        // 2. Ošetření neexistence záznamu (404 Not Found)
        if (!$dataset) {
            http_response_code(404);
            header('Content-Type: application/json; charset=utf-8');
            echo json_encode(['error' => 'Datová sada nenalezena']);
            exit;
        }

        // 3. Úspěšná odpověď (200 OK)
        http_response_code(200);
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode($dataset);

    } catch (Exception $e) {
        // 4. Systémová chyba serveru (500 Internal Server Error)
        http_response_code(500);
        header('Content-Type: application/json; charset=utf-8');
        echo json_encode(['error' => 'Interní chyba serveru']);
    }
    exit;
}
?>
```

#### PHP Interleaving, HTML5 formulář, XSS a Anti-CSRF token:
```php
<?php
// Generování náhodného Anti-CSRF tokenu do Session
if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));
}

// Zpracování POST požadavku a ověření CSRF tokenu
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    if (!hash_equals($_SESSION['csrf_token'], $_POST['csrf_token'] ?? '')) {
        http_response_code(403);
        die('Neplatný CSRF token!');
    }
    // Uložení do DB a bezpečné přesměrování podle PRG vzoru:
    $_SESSION['flash'] = 'Úspěšně uloženo!';
    header('Location: formular.php');
    exit;
}
?>

<!-- PŘEPNUTÍ DO HTML ŠABLONY (INTERLEAVING) -->
<!DOCTYPE html>
<html lang='cs'>
<body>
  <?php if (!empty($_SESSION['flash'])): ?>
    <p class='msg'><?= htmlspecialchars($_SESSION['flash']) ?></p>
    <?php unset($_SESSION['flash']); // Flash message po zobrazení smažeme ?>
  <?php endif; ?>

  <!-- HTML5 nativní validační omezení (required, email, pattern, min/max) -->
  <form action='formular.php' method='POST'>
    <!-- Skrytý Anti-CSRF token v těle formuláře -->
    <input type='hidden' name='csrf_token' value='<?= htmlspecialchars($_SESSION['csrf_token']) ?>'>

    <label for='inp_email'>E-mail:</label>
    <input type='email' id='inp_email' name='email' required placeholder='jmeno@domena.cz'>

    <label for='inp_login'>Login (5–10 písmen):</label>
    <input type='text' id='inp_login' name='login' required pattern='[a-z]{5,10}'>

    <label for='inp_age'>Věk:</label>
    <input type='number' id='inp_age' name='age' min='18' max='99'>

    <button type='submit'>Odeslat</button>
  </form>

  <!-- Alternativní syntaxe řídicích struktur a XSS ochrana (htmlspecialchars) -->
  <?php if (!empty($clanky)): ?>
    <ul>
      <?php foreach ($clanky as $clanek): ?>
        <li><?= htmlspecialchars($clanek['title']) ?> (<?= htmlspecialchars($clanek['author']) ?>)</li>
      <?php endforeach; ?>
    </ul>
  <?php else: ?>
    <p>Zatím nebyly vydány žádné články.</p>
  <?php endif; ?>
</body>
</html>
```


#### Klientský JavaScript – Události, Asynchronní Fetch (Guard zámek) a Bezpečný DOM:

**1. Odeslání formuláře (submit), FormData, Async/Await a renderování:**
```javascript
// 1. Hledání prvků v DOMu
const form = document.getElementById('searchForm');
const resultsList = document.querySelector('#results');
let isFetching = false; // Zámek (Guard) proti data races při zběsilém klikání

// 2. Event 'submit' na formuláři (zachytí klik i klávesu Enter)
form.addEventListener('submit', async (e) => {
  e.preventDefault(); // Zabrání výchozímu odeslání a znovunačtení stránky

  if (isFetching) return;
  isFetching = true;

  try {
    // 3. Asynchronní POST request s FormData (automaticky zabalí vstupy)
    const response = await fetch('/api/search', {
      method: 'POST',
      body: new FormData(form)
    });
    if (!response.ok) throw new Error('HTTP status: ' + response.status);

    const items = await response.json(); // Druhý await pro JSON tělo

    // 4. Bezpečná manipulace s DOMem (XSS ochrana)
    resultsList.textContent = ''; // Vyčištění starých položek
    items.forEach(item => {
      const li = document.createElement('li');
      li.textContent = item.title; // textContent = klientská obdoba htmlspecialchars (nikdy ne innerHTML!)
      resultsList.appendChild(li);
    });
  } catch (err) {
    console.error('Chyba sítě/API:', err);
  } finally {
    isFetching = false; // Odemčení zámku VŽDY v bloku finally
  }
});
```

**2. Obsluha tlačítka (click), DELETE dotaz, Event Delegation a přesun v DOMu:**
```javascript
const activeList = document.getElementById('activeList');
const doneList = document.getElementById('doneList');

// Event Delegation: Posluchač je pověšený na rodiči activeList (událost click probublá nahoru).
// Jakmile položku přesuneme do doneList, bublání na activeList automaticky přestane fungovat!
activeList.addEventListener('click', async (e) => {
  // closest('.delete-btn'): Hledá předka směrem NAHORU od kliknutého prvku (e.target).
  // Spolehlivě zachytí klik, i když uživatel klikl na vnořenou ikonku uvnitř tlačítka (např. <i> či <span>).
  const btn = e.target.closest('.delete-btn');
  if (!btn) return;
  
  // Robustní vyhledání nadřazeného <li> bez ohledu na hloubku zanoření (lepší než parentElement)
  const item = btn.closest('li');
  const id = item.dataset.id;

  const res = await fetch(`/api/items/${id}`, { method: 'DELETE' });
  if (res.ok) {
    // appendChild(): Každý DOM prvek smí mít v jeden okamžik POUZE 1 rodiče!
    // Předání existujícího uzlu ho automaticky 'vytrhne' z activeList a přesune do doneList (není nutné volat removeChild).
    // (Pokud bychom chtěli prvek duplikovat místo přesunu, použije se item.cloneNode(true)).
    doneList.appendChild(item);
    // nebo pro úplné smazání ze stránky: item.remove();
  }
});
```

#### OpenAPI (Swagger) – Definice endpointu v YAML:
* **Ukázka cesty s parametrem a odpovědí 200 ($ref model):**
```yaml
paths:
  /api/users/{userId}:
    get:
      summary: 'Detail uživatele'
      parameters:
        - name: userId
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: 'Úspěch'
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/User'
        '404':
          description: 'Nenalezeno'
```

#### GraphQL – Princip, Dotaz (Query) a JSON Odpověď:
* **Princip:** Řeší *Over-fetching* (přebírání nechtěných polí) i *Under-fetching* (nutnost vícenásobných HTTP dotazů pro vazby). Má jediný endpoint (`POST /graphql`).
* **Zápis dotazu (Query):**
```graphql
query {
  produkt(id: 42) {
    nazev
    recenze {
      hodnoceni
    }
  }
}
```
* **Odpověď serveru:** Vždy obalena v kořenovém klíči `"data"` a kopíruje hierarchii:
```json
{
  "data": {
    "produkt": {
      "nazev": "Horská kola",
      "recenze": [
        { "hodnoceni": 5 },
        { "hodnoceni": 4 }
      ]
    }
  }
}
```

#### CSS – Syntaxe, Specificita a Responzivita:
* **Syntaxe & Vložení:** `selektor { vlastnost: hodnota; }` | Externí `<link>` (cacheable, doporučeno), Interní `<style>`, Inline `style="..."`.
* **Specificita `(a, b, c, d)`:** Inline (1000) > `#id` (100) > `.trida`, `[attr]`, `:pseudo` (10) > `tag`, `::pseudo` (1). `!important` přebíjí vše; při rovnosti vyhrává pravidlo zapsané v CSS později.
* **Responzivní layout (CSS Grid + Flexbox):**
  * *Desktop:* `display: grid; grid-template-areas: "header header" "sidebar main" "footer footer"; grid-template-columns: 240px 1fr;`
  * *Mobil (Media Query):* `@media (max-width: 768px) { .layout { grid-template-areas: "header" "main" "sidebar" "footer"; grid-template-columns: 1fr; } }`
  * *Menu:* `display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center;`

#### Webové architektury – Front Controller, MVC, MVP, MVVM:
* **Front Controller:** Centrální vstupní bod (`index.php`) – routing na kontrolery, autentizace, session, logging.
* **MVC:** *Model* (data a business logika), *View* (HTML/JSON prezentace), *Controller* (přijme HTTP request, volá Model, předává data do View).
* **MVP:** View je pasivní rozhraní (*Passive View*); *Presenter* řídí veškerou komunikaci oboustranně (ideální pro unit testy UI).
* **MVVM:** *ViewModel* (stav a příkazy pro UI), *Data Binding* (automatická obousměrná synchronizace Modelu a DOMu bez psaní event listenerů).

#### Klientský JavaScript, Web API a Event Loop:
* **Web API:** DOM (`querySelector`, `addEventListener`, `closest`), `fetch()`, History API (`pushState`, `onpopstate` pro klientský routing), Web Storage (`localStorage` perzistentní vs. `sessionStorage` na tab – obojí v JS zranitelné vůči XSS).
* **Event Loop smyčka:**
  $$\text{Call Stack} \to \text{Microtask Queue (Promises, async/await – vyčerpá se CELÁ)} \to \text{Macrotask Queue (1 úloha: setTimeout, I/O, event)} \to \text{UI Render}$$

#### REST API a Richardsonův model zralosti (L0–L3):
* **6 principů RESTu:** Client-Server, Stateless (server nedrží stav relace), Cacheable (`ETag`, `Cache-Control`), Uniform Interface, Layered System, Code on Demand.
* **Richardson Maturity Model:**
  * *Level 0:* POX / RPC (jedno URI, jediná metoda `POST`).
  * *Level 1:* Resources (samostatná URI pro entity: `/users`, `/users/42`).
  * *Level 2:* HTTP Slovesa & Statusy (`GET` safe/idempotentní, `POST` vytvoření `201`, `PUT` kompletní přepis/idempotentní, `PATCH` částečný, `DELETE` idempotentní `204`; statusy 2xx, 4xx, 5xx).
  * *Level 3:* HATEOAS (hypertextové odkazy `_links` v odpovědi dynamicky řídí dostupné přechody stavu aplikace).

#### Single-Page Aplikace (SPA), Stav a CGI / PHP-FPM:
* **SPA:** Server pošle 1 prázdný `index.html` + JS bundle. Klientský routing přes History API. **Nutný Fallback routing na serveru:** neznámé URL musí vrátit `index.html` (`try_files $uri /index.html`).
* **Správa stavu:** In-memory (store), URL parametry (query), Web Storage, Cookies (`HttpOnly` = ochrana proti XSS krádeži, `SameSite=Strict/Lax` = ochrana proti CSRF), JWT tokeny v `Authorization: Bearer`.
* **CGI vs. FastCGI / PHP-FPM:**
  * *CGI:* Nový proces OS (`fork()`) pro každý HTTP request; parametry v ENV, data na `stdin`, výstup na `stdout` $\implies$ obrovská režie.
  * *FastCGI (PHP-FPM):* Persistentní pool workerů na pozadí, komunikace přes Unix/TCP socket $\implies$ nulová režie na start, sdílená mezipaměť kódu (OPcache).

#### Webová bezpečnost a OWASP Top 10:
* **HTTPS / TLS:** Asymetrická kryptografie ověří certifikát CA a bezpečně vymění klíč $\to$ symetrické šifrování (AES-GCM) šifruje veškerý aplikační provoz.
* **JWT (JSON Web Token):** `Header.Payload.Signature` (Base64Url). **Payload NENÍ šifrovaný** (jen podepsaný HMAC/RSA pro integritu).
* **OWASP rizika & obrana:**
  * *SQL Injection:* Útok na dotaz $\implies$ **Prepared Statements (PDO)**, nikdy neslepovat SQL řetězce!
  * *XSS (Stored / Reflected / DOM):* Podstrčení škodlivého JS $\implies$ escaping (`htmlspecialchars`, `textContent`), `HttpOnly` cookies, Content-Security-Policy (CSP).
  * *CSRF:* Podvržení požadavku přihlášeného uživatele $\implies$ náhodné **Anti-CSRF tokeny** ve formulářích, `SameSite` cookies.
  * *SSRF:* Zneužití serveru k volání interní sítě $\implies$ whitelist URL, zákaz privátních IP (RFC 1918).
  * *Broken Access Control (IDOR):* Změna ID v URL $\implies$ v DB vždy ověřovat vlastnictví `WHERE id = :id AND user_id = :uid`.

#### Doporučovací systémy (RecSys):
* **Data & Dynamika:** Řídká matice $R \in \mathbb{R}^{|U| \times |I|}$. Feedback: Explicitní (hvězdičky) vs. Implicitní (kliky, nákupy).
* **Cold Start problém:** Nový uživatel (onboarding dotazník, globální top položky) / Nová položka (obsahové doporučování podle popisu/kategorií).
* **Třídy algoritmů:**
  * *Kolaborativní filtrování (CF):* Pouze chování komunity. **User-KNN** (podobní uživatelé), **Item-KNN** (podobná hodnocení položek), **Maticová faktorizace (SVD):** $R \approx P \cdot Q^T$, predikce $\hat{r}_{u,i} = \vec{p}_u \cdot \vec{q}_i^T$.
  * *Content-Based:* Profil položky a uživatele z textových/žánrových příznaků (TF-IDF).
  * *Knowledge-Based:* Explicitní pravidla a ontologie pro zřídkavé nákupy (auta, reality).
* **Evaluace:** Offline (RMSE, nDCG@K, MAP, Precision@K, Recall@K), Online (A/B testing, CTR, konverze), User studies (subjektivní novost a spokojenost).

#### Vyhledávání na webu a v multimédiích:
* **Textové modely:** Booleovský (množiny slov, logické spojky, bez rankingu) vs. Vektorový (VSM s váhami TF-IDF a kosinovou podobností $\cos\theta = \frac{\vec{q} \cdot \vec{d}}{\|\vec{q}\|\|\vec{d}\|}$). Word2Vec: CBOW (z kontextu na středové slovo) vs. Skip-Gram (ze slova na kontext).
* **CLIP (OpenAI):** Dva enkodéry (Image ViT + Text Transformer) trénované kontrastivním učením. Zero-shot vyhledávání obrázků textem: $\operatorname{argmax}_i (\vec{q}_{\text{text}} \cdot \vec{v}_{i,\text{image}})$.
* **Komprese videa:** GOP snímky: **I-snímky** (klíčové, statický JPEG), **P-snímky** (vektory pohybu z minulého snímku), **B-snímky** (obousměrná interpolace z minulosti i budoucnosti $\implies$ max komprese). HEVC: Quad-tree dělení CTU ($64\times 64$ až $8\times 8$).
* **Detekce střihů:** Tvrdý střih (rozdíl barevných histogramů $D(t, t-1) > \tau$ nebo CNN inference) vs. Pozvolný přechod (prolínačka sledovaná v klouzavém okně).

---

#### Pearsonův korelační koeficient (User Bias v UB-KNN):
* **Vzorec:** $sim(u, v) = \frac{\sum_{i \in I_{uv}} (r_{u,i} - \bar{r}_u)(r_{v,i} - \bar{r}_v)}{\sqrt{\sum_{i \in I_{uv}} (r_{u,i} - \bar{r}_u)^2} \cdot \sqrt{\sum_{i \in I_{uv}} (r_{v,i} - \bar{r}_v)^2}}$
* $I_{uv}$ = společně ohodnocené položky, $\bar{r}_u, \bar{r}_v$ = průměrná hodnocení uživatelů (centrace do nuly řeší optimisty/pesimisty).

#### nDCG@K (Normalized Discounted Cumulative Gain):
* **Vzorce:** $DCG@K = \sum_{i=1}^K \frac{rel_i}{\log_2(i + 1)}, \quad nDCG@K = \frac{DCG@K}{iDCG@K}$
* $rel_i$ = stupňovitá relevance (např. 1–5 hvězd, nákup), $\log_2(i+1)$ = logaritmický útlum s rostoucí pozicí, $iDCG$ = ideální DCG (položky seřazeny sestupně od nejlepší).

#### Precision@K a Recall@K (Ranking metriky v RecSys / IR):
* **$\text{Precision@K} = \frac{|\text{Relevantní} \cap \text{Doporučené}_K|}{K}$** (podíl relevantních mezi prvními $K$ položkami).
* **$\text{Recall@K} = \frac{|\text{Relevantní} \cap \text{Doporučené}_K|}{|\text{Všechny Relevantní}|}$** (podíl nalezených relevantních z celé DB).

#### TF-IDF (Váhování termů ve VSM):
* **Vzorec:** $w_{t,d} = TF(t,d) \times IDF(t,D) = f_{t,d} \cdot \log_{10}\left(\frac{N}{df_t}\right)$
* $TF$ = Četnost slova $t$ v dokumentu $d$ (lokální význam).
* $IDF$ = Inverzní frekvence v korpusu ($N$ dokumentů, $df_t$ obsahuje term $t$) $\implies$ vzácná slova mají vysokou váhu.

#### F1-score:
* **Vzorec (Harmonický průměr):** $F_1 = 2 \cdot \frac{P \cdot R}{P + R} = \frac{2 \cdot TP}{2 \cdot TP + FP + FN}$
* Penalizuje extrémní nepoměr mezi Precision ($P = \frac{TP}{TP+FP}$) a Recall ($R = \frac{TP}{TP+FN}$).

#### MAP (Mean Average Precision):
* **Average Precision pro 1 dotaz:** $AP@K = \frac{1}{|R|} \sum_{k=1}^K P@k \cdot rel(k)$
  * **Klíčový princip:** $P@k$ se počítá **pouze na pozicích $k$, kde je skutečně relevantní položka** ($rel(k)=1$). Tyto dílčí přesnosti se sečtou a vydělí počtem všech relevantních položek $|R|$ v databázi pro daný dotaz.
* **Mean AP přes celou sadu dotazů:** $MAP@K = \frac{1}{|Q|} \sum_{q \in Q} AP@K(q)$

#### Hodnocení interaktivních vyhledávacích systémů:
* **Task-based metriky:** *Time to Task Completion* (čas do vyřešení úlohy), *Success Rate* (úspěšnost nalezení cíle).
* **Uživatelská interakce:** Počet dotazů/reformulací dotazu (*query reformulations*), počet kliknutí, *Dwell time* (doba prohlížení výsledku).
* **Relevance Feedback:** Implicitní (prokliky CTR) vs. explicitní (označení relevantních položek $\to$ Rocchio algoritmus úpravy vektoru dotazu). Subjektivní dotazníky použitelnosti (*SUS – System Usability Scale*).

#### PageRank (nenormalizovaný tvar):
$$PR^{(k+1)}(A) = (1 - d) + d \sum_{T_i \to A} \frac{PR^{(k)}(T_i)}{C(T_i)}$$
* Inicializace: $PR^{(0)}(u) = 1$.
* **Kontrolní součet:** Vždy platí $\sum_{u} PR^{(k)}(u) = N$ (lze ověřit výpočet, pokud z mrtvých konců vedou virtuální odkazy na všechny uzly).

#### Podobnostní model a fúze:
* **Formální definice:** Trojice $(O, F, D)$:
  1. **Objekty ($O$):** Původní multimediální data (obrázek, video).
  2. **Deskriptor / Příznakový vektor ($F$):** Matematická reprezentace (např. barevný histogram, CNN embedding).
  3. **Metrika vzdálenosti ($D$):** Funkce $d(x, y) \ge 0$, kde menší číslo značí vyšší podobnost (např. Euklidovská norma $d=\sqrt{\sum (x_i-y_i)^2}$ nebo kosinová vzdálenost $1 - \cos\theta$).
* **Fúze modalit (kombinace textu a obrazu):**
  * **Early Fusion (na úrovni příznaků):** Zřetězení vektorů $[V_{text}, V_{vis}]$ před výpočtem vzdálenosti (hledá křížové vazby, vyžaduje normalizaci, hrozí prokletí dimenzionality).
  * **Late Fusion (na úrovni skóre):** Samostatné vyhodnocení textu a obrazu, následná agregace skóre (např. vážený součet $Score = \alpha \cdot sim_{vis} + (1-\alpha) \cdot sim_{text}$). Robustní a modulární.

#### Multimediální formáty:
* **JPEG:** Ztrátová komprese – 8×8 bloky, **DCT (Diskrétní kosinová transformace)** do frekvenční domény, **kvantizace** (zahození vysokých frekvencí nepostřehnutelných lidským okem), Huffmanovo kódování.
* **MP4:** Multimediální **kontejner (obálka)**, nikoliv kodek. Synchronizovaně balí videostopu (HEVC/H.264), audiostopu (AAC) a titulky.

#### Metrické indexování a filtrování:
* **Filtrování pivotem (Trojúhelníková nerovnost):** Objekt $O_i$ bezpečně odfiltrujeme bez počítání $d(q, O_i)$, pokud $|d(P, q) - d(P, O_i)| > r$ (pro poloměr dotazu $r$).
* **Maticové indexy (např. LAESA):** Tabulka předpočítaných vzdáleností $N \times k$ k fixním pivotům; sekvenční čtení v paměti těží z HW vektorizace (SIMD) bez stromových cache missů.
* **Stromové indexy (např. VP-tree, M-tree):** Hierarchické dělení prostoru na koule/mezikruží kolem lokálních pivotů v uzlech; umožňují prořezávat celé větve (ve vysokých dimenzích však trpí překryvy).
* **Hašované indexy (LSH – Locality-Sensitive Hashing):** Hašovací funkce navržená tak, že podobné vektory padají do stejného bucketu; slouží pro rychlé přibližné vyhledávání (Approximate k-NN).
* **Hybridní indexy (např. PM-tree, M-Index):** Kombinují stromové dělení s maticí pivotů v listech, případně metrický index pro vizuální data s invertovaným indexem pro text.

#### SOM (Self-Organizing Map) – Algoritmus trénování:
* **Princip:** 2D grid neuronů s váhami $W_i$. Unsupervised learning, zachovává topologii, ale **negarantuje 1:1 zaplnění** (vznikají díry / shluky).
```text
Inicializuj váhy W_i náhodně
Opakuj pro náhodný vstupní vektor V:
  1. Najdi BMU = argmin_i δ(V, W_i)  // uzel s nejmenší vzdáleností
  2. Aktualizuj BMU a sousedy: W_i(t+1) = W_i(t) + lr(t) * h_BMU,i(t) * (V(t) - W_i(t))
  3. Postupně snižuj lr(t) a šíři sousedství h(t)
```

#### SSM (Self-Sorting Map) – Cílová funkce a řazení:
* **Princip:** Heuristické přerovnání existujícího gridu. **Garantuje 1:1 přiřazení** (jedna buňka = právě jeden obrázek, ideální pro UI).
* **Cílová funkce (maximalizuje Pearsonovu korelaci mřížkové vzdálenosti a vizuální nepodobnosti):**
$$\operatorname*{arg\,max}_{L} \sum_{s, t \in \Omega} \frac{\left( \|P(L_s) - P(L_t)\| - \bar{P} \right) \left( \delta(s, t) - \bar{\delta} \right)}{\sigma_P \sigma_\delta}$$
* **Řazení v 2D gridu:** Iterativně se prochází mřížka a testuje se všech $4! = 24$ možných permutací sousedních **čtveřic buněk** (swaps). Vybere se permutace, která nejvíce zvýší skóre cílové funkce.
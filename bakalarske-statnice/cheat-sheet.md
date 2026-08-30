# Souhrn na rychlé zopakování před termínem
Už ho udělat se správnými uvozovkami
V poznámkách můžu kouknout na žlutý nebo horší poznámky co jsem si tam nechal, ale to co je tady by mělo stačit

## Matika

### Analýza

### Lingebra

### Grafy

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

### Automaty

### Ads

### Architektury

### Programko

## Web


### Databáze

### Data
* **W3C** – HTML, CSS, XML (XSD, XSLT), RDF, SPARQL, JSON-LD, CSVW, SKOS, DCAT, OWL | **IETF** – TCP/IP, HTTP, URI/URL, JSON (RFC 8259), CSV (RFC 4180) | **OGC** – WKT, GML, GeoSPARQL (prostorová data)

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
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
* **Data Lifting vs. Data Lowering:**
  * **Data Lifting (Zvedání dat):** Transformace nestrukturovaných / relačních dat (CSV, JSON, SQL) do sémantického RDF grafu obohacením o ontologie (CSVW, RML, Tarql). Umožňuje SPARQL dotazování a globální propojitelnost.
  * **Data Lowering (Srážení dat):** Transformace sémantických RDF grafů zpět do plochých formátů (CSV, JSON) pro klasické nástroje (BI, Pandas, ML matice), typicky přes `SPARQL SELECT`.
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

#### Fyzická organizace tabulek na disku (File Organization):
* **Logická tabulka vs. Fyzický soubor:** Logická tabulka v SQL je na disku (úložný stroj / Storage Engine) uložena jako soubor rozřezaný na bloky/stránky (Pages, např. 4–16 KB).
* **3 základní teoretické přístupy:**
  1. **Hromada (Heap File):** Řádky se sypou na konec posledního bloku bez řazení. Rychlý `INSERT` ($\mathcal{O}(1)$), pomalý `SELECT` (Full Table Scan $\mathcal{O}(N)$). Vyžaduje **hustý (dense) index** (odkaz na každý řádek / `TID`).
  2. **Sekvenční / Tříděný soubor (Sorted File):** Řádky jsou v blocích fyzicky seřazeny podle klíče. Rychlý `SELECT` (binární půlení $\mathcal{O}(\log N)$, range scan), drahý `INSERT`/`DELETE` ($\mathcal{O}(N)$ kvůli posouvání). Stačí **řídký (sparse) index** (1 ukazatel na blok).
  3. **Index-sekvenční soubor (ISAM):** Tříděná data s řídkým indexem a bloky přetečení (Overflow blocks). Odstranil posouvání, ale trpí degradací řetězců přetečení (nutnost offline reorganizace).
* **Co se používá v moderní praxi (2 hlavní tábory):**
  * **Tábor A – Heap File + B+ strom indexy (PostgreSQL, Oracle):** Data tabulky jsou v hromadě, každý řádek má diskovou adresu **TID (Tuple ID: blok + slot)**. Všechny indexy jsou samostatné **husté sekundární B+ stromy** ukazující na toto TID.
  * **Tábor B – Klusterovaný B+ strom (MySQL InnoDB, SQLite, MS SQL):** Samotná tabulka **JE** fyzicky jedním velkým B+ stromem (Index-Organized Table). Celá data řádků leží přímo v **listech B+ stromu** seřazená podle primárního klíče.

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
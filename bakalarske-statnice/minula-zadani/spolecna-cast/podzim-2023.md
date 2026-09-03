# Bakalářské zkoušky (příklady otázek) 

2023-09-14 

## **1 Architektura počítačů a operačních systémů (společné okruhy)** 

Mějme následující třídu v pseudokódu: 

- 1 `class LimitedStack {` 

- 2 `public:` 

- 3 `LimitedStack(int md) {` 4 `currentDepth = 0;` 5 `maxDepth = md;` 6 `stack = new int[maxDepth];` 7 `}` 

- 8 

9 `int getDepth() {` 10 `return currentDepth;` 11 `}` 12 13 `bool pushValue(int v) {` 14 `if (currentDepth >= maxDepth)` 15 `return false;` 16 `stack[currentDepth] = v;` 17 `currentDepth++;` 18 `return true;` 19 `}` 20 

- 21 `private:` 

22 `int maxDepth;` 23 `int currentDepth;` 24 `int[] stack;` _`// int *stack; pro C++`_ 25 `};` 

Dále předpokládejme, že máme multiprocesorový systém a program si spustí několik vláken, která budou mít všechna přístup ke sdílené proměnné typu `LimitedStack` . Tato vlákna budou volat podle své potřeby funkce `getDepth` a `pushValue` . 

1. Je možné, že v programu nastane jev zvaný _race condition_ ? Pokud ano, napište rozsahy řádek nebo vyznačte přímo v uvedeném kódu řádky, které představují kritickou sekci. 

2. Je možné, aby nějakým způsobem nastala situace, kdy při volání funkce `pushValue` přeteče zásobník (program se bude pokoušet zapisovat mimo alokované pole)? Zdůvodněte. 

3. Pokud se domníváte, že v uvedeném kódu může nastat race condition, pokuste se tento problém odstranit úpravou programu (včetně možného přidání nějakých nových řádek). 

Kde je to důležité, ve své odpovědi uvažujte jazyk C#, C++ nebo Java (a vaši volbu vyznačte). 

### **Nástin řešení** 

1. Ano, 10 a 14-17. 

1 

2. Ano, T1 i T2 vykonají řadek 14 souběžně. Přečtou shodnou proměnnou `currentDepth` , která má hodnotu `maxDepth` _−_ 1, takže test selže. Následně po testu je T2 plánovačem zastaveno, T1 funkci dokončí a zvětší `currentDepth` . Poté je T2 znovu naplánovano a při zápisu hodnoty použije zvětšený index sahající za pole. 

3. Záleží na jazyku. V Javě triviálně použitím `synchronized` metod. C# buď použije `lock` na nějaký vedlejší objekt nebo se použije `[MethodImpl(MethodImplOptions.Synchronized)]` . C++ použije třeba `Mutex` a buď explicitní `lock` a `unlock` nebo lépe `lock_guard` . Pozor na odemknutí před každým `return` . 

## **2 Zásobníkový automat (společné okruhy)** 

1. Uveďte definici _zásobníkového automatu_ . 

2. Sestrojte zásobníkový automat _A_ , který přijímá právě řetězce _w ∈{a, b}_<sup>_∗_</sup> , které mají více znaků _a_ než _b_ a zároveň počet _a_ je lichý, tj. _L_ ( _A_ ) = _{w | w ∈{a, b}_<sup>_∗_</sup> & _|w|a > |w|b_ & ( _∃k ∈_ N0) _|w|a_ = 2 _k_ + 1 _}._ 

Za částečné řešení se uznává i automat rozpoznávající „více _a_ než _b_ “. 

### **Nástin řešení** 

1. _Zásobníkový automat_ je sedmice ( _Q,_ Σ _,_ Γ _, δ, q_ 0 _, Z_ 0 _, F_ ), kde 

      - _Q_ je konečná množina stavů, 

      - Σ je konečná vstupní abeceda, 

      - Γ je konečná zásobníková abeceda, 

      - _δ_ je přechodová funkce _Q ×_ (Σ _∪{λ}_ ) _×_ Γ _→PF IN_ ( _Q ×_ Γ<sup>_∗_</sup> ), 

      - _q_ 0 _∈ Q_ je počáteční stav, 

      - _Z_ 0 _∈_ Γ je počáteční zásobníkový symbol, 

      - _F ⊆ Q_ je množina přijímacích stavů. 

   - V případě přijímání prázdným zásobníkem bez množiny přijímajících stavů. 

2. Úkol řeší například zásobníkový automat _A_ se třemi stavy: přijímacím _qf_ a _q_ 0, _q_ 1 rozlišujícími sudý a lichý počet _a_ . Přebytečné znaky _a_ resp. _b_ si ukládáme na zásobník, adekvátně odebíráme. Formálně: _A_ = ( _{q_ 0 _, q_ 1 _, qf }, {a, b}, {Z, A, B}, δ, q_ 0 _, Z, {qf }_ ), s přechodovou funkcí _δ_ popsanou grafem 



<!-- Start of picture text -->
b, Z → BZ b, Z → BZ<br>b, B → BB b, B → BB<br>b, A → λ a, Z → AZ b, A → λ<br>a, A → AA<br>a, B → λ<br>start q 0 q 1 qf<br>a, Z → AZ λ, A → A<br>a, A → AA<br>a, B → λ<br><!-- End of picture text -->

## **3 Souvislost grafů (společné okruhy)** 

Mějme graf _G_ na 64 vrcholech, přičemž jeho vrcholy jsou označeny různými šesticemi nul a jedniček. Hrany tvoří: 

- vrcholy, které se liší pouze v první souřadnici, např. 111010 a 011010 (tyto hrany tvoří perfektní párování), 

- vrcholy, které mají první dva znaky totožné, např. 111010 a 110001, a také 

- dvojice vrcholů (111010 _,_ 101100), (101100 _,_ 010110) a (010110 _,_ 111011). 

2 

Jiné dvojice vrcholů spojeny nejsou. 

   1. Vyslovte Mengerovu větu (o vrcholové souvislosti a řezech) včetně formálního zavedení potřebných pojmů. 

   2. Určete, kolik hranově disjunktních cest vede mezi vrcholy 000000 a 111111. 

   3. Nalezněte nejmenší hranový řez a nejmenší vrcholový řez oddělující 000000 a 111111. 

- **4 Geometrická řada (společné okruhy)** 

   1. Definujte geometrickou řadu: řada<sup>�</sup><sup>_∞_</sup> _n_ =0<sup>_an_jegeometrická,právěkdyž</sup><sup>_an_=</sup><sup>_. . ._.</sup> 

   2. Uveďte, jaké součty má geometrická řada (v závislosti na příslušných parametrech). 

   3. Sečtěte řadu<sup><u>4</u></sup> 9<sup>+</sup> 27<sup><u>8</u>+</sup> 81<sup><u>16</u>+ ....Odpověďpřiměřenězdůvodněte.</sup> 

### **Nástin řešení** 

1. ... právě když _an_ = _q_<sup>_n_</sup> pro nějaké reálné číslo _q_ . 

2. Pro _|q| <_ 1 má součet 1 _/_ (1 _− q_ ), pro _q ≥_ 1 má součet + _∞_ a pro _q ≤−_ 1 součet nemá (součet neexistuje). 3. Součet je (2 _/_ 3)<sup>2 �</sup> _n≥_ 0<sup>(2</sup><sup>_/_3)</sup><sup>_n_= (2</sup><sup>_/_3)2</sup><sup>_/_(1</sup><sup>_−_2</sup><sup>_/_3) = 4</sup><sup>_/_3.</sup> 


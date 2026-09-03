# Bakalářské zkoušky (příklady otázek) 

2024-09-03 

## **1 Doplněk regulárního výrazu (společné okruhy)** 

Mějme následující regulární výraz nad abecedou Σ = _{a, b}_ : 

_R_ = (( _a_ + _b_ )( _a_ + _b_ ))<sup>_∗_</sup> _ab_ 

Označme jako _L_ regulární jazyk popsaný výrazem _R_ . 

1. Sestrojte (co nejmenší) _nedeterministický_ konečný automat _A_ rozpoznávající jazyk _L_ . 

2. Pomocí podmnožinové konstrukce převeďte automat _A_ na _deterministický_ konečný automat _B_ . 

3. Z automatu _B_ sestrojte _deterministický_ konečný automat _C_ rozpoznávající _doplněk_ jazyka _L_ . 

Sestrojené automaty _A_ , _B_ a _C_ znázorněte pomocí stavových diagramů. 

### **Nástin řešení** 

1. Nejmenší NFA má 4 stavy: _A_ = ( _{q_ 0 _, q_ 1 _, q_ 2 _, qF }, {a, b}, δA, q_ 0 _, {qF }_ ), kde _δA_ popíšeme stavovým diagramem: 



<!-- Start of picture text -->
a b<br>start q 0 q 2 qF<br>a, b a, b<br>q 1<br><!-- End of picture text -->

2. Výsledkem podmnožinové konstrukce je následující DFA: _B_ = ( _{{q_ 0 _}, {q_ 1 _}, {q_ 1 _, q_ 2 _}, {q_ 0 _, qF }}, {a, b}, δB, q_ 0 _, {{q_ 0 _, qF }}_ ), kde _δB_ popíšeme stavovým diagramem: 



<!-- Start of picture text -->
a b<br>start {q 0 } {q 1 , q 2 } {q 0 , qF }<br>a a<br>a, b b<br>b<br>{q 1 }<br><!-- End of picture text -->

3. Stačí zaměnit přijímající a nepřijímající stavy: 

1 



<!-- Start of picture text -->
a b<br>start {q 0 } {q 1 , q 2 } {q 0 , qF }<br>a a<br>a, b b<br>b<br>e {q 1 } a<br>(Všimněte si, že přechodová funkce automatu B je totální, proto není třeba přidávat FAIL stav.)<br><!-- End of picture text -->

## **2 Reprezentace typů (společné okruhy)** 

1. Představte si, že vyvíjíte integrované vývojové prostředí (IDE). V okně projektu je potřeba zobrazit typy a elementy typů (tj. jejich metody, datové položky, vnitřní/vnořené typy – viz obrázek níže). Ve zvoleném jazyce (Java, C++, C#) navrhněte vhodnou sadu tříd/interfaců, které vám umožní uchovávat informace o typech tak, aby mohly být zobrazeny v okně v IDE. Informace zahrnují alespoň názvy typů, jejich druhy, metody typů a jejich signatury, datové položky a vnitřní/vnořené typy. Navrhněte vaše řešení tak, aby bylo v budoucnu snadno rozšiřitelné. Vytvořte pouze deklarace tříd/interfaců, tj. bez těl jejich metod. 



<!-- Start of picture text -->
© © AClass<br>®* AninnerEnum<br>© * InnerClass1<br>® © aMethodOfinnerClass1(): long<br>® © aFieldOfinnerClass1: boolean<br>® © aMethod1(): void<br>® © aMethod2(int): int<br>® © aField1: int<br>® * aField2: String<br><!-- End of picture text -->

2. Implementujte metodu, která bere jako parametry (i) typ (jak jste jej definovali pro část otázky výše) a (ii) „operaci“. Metoda aplikuje danou operaci na daný typ a všechny elementy typu. Pokud založíte procházení struktury typu na nějakém obecně známém řešení, explicitně toto řešení pojmenujte. Pro operaci použijte vhodný koncept, který nabízí vámi zvolený jazyk. 

3. Napište kód, který zavolá vaší metodu z předchozího bodu. Operace předaná metodě je: „vytiskne název elementu, ale pouze v případě, že element reprezentuje datovou položku nebo typ (včetně vnitřních/vnořených typů)“. 

### **Nástin řešení** 

1. Existuje více správných řešení. Typické řešení je obvyklá hierarchie tříd, např. abstraktní třída Element, a dále pak třídy, které od Element dědí, tj. třída Type, třída Method, třída Field, atd. 

2. Existuje více správných řešení. Průchod strukturou může být založen např. na vzoru „Visitor“, nebo mohou být typy deklarovány jako „sealed“ (pokud to jazyk umožňuje) a průchod používá pattern matching, atd. 

Pro reprezentaci operace lze použít interface nebo funkcionální typ apod. 

3. V závislosti na reprezentaci bude operace definována jako anonymní třída, lambda výraz atd. 

## **3 Integrály a primitivní funkce (společné okruhy)** 

1. Definujte, co je „primitivní funkce“ k dané funkci _f_ na daném otevřeném intervalu _I_ . 

2. Zformulujte pravidlo “per partes” (též známé jako integrování po částech) pro výpočet primitivní funkce. Můžete se pro jednoduchost omezit na situaci, kdy všechny uvažované funkce jsou spojité. 

2 

3. Nechť _P ⊆_ R<sup>2</sup> je oblast roviny ohraničená zdola osou _x_ a shora grafem funkce _f_ ( _x_ ) = _x_ cos( _x_ ) pro _x ∈_ [0 _, π/_ 2]. Formálněji řečeno, _P_ = �( _x, y_ ) _∈_ R<sup>2</sup> ; 0 _≤ x ≤_<sup>_π_</sup> 2<sup>_∧_0</sup><sup>_≤y≤x_cos(</sup><sup>_x_)</sup> � _._ 

Spočítejte plošný obsah oblasti _P_ . 

### **Nástin řešení** 

1. Funkce _F_ je primitivní funkce k funkci _f_ na intervalu _I_ , pokud má _F_ v každém bodě _x ∈ I_ derivaci rovnou _f_ ( _x_ ). 

2. Pravidlo pro integrování per partes říká, že pokud na nějakém intervalu _I_ jsou _f_ a _g_ spojité funkce, _F_ je primitivní funkce k _f_ a _G_ je primitivní funkce ke _g_ , pak na tomto intervalu platí 



3. Hledaný plošný obsah lze vyjádřit pomocí integrálu jako �0 _π/_ 2 _x_ cos( _x_ )d _x_ . Hodnotu integrálu určíme použitím metody per partes pro výpočet určitého integrálu: 



## **4 Barevnost grafů (společné okruhy)** 

1. Definujte, co je barevnost grafu. 

2. Jaké platí omezení pro barevnosti rovinných grafů? 

3. Určete barevnost grafu na obrázku níže. 



### **Nástin řešení** 

- Barevnost grafu je minimální počet barev, kterými lze obarvit vrcholy grafu tak, aby žádné dva sousední vrcholy neměly stejnou barvu. Formálně, dobré obarvení grafu _G k_ barvami je funkce _f_ : _V →{_ 1 _, . . . , k}_ , kde _V_ je množina vrcholů 

3 

grafu, splňující _f_ ( _u_ ) _̸_ = _f_ ( _v_ ) pro každé dva sousední vrcholy _u, v ∈ V_ , a barevnost grafu _χ_ ( _G_ ) je nejmenší _k_ , pro které existuje dobré obarvení _G k_ barvami. 

– Pro rovinné grafy platí, že jejich barevnost je nejvýše 4 a tento odhad je těsný. 

– Barevnost grafu na obrázku je 4. Horní odhad lze nahlédnout buď z věty výše (graf je rovinný), nebo konstruktivně: pro vrcholy s písmeny _a, b, . . . , j_ lze použít barvy v pořadí 4 _,_ 3 _,_ 2 _,_ 1 _,_ 2 _,_ 1 _,_ 4 _,_ 3 _,_ 4 _,_ 3. Dolní odhad vyplývá z toho, že graf na obrázku má jako podgraf 5-cyklus s připojeným univerzálním vrcholem a protože 5-cyklus má barevnost 3, musí mít graf na obrázku barevnost alespoň 4. 


# Bakalářské zkoušky (příklady otázek) 

2025-09-08 

## **1 Třídy složitosti (společné okruhy)** 

1. Definujte _třídy složitosti_ **P** a **NP** . 

2. Definujte _převod_ (redukci) mezi rozhodovacími problémy (jazyky). 

3. Definujte **NP** _-úplnost_ rozhodovacího problému. 

4. Rozhoděte, zda následující problém leží v třídě **NP** , a odpověď zdůvodněte: Je dáno přirozené číslo _x_ zapsané v desítkové soustavě. Existují přirozená čísla _a_ a _b_ taková, že 1 _< a, b < x_ , _x_ = _a · b_ a desítkové zápisy _a_ i _b_ bez počátečních nul jsou stejně dlouhé? 

**Nástin řešení** Definice viz Průvodce labyrintem algoritmů, kapitoly 19.1 a 19.3. Problém leží v třídě **NP** , jako certifikát stačí použít číslo _a_ . Verifikátor pak vypočte _b_ = _x/a_ (pokud by při dělení vyšel zbytek, zamítne) a zkontroluje, že 1 _< a, b < x_ a desítkové zápisy _a_ a _b_ jsou stejně dlouhé. Délka certifikátu je lineární a časová složitost verifikátoru polynomiální, obojí vzhledem k délce vstupu (počtu číslic _x_ ). 

## **2 Ukládání dat v binárním souboru (společné okruhy)** 

Aplikace ukládá svá data do binárního souboru, což je ilustrováno následujícím (částečným) hexadecimálním výpisem: 

```
0000:0006486853534C4C002203E8FC180005..HhSSLL."......
0010:48656C6C6F0005576F726C6400000000Hello..World....
0020:0000002C0000000000001234008801F4...,.......4....
```

Logicky soubor obsahuje _uzly_ . Každý uzel obsahuje stejnou sadu _atributů_ . Typy atributů jsou určeny _hlavičkou_ souboru umístěnou na jeho začátku, která se skládá ze dvou bajtů udávajících počet atributů (v našem příkladu 6), následovaných typy atributů, kódovanými jedním bajtem pro každý atribut, odpovídající tomuto výčtu: 

```
enumAttrType{TUInt16=0x48,TLink=0x4C,TString=0x53,TSInt16=0x68};
```

Vícebajtová čísla uložená v souboru jsou vždy v big-endian pořadí. Bezprostředně za hlavičkou se nachází _kořenový uzel_ . Každý uzel začíná dvěma bajty obsahujícími délku dat uzlu v bajtech (v kořenovém uzlu našeho příkladu 34). Data uzlu obsahují hodnoty atributů, kódované podle typů atributů deklarovaných v hlavičce. Pro typy `TUInt16` a `TSInt16` je atribut uložen jako dva bajty obsahující 16bitové celé číslo bez znaménka nebo se znaménkem (dvojkový doplněk). Atributy typu `TString` jsou ASCII řetězce proměnné délky kódované jako dva bajty určující počet znaků, následované znaky, každý uložený v jednom bajtu. Pro `TLink` je uloženo 8 bajtů obsahujících pozici jiného uzlu v souboru. Částečný výpis ukazuje, že kořenový uzel nese hodnoty `{1000, -1000, "Hello", "World", 0x2C, 0x1234}` . 

Binární soubor je reprezentován třídou `BinaryFile` , která poskytuje následující metodu, jež načte `len` bajtů do bufferu `buf` , začínajícího na absolutní pozici `filepos` v souboru (znaménkové typy se používají kvůli kompatibilitě s Javou): 

```
voidreadBytes(longfilepos,byte[]buf,intlen);//Java,
voidreadBytes(std::int64_tfilepos,unsignedchar*buf,intlen);//C++
```

```
//Java,C#
```

1. Napište deklaraci třídy `Reader` , včetně jejích privátních dat a implementace následujících metod: Konstruktor obdrží otevřený objekt `BinaryFile` jako parametr; okamžitě načte hlavičku. Metoda `attributes` vrací počet atributů. Metoda `getType` vrací typ `i` -tého atributu, číslováno od nuly. Metoda `getRoot` vrací pozici kořenového uzlu. Metoda `readNode` 

1 

vrátí nový objekt `Node` reprezentující uzel uložený na pozici `filepos` . Objekt je vracen odkazem v Java/C#, ale hodnotou v C++. Data uzlu se načítají ze souboru pouze touto funkcí. 

2. Deklarujte a implementujte privátní datové prvky a konstruktor třídy `Node` . Třída má ukládat data uzlu jako pole bajtů, tj. tak, jak jsou uložena v souboru. Navíc má obsahovat strukturu, která umožní lokalizovat libovolný atribut v konstantním čase. Konverze bajtů na celá čísla nebo řetězce se provádí pouze při volání odpovídajících metod `get...` třídy `Node` . 

3. Napište implementaci následujících metod třídy `Node` pro získání hodnoty celočíselných atributů se znaménkem a bez znaménka (16bit), použijte přitom pouze vestavěné operátory zvoleného jazyka: 

```
intgetUInt16(inti);
```

```
intgetSInt16(inti);
```

Každá metoda čte `i` -tý atribut; je odpovědností volajícího zajistit, že volání odpovídá typu atributu. Typ `int` se považuje za dostatečně velký, aby obsahoval rozsah _⟨−_ 32768 _,_ 65535 _⟩_ . 

## **3 Základy analýzy (společné okruhy)** 

Nechť _p ∈_ (0 _,_ + _∞_ ) je kladné reálné číslo. Označme _Up_ rovinný útvar, který je zleva ohraničen přímkou _x_ = _p_ , zprava přímkou _x_ = _p_ + 1, zdola osou _x_ a shora grafem funkce _f_ ( _x_ ) = _x_ + _x_<sup><u>1</u>.Jinýmislovy,</sup> 





2. Existuje v intervalu (0 _,_ 100) nějaká hodnota _p_ , pro kterou má _Up_ obsah větší než 10 000 čtverečních jednotek? 

3. Najděte hodnotu _p ∈_ (0 _,_ + _∞_ ), pro niž obsah _Up_ nabývá svého minima, případně ukažte, že taková hodnota neexistuje. 

### **Nástin řešení** 

1. Označme _u_ ( _p_ ) obsah útvaru _Up_ . Tento obsah je roven integrálu � _pp_ +1 _f_ ( _x_ ) _dx_ . Funkce _f_ ( _x_ ) = _x_ + _x_<sup><u>1</u>má primitivní funkci</sup> _F_ ( _x_ ) =<sup>_<u>x</u>_</sup> 2<sup>2+ ln(</sup><sup>_x_) +</sup><sup>_c_prolibovolné</sup><sup>_c ∈_R.Hledanýobsahjetedyroven</sup> 



2. Zde si stačí všimnout, že funkce _u_ ( _p_ ) má pro _p_ jdoucí k nule zprava limitu + _∞_ , a tedy na libovolném pravém okolí nuly nabývá libovolně velkých hodnot. Pro dostatečně malé _p >_ 0 má tedy _Up_ obsah větší než 10 000 čtverečních jednotek. 

3. Pomocí aritmetiky derivací a pravidel pro derivování složené funkce zjistíme, že funkce _u_ ( _p_ ) má na uvažovaném intervalu (0 _,_ + _∞_ ) derivaci 



2 

_~~<u>√</u>~~_ <u>5</u> Vyřešením kvadratické rovnice zjistíme, že jediné kladné _p_ 0 splňující _u_<sup>_′_</sup> ( _p_ 0) = 0 je _p_ 0 =<sup>_−_</sup><sup><u>1+</u></sup> 2 . Zároveň vidíme, že _u_<sup>_′_</sup> ( _p_ ) je rostoucí funkce – to lze vidět přímo ze vzorce pro _u_<sup>_′_</sup> ( _p_ ), případně výpočtem druhé derivace 



která je pro _p ∈_ (0 _,_ + _∞_ ) zjevně kladná. Z toho plyne, že _u_<sup>_′_</sup> ( _p_ ) je záporná pro _p ∈_ (0 _, p_ 0) a kladná pro _p > p_ 0, a tedy funkce _u_ ( _p_ ) je klesající na intervalu (0 _, p_ 0] a rostoucí na intervalu [ _p_ 0 _,_ + _∞_ ). Funkce _u_ ( _p_ ) tedy v bodě _p_ 0 nabývá své jediné minimum. 

## **4 Binární relace (společné okruhy)** 

1. Definujte podmínky, které musí splňovat binární relace _R_ na neprázdné množině _X_ , aby byla ekvivalencí. Podmínky formulujte pomocí matematických zápisů s použitím logických spojek, kvantifikátorů a podobně. 

2. Pro _X_ = _{a, b, c, d}_ určete, kolik různých ekvivalencí na množině _X_ existuje. 

3. Pro _X_ = _{a, b, c, d}_ najděte příklad binární relace, která je tranzitivní, ale není symetrická ani (slabě) antisymetrická. Zdůvodněte, že nalezená relace má požadované vlastnosti. 

   - (Antisymetrií míníme _∀x, y ∈ X_ : (( _x, y_ ) _∈ R ∧_ ( _y, x_ ) _∈ R_ ) _⇒ x_ = _y_ .) 

### **Nástin řešení** 

1. Ekvivalence je relace, která je 

   - reflexivní _∀x ∈ X_ : ( _x, x_ ) _∈ R_ 

   - symetrická _∀x, y ∈ X_ : ( _x, y_ ) _∈ R ⇒_ ( _y, x_ ) _∈ R_ 

   - tranzitivní _∀x, y, z ∈ R_ : (( _x, y_ ) _∈ R ∨_ ( _y, z_ ) _∈ R_ ) _⇒_ ( _x, z_ ) _∈ R_ 

2. Budeme počítat rozklady _X_ na třídy ekvivalence, rozborem případů dle velikostí rozkladových tříd: jedna třída (velikosti 4) 1x, dvě třídy 1 + 3 4x, 2 + 2 3x, tři třídy (2 + 1 + 1) 6x, čtyři jednoprvkové třídy 1x, celkem 15 možností. 

3. Například _R_ = _{_ ( _a, a_ ) _,_ ( _a, b_ ) _,_ ( _b, a_ ) _,_ ( _b, b_ ) _,_ ( _c, d_ ) _}_ . Tranzitivita rozborem případů (předpoklady splňují volby _x_ = _a, y_ = _b, z_ = _a_ a _x_ = _b, y_ = _a, z_ = _b_ ), volba _x_ = _a, y_ = _b_ porušuje antisymetrii, volba _x_ = _c, y_ = _d_ porušuje symetrii. 


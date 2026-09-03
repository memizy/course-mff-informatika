# **5 Hierarchické indexy (specializace WDOP)** 

1. Definujte datovou strukturu B-strom. 

2. Uvažujte následující neredundantní B-strom stupně 3. Vložte do něj hodnotu 45 a následně smažte hodnotu 9. Nakreslete stav po každé z operací. 

```
|15|23|
/|\
|9|.||17|19||25|40|
```

3. V relačních databázových systémech se ovšem pro indexaci sloupců využívají především B+ stromy. Vysvětlete, jak se liší od B-stromu, a co tyto modifikace v tomto kontextu přinášejí za výhody. 

**Nástin řešení** Odpověď 1. B-stromem stupně _m_ rozumíme strom splňující následující – Kořen má alespoň 2 potomky, pokud není list. – Každý uzel (kromě kořene) má alespoň _⌈m/_ 2 _⌉_ potomků. – Každý uzel má nejvýše _m_ potomků (stupeň). 

B-stromem stupně _m_ rozumíme strom splňující následující podmínky: 

3 

- Každý uzel obsahuje _k −_ 1 klíčů, kde _k_ je počet potomků (tedy počet klíčů = počet potomků – 1). 

– Klíče v uzlu jsou uspořádány vzestupně a rozdělují intervaly hodnot pro podstromy: 

   - klíče v prvním podstromu _<_ první klíč, 

   - klíče mezi _i_ -tým a ( _i_ + 1)-ním potomkem jsou mezi _i_ -tým a ( _i_ + 1)-ním klíčem, 

   - klíče v posledním podstromu _>_ poslední klíč. 

- Všechny listy se nacházejí na stejné úrovni (strom je vyvážený). 

Odpověď 2. Operace 1: `|23|.| / \ |15|.| |40|.| / \ / \ |9|.| |17|19| |25|.| |45|.|` Operace 2: `|23|.| / \ |17|.| |40|.| / \ / \ |15|.| |19|.| |25|.| |45|.|` Odpověď 3. B+ strom: 

- Vnitřní uzly obsahují pouze klíče (ne data). 

- Všechna data jsou uložena až v listech. 

- Listy jsou navíc mezi sebou propojené (lineární seznam). 

– Výhody: rychlejší sekvenční procházení, efektivnější rozsahové dotazy. 

# **6 Moderní databázové systémy (specializace WDOP)** 

Uvažujte následující situaci: Chceme vhodně reprezentovat entity _kniha_ , _autor_ a _vydavatelství_ a vztahy mezi nimi zachycující kde byla kniha vydána, kdo ji napsal a zda jsou dva autoři přátelé. Dále chceme vyhodnocovat např. následující dotaz: "Které knihy napsal Dan Brown s někým, kdo nepatří do jeho přátel?" 

1. Demonstrujte, jak byste taková data reprezentovali v grafové databázi jako např. neo4j, a jak by bylo možné dotaz vyjádřit např. v jazyce Cypher. (Je možné využít i jinou grafovou databázi podobného typu nebo jazyk. Pak specifikujte, o které jde. Není požadována absolutně přesná syntaxe jazyka, ale je třeba demonstrovat správnou znalost jeho základních principů.) 

2. Naznačte (stačí schematicky, ne nutně přímo v jazyce SQL), jak by bylo možné stejnou situaci reprezentovat v tradiční relační databázi. Porovnejte, jak se tyto dva přístupy liší, jaké mají výhody a nevýhody (v tomto případě, popř. i obecně). 

**Nástin řešení** Odpověď 1. Reprezentace: – Uzly: `(Autor {jmeno})` , `(Kniha {nazev})` , `(Vydavatelstvi {nazev})` – Hrany: – `(Autor)-[:NAPSAL]->(Kniha)` 

4 

– `(Kniha)-[:VYDAL]->(Vydavatelstvi)` 

- `(Autor)-[:PRITEL]-(Autor)` 

Dotaz: 

```
MATCH(dan:Autor{jmeno:"DanBrown"})-[:NAPSAL]->(k:Kniha)<-[:NAPSAL]-(spoluautor:Autor)
WHEREdan<>spoluautor
```

```
ANDNOT(dan)-[:PRITEL]-(spoluautor)
RETURNDISTINCTk.nazev;
```

Odpověď 2. 

Reprezentace: 

- **Autor** (id_autor **PK** , jméno) 

- **Vydavatelství** (id_vydavatelstvi **PK** , název) 

- **Kniha** (id_kniha **PK** , název, id_vydavatelstvi **FK →Vydavatelství** ) 

- **Napsal** (id_autor **FK →Autor** , id_kniha **FK →Kniha** , **PK** = (id_autor, id_kniha)) 

- **Přítel** (id_autor1 **FK →Autor** , id_autor2 **FK →Autor** , **PK** = (id_autor1, id_autor2)) 

V relační databázi by se dotaz skládál z několika drahých spojení tabulek. Komplikované by bylo, pokud bychom chtěli vyjádřit např. přátele přátel, nebo obecně rekurzi. Složité je i přidávání nových typů vztahů. 

# **7 Vyhledávání na webu (specializace WDOP)** 

Do databáze dokumentů bylo zaindexováno prvních pět dokumentů. Data byla uložena v podobě matice, kde sloupce reprezentují jednotlivé termy a řádky dokumenty. 

||**A**|**B**|**C**|**D**|**E**|
|---|---|---|---|---|---|
|_D_1|1|0|1|1|0|
|_D_2|**0**|**1**|**1**|**0**|**1**|
|_D_3|**1**|**1**|**1**|**0**|**0**|
|_D_4|0|1|0|1|1|
|_D_5|1|0|1|0|1|



Nad touto databází byly implementovány dvě klientské aplikace. První z nich podporuje boolský model vyhledávání a druhá model vektorový. Uživatel, pro něhož databáze obsahuje dva relevantní dokumenty _D_ 2 a _D_ 3, položil prostřednictvím první aplikace dotaz "A and (B or C)"a prostřednictvím druhé aplikace dotaz "(1, 1, 1, 0, 0)". 

1. Vysvětlete, jak se ve vektorovém modelu vyhodnocuje Kosinová míra podobnosti. Určete, jaká ohodnocení přidělí dokumentům první aplikace, a jaká ohodnocení jim přidělí aplikace druhá, pokud používá právě Kosinovu míru. Jaké dokumenty jednotlivé aplikace vrátí jako odpověď a v jakém pořadí? 

2. Popište, co znamenají pojmy přesnost a úplnost pro vyhodnocení efektivity vyhledávacího modelu a spočtěte je pro odpovědi poskytnuté výše uvedenými aplikacemi pro položené dotazy. 

3. Lze nad těmito zaindexovanými dokumenty prostřednictvím jednotlivých klientských aplikací položit takový dotaz, který by vrátil právě a pouze oba relevantní dokumenty? Pokud ano, jak by dotaz vypadal? Pokud ne, proč? 

## **Nástin řešení** 

1. Kosinova míra podobnosti dvou k-rozměrných vektorů _⃗D_ a _⃗q_ se spočte jako ( _⃗D ·⃗q_ ) _/_ ( _|⃗D| · |⃗q|_ ) =<sup>�</sup><sup>_k_</sup> _n_ =1<sup>(</sup><sup>_Di∗_</sup> _qi_ ) _/_ �� _kn_ =1<sup>_D_</sup> _i_<sup>2</sup><sup>_/_</sup> �� _kn_ =1<sup>_q_</sup> _i_<sup>2.Boolskýmodelohodnotídokumentyvyhovujícípodmíncehodnotou1(true),ostatníhod-</sup> notou false (0). V daném případě budou ohodnocení po řadě 1, 0, 1, 0, 1 a aplikace vrátí dané tři dokumenty v neurčeném pořadí. Vektorový model ohodnotí dokumenty po řadě hodnotami 2 _/√_ 3 _/√_ 3, 2 _/√_ 3 _/√_ 3, 3 _/√_ 3 _/√_ 3, 1 _/√_ 3 _/√_ 3, 2 _/√_ 3 _/√_ 3, tedy hodnotami 2 _/_ 3, 2 _/_ 3, 3 _/_ 3, 1 _/_ 3, 2 _/_ 3. Model vrátí všech pět dokumentů. _D_ 3 bude první, _D_ 4 bude poslední, pořadí ostatních nebude určeno. 

5 

2. Přesnost _P_ se získá jako podíl počtu vrácených relevantních dokumentů a počtu vrácených dokumentů. Uplnost _R_ se získá jako podíl počtu vrácených relevantních dokumentů a počtu všech relevantních dokumentů. První vyjadřuje pravděpodobnost, že vrácený dokument je relevantní, druhá pravděpodobnost, že relevantní dokument je vrácený. V případě Boolského modelu získáme hodnoty _P_ = 1 _/_ 3 a _R_ = 1 _/_ 2. V případě vektorového modelu získáme hodnoty _P_ = 2 _/_ 5 a _R_ = 2 _/_ 2. 

3. V případě Boolského modelu by šlo napsat podmínku například "B and C". V případě vektorového modelu jednička na libovolné pozici do odpovědi zařadí i nějaký nerelevantní dokument. Dotaz “(0, 1, 1, 0, 0)” by vrátil požadované dokumenty na prvních dvou místech, ale nasledované i zbylými dokumenty. 

# **8 Transakční rozvrhy (specializace WDOP)** 

Jsou dány dva transakční rozvrhy _S_ 1 a _S_ 2: 

|_S_1:|_T_1|_T_2|_T_3|
|---|---|---|---|
|1)|_R_(_A_)|||
|2)||_W_(_B_)||
|3)|||_W_(_A_)|
|4)|_R_(_B_)|||
|5)|COMMIT|||
|6)||_R_(_A_)||
|7)||COMMIT||
|8)|||_W_(_B_)|
|9)|||COMMIT|



a 

|_S_2:|_T_1|_T_2|_T_3|
|---|---|---|---|
|1)|_R_(_A_)|||
|2)|_R_(_B_)|||
|3)|COMMIT|||
|4)||_W_(_B_)||
|5)||_R_(_A_)||
|6)||COMMIT||
|7)|||_W_(_A_)|
|8)|||_W_(_B_)|
|9)|||COMMIT|



1. Definujte konfliktovou ekvivalenci rozvrhů a rozhodněte, zda jsou rozvrhy _S_ 1 a _S_ 2 konfliktově uspořádatelné. Své rozhodnutí zdůvodněte. 

2. Je rozvrh _S_ 1 zotavitelný? Své rozhodnutí zdůvodněte. Pokud ne, navrhněte, zda a jak by šel zotavitelným učinit, aniž by se změnilo vzájemné pořadí čtení a zápisů v rozvrhu. 

3. Je zaručeno, že oba rozvrhy _S_ 1 a _S_ 2, pokud by byly spuštěné na stejných datech, povedou ke shodnému výslednému stavu databáze? Své rozhodnutí zdůvodněte. 

## **Nástin řešení** 

1. Dva rozvrhy jsou konfliktově ekvivalentní, pokd v obou všechny dvojice konfliktních operací (stejná proměnná, jiná transakce, ne dvojice čtení) probíhají ve stejném relatviním pořadí. _S_ 1 je konfliktově uspořádatelný. Dvojice operací 1-3, 3-6, 2-4 a 2-8 mají stejné relativní pořadí, jaké by měly v sériovém rozvrhu _T_ 2 _T_ 1 _T_ 3. Lze ukázat i na precedenčním grafu, který nebude obsahovat cykly. Rozvrh _S_ 1 je sám o sobě sériový, a je tedy konfliktově ekvivalentní sám se sebou. 

2. Není. Operace 4 čte nepotvrzenou hodnotu, zapsanou v 2, ale _T_ 1 potvrzuje dříve, než _T_ 2. Podobně čte operace 6 nepotvrzenou hodnotu, zapsanou v 3, ale _T_ 2 potvrzuje dříve, než _T_ 3. Pokud se nemá prohodit pořadí čtení a zápisů v rozvrhu, je potřeba s COMMITem v _T_ 2 počkat, až skončí _T_ 3. S COMMITem v _T_ 1 je třeba počkat, až opožděně skončí _T_ 2. 

6 

3. Není. _S_ 1 je konfliktově ekvivalentní s _T_ 2 _T_ 1 _T_ 3, ale ne s _T_ 1 _T_ 2 _T_ 3. V prvním rozvrhu čte _T_ 1 hodnotu A zapsanou v _T_ 2. Ve druhém čte původní hodnotu v databázi. Zbytek transakce a celkový výsledek tedy může být jiný. 


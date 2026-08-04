# Jaro 2026
## 5 Konceptuální modelování (specializace WDOP)

1. Vysvětlete rozdíl mezi konceptuální, logickou a fyzickou úrovní při návrhu dat. Uveďte pro každou úroveň co je jejím typickým výstupem a kdo ji typicky používá.
2. Navrhněte ER/UML model pro evidenci vládních usnesení: Existují Ministerstva (mají id a název) a Ministři (mají id a jméno). Každé ministerstvo má právě jednoho ministra. Existují Usnesení vlády (mají id, datum a název). Usnesení připravuje jedno nebo více ministerstev. U každé účasti ministerstva na přípravě usnesení evidujeme roli (garant, spoluřešitel). Každé usnesení má právě jedno odpovědné ministerstvo. Navrhněte entity a jejich atributy, vztahy mezi entitami včetně kardinalit a určete, které vztahy mají vlastní atributy.
3. Transformujte navržený konceptuální model do relačního modelu. Uveďte tabulky, atributy, primární a cizí klíče a relevantní omezení. Navrhněte alespoň jednu alternativu pro vybranou část návrhu a vysvětlete, kdy je daná alternativa vhodnější nebo méně vhodná.


## 6 R stromy (specializace WDOP)

1. Definujte R strom a vysvětlete, k čemu se používá.
2. Vysvětlete princip MBR (Minimum Bounding Rectangle), včetně alespoň jedné výhody a jedné nevýhody.
3. Je dán přetečený listový uzel R-stromu s maximální kapacitou M = 4. Vytvořte konkrétní příklad takového uzlu a objektů v něm. Na tomto příkladu vysvětlete, jak tuto situaci řešit pomocí vhodného algoritmu pro rozdělení uzlu R stromu. Vysvětlete, jaký je cíl tohoto algoritmu, a uveďte jeho časovou složitost. (Hodnotu minimální zaplněnosti m zvolte dle vlastního uvážení, ale tuto volbu zdůvodněte.)


## 7 REST API pro streamovací aplikaci (specializace WDOP)

Uvažujte následující webové (REST) API inspirované službou Spotify. Všechny odpovědi jsou ve formátu JSON.

*   `GET /api/me/top/artists`  
    Vrátí pole identifikátorů interpretů, např. `["a1", "a2", "a3"]`
*   `GET /api/artists/{artistId}`  
    Vrátí detail interpreta, např. `{ "id": "a123", "name": "Radiohead", "popularity": 87, "genres": ["alternative","rock"] }`
*   `GET /api/artists/{artistId}/related-artists`  
    Vrátí pole interpretů (objekty), např. `[{ "id": "a9", "name": "Thom Yorke"}, { "id": "a8", "name": "Portishead"}]`
*   `GET /api/artists/{artistId}/top-tracks`  
    Vrátí pole skladeb (objekty) pro daného interpreta, např. `[{ "id": "t1", "name": "Karma Police"}, { "id": "t2", "name": "No Surprises"}]`

1. Vysvětlete, co je to REST API a jaký je význam HTTP metod GET a POST při návrhu webových aplikací.
2. Napište v JavaScriptu (kód poběží ve webovém prohlížeči) funkci, která:
    (a) získá seznam identifikátorů uživatelových top interpretů,  
    (b) pro každý identifikátor stáhne jméno interpreta,  
    (c) vypíše všechna tato jména do HTML elementu ul s id top-artists.  
    Drobné syntaktické chyby namají vliv na hodnocení. Pokud si nejste jistí názvem metody, popište její funkci.
3. Napište samostatnou JavaScriptovou funkci, která:
    (a) dostane jako argument artistId,  
    (b) získá seznam souvisejících interpretů,  
    (c) vypíše jejich jména do HTML elementu ul s id related-artists.  
    Drobné syntaktické chyby nemají vliv na hodnocení. Pokud si nejste jistí názvem metody, popište její funkci.
4. Stručně vysvětlete, jak by bylo možné na základě výše uvedeného API vytvořit jednoduché doporučení dalších skladeb aktuálnímu uživateli. (Popis postačí na úrovni algoritmu, není nutná implementace.)


## 8 Doporučovací systémy (specializace WDOP)

1. Vysvětlete princip fungování user-based k-nearest neighbors (UB-KNN) algoritmu pro kolaborativní filtrování. Uveďte alespoň 2 nevýhody tohoto přístupu.
2. Uvažujte následující matici explicitních hodnocení (vyšší číslo znamená lepší hodnocení, symbol „-“ znamená, že uživatel položku nehodnotil):

| uživatel \ položka | I1 | I2 | I3 | I4 | I5 | I6 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| U0 (cílový) | 5 | 3 | - | - | - | - |
| U1 | 5 | 3 | 5 | 1 | - | - |
| U2 | 4 | - | 4 | 5 | - | - |
| U3 | 1 | 1 | - | 5 | 5 | - |
| U4 | 5 | 4 | - | - | 5 | 1 |

Předpokládejte doporučování pomocí user-based KNN s počtem sousedů k = 2 pro cílového uživatele U0.

(a) Zvolte metriku podobnosti uživatelů¹ a stručně popište, jak se počítá. Určete nejbližší sousedy pro uživatele U0.

¹*V tomto kroku existuje řada akceptovatelných variant. Vyberte libovolnou metriku, která je běžně používaná v referenčních implementacích – případně takovou, jejíž vhodnost dokážete dostatečně vysvětlit.*

(b) Zvolte vhodnou agregační funkci², stručně ji popište a na základě ní určete top-2 itemy, které by měly být uživateli U0 doporučeny.

Pokud používáte běžné heuristiky (např. týkající se zpracování nehodnocených položek, normalizaci hodnocení, vážení sousedů, nebo omezení množiny doporučitelných objektů), uveďte je explicitně.

²*V tomto kroku existuje řada akceptovatelných variant. Vyberte libovolnou agregační funkci, která je běžně používaná v referenčních implementacích – případně takovou, jejíž vhodnost dokážete dostatečně vysvětlit.*

3. Chceme vyhodnotit relevanci výsledného seznamu doporučených objektů, ale nemáme k dispozici živé uživatele, kteří by na ně mohli přímo reagovat – máme pouze historické interakce uživatelů se systémem (hodnocení objektů).
(a) Stručně vysvětlete, jak lze postupovat, tj. popište základní principy offline evaluace.
(b) Uveďte alespoň dvě vhodné metriky relevance doporučení a vysvětlete, co měří.

***

# Soubor ze dne 2025-06-23

## 5 SQL schéma pro datové katalogy (specializace WDOP)

Navrhněte SQL schéma pro reprezentaci datových katalogů na základě DCAT slovníku. Schéma musí obsahovat reprezentaci pro následující entity a jejich vlastnosti:
*   Entita datový katalog (`dcat:Catalog`) s vlastnostmi:
    *   IRI
    *   název (`dct:title`)
    *   datové sady (`dcat:dataset`)
*   Entita datová sada (`dcat:Dataset`) s vlastnostmi:
    *   IRI
    *   název (`dct:title`)
    *   klíčová slova (`dct:keyword`)
    *   distribuce (`dcat:distribution`)
*   Entita distribuce datové sady (`dcat:Distribution`) s vlastnostmi:
    *   IRI
    *   URL pro stažení (`dcat:downloadURL`)
    *   formát (`dcat:format`)
    *   poslední úprava (`dct:modified`)

Při návrhu předpokládejte následující:
*   název je pouze v jednom jazyce,
*   datová sada může mít více klíčových slov,
*   datová sada náleží do právě jednoho katalogu,
*   distribuce náleží do právě jedné datové sady.

Vysvětlete 3. normální formu a zajistěte, aby jí navržené schéma splňovalo.
Napište SQL, které vytvoří uvedené tabulky a vhodná integritní omezení.


## 6 JSON-schéma (specializace WDOP)

Navrhněte JSON schéma pro publikaci dat o datové sadě z databáze v předchozí otázce. Vlastnost „název“ (`dct:title`) bude povinná jak pro datovou sadu, tak pro katalog.


## 7 JSON-LD (specializace WDOP)

Navrhněte JSON-LD kontext a popište úpravu JSON schématu tak, aby bylo možné na data pohlížet jako na RDF reprezentaci entity datové sady (`dcat:Dataset`) obsahující distribuce.


## 8 PHP (specializace WDOP)

Navrhněte kostru implementace PHP skriptu pro obsluhu HTTP GET dotazu pro získání JSON reprezentace datové sady. HTTP GET dotaz obsahuje v URL QUERY části název "title", který je použitý pro získání a vrácení první datové sady s daným názvem. Pokud je datová sada nalezena, PHP skript jí pošle jako odpoveď na požadavek ve formátu JSON. Schéma JSON dokumentu není specifikováno, můžete využít schéma z předchozích otázek.

Obslužte vhodně chybové stavy pomocí HTTP stavových kódů.
Cílem není poskytnout úplnou implementaci, ale popsat její hlavní body.

---

# 2. Soubor (z data 2025-09-08)

## 5 Hierarchické indexy (specializace WDOP)

1. Definujte datovou strukturu B-strom.
2. Uvažujte následující neredundantní B-strom stupně 3. Vložte do něj hodnotu 45 a následně smažte hodnotu 9. Nakreslete stav po každé z operací.
   
   ```text
         |15|23|
        /   |   \
   |9|.|  |17|19|  |25|40|
   ```
   
3. V relačních databázových systémech se ovšem pro indexaci sloupců využívají především B+ stromy. Vysvětlete, jak se liší od B-stromu, a co tyto modifikace v tomto kontextu přinášejí za výhody.


## 6 Moderní databázové systémy (specializace WDOP)

Uvažujte následující situaci: Chceme vhodně reprezentovat entity *kniha*, *autor* a *vydavatelství* a vztahy mezi nimi zachycující kde byla kniha vydána, kdo ji napsal a zda jsou dva autoři přátelé. Dále chceme vyhodnocovat např. následující dotaz: "Které knihy napsal Dan Brown s někým, kdo nepatří do jeho přátel?"

1. Demonstrujte, jak byste taková data reprezentovali v grafové databázi jako např. neo4j, a jak by bylo možné dotaz vyjádřit např. v jazyce Cypher. (Je možné využít i jinou grafovou databázi podobného typu nebo jazyk. Pak specifikujte, o které jde. Není požadována absolutně přesná syntaxe jazyka, ale je třeba demonstrovat správnou znalost jeho základních principů.)
2. Naznačte (stačí schematicky, ne nutně přímo v jazyce SQL), jak by bylo možné stejnou situaci reprezentovat v tradiční relační databázi. Porovnejte, jak se tyto dva přístupy liší, jaké mají výhody a nevýhody (v tomto případě, popř. i obecně).


## 7 Vyhledávání na webu (specializace WDOP)

Do databáze dokumentů bylo zaindexováno prvních pět dokumentů. Data byla uložena v podobě matice, kde sloupce reprezentují jednotlivé termy a řádky dokumenty.

|    | A | B | C | D | E |
|:---|:-:|:-:|:-:|:-:|:-:|
| D1 | 1 | 0 | 1 | 1 | 0 |
| D2 | 0 | 1 | 1 | 0 | 1 |
| D3 | 1 | 1 | 1 | 0 | 0 |
| D4 | 0 | 1 | 0 | 1 | 1 |
| D5 | 1 | 0 | 1 | 0 | 1 |

Nad touto databází byly implementovány dvě klientské aplikace. První z nich podporuje boolský model vyhledávání a druhá model vektorový. Uživatel, pro něhož databáze obsahuje dva relevantní dokumenty D2 a D3, položil prostřednictvím první aplikace dotaz "A and (B or C)" a prostřednictvím druhé aplikace dotaz "(1, 1, 1, 0, 0)".

1. Vysvětlete, jak se ve vektorovém modelu vyhodnocuje Kosinová míra podobnosti. Určete, jaká ohodnocení přidělí dokumentům první aplikace, a jaká ohodnocení jim přidělí aplikace druhá, pokud používá právě Kosinovu míru. Jaké dokumenty jednotlivé aplikace vrátí jako odpověď a v jakém pořadí?
2. Popište, co znamenají pojmy přesnost a úplnost pro vyhodnocení efektivity vyhledávacího modelu a spočtěte je pro odpovědi poskytnuté výše uvedenými aplikacemi pro položené dotazy.
3. Lze nad těmito zaindexovanými dokumenty prostřednictvím jednotlivých klientských aplikací položit takový dotaz, který by vrátil právě a pouze oba relevantní dokumenty? Pokud ano, jak by dotaz vypadal? Pokud ne, proč?


## 8 Transakční rozvrhy (specializace WDOP)

Jsou dány dva transakční rozvrhy $S_1$ a $S_2$:

| $S_1$: | $T_1$ | $T_2$ | $T_3$ |
|:---|:---:|:---:|:---:|
| 1) | R(A) | | |
| 2) | | W(B) | |
| 3) | | | W(A) |
| 4) | R(B) | | |
| 5) | COMMIT | | |
| 6) | | R(A) | |
| 7) | | COMMIT | |
| 8) | | | W(B) |
| 9) | | | COMMIT |

a

| $S_2$: | $T_1$ | $T_2$ | $T_3$ |
|:---|:---:|:---:|:---:|
| 1) | R(A) | | |
| 2) | R(B) | | |
| 3) | COMMIT | | |
| 4) | | W(B) | |
| 5) | | R(A) | |
| 6) | | COMMIT | |
| 7) | | | W(A) |
| 8) | | | W(B) |
| 9) | | | COMMIT |

1. Definujte konfliktovou ekvivalenci rozvrhů a rozhodněte, zda jsou rozvrhy $S_1$ a $S_2$ konfliktově uspořádatelné. Své rozhodnutí zdůvodněte.
2. Je rozvrh $S_1$ zotavitelný? Své rozhodnutí zdůvodněte. Pokud ne, navrhněte, zda a jak by šel zotavitelným učinit, aniž by se změnilo vzájemné pořadí čtení a zápisů v rozvrhu.
3. Je zaručeno, že oba rozvrhy $S_1$ a $S_2$, pokud by byly spuštěné na stejných datech, povedou ke shodnému výslednému stavu databáze? Své rozhodnutí zdůvodněte.

---

# 3. Soubor (z data 2025-02-04)

*Poznámka: Třetí soubor obsahuje odlišné téma pro otázky 5 až 8.*

## 5 SQL (specializace WDOP)

Uvažujte následující situaci: Uživatelé konverzují s ChatBotem. Ke konverzaci můžou přidávat dokumenty, které se v konverzaci využívají. Konverzace pak obsahuje zprávy vložené uživatelem a také zprávy vygenerované ChatBotem.

1. Pomocí jazyka SQL specifikujte příkazy pro vytvoření tabulek `Uzivatel`, `Zprava` a `Dokument`, v nichž jsou ukládána příslušná data. Zajistěte referenční integritu mezi tabulkami.
2. Specifikujte příkazy, které do každé tabulky vloží alespoň jeden záznam. Záznamy se musí vztahovat k jedné konkrétní konverzaci.
3. Specifikujte dotaz, který vrátí počty zpráv dlouhých konverzací. Dlouhou konverzaci definujeme jako konverzaci, která obsahuje alespoň 100 zpráv.
4. Specifikujte příkazy pro smazání tabulek.


## 6 Indexování dat (specializace WDOP)

Do tabulky `Uzivatel` z předchozího příkladu byli postupně vloženi uživatelé s `id_u` = [ 15, 9, 23, 25, 19, 40, 17 ] v tomto pořadí. Následně byl uživatel s `id_u` = 15 smazán.

1. Nakreslete, jak bude vypadat index nad sloupcem `id_u`, který je realizován jako B+ strom, kde maximální počet potomků $m = 3$, po vložení všech záznamů.
2. Nakreslete tentýž index po smazání uvedeného záznamu.
3. Specifikujte, zda se jedná o redundantní nebo neredundantní B-strom a proč.


## 7 Návrh REST API (specializace WDOP)

Popište základní principy a úrovně návrhu REST API. Demonstrujte principy na návrhu REST API pro aplikaci 2. úrovně, ve které uživatelé konverzují s ChatBotem. API musí umožnit pracovat s následujícími zdroji: konverzace, zpráva. Popište, jak by se projevila implementace 3. úrovně.


## 8 Základy šifrování (specializace WDOP)

Popište úlohu a využití public key infrastructure (PKI) certifikátů a šifrování pro implementaci HTTPS. Není třeba jít do implementačních detailů, konkrétního výběru algoritmů nebo struktury certifikátu. Z odpovědi však musí být jasné, jak na sebe jednotlivé pojmy navazují a proč jsou třeba.
***



# Soubor ze dne 2024-09-03

## 5 Jazyk SQL (specializace WDOP)

Uvažujte doménu hudební scény.

1. Napište v jazyce SQL příkazy, které vytvoří tabulky pro reprezentaci zpěváků, kapel a skladeb. Vytvořte alespoň dva atributy pro každou z těchto entit (např. jméno a země původu zpěváka) a použijte vhodné datové typy.
2. Upravte vhodnými SQL příkazy tabulky tak, aby bylo možné ukládat informace o členství zpěváků v kapelách a o interpretech skladeb. Předpokládejte, že každý zpěvák je členem maximálně jedné kapely a každá skladba může mít maximálně jednoho interpreta. Kapela ale může mít více zpěváků a zpěvák může interpretovat více skladeb. Zajistěte referenční integritu.
3. Napište SQL příkaz, který vloží do tabulek zpěváka, který je členem nějaké kapely a interpretuje nějakou skladbu.
4. Napište v SQL dotaz, který vypíše jména všech zpěváků, kteří nejsou členy žádné kapely.
5. Vysvětlete, co dělá následující SQL dotaz (obecně i nad aktuálně vloženými daty):

   ```sql
   SELECT nazev, COUNT(*)
   FROM kapela
   GROUP BY nazev
   HAVING COUNT(*) > 2;
   ```

6. Napište SQL příkazy, které smažou vytvořené tabulky.


## 6 Moderní databázové systémy (specializace WDOP)

Uvažujte problematiku multi-modelových dat a databází.

1. Vysvětlete pojem „multi-modelová data“ a rozdíl mezi multi-model a single-model databázemi. Uveďte příklad.
2. Uveďte alespoň dvě výhody a dvě nevýhody multi-modelových databází oproti tradičním single-model databázím.
3. Pro libovolnou multi-modelovou databázi vytvořte jednoduchý příklad databázového schématu, resp. dat a nad nimi multi-modelový dotaz. Demonstrujte na něm uvedené výhody multi-modelových databází.
4. Vysvětlete rozdíl mezi multi-modelovou databází a polystorem.


## 7 Web (specializace WDOP)

1. Vysvětlete návrhový vzor Front Controller a jeho využití pro vývoj webových aplikací. S pomocí pseudokódu nebo PHP demonstrujte základní myšlenku implementace.
2. Uvažujte následující webové (REST) API:
    *   `GET /api/singer` – vrátí JSON, který je polem identifikátorů zpěváků, například: `["jaroslav-1980", "pavelka-1958"]`
    *   `GET /api/singer/{identifikátor}` – vrátí JSON, který obsahuje jméno zpěváka, například: `{ "name": "Jaroslav" }`
    *   `DELETE /api/singer/{identifikátor}` – smaže zpěváka

    Pro popsané API napište v JavaScriptu, který poběží ve webovém prohlížeči, funkci, která dostane jako argument jméno zpěváka a provede následující kroky:
    1. smaže všechny zpěváky daného jména,
    2. pro každého smazaného zpěváka přidá HTML element li se jménem zpěváka do elementu s id `deleted-list`.

    Pokud si nejste jisti názvem nějaké funkce/proměnné, popište její chování. Výsledný kód může být strukturován do více funkcí, na drobné syntaktické chyby nebude při hodnocení brán zřetel. V kódu nemusíte řešit obsluhu chybových stavů.


## 8 Základy indexování (specializace WDOP)

Pro potřeby této otázky uvažujme databázi vytvořenou v první otázce specializace („Jazyk SQL”).

1. Vysvětlete přímé/nepřímé indexování a primární/sekundární index.
2. Uveďte příklady možného použití přímého primárního, přímého sekundárního a nepřímého sekundárního indexu pro tabulku reprezentující zpěváky (`zpevak`). Jaké jsou výhody a nevýhody použití indexů?
3. Předpokládejme přímé primární indexování sloupce `zpevak.id` (identifikátor zpěváka) pomocí redundantního B-stromu bez odloženého štěpení, stupně 3, tedy 2 hodnoty a 3 ukazatele. Demonstrujte postupné vkládání záznamů s hodnotou klíče: 1, 2, 3, 4, 5, 0.

***

# Soubor ze dne 2024-06-25

## 5 Datový model (specializace DW)

V informačním systému nemocnice je použit následující logický relační datový model, kde podtržením jsou vyznačeny klíče a *italikou* cizí klíče:
*   Diagnóza(**Kód**, Název)
*   Lékař(**RČ**, Jméno, Příjmení, Město, Ulice, Číslo, PSČ, Odbornost, RokyPraxe)
*   Pacient(**RČ**, Jméno, Příjmení, Město, Ulice, Číslo, PSČ, *PraktickýLékařRČ*), PraktickýLékařRČ $\subseteq$ Lékař[RČ]
*   LéčíSe(*RČ*, *Kód*), RČ $\subseteq$ Pacient[RČ], Kód $\subseteq$ Diagnóza[Kód]

1. Znázorněte výše uvedený logický relační datový model pomocí diagramu ve zvoleném konceptuálním jazyce (ER, UML).
2. Pokud je to potřeba, rozšiřte konceptuální model a odpovídající logický relační datový model tak, aby:
    *   každý pacient se mohl léčit na libovolný počet diagnóz,
    *   každý pacient měl právě jednoho praktického a mohl mít libovolný počet dalších lékařů,
    *   každý pacient mohl podstoupit libovolný počet vyšetření v rámci nějaké diagnózy a naopak,
    *   pacient, který je zároveň lékařem, neměl osobní údaje evidovány redundantně.


## 6 Transakce (specializace DW)

Pro následující transakční rozvrh, kde R znamená operaci čtení a W operaci zápisu:

| | $T_1$ | $T_2$ | $T_3$ |
|:-:|:---:|:---:|:---:|
| 1 | W(*Patient*$_1$) | | |
| 2 | | ??? | |
| 3 | | W(*Patient*$_1$) | |
| 4 | | COMMIT | |
| 5 | | | R(*Patient*$_1$) |
| 6 | | | W(*Patient*$_1$) |
| 7 | | | COMMIT |
| 8 | R(*Patient*$_2$) | | |
| 9 | COMMIT | | |

1. Jaká databázová operace čtení/zápisu v transakci $T_2$ v čase 2 místo ??? způsobí, že rozvrh nebude konfliktově uspořádatelný (conflict-serializable)? Své rozhodnutí zdůvodněte.
2. Jaká databázová operace čtení/zápisu v transakci $T_2$ v čase 2 místo ??? způsobí, že rozvrh nebude zotavitelný (recoverable)? Své rozhodnutí zdůvodněte.


## 7 API a skriptování (specializace DW)

1. Navrhněte a popište REST API pro nemocniční systém z dřívější otázky. API musí podporovat následující funkcionalitu:
    *   získání pacientů, jejichž jméno odpovídá query patternu,
    *   získání informací o konkrétním pacientovi,
    *   vytvořit, aktualizovat a zrušit pacienta,
    *   získat seznam diagnóz pacienta,
    *   přidat a odebrat diagnózu pacienta,
    *   získat seznam lékařů pacienta,
    *   získat seznam pacientů, kteří mají aspoň jednu ze zadaných diagnóz (seznam diagnóz může být hodně dlouhý).
2. Mějme webovou aplikaci, která zajišťuje přístup k IS přes navržené API. Napište JavaScript fragment, který po zadání query patternu (první endpoint) a kliknutí na tlačítko vyvolá příslušný HTTP API request, získá všechny pacienty odpovídající dotazu a zobrazí je v seznamu. Když uživatel klikne na konkrétního pacienta ze seznamu získaného prvním dotazem, tak se aktualizuje seznam jeho doktorů a diagnóz získáním dat z API a jejich následným zobrazením.

Předpokládejte, že API vrací data v JSON formátu a tento krátce popište formou příkladu pro každý použitý z endpointů. Předpokládejte existenci funkcí `displayDoctors` a `displayDiagnoses` pro zajištění úpravy DOM stromu. Stejně tak můžete použít funkce `clearDoctors` a `clearDiagnoses`. Dále předpokládejte existenci všech potřebných HTML elementů.

Dbejte na správné využití asynchronního zpracování požadavků. Zajistěte, aby i při nepříznivém souběhu asynchronních volání po načtení seznamu pacientů byl seznam doktorů a diagnóz v konzistentním stavu, tj. zobrazují se seznamy ke zvolenému pacientu a nezobrazují se seznamy v případě, kdy pacient vybrán nebyl. Není třeba řešit chybové stavy fetch operací ani autentikaci.


## 8 Získávání informací (specializace DW)

Uvažujte situaci, kdy je třeba obohatit systém z předchozích otázek tak, aby umožňoval stanovit diagnózu na základě zadaných symptomů. Mějme kolekci dokumentů, kde každý dokument popisuje konkrétní nemoc.

1. Jak by vypadal booleovský model pro danou úlohu? Jaké termy by obsahoval spcializovaný slovník pro danou úlohu? Jak jsou reprezentovány dotazy a dokumenty v booleovském modelu a jak lze dotazování v tomto modelu efektivně implementovat?
2. Řekněme, že chceme systém modifikovat tak, aby dotaz nebyl seznam symptomů, ale přímo zpráva lékařského vyšetření. Jakou modifikaci booleovského modelu je vhodné v takovém případě použít? Jak se změní reprezentace dotazu a dokumentu? Jak bude pak vyhodnocována podobnost mezi dotazem a dokumentem a proč?

***

# Soubor ze dne 2024-02-09

## 5 Databáze SIS-Junior (specializace DW)

Na jedné základní škole v ČR nasadili nový informační systém SIS-Junior pro evidenci žáků a jejich studijní agendy. V seznamu níže jsou uvedeny vybrané tabulky a sloupce, které se týkají dat potřebných pro tisk vysvědčení (uvažujeme tradiční vysvědčení, na kterém jsou předměty a známky, nikoli slovní hodnocení).

*   STUDENT(**id**, first_name:CHAR, last_name:CHAR, born:DATE)
*   CLASS(**id**, label:CHAR, academic_year:INT, school_year:INT{1..9})
*   SUBJECT(**id**, name:CHAR)
*   REPORT_GRADE(*student_id*, *class_id*, *subject_id*, semester:INT{1..2}, grade:INT{1..5})

Sloupce pojmenované id jsou PK (s hodnotou UUID), cizí klíče mají vždy tvar název-tabulky_id. Datové typy jsou naznačeny za názvy položek, u čísel (kde je to podstatné) jsou uvedeny i očekávané rozsahy. Akademický rok se ukládá jako číslo roku, kdy začal (tj. 2023 odpovídá roku 2023/24).

1. Uvedené DB schéma zcela jistě není úplné. Doplňte sloupce a tabulky (včetně popisu jejich sloupců), které nejsou ve výpisu výše, abychom měli úplný popis části schématu odpovídající záměru použití (agenda vysvědčení), především aby bylo možné zcela splnit následující body.
2. Napište SQL dotaz typu SELECT, který vygeneruje podklady pro přípravu vysvědčení na druhé pololetí roku 2023/24 (tj. vypíše všechny platné trojice žák-třída-předmět, ke kterým pak učitelé budou ručně doplňovat známky a ukládat je do REPORT_GRADE).
3. Napište SQL dotaz typu SELECT, který vypíše průměrné známky pro každou unikátní kombinaci předmětu, ročníku studentů a školního roku (známky obou pololetí se průměrují dohromady).


## 6 Databáze diplomových prací (specializace DW)

V rámci návrhu datového modelu aplikace byly na konceptuální úrovni identifikovány dvě datové třídy - *Osoba* a *Diplomová práce*. O osobě je nutné si pamatovat její unikátní číslo osoby, jméno, příjmení a typ (student/učitel). O diplomové práci je potřeba si pamatovat její název, studijní obor, název fakulty. Dále byly identifikovány následující vztahy:
*   Diplomová práce má nejvýše jednoho *řešitele*. Řešitel může mít přidělenu nejvýše jednu práci
*   Diplomová práce má právě jednoho *vedoucího*. Vedoucí může vést libovolný počet prací.

Pro výše popsanou situaci:
1. Načrtněte pro popsanou situaci odpovídající UML model. Nezapomeňte vyznačit kardinality vztahů.
2. Převeďte Vámi navržený UML model na logický relační model. Nezapomeňte vyznačit všechny klíče a referenční integritu (cizí klíče). Převod proveďte tak, aby v cizích klíčích nemusela být nikdy vložena NULL hodnota.
3. Je logický relační model vzniklý převodem UML modelu vhodný z hlediska dosažené normální formy, pokud víte, že v modelované doméně atribut název fakulty funkčně závisí na studijním oboru (tedy *Studijní obor* $\rightarrow$ *Název fakulty*)? Pokud ne, jak by měl být logický relační model upraven, aby vhodný byl a proč?


## 7 Komprese (specializace DW)

Zpráva nad abecedou $\{a, b, c, d, e\}$ je náhodnou veličinou s rozložením pravděpodobností $\{\frac{4}{20}, \frac{3}{20}, \frac{2}{20}, \frac{4}{20}, \frac{7}{20}\}$.

1. Vytvořte odpovídající kódovací strom pro Huffmanovo kódování do binární abecedy $\{0, 1\}$. Sourozence ve stromu řaďte dle (kumulativní) pravděpodobnosti. Následně zakódujte začátek zprávy $cdebea\dots$
2. Nadřízení by si přáli, aby byly zprávy kódovány pomocí následující tabulky:
    $a = 1, b = 10, c = 100, d = 1000, e = 0000$.  
    Vysvětlete, proč použití tohoto způsobu kódování není úplně vhodné.
3. Jaké binární kódování by bylo potřeba použít, aby se délka zpráv co nejvíce blížila entropii zprávy?


## 8 Odeslání webového formuláře (specializace DW)

Mějme HTML formulář v tradiční (CGI-like, tedy bez skriptů na straně klienta) webové aplikaci na přidávání položek do databáze.

```html
<form id="addForm" action="index.php?action=addItem" method="POST">...
```

Skript na straně serveru zpracuje data z formuláře a pokud jsou korektní, přidá nový záznam do databáze. Jako odpověď pak vygeneruje HTML stránku, na které je tabulka se všemi záznamy v databázi.

1. Uživatel vyplnil formulář, odeslal jej na server a zobrazila se mu stránka s aktuální tabulkou všech záznamů (včetně nově přidaného). Co přesně se stane, když uživatel klikne na tlačítko pro znovunačtení stránky (*Refresh*) v prohlížeči? Takové chování zřejmě není zcela žádoucí z pohledu uživatele, navrhněte příslušnou úpravu aplikace (bez použití skriptů na straně klienta).
2. Pokud data odesílaného formuláře nejsou korektní (nelze je uložit), je třeba zobrazit tento formulář znovu a zároveň jej předvyplnit daty, která uživatel zadal (aby je uživatel mohl jen upravit a nemusel zadávat znovu). Jak tuto funkcionalitu zajistit v kombinaci s vaším řešením problému z bodu 1?
3. Jak by bylo možné situaci popsanou v prvním bodě vyřešit, pokud bychom dovolili použít skripty na straně klienta? Načrtněte kostru takového řešení v JavaScriptu, pokud si nejste jisti názvy funkcí nebo událostí z DOM API, doplňte k nim komentář s vysvětlením.

Vaše řešení z bodů 1. a 2. popište pokud možno stručně a strukturovaně (např. formou odrážek), stačí popis pro běžnou situaci (nemusí pokrývat všechny myslitelné speciální případy). Naopak buďte konkrétní v technických detailech, zejména těch, které se týkají ukládání a přenosu dat mezi klientem a serverem (pokud je např. potřeba data od uživatele v bodu 2. dočasně někam uložit, napište kam/jak). Také můžete použít fragmenty PHP kódu, kde je považujete za vhodné.


# Soubor ze dne 2023-09-14

## 5 Databáze (specializace DW)

Je dán následující transakční rozvrh $S$:

| $T_1$ | $T_2$ | $T_3$ |
| :---: | :---: | :---: |
| $R(A)$ | | |
| | $W(B)$ | |
| | | $W(A)$ |
| $W(B)$ | | |
| | $R(A)$ | |
| | | $W(B)$ |
| COMMIT | | |
| | COMMIT | |
| | | COMMIT |

1. Je rozvrh $S$ konfliktově uspořádatelný (conflict–serializable)? Své rozhodnutí vysvětlete.
2. Je rozvrh $S$ zotavitelný? Své rozhodnutí vysvětlete. Pokud ne, bylo by možné zotavitelnosti dosáhnout bez toho, že by se změnilo současné vzájemné pořadí operací $R$ a $W$? Jak?

Do rozvrhu $S$ byly doplněny operace pro uzamykání $L_X$ (exkluzivní zámek) a $L_S$ (sdílený zámek) s cílem získat rozvrh odpovídající požadavkům pro striktní dvoufázový uzamykací protokol (strict 2PL).

| $T_1$ | $T_2$ | $T_3$ |
| :---: | :---: | :---: |
| $L_S(A)\ R(A)$ | | |
| | $L_X(B)\ W(B)$ | |
| | | $L_X(A)\ W(A)$ |
| $L_X(B)\ W(B)$ | | |
| | $L_S(A)\ R(A)$ | |
| | | $L_X(B)\ W(B)$ |
| COMMIT | | |
| | COMMIT | |
| | | COMMIT |

3. Bylo cíle dosaženo? Své rozhodnutí vysvětlete.


## 6 Datový management (specializace DW)

Do netříděného sekvenčního souboru s délkou bloku 4096 B je uloženo 8192 záznamů, každý s pevnou délkou 500 B.

1. Kolik pater bude mít hierarchický index nad sloupcem reprezentujícím klíč jednotlivých záznamů, pokud se do jednoho bloku indexu vejde 64 položek? Jedná se o přímý nebo nepřímý index? Svoje odpovědi zdůvodněte.
2. Jak se odpověď změní (pokud vůbec) v případě, že bude primární soubor uložen jako tříděný sekvenční soubor seřazený podle hodnot klíče? Své rozhodnutí vysvětlete.
3. Popište vkládání hodnot do neredundantního B-stromu s řádem $m$. Znázorněte, jak bude vypadat neredundantní B-strom ($m=3$) po vložení prvků 9, 3, 7, 6, 5 v tomto pořadí.


## 7 Web app: vyhledávání článků (specializace DW)

Mějme webovou aplikaci pro vyhledávání článků. Uživatel má k dispozici textový vstup (input element s ID `searchInput`) a vyhledávací tlačítko (button element s ID `searchButton`). Při stisku tlačítka se uživateli zobrazí všechny články, které obsahují text ze vstupního pole jako podřetězec.

Aplikace používá REST API, z něhož potřebujete dva endpointy:
*   `/api/articles?search=<text-fragment>` vrací články, které obsahují daný řetězec, jako JSON seznam:  
    `[ { "id": <id článku>, "content": <html fragment s obsahem>, "author": <id autora>, ... }, ... ]`
*   `/api/user/<id>` vrací údaje o jednom uživateli jako JSON kolekci:  
    `{ "id": <id uživatele>, "name": <celé jméno>, ... }`

Pro jednoduchost již máte připravené funkce pro úpravu DOM: `clearArticles()` odstraní aktuálně zobrazované články a `addArticle(content, author)` přidá na stránku nový článek od daného autora.

1. Napište fragment JavaScriptu, který zajistí popisovanou funkcionalitu. Tedy při stisku tlačítka se provedou HTTP požadavky na příslušné endpointy z REST API a odpovídajícím způsobem se upraví DOM model (zobrazí se stažené články). Ve vašem řešení máte především demonstrovat práci s asynchronními požadavky (pomocí promises nebo `async`/`await`). Rovněž je nutné zajistit, aby se opakované stisky tlačítka během načítání článků ignorovaly.
2. Naznačte, jak by mohla vypadat implementace funkce `addArticle`. Není třeba psát celý kód, důležité je především nastínit, jak se do stránky vloží HTML fragment z položky `content` zaslané z REST API.

Ve vašem kódu nemusíte řešit okrajové situace (selhání sítě, chyby v datech, apod.). Pokud si nejste jisti přesnými názvy standardních funkcí a metod JS nebo DOM API, doplňte do komentáře, co očekáváte, že daná funkce dělá. Drobné chyby v syntax budou tolerovány.


## 8 Bezpečnostní tokeny (specializace DW)

Webová aplikace používá bezpečnostní tokeny JWT pro interní udržování autentizace (tedy autentizaci HTTP dotazů po té, co se uživatel přihlásil loginem a heslem). Token má hlavičku

```json
{ "alg": "HS256", "typ": "JWT" }
```

kde HS256 je identifikátor metody Hash-Based Message Authentication Code (HMAC) s použitím SHA256 jako hašovací funkce (pro připomenutí: HS256 je výchozí metoda, kterou musí podporovat všechny implementace JWT knihoven, a se kterou se potkáme nejčastěji).

1. Stručně popište (nejlépe algoritmicky pomocí funkcí) jak je zajištěna bezpečnost tohoto typu tokenu — tedy jak probíhá vydání a ověření tokenu bezpečnostní entitou (serverem).
2. Navrhněte, jaké položky musí mít tělo (payload) JWT tokenu, aby plnil autentizační funkci a byly zajištěny základní zásady bezpečnosti. Váš návrh by neměl by obsahovat zbytečné položky (tokeny mají být malé). Jednotlivé položky stručně (jednou větou) vysvětlete/zdůvodněte.
3. Popište dva nejčastější mechanismy pro perzistentní uchování tokenu na straně klienta (tj. v prohlížeči) a stručně porovnejte jejich výhody nevýhody.

***

# Soubor ze dne 2023-06-27

## 19 Architektury databázových systémů (otázka studijního zaměření – 3 body)

Uvažujte tabulky PROJECT a EMPLOYEE se schématy PROJECT(ID, Name, Budget) a EMPLOYEE(ID, Name, Position, Salary, PID), kde PID $\subseteq$ PROJECT.ID.

*   Je uvedené schéma ve 3NF, pokud víte, že firemní politika vyžaduje funkční závislost EMPLOYEE.Position $\rightarrow$ EMPLOYEE.Salary? Pokud ano, zdůvodněte. Pokud ne, upravte schéma, aby bylo ve 3NF.
*   Pro výsledné relační schéma nakreslete ekvivalentní konceptuální model pomocí jezika E-R, případně UML.
*   Napište nad uvedeným schématem v jazyce SQL dotaz, který vrátí seznam projektů i s počty zaměstnanců, kteří na nich pracují.


## 20 Web chat (otázka studijního zaměření – 3 body)

Uvažme jednoduchou webovou aplikaci s přihlašováním, ve které uživatelé sdílejí krátké textové zprávy (chat). Přihlašovací formulář v HTML vypadá přibližně takto:

```html
<form action="?action=login" method="POST">
Login: <input type="text" name="login">
Password: <input type="password" name="password">
<button type="submit">Sign in</button>
</form>
```

Front controller webové aplikace (jeho nejpodstatnější části) vypadají následovně.

```php
if (($_GET['action'] ?? '') === 'login') {
    if (verify_credentials($_POST['login'], $_POST['password'])) {
        $res = $db->query("SELECT id FROM user WHERE login = '" . $_POST['login'] . "'");
        $userId = $res->fetch_column(0);
        if ($userId) setcookie('user', $userId);
    } else {
        showWrongCredentialsError();
    }
    redirectAndExit();
}
// ...
if (empty($_COOKIE['user'])) {
    showLoginForm();
} else {
    showChatMessagesForUser($db, $_COOKIE['user']);
}

// ... v pomocných inkludovaných souborech se také nachází
function showChatMessagesForUser($db, $userId) {
    // ...
    $messages = loadMessagesForUser($db, $userId);
    foreach ($messages as $m) {
        echo "<p>[$m->from]: $m->text</p>";
    }
    // ...
}
```

Může předpokládat, že chybějící části kódu (včetně funkcí) jsou rozumně implementovány (a neobsahují bezpečnostní chyby). Např. proměnná `$db` obsahuje Mysqli objekt reprezentující spojení k databázi, superglobální proměnné nebyly skriptem modifikovány atd.

Identifikujte všechny bezpečnostní chyby ve výše uvedených příkladech. U každé chyby stručně popište možný způsob zneužití (v případě injection útoků uveďte zejména, jaký řetězec by byl injektován) a způsob opravy (načrtněte krátký kód, nebo stručně popište, jaké změny je třeba v kódu provést).

Pokud v kódu žádné zranitelnosti nejsou, popište stručně jeden možný typ injection útoku (na tuto konkrétní aplikaci) a identifikujte bezpečnostní mechanismy v kódu, které tomuto útoku zabrání.


## 21 Přehled SQL (otázka studijního zaměření – 3 body)

Uvažujte tabulky PROJECT a EMPLOYEE se schématy PROJECT(ID, Name, Budget) a EMPLOYEE(ID, Name, Position, PID), kde PID $\subseteq$ PROJECT.ID. Tabulka PROJECT obsahuje záznamy ([1, 'SIS', 500000], [2, 'FIS', 400000], [3, 'CARS', 400000]). Tabulka EMPLOYEE obsahuje záznamy ([1, 'Alex', 'Consultant', 1], [2, 'Peter', 'Programmer', 3], [3, 'John', 'Programmer', 2], [4, 'Paul', 'Designer', 2]).

Zapište výsledek následujících dotazů, v případě chyby v SQL dotazu místo s chybou vyznačte.

1.  Select Min(Budget) From PROJECT
2.  Select Name From EMPLOYEE Inner Join PROJECT On (Name = Name)
3.  Select Name From PROJECT Where Budget = Min(Budget)
4.  Select Name From PROJECT Where ID Not In (Select PID From EMPLOYEE)
5.  Select PID, Count(ID) From EMPLOYEE Where Position='Programmer' Group By PID Having Count(ID) > 1


## 22 Transakční zpracování (otázka studijního zaměření – 3 body)

Uvažujte transakce $T_1$: $W(B)\ W(C)\ \text{COMMIT}$, $T_2$: $R(A)\ W(B)\ \text{COMMIT}$ a $T_3$: $W(A)\ W(C)\ \text{COMMIT}$.

Je rozvrh $S$: $W_3(A)\ R_2(A)\ W_1(B)\ W_2(B)\ W_1(C)\ W_3(C)\ \text{COMMIT}_1\ \text{COMMIT}_2\ \text{COMMIT}_3$ konfliktově uspořádatelný (conflict-serializable)? Pokud ano, uveďte příklad konfliktově ekvivalentního sériového rozvrhu. Pokud ne, vysvětlete proč.

Je rozvrh $S$ zotavitelný (recoverable)? Pokud ano, proč? Pokud ne, jak by bylo potřeba jej upravit, aby zotavitelný byl?

Operace $R$ reprezentuje čtení dané proměnné, operace $W$ reprezentuje její zápis.


## 23 Datové formáty (otázka studijního zaměření – 3 body)

Uvažujme následující JSON-Schéma:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "version": { "type": "string" },
    "content": {
      "type": "array",
      "items": {
        "oneOf" : [
          { "type": "string" },
          { "type": "number" }
        ]
      }
    }
  }
}
```

a JSON dokument:

```json
{
  "node": "My document",
  "content": [ "Ailish", 2, [3] ]
}
```

1.  Rozhodněte, zda je daný JSON dokument validní podle uvedeného JSON-schématu. Pokud není validní, popište co do rozsahu minimální variantu úpravu JSON dokumentu, aby validní byl.
2.  Naznačte, jakým způsobem by bylo nutné JSON dokument rozšířit, aby bylo možné na něj nahlížet jako na RDF data. Není dovoleno měnit existující klíče ani hodnoty v JSON dokumentu.


## 24 Základy indexování (otázka studijního zaměření – 3 body)

Uvažujme následující neredundantní 3-rní B-strom. Kořenem stromu je uzel $[5,12]$. Potomky stromy jsou pak zleva doprava uzly $[1, ]\ [6, 7]\ [13, 14]$.

1.  Graficky znázorněte výsledný stav B-stromu po vložení nové hodnoty 20.
2.  Mohl by výše uvedený příklad B-stromu být validním redundantním stromem? Odpověď zdůvodněte.
3.  Vysvětlete rozdíl mezi B-stromem a B*-stromem.
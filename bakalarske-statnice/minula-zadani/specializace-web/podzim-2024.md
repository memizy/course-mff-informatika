**5 Jazyk SQL (specializace WDOP)** 

Uvažujte doménu hudební scény. 

1. Napište v jazyce SQL příkazy, které vytvoří tabulky pro reprezentaci zpěváků, kapel a skladeb. Vytvořte alespoň dva atributy pro každou z těchto entit (např. jméno a země původu zpěváka) a použijte vhodné datové typy. 

2. Upravte vhodnými SQL příkazy tabulky tak, aby bylo možné ukládat informace o členství zpěváků v kapelách a o interpretech skladeb. Předpokládejte, že každý zpěvák je členem maximálně jedné kapely a každá skladba může mít maximálně jednoho interpreta. Kapela ale může mít více zpěváků a zpěvák může interpretovat více skladeb. Zajistěte referenční integritu. 

3. Napište SQL příkaz, který vloží do tabulek zpěváka, který je členem nějaké kapely a interpretuje nějakou skladbu. 

4. Napište v SQL dotaz, který vypíše jména všech zpěváků, kteří nejsou členy žádné kapely. 

5. Vysvětlete, co dělá následující SQL dotaz (obecně i nad aktuálně vloženými daty): 

```
SELECTnazev,COUNT(*)
FROMkapela
GROUPBYnazev
HAVINGCOUNT(*)>2;
```

6. Napište SQL příkazy, které smažou vytvořené tabulky. 

**Nástin řešení** 1. 

```
CREATETABLEzpevak(id_zINTPRIMARYKEY,jmenoVARCHAR(100),zemeVARCHAR(200));
CREATETABLEkapela(id_kINTPRIMARYKEY,nazevVARCHAR(100),zalozenaINT);
CREATETABLEskladba(id_sINTPRIMARYKEY,titulVARCHAR(100),delkaTIME);
```

2. 

```
ALTERTABLEzpevakADDCOLUMNclenINT;
ALTERTABLEzpevakADDFOREIGNKEY(clen)REFERENCESkapela(id_k);
ALTERTABLEskladbaADDCOLUMNinterpretINT;
ALTERTABLEskladbaADDFOREIGNKEY(interpret)REFERENCESzpevak(id_z);
```

3. 

```
INSERTINTOkapelaVALUES(1,’Queen’,1970);
INSERTINTOzpevakVALUES(101,’FreddieMercury’,’Zanzibar’,1);
INSERTINTOskladbaVALUES(201,’UnderPressure’,’00:04:08’,101);
```

(Pozor na pořadí nebo ADD FOREIGN KEY až po vložení všech dat.) 4. 

```
SELECTjmenoFROMzpevakz
WHERENOTEXISTS(SELECT*FROMskladbaWHEREinterpret=z.id_z);
```

5. Vrací název a počet členů kapel, které mají více než dva zpěváky. Pro daná data nevrátí nic. 

6. 

4 

```
DROPTABLEskladba;
DROPTABLEzpevak;
DROPTABLEkapela;
```

(Pozor na pořadí nebo nejdřív DROP CONSTRAINT.) 

# **6 Moderní databázové systémy (specializace WDOP)** 

Uvažujte problematiku multi-modelových dat a databází. 

1. Vysvětlete pojem „multi-modelová data“ a rozdíl mezi multi-model a single-model databázemi. Uveďte příklad. 

2. Uveďte alespoň dvě výhody a dvě nevýhody multi-modelových databází oproti tradičním single-model databázím. 

3. Pro libovolnou multi-modelovou databázi vytvořte jednoduchý příklad databázového schématu, resp. dat a nad nimi multi-modelový dotaz. Demonstrujte na něm uvedené výhody multi-modelových databází. 

4. Vysvětlete rozdíl mezi multi-modelovou databází a polystorem. 

**Nástin řešení** 1. Multi-modelová data jsou data, která kombinují více než jeden model. Multi-modelové databáze jsou databáze, které takovou kombinaci nativně podporují. Např. PostgreSQL kombinuje relační a dokumentový model pomocí embeddingu, tj. sloupec relační tabulky může být typu JSON/JSONB a obsahovat dokumenty. Single-model databáze podporují jen jeden model. 

2. Výhody: data jsou uložena nativně pomocí optimálního modelu, jsou uložena v jediném systému (ne v několika singlemodel systémech), existuje k nim jediný společný dotazovací jazyk, ... Nevýhody: neexistuje žádný standard pro kombinaci modelů (jaké, jak), standardní dotazovací jazyk (kromě SQL/XML a SQL/JSON pro relační/dokumentová data) apod., implementace multi-model systému je složitá (modely mají z principu protichůdné vlastnosti), existující systémy mají stále mnoho omezení, ... 

3. Např. v PostgreSQL vytvoříme klasickou relační tabulku se sloupcem pro dokumentová data a dotážeme se na ně: 

```
CREATETABLEzakaznik(
idINTEGERPRIMARYKEY,
jmenoVARCHAR(50),
objednavkyJSONB
);
INSERTINTOzakaznik
VALUES(1,’KarelNovák’,
’{"Cislo_obj":"o43",
"Polozky":[
{"Id_produktu":"p34","Jmeno_produktu":"Myš","Cena":230,"Pocet":2},
{"Id_produktu":"p56","Jmeno_produktu":"Klávesnice","Cena":788}]
}’);
INSERTINTOzakaznik
VALUES(2,’PetrNovák’,
’{"Cislo_obj":"o33",
"Polozky":[
{"Id_produktu":"p777","Jmeno_produktu":"Počítač","Cena":34000}]
}’);
SELECTjmeno,
objednavky->>’Cislo_obj’ascislo_obj,
objednavky#>’{Polozky,0}’->>’Jmeno_produktu’asJmeno_produktu
FROMzakaznik
WHEREobjednavky->>’Cislo_obj’<>’o33’;
```

Jak je vidět, tak nám stačí jeden systém, ale rozšíření jazyka SQL o konstrukty pro JSON data je systémově specifické, další modely nemusíme mít podporované atd. 

5 

4. Polystore stejně jako multi-model databáze ukládá multi-modelová data, ale pro jednotlivé modely využívá samostatné single-model databáze. Centrální prvek (mediator) pak zajišťuje jejich management, dekompozici a vyhodnocení dotazu, spojení mezivýsledků atd. Hlavní výhodou je využití robustních prověřených single-model systémů, nevýhodou je komplexita mediatoru, malá podpora v komerčním světě (spíš akademické systémy). 

# **7 Web (specializace WDOP)** 

1. Vysvětlete návrhový vzor Front Controller a jeho využití pro vývoj webových aplikací. S pomocí pseudokódu nebo PHP demonstrujte základní myšlenku implementace. 

2. Uvažujte následující webové (REST) API: 

- `GET /api/singer` – vrátí JSON, který je polem identifikátorů zpěváků, například: 

   - `["jaroslav-1980", "pavelka-1958"]` 

– `GET /api/singer/{identifikátor}` – vrátí JSON, který obsahuje jméno zpěváka, například: 

- `{ "name": "Jaroslav" }` 

– `DELETE /api/singer/{identifikátor}` – smaže zpěváka 

Pro popsané API napište v JavaScriptu, který poběží ve webovém prohlížeči, funkci, která dostane jako argument jméno zpěváka a provede následující kroky: 

1. smaže všechny zpěváky daného jména, 

2. pro každého smazaného zpěváka přidá HTML element `li` se jménem zpěváka do elementu s id `deleted-list` . 

Pokud si nejste jisti názvem nějaké funkce/proměnné, popište její chování. Výsledný kód může být strukturován do více funkcí, na drobné syntaktické chyby nebude při hodnocení brán zřetel. V kódu nemusíte řešit obsluhu chybových stavů. 

**Nástin řešení** 1. Základní myšlenkou je mít jedno vstupní místo do aplikace pro obsloužení požadavků od klienta. Návrhový vzor je použitý na straně serveru. 

V zásadě stačí switch, nebo třída podobného stylu. Skládá ze dvou částí – routing a dispatching, tedy například: 

```
//Routing.
$handler=routing($_GET,$_SERVER);
//Nechámemetoduobsloužit-dispatching.
$handler->handle($_GET,$_POST,$_SERVER);
```

Dále je možné uvést například inicializaci a ošetření chybového stavu. 

2. Implementace by měla obsahovat fetch na seznam a pak na jednotlivé zpěváky. Následně fetch, který provede delete. Poslední je vytvoření a vložení HTML elementu. 

Například: 

```
asyncfunctiondeleteSingersByName(name){
constidentifiers=awaitfetchJson("./api/singer");;
for(constidentifierofidentifiers){
consturl="./api/singer/"+encodeURI(identifier);
constsinger=awaitfetchJson(url);
if(singer.name!==name){
continue;
}
awaitfetch(url,{method:"DELETE"});
addToList(singer.name);
```

```
}
```

```
}
```

6 

```
asyncfunctionfetchJson(url){
returnawait(awaitfetch(url)).json();
}
```

```
functionaddToList(name){
constli=document.createElement("li");
li.innerText=name;
document.getElementById("deleted-list").appendChild(li);
```

```
}
```

# **8 Základy indexování (specializace WDOP)** 

Pro potřeby této otázky uvažujme databázi vytvořenou v první otázce specializace („Jazyk SQL”). 

1. Vysvětlete přímé/nepřímé indexování a primární/sekundární index. 

2. Uveďte příklady možného použití přímého primárního, přímého sekundárního a nepřímého sekundárního indexu pro tabulku reprezentující zpěváky (zpevak). Jaké jsou výhody a nevýhody použití indexů? 

3. Předpokládejme přímé primární indexování sloupce zpevak.id (identifikátor zpěváka) pomocí redundantního B-stromu bez odloženého štěpení, stupně 3, tedy 2 hodnoty a 3 ukazatele. Demonstrujte postupné vkládání záznamů s hodnotou klíče: 1, 2, 3, 4, 5, 0. 

**Nástin řešení** 1. Přímé indexování ukazuje přímo na data, nepřímé indexování ukazuje na jiný index. Primární index odpovídá fyzickému pořadí uložení záznamů, sekundární index mu neodpovídá. 

2. Přímý primární – primární klíč, zpevak.id_z. Takový klíč může být jen jeden. Sekundární indexy je možné použít na všechny ostatní sloupce, kde očekáváme časté dotazování. Přímá a nepřímá varianta je zde jen implementačním detailem. 

Výhodou indexu je rychlejší dotazování, nevýhodou pak pomalejší vkládání a mazání, kdy je třeba index upravit. 

3. Postupně, první 4 jsou zapsány na jeden řádek, jedná se vždy o kořen a jeho potomky. Úrovně jsou oddělené čárkou. 1: 

[1] 

2: 

[1,2] 

3: Tady je možné [2], [1] [2,3] i [2], [1,2] [3] – záleží na tom, na jakou stranu uvažujeme ostrou nerovnost, jestli ’<,>=’ ,nebo ’<=,>’. Důležité je, že je třeba být v tomto konzistentní i ve zbytku řešení. 4: 

’<,>=’: [2,3], [1] [2] [3,4] ’<=,>’: [2], [1,2] [3,4] 5: 

’<,>=’: [3], [2] [4], [1] [2] [3] [4,5] ’<=,>’: [2,4], [1,2] [3,4] [5] 0: ’<,>=’: [3], [2] [4], [0,1] [2] [3] [4,5] ’<=,>’: [2], [1] [4], [0,1] [2] [3,4] [5] 

7 


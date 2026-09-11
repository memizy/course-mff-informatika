R-strom je výškově vyvážený vícecestný strom umožňující indexaci prostorových dat. Je zobecněním B-stromu pro prostorová data. MBR je osově zarovnaný obdélník, který obsahuje všechny MBR v daném podstromu. R-strom je strom v jehož každém uzlu jsou MBR všech potomků tohoto uzlu a odkazy na ně. V prostoru si to můžeme představit jako že všechny ty menší obdelníky v podstromu jsou uvnitř obdélníku toho potomka (případně ve 3D kvádry). Listové uzly obsahují MBR každého objektu který obsahují a odkaz na něj, což může být např. polygon či kus dálnice.

Když hledáme objekty v určité oblasti koukáme se vždy v uzlu na MBR potomků a zkoumáme zdali se nějaký z nich překrývá s MBR našeho dotazu, díky zarovnání MBR na osy je takové porovnání triviální a rychlé. Celý podstrom lze bezpečně vynechat pokud se jeho MBR nepřekrývá s MBR našeho dotazu. Pokud ses MBR potomka či potomků protíná pokrčujeme s hledáním ve všech těchto potomcích. V listech se pak ověří konkrétní objekty i s jejich složitou prostorovou strukturou.

Provnejme R strom například se Z-indexem, u R-stromu je největším problémem překrývání MBR potomků uzlu kvůli kterému je nutné hledat ve více uzlech, díky tomu není zaručena logaritmická složitost jako u B-stromu, tomu se snaží bránit R* stromy které se reálně používají, ty chytře překryvy minimalizují a občas provedou re insert některých objektů pro vyvážení při přetečení.

Z-křivku je možné použít pro indexaci bodů v prostoru, narozdíl od R-tree který umí vyhodnocovat překryvy složitých objektů, Z-křivka slouží hlavně pro vyhledání blízkosti některých bodů, či bodů v okolí. Z křivka protáhne body jednu křivku po tvarech Z to ale často vede k velkým skokům a body na druhé straně mapy mohou být v naší křivce ihned zasebou, její výhodou je ale vysoká rychlost neboť souřadnici na Z křivce lze zjistit pouze prokládáním x a y souřadnic daného bodu.
Na tyto hodnoty lze pak použít již ověřený B+ strom.


Ano lze to vyřešit jedním MapReduce krokem, dva kroky by byly zbytečné, postup je níže ve funkcích map reduce a popisu shuffle.


map(dokument_id, obsah):
    čti dokument pro slovech a pro každé slovo:
        emituj na výstup dvojici slovo, dokument_id

fáze shuffle dá dohromady dvojice se stejným slovem a dostaneme seznam pro dané slovo


reduce(slovo, seznam_doc_id):
    projdi postupně každý záznam:
        stavěj invertovaný index neboli vezmi to i dokumentu a přidej ho do indexu jestli tam ještě není nebo u něho zvětši hodnotu o 1


Ano funkce combine by nám pomohla, umožňuje provést lokální redukci přímo na uzlu po mapu mohli bychom rovnou postavit lokální invertovaný index a shuffle operace a posílání po síti by díky tomu nebyla tak nákladná.
Cíl agenta: Analyzovat text ze zadaného PDF souboru (nebo OCR textu)
státnicového testu a neomylně určit, o jaký zkouškový termín (Semestr a Rok) se
jedná.

Způsob identifikace: K určení termínu NIKDY nehledej datum v hlavičce (často tam
není). Termín urči výhradně na základě unikátního obsahu (klíčových slov a
zadání úloh) podle následujícího slovníku:

  - Léto 2023: Hledej otázku 20 Web chat a konkrétní ukázku PHP kódu: if
    (($_GET['action'] ?? '') === 'login'). Dále obsahuje otázku 19 Architektury
    databázových systémů (PROJECT a EMPLOYEE).
  - Podzim 2023: Hledej otázku 7 Web app: vyhledávání článků obsahující HTML
    id="searchInput" a JS fetch endpoint /api/articles?search=. Dále otázku 8
    Bezpečnostní tokeny začínající { "alg": "HS256", "typ": "JWT" }.
  - Jaro 2024: Hledej otázku 8 Odeslání webového formuláře s ukázkou HTML kódu
    <form id="addForm" action="index.php?action=addItem" method="POST">. (Řeší
    problém s tlačítkem Refresh / F5). Dále tabulky STUDENT, CLASS,
    REPORT_GRADE.
  - Léto 2024: Hledej otázku 7 API a skriptování týkající se REST API pro
    nemocniční systém (pacienti, lékaři, diagnózy). Začíná schématem
    Diagnóza(Kód, Název) ... Pacient(RČ, Jméno...).
  - Podzim 2024: Hledej otázku 7 Web (specializace WDOP) zmiňující návrhový vzor
    Front Controller a REST API s endpointy jako GET /api/singer a DELETE
    /api/singer/{identifikátor}. Dále obsahuje zadání tabulek hudební scény
    (zpěvák, kapela, skladba).
  - Jaro 2025: Hledej otázku 7 Návrh REST API, kde se navrhuje API 2. a 3.
    úrovně pro aplikaci, ve které "uživatelé konverzují s ChatBotem". Dále
    obsahuje úvodní tabulky Uzivatel(id_u, jmeno) a Zprava(id_z, id_k, cas).
  - Léto 2025: Hledej otázku 5 SQL schéma pro datové katalogy obsahující termíny
    dcat:Catalog, dct:title, dcat:downloadURL. Dále otázku 8 PHP na implementaci
    GET dotazu s URL query ?title=..., který vrací JSON.
  - Podzim 2025: Hledej otázku 7 Vyhledávání na webu obsahující malou
    boolskou/vektorovou matici 5x5 (sloupce A, B, C, D, E a řádky D1 až D5) a
    zadaný dotaz "A and (B or C)".
  - Jaro 2026: Hledej otázku 7 REST API pro streamovací aplikaci obsahující
    fiktivní Spotify endpointy GET /api/me/top/artists. Dále otázku 8
    Doporučovací systémy obsahující hodnocení U0 až U4 a položky I1 až I6 pro
    výpočet KNN.
  - Léto 2026: Specifický termín – neobsahuje žádné klasické Webové otázky.
    Hledej otázku 5 Indexace v prostorových databázích (R-strom a MBR), otázku 6
    MapReduce a modelování entit Hudebník a Nástroj (kardinalita UmíHrát).

Postup výstupu: Jakmile najdeš shodu z výše uvedeného klíče, vrať jasný výsledek
ve formátu: TERMÍN DETEKOVÁN: [Zjištěný semestr a rok].
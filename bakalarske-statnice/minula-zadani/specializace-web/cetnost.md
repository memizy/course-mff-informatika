Tady je detailní a přehledný souhrn všech tvých zkouškových otázek z okruhů **Databáze, Datový management a Web**. 

Jak jsi správně vypozoroval, systém zkoušky je striktní: z tvých PDF jasně vyplývá, že ať si vytáhneš jakýkoliv termín, dostaneš vždy **kombinaci přesně těchto tří oblastí**. Otázek bylo ve tvých 10 termínech celkem 42 (jeden termín měl 6 otázek, ostatní 4).

Rozřadil jsem je přesně podle struktury státnicových okruhů s přiřazenými daty, abys viděl, co se opakuje nejčastěji.

---

### 🗄️ 1. DATABÁZE (Celkem 18 výskytů)
Nejčastěji se objevoval Konceptuální a logický návrh (6x) a Transakční zpracování (5x). Každý termín obsahuje alespoň jednu čistě databázovou úlohu.

*   **Konceptuální, logický návrh a normální formy (6 výskytů)**
    *   **ER/UML model a úrovně návrhu:** Návrh agendy vládních usnesení (ministerstva), rozdíl mezi logickou, fyzickou a koncept. úrovní (2. 2. 2026)
    *   **Převod do 3. normální formy (3NF):** Tabulky PROJECT a EMPLOYEE, kontrola 3NF, kreslení ER diagramu z relace (27. 6. 2023)
    *   **Návrh relací nemocnice:** Pacient, diagnóza, lékař. Tvorba M:N vztahů a odstranění redundance (25. 6. 2024)
    *   **Tvorba schématu dle DCAT:** Datové katalogy, převod do 3NF a zápis SQL DDL s cizími klíči (23. 6. 2025)
    *   **Dekompozice do BCNF:** Doména hudební scény, vazby M:N, ověření BCNF formy (3. 9. 2024)
    *   **Doplňování schématu:** Databáze SIS-Junior. Navržení chybějících tabulek (vazební tabulky) pro podporu složitějších SQL dotazů (9. 2. 2024)
*   **Jazyk SQL (4 výskyty)**
    *   **Vyhodnocení 5 dotazů:** Sledování provádění JOINů, GROUP BY, vnořených SELECTů a IN/NOT IN operátorů (27. 6. 2023)
    *   **DDL a DML:** Tvorba tabulek hudební scény, `INSERT` dat, využití `GROUP BY` a `HAVING COUNT` (3. 9. 2024)
    *   **Analytické dotazy s agregací:** Získání podkladů pro vysvědčení v SIS-Junior, složité `JOIN` a počítání `AVG` (9. 2. 2024)
    *   **Dotazy pro ChatBota:** Vytvoření struktury tabulek s referenční integritou, počítání zpráv v konverzacích (4. 2. 2025)
*   **Transakční zpracování (5 výskytů)**
    *   **Uspořádatelnost a zotavitelnost:** Klasický rozvrh čtení a zápisu $R(A), W(B)$. Kreslení precedenčního grafu (27. 6. 2023)
    *   **Striktní 2PL a uzamykání:** Aplikace sdílených ($L_S$) a exkluzivních ($L_X$) zámků. Identifikace uváznutí (deadlock) (14. 9. 2023)
    *   **Rozvrh a nepotvrzená data:** Hledání cyklů v grafu transakcí nemocnice. Čtení nepotvrzených dat (Dirty Read) před `COMMIT` (25. 6. 2024)
    *   **Doplnění neznámé operace:** Rozvrh transakcí s otazníky (???), hledání operace, která způsobí konflikt / nezotavitelnost (22. 6. 2026)
    *   **Konfliktová ekvivalence S1 a S2:** Srovnání dvou rozvrhů a zajištění shodného výsledného stavu databáze (8. 9. 2025)
*   **Moderní databázové systémy (3 výskyty)**
    *   **MapReduce:** Úloha na invertovaný index. Napsání pseudokódu pro `map`, `reduce` a význam funkce `combine` (22. 6. 2026)
    *   **Multi-model vs. Polystore:** Rozdíly, vložení a dotazování na JSON data uvnitř relační PostgreSQL databáze (3. 9. 2024)
    *   **Grafové databáze (Neo4j):** Modelování vztahů (Autoři, Knihy) a ukázka dotazu v jazyce Cypher v porovnání s relací (8. 9. 2025)

---

### 📂 2. DATOVÝ MANAGEMENT (Celkem 11 výskytů)
Zde jasně dominují hierarchické B-stromy a prostorové indexy. Objevuje se i sémantický web (JSON-LD, RDF) a občasně komprese/šifrování.

*   **Základy indexování a B-stromy (5 výskytů)**
    *   **Neredundantní B-strom vs. B*-strom:** Ruční vkládání do uzlů, štípání a porovnání s B*-stromem (27. 6. 2023)
    *   **Výpočet pater indexu:** Výpočet velikosti bloků a pater nad pevnou délkou záznamů. Přímý a nepřímý index (14. 9. 2023)
    *   **Přímé/nepřímé a primární/sekundární indexování:** Teorie a manuální průchod vkládáním čísel do stromu (3. 9. 2024)
    *   **B-strom (teorie):** Definice pravidel B-stromu, grafické kreslení vložení a smazání, srovnání výhod B+ stromu (8. 9. 2025)
    *   **Redundantní B+ strom:** Vizualizace B+ stromu pro uživatele ChatBota, smazání záznamu a poznání redundance (4. 2. 2025)
*   **Indexování v prostorových databázích (2 výskyty)**
    *   **R-strom:** Definice uzlů, MBR (Minimum Bounding Rectangle), štípání přeplněného uzlu pro kapacitu $M=4$ (2. 2. 2026)
    *   **R-strom vs. Z-křivka:** Popis průchodu dotazu "Najdi všechny objekty v obdélníku" u R-stromu a porovnání se Z-křivkou (22. 6. 2026)
*   **Datové formáty, katalogy a sémantika (3 výskyty)**
    *   **JSON-Schema a validace:** Rozhodnutí o validitě JSON dokumentu a jeho převod na RDF pomocí úpravy schématu (27. 6. 2023)
    *   **JSON-Schema pro DCAT:** Návrh `dct:title` v JSON schématu pro datové sady a katalogy (23. 6. 2025)
    *   **JSON-LD:** Úprava JSON pro mapování na RDF pomocí speciálních klíčů `@context`, `@id` a `@type` (23. 6. 2025)
*   **Komprese a šifrování (2 výskyty)**
    *   **Huffmanovo kódování:** Sestrojení kódovacího stromu z pravděpodobností, entropie a zakódování zprávy (9. 2. 2024)
    *   **HTTPS a PKI:** Úloha certifikátů, symetrické vs. asymetrické šifrování a certifikační autority (4. 2. 2025) *(Prolíná se s bezpečností Webu)*

---

### 🌐 3. WEBOVÉ INŽENÝRSTVÍ & VYHLEDÁVÁNÍ (Celkem 13 výskytů)
Dominantním tématem je práce s JavaScriptem na klientovi (Asynchronní `fetch`) a bezpečnost. Často se testuje i IR (Information Retrieval - vektorové a booleovské modely).

*   **Architektury webu a návrh REST API (4 výskyty)**
    *   **Front Controller:** Návrhový vzor (routing/dispatching) vysvětlen na PHP pseudokódu (3. 9. 2024)
    *   **Richardson Maturity Model:** Tři úrovně REST API, aplikace na ChatBota. Princip HATEOAS / Hypermedia (4. 2. 2025)
    *   **Návrh endpointů (Nemocnice):** Komplexní návrh API zdrojů (pacienti, diagnózy, CRUD operace) (25. 6. 2024)
    *   **Vzor PRG (POST-Redirect-GET):** Řešení problému s dvojitým odesláním formuláře po stisknutí F5/Refresh bez klientského JS (9. 2. 2024)
*   **Klientský JavaScript (JS), DOM a asynchronní volání (4 výskyty)**
    *   **Spotify API Fetch:** Stažení pole IDs a asynchronní zřetězené volání detailů pro zobrazení v HTML přes DOM (2. 2. 2026)
    *   **Ošetření Race-Condition:** Volání zobrazení článků po stisku tlačítka. Blokování duplicitního stisku pomocí `lock flagu` (14. 9. 2023)
    *   **Asynchronní DELETE:** Konzumace REST API, cyklus smazání položek přes HTTP DELETE a úprava seznamu na stránce (3. 9. 2024)
    *   **Zamezení defaultní akce formuláře:** Využití `event.preventDefault()` a odeslání HTML form dat přímo přes JS `fetch` (9. 2. 2024)
*   **Bezpečnost webových aplikací (2 výskyty)**
    *   **Zranitelnosti kódu (PHP):** Praktická analýza webového chatu, prevence proti SQL Injection (27. 6. 2023)
    *   **JWT tokeny (JSON Web Token):** Princip HMAC podpisu, obsah payloadu a správa na klientovi – LocalStorage vs. HttpOnly Cookies (14. 9. 2023)
*   **Vyhledávání informací a Doporučovací systémy (3 výskyty)**
    *   **Vyhledávání diagnóz (IR):** Booleovský model vs. tf-idf Vektorový model (Kosinova vzdálenost) z textu vyšetření (25. 6. 2024)
    *   **Kosinova míra, Precision a Recall:** Výpočet míry podobnosti vektorů nad binární maticí, výpočet přesnosti a úplnosti (8. 9. 2025)
    *   **Doporučovací systémy (UB-KNN):** Kolaborativní filtrování, hledání nejbližších uživatelů podle explicitní matice hodnocení (2. 2. 2026)

---
**💡 Rychlý postřeh pro státnice z této sekce:** 
Pokud jdeš na kombinaci Web a DB/DM, máš prakticky 100% jistotu, že dostaneš úlohu na **Relační návrh / ER diagramy** a úlohu na **B-stromy / Prostorové indexy**. Z Webu musíš bezchybně zvládat **Javascriptový `fetch` s async/await (modifikace DOMu)** a navrhování **REST API endpointů**.
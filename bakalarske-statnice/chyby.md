# Chyby na pozdější opravu
## Celkové
Možná ještě tam zbyly nějaké chyby z celkových změn věci jako zkoušková je vyžadováno a často tam zbyly tvrzení stále o zkoušce či sylabu co jsou nadnesené nebo nejsou úplně pravda, ty plošné změny mohly něco rozbít

Title u poznámek by měl být plain text otázka je jestli to tak chceme opravdu

Celkovou opravu jsem dodělal u Webu, Datového managementu, Pasti a Diskrétky

U programka a architektur je otázka jestli to nedat nějak dohromady či možná ne ale jak to vymyslet

Ty zkouškové úlohy nejsou vždy celé a přesné obzvlášť u specializace, ale i jinde
Celkově to procházet a tvořit ten cheat-sheet dívaní na něj mi dodá důvěru a pak rychlý opakování, psát tam i co dostudovat z původních poznámek
Také si pak vzít ty požadavky, procházet si je a vyškrtávat, na to si můžu udělat jednoduchou aplikaci jen pro sebe, nespoléhat jen na minulé termíny

Někdy je špatný pořadí trochu a zkouškový otázky předbíhaj ale asi to klidně nechat takhle jen si to zapsat, pořád jsou tam zmínky o ústní zkoušce 

## Matika

### Analýza
Vylepšit to teorie limity aby tam nebylo skoro a definoavt to přesně
Chybí tam definice limity, dát tam ve vlastním i nevlastním bodě
Co to je uspořádání, to bám tu taky úplně chybíp
Chybí tam přesně definice kouknout do Jirkovo poznámek

### Lingebra
Jak najdu ortonormalni bazi a kdyz delam skalarni soucet tak zjistuju jak moc je ponoci toho jednoho vektoru ten druhej
Zeptat se když delam skalarni soucin tak vlastne zjistuju jak jde ten jeden vektor ve smeru druheho

Jak je definovaná transpozice pro matice mxn
Pridat definici vektorového prostoru
To Sarusovo pravidlo a determinant pro 2x2 a 3x3 matice tam chybí 
Axiomy skalárního součinu je tam zbytečně dostavame se do 6 bloku
Co to je ten charakteristický polynom matice

### Grafy
Přidat že graf je bipartitní právě tehdy když nemá lichou kružnici
Nápověda jaro 2025 je rozbitá

### Diskrétka
Možná někde ještě slova zkouška

### Logika
Výrokovka opravit Mermaid tablo a rezoluce, nezobrazují se
U logiky chybí vyřešená zkoušková otázka
Presna definice dnf a ze je to vlastne vycet nodelu
Extenze o definuci pomocí sčítání asi ne spíš je větší ne
U Godela má kalkul lže asi spíš nelže ne
Pridat nrkde driv vysvetlrni th pak se yo pouziva
U te kompletnosti je to pokud v ni nejsou nezavisle sentence přidat tam pozor sentence je uzavřená formule
Overit ze ty vety o uplnosti a kompaktnosti jsou opravdu jak od Bulina a to i v predikátové tak ve výrokové logice

### Past
Na mobilu jsou některé grafy uřízlé ale to je možná problém Learn pluginu

## Informatika

### Automaty
Chyba zápisu první úloha 2025 automaty
Pridat zapisy * a + a jestli tam byly i dalsi co znamenaj
Chybí tam ta Kleeneho věta důkladně je v převod automatů na regulární výrazy a u toho převodu co když z odebíraného vrcholu vedou dvě hrany
V tabulce průchodu u myhil nerodovy věty je zbytečně 4,5 dvakrát
U pumping lemmatu jsou rozbitý znaky
Tu zkouškovou otázku CFG na PDA předunout níž až za to vysvětlení mechanismu předělaní
Časová a ptostorová složitost smazat metmaid graf
A v tom závérecnym ho taky smazat otázka je jestli nesmazat i Savitchovu a ty jiný věty tam ale možná je tam nechat jako že nejsou potřeba napsat k nim

### Ads
V algoritmech jsou zbytečný grafy co nefungujou
U mergesortu a dalších tam nefungujou v grafech znaky často
U haldy je blbě že sestavení trvá čas O(k)
Quickselect líp vysvětlit zase je u nej zbytecny graf
U inverzí musí mít v nejhorším případě a pak použije značku dolního odhadu s těmi dolními odhady si to tam vyjasnit, pak zas používá thety v nejlepší případech vyjasnit si to tam, ten spodni odhad je tam pak
U Quicksortu to zdůvodnění a taky detailní popis algoritmu pseudokódem
Tu haldu by to chtělo detailněji a zmínit ten Heapsort aspoň trochu jak funguje, ta minhalda se pak dál používá všude a taky Fibonacoho haldu aspoň co to je
U AVL rozbitá syntaxe a ať to udělá jako je to ve skriptech
U rotací i ukázku té jednoduché a ukázky v opačnym pořadí a pryč z hidden contentu co tam být nemá
U BFS a DFS to samé používá hiddenContent když nemá
Prubeh Djikstrova algoritmu nevysvětluje vůbec nic
Selhání djikstry cápek si myslel že dal proti příklad ale dal houby
U bf je opravdu ta konteola na zapornt cyklus správně?
U minimální kostry je zase rozbito kódování
Jarník i Borůvka maj zase použit hiddenContent špatně, tohke bude potřeba prohledat možná i jinde ale tady je to nejvíc
Boruvka zbytečné grafy
I ten nax flow min cut byl u teorie grafů nějak líp vysvětlenej
U P a NP všude rozbitá notace a grafy zbytečný lepší by byl graf překryvů těch tříd, zminit tam co-NP jako ty co nelze ani verifikovat a dát tam množinový graf či co je podmnožinou čeho
Ty překlady problémů dát jich tam víc podle toho co tam má Mareš

### Architektury
Přidat všechny základní risc příkazy není to rak složité a hi a low a proc je to RD a RS inspirovat se i u ježkovo tabulky napsat tam že tam dali tabulku s nápovědou ale nemuseli by podle požadavků
Chybí tam o té roli řadiče zařízení při programem řízené obsluze
Opravit tu úlohu se semaforem ta je divně zadaná a vysvětlená

Ten zápis instrukcí pro volání funkce je tam spíš pro x86 než pro ARM
Zkouška často vyžaduje nakreslení stavového automatu
Přesně toto se objevilo v zadání u zkoušky 2024 - řadič disku a jeho LBA/DMA registry, opravdu přesně toto?
Chybí tam že stránkování je víceúrovňové reálně i když se vyžaduje jen jednoúrovňové
Zkouškový chyták hladovění Writera

Umět číst pointery v C++, jsou často v zadáních
Zapsat poznatky ze vzorových řešení C++ úloh co a jak tam chtějí jak to číst

### Programko
Udělat tam poznámku na volání base metody dát tam příklad syntaxe a jaké metody má ten Object a také pak syntaxe pro virtuální metody  u té tabulky virutální metod aby tam byla nějaká praxe s ukázkous syntaxe

Krátce co in, out a ref dělají u tříd
Pridat jak vypada twos complement jen kratolince
Vysvetleni backing fieldu
U geenrik to smazalo < a >
Tady ale tedy lze napsat return null
Ukázka kovariance a kontravariance
Konzument se usíní
Endianita se vztahuje na velikost ukladane jednotky pole ci stringy crle se neprohazuji, pro 1 bit se to neresi, možná nemusim jestli už je to v architekturách

Ty promises v C# a delegati určitě zopakovat 

U C# tam nejsou přesně ty zkouškové úlohy ale trochu jiné a u Architekrur jsou tam někdy zjednodušené verze a pak ještě jakoby dublované plné verze tam to ale tolika neva

Doplnit ukázku volání u in out ref
Matfyzácký chyták, zásadní věc na obhájení u komise
Přidat ukázku přiřazení do field s podmínkou
Komise se často ptá na to
Komise velmi ráda testuje
Nefunguje zobrazování generik
Syntaxe generik na papíře jenže tam je to omezení na class
Zní divně Slůvko 'in' (Kontravariance) se používá u delegátů, kde parametry do funkce pouze vstupují. a dát tam příklad
Chyták komise - co vypíše
Producent se musí uspět a pak usíní

Dostáváme se do dalšího bloku
Gratuluji, úspěšně jsme prošli celých 60 bodů našeho plánu a pokryli 100 % sylabu! 
## Web

### Databáze
Píše se do konceptuálního návrhu ta role u usnesení nebo kde se vymyslí
Kouknout vizuálně na tu ER a UML notaci a kam se píšou kardinality, napsat to k UML
Podtrzenim jsou vyznačeny klíče ale nic podtržené není
Mozna u Update Anomaly nehrozí ztráta konzustence ale je to tak špatné
Jazyk sql DML operace používejte ten první způsob když ten druhý není ukázán
Aplikace striktního 2PLá pouze dvě ne tři transakce v příkladu
Vnořené podditazy, dát příklad selhání v přítomnksti null hodnot
Zkoušková úloha podzim 2024 je nejspíš špatně
Pro co je zkratka to Select 1
Úloha jaro 2025 je taky divná
Čitelnost (Faktová vs. Dimenze): Tabulka REPORT_GRADE je tzv. "faktová" tabulka (obsahuje samotná data k počítání – známky). Tabulky CLASS a SUBJECT jsou "číselníky/dimenze" (popisují ta data). Programátoři často instinktivně dávají do FROM tu hlavní tabulku, nad kterou se dělá agregace (AVG(grade)), a k ní pak "přilepují" číselníky pomocí joinů. Je to ale jen o zvyku a čitelnosti.
Přidat Map Combine Reduce postup k MapReduce
U Graph traversal by asi mělo být spíš O logN + F na 3

### Data
Třídy grafových dotazů chybí
U Hashování jsou tam všechny tři ve finálním souhrnu ale stačí jen 1

### Web
Občas malé chybky ve formátování že se nenapárují správně **
Jak u doporučovacích systémů tak u vyhledávání na webu jsou ty úlohy v sadě odlišné od reálných úloh často jsou tam jen části nebo jsou rozděleně jako u toho vyhledávání
SOM a SSM je tam jakoby dvakrát
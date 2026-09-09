# Test 9: Programování, C# a Architektury (Všechna minulá zkoušková zadání MFF UK)

* **Datum zadání:** 8. 9. 2026
* **Rozsah:** Všech 9 autentických zkouškových úloh z Programování, C#, OOP, vícevláknovosti a systémového programování ze všech 10 státnicových termínů MFF UK (2023–2026).
* **Styl zadání:** Textová znění původních zkouškových úloh z písemek MFF UK.

---

## Úloha 1: Vlákna a třída LimitedStack (MFF termín Podzim 2023 – 14. 9. 2023)

*Zdroj: [podzim-2023.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/podzim-2023.pdf) (Úloha 1)*

Mějme následující třídu v pseudokódu:

```csharp
class LimitedStack {
public:
    LimitedStack(int md) {
        currentDepth = 0;
        maxDepth = md;
        stack = new int[maxDepth];
    }

    int getDepth() {
        return currentDepth;
    }

    bool pushValue(int v) {
        if (currentDepth >= maxDepth)
            return false;
        stack[currentDepth] = v;
        currentDepth++;
        return true;
    }

private:
    int maxDepth;
    int currentDepth;
    int[] stack; // int *stack; pro C++
};
```

Dále předpokládejme, že máme multiprocesorový systém a program si spustí několik vláken, která budou mít všechna přístup ke sdílené proměnné typu `LimitedStack`. Tato vlákna budou volat podle své potřeby funkce `getDepth` a `pushValue`.

1. Je možné, že v programu nastane jev zvaný *race condition*? Pokud ano, napište rozsahy řádek nebo vyznačte přímo v uvedeném kódu řádky, které představují kritickou sekci.
2. Je možné, aby nějakým způsobem nastala situace, kdy při volání funkce `pushValue` přeteče zásobník (program se bude pokoušet zapisovat mimo alokované pole)? Zdůvodněte.
3. Pokud se domníváte, že v uvedeném kódu může nastat race condition, pokuste se tento problém odstranit úpravou programu (včetně možného přidání nějakých nových řádek).

Kde je to důležité, ve své odpovědi uvažujte jazyk C#, C++ nebo Java (a vaši volbu vyznačte).

> **Tvé řešení:**
1. Celý obsah funkce pushValue kromě samotného return nakonci je kritickou sekcí a obsah getDepth() 
2. Ano je pokud první vlákno projde podmínkou if (currentDepth >= maxDepth) a pak je uspáno druhé vlákno může udělat celé push value tím se zvýší currentDepth následně první vlákno zapíše mimo alokované pole
3. přidáme private readonly object _syncroot = new object()
lock(_syncroot) {
    return currentDepth
}

lock(_syncroot) {
    if ...

    currentDepth+
}
return true

---

## Úloha 2: Ovladač pro řadič disku (MFF termín Jaro 2024 – 9. 2. 2024)

*Zdroj: [jaro-2024.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2024.pdf) (Úloha 2)*

Napište implementaci funkce ovladače disku pro načtení jednoho bloku.

Uvažovaný disk je řízen pěti paměťově mapovanými registry, které slouží k zápisu příkazů (a jejich parametrů) a ke čtení aktuálního stavu zařízení (uvažujeme zařízení bez podpory přerušení, s obsluhou s aktivním čekáním).

| Offset | Registr | Typ | Popis registru |
|---|---|---|---|
| 0 | Status | R | Bitové pole pro aktuální stav řadiče (bit 0: `ERR` – chyba, bit 1: `BUSY` – provádění příkazu). |
| 4 | Size | R | Velikost disku v blocích (pouze pro čtení). |
| 8 | Command | W | Zápis do registru spustí zadaný příkaz (`1` čtení, `2` zápis). |
| 12 | LBA | W | Logická adresa bloku pro příkaz zadaný v *Command*. |
| 16 | DMA | W | Fyzická adresa paměti pro uložení načtených dat z disku. |

Bloky jsou na disku adresovány obvyklým způsobem pomocí LBA, jednotlivé bloky mají pevně danou velikost 512 bajtů. Přenos čtených či zapisovaných dat probíhá pomocí DMA (tedy z pohledu této otázky není třeba řešit nic víc než nastavení fyzické adresy pro uložení dat, vlastní čtení z disku a zápis do paměti je plně v režii řadiče), dokončení operace je signalizováno stavovým registrem (předpokládáme 32-bitový systém, velikost disku je omezena na 2 TB).

Dopište těla dvou níže uvedených funkcí a navrhněte strukturu pro uchování informací o disku (předpokládáme, že k systému může být připojeno více disků a ty jsou na úrovni jádra operačního systému rozlišeny různými instancemi struktury `disk_t`). Obě funkce vrací `true` pokud se daná operace zdařila, jinak `false` (bez dalších detailů).

Funkce `disk_init` je volána jednou při inicializaci daného zařízení, parametr `register_address` je virtuální adresa mapovaných registrů (tj. přímo adresa stavového registru). Funkce `disk_read_block_waiting` přečte jeden blok z disku. Načtený blok má být zapsán na fyzickou adresu `data_phys_addr` (váš kód může předpokládat její správnost). Návrat z funkce musí proběhnout až po dokončení čtení (je možné využít aktivní čekání).

Vaše implementace musí alespoň triviálním způsobem ošetřit možný současný přístup k disku z více procesů.

```c
typedef struct {
    volatile uint_32 status;
    uint_32 size;
    volatile uint_32 command;
    volatile uint_32 lba;
    volatile uint_32 dma;
} disk_regs;


typedef struct {
    disk_regs* disk_regs;
    readonly object _syncroot = new object();
} disk_t;

bool disk_init(disk_t *disk, uint32_t register_address) {
    try {
        lock(_syncroot) {
            disk->disk_regs = (disk_regs_t *) register_adress;
            return true
        }
    } catch {
        return false
    }
}

bool disk_read_block_waiting(disk_t *disk, size_t lba, uint32_t data_phys_addr) {
    try {
        lock(_syncroot) {
            disk->disk_regs->lba = lba;
            disk->disk_regs->dma = data_phys_addr;
            disk->disk_regs->command = 1;

            while ((disk->disk_regs->status & 2) == 2) {}
            if ((disk->disk_regs->status & 1) == 1) { return false; }
            return true;
        }
    } catch {
        return false
    }
}
```

> **Tvé řešení:**
> 
> 
> 

---

## Úloha 3: Semafor a souběžnost v C# (MFF termín Léto 2024 – 25. 6. 2024)

*Zdroj: [leto-2024.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/leto-2024.pdf) (Úloha 2)*

Knihovna `System.Threading` jazyka C# obsahuje třídu `Semaphore` s metodami odpovídajícími operacím klasického semaforu, $P$ (`WaitOne`) a $V$ (`Release`). Objekt vytvořený pomocí `new Semaphore(0, 1)` odpovídá binárnímu semaforu inicializovanému nulou. Pokud více než jedno vlákno čeká na tentýž semafor, pořadí, ve kterém budou vlákna spouštěna po uvolnění semaforu, není specifikováno.

Program níže má produkovat výstup `OneTwoThreeFourFive`, přitom liché části výstupu mají být vypisovány funkcí `f1` a sudé části funkcí `f2`, přičemž tyto funkce běží v různých vláknech.

Synchronizace, implementovaná pomocí semaforu, téměř funguje, ale obsahuje časově závislé chyby (race conditions).

```csharp
class Program
{
    private static Semaphore sem;

    private static void f1()
    {
        Console.Write("One");
        sem.Release();
        sem.WaitOne();
        Console.Write("Three");
        sem.Release();
        sem.WaitOne();
        Console.Write("Five");
    }

    private static void f2()
    {
        sem.WaitOne();
        Console.Write("Two");
        sem.Release();
        sem.WaitOne();
        Console.Write("Four");
        sem.Release();
    }

    static void Main(string[] args)
    {
        sem = new Semaphore(0, 1);
        Thread t1 = new Thread(f1);
        Thread t2 = new Thread(f2);
        t1.Start();
        t2.Start();
        t1.Join();
        t2.Join();
    }
}
```

1. Popište scénář, který vede k jinému výstupu než `OneTwoThreeFourFive`, nebo končí uváznutím (deadlock). Scénář zapište jako posloupnost čísel řádek, přičemž každé číslo reprezentuje *ukončení* příkazu na dané řádce. Pouze vnitřky funkcí `f1` a `f2` jsou relevantní.
2. Existovaly by v tomto kódu časově závislé chyby i v případě, že by knihovna C# garantovala FIFO pořadí spouštění vláken čekajících ve `WaitOne`?
3. Napište řešení, které neobsahuje časově závislé chyby a spolehlivě vypisuje požadovaný výstup `OneTwoThreeFourFive`. Použijte přitom dva semafory a pouze jejich funkce `Release()` a `WaitOne()`. Řešení nesmí používat žádné jiné proměnné nebo objekty sdílené mezi vlákny kromě těchto dvou semaforů. Volání `Console.Write` musejí samozřejmě zůstat tam, kde jsou.

(Jazyk C# je v této otázce použitý pouze jako generický zástupce běžných programovacích jazyků, otázka ani řešení s jazykem C# jako takovým nesouvisí.)

> **Tvé řešení:**
7,8,9,10,11,12,13 Vypsali jsme One Three Five a pak jsme se deadlocknuli
Ano to by nijak nepomohlo jak vidíme na předchozím příkladu vlákno 1 proběhlo celé a vypsali jsme něco co jsme nechtěli a ještě došlo k deadlocku
Zavoláme vždy na jednom semaforu 

semafor s1 i s2 dáme na nulu

1
s2. Release
s1. WaitOne

s2. WaitOne
2
s1. Release


---

## Úloha 4: Reprezentace typů a návrhové vzory (MFF termín Podzim 2024 – 3. 9. 2024)

*Zdroj: [podzim-2024.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/podzim-2024.pdf) (Úloha 2)*

1. Představte si, že vyvíjíte integrované vývojové prostředí (IDE). V okně projektu je potřeba zobrazit typy a elementy typů (tj. jejich metody, datové položky, vnitřní/vnořené typy). Ve zvoleném jazyce (Java, C++, C#) navrhněte vhodnou sadu tříd/interfaců, které vám umožní uchovávat informace o typech tak, aby mohly být zobrazeny v okně v IDE. Informace zahrnují alespoň názvy typů, jejich druhy, metody typů a jejich signatury, datové položky a vnitřní/vnořené typy. Navrhněte vaše řešení tak, aby bylo v budoucnu snadno rozšiřitelné. Vytvořte pouze deklarace tříd/interfaců, tj. bez těl jejich metod.

2. Implementujte metodu, která bere jako parametry (i) typ (jak jste jej definovali pro část otázky výše) a (ii) „operaci“. Metoda aplikuje danou operaci na daný typ a všechny elementy typu. Pokud založíte procházení struktury typu na nějakém obecně známém řešení, explicitně toto řešení pojmenujte. Pro operaci použijte vhodný koncept, který nabízí vámi zvolený jazyk.

3. Napište kód, který zavolá vaší metodu z předchozího bodu. Operace předaná metodě je: „vytiskne název elementu, ale pouze v případě, že element reprezentuje datovou položku nebo typ (včetně vnitřních/vnořených typů)“.

> **Tvé řešení:**
```csharp
public interface IIdeElement { public string Name {get; set;} }

public inteface IIdeMethod : IdeElement {
    public List<
    public string returnType;
}

public inteface IIdeField : IdeElement {
    
}

public inteface IIdeType : IdeElement {
    public List<IdeElements> elements;
}

public class IdeType : IIdeType {
    public void ApplyOperation(type, Action<IIdeElement>) {
        if (... is )
    }
}

Pattern matching
```

<details>
<summary><b>Vzorové řešení (C# – Návrhový vzor Composite + Pattern Matching):</b></summary>

```csharp
// ==========================================
// 1. DEKLARACE STRUKTURY (Návrhový vzor Composite)
// ==========================================

public enum TypeKind { Class, Struct, Interface, Enum }

public abstract class IdeElement
{
    public string Name { get; }
    protected IdeElement(string name) => Name = name;
}

public class FieldElement : IdeElement
{
    public string TypeName { get; }
    public FieldElement(string name, string typeName) : base(name) => TypeName = typeName;
}

public class MethodElement : IdeElement
{
    public string ReturnType { get; }
    public IReadOnlyList<string> ParameterTypes { get; }

    public MethodElement(string name, string returnType, IReadOnlyList<string> parameterTypes)
        : base(name)
    {
        ReturnType = returnType;
        ParameterTypes = parameterTypes;
    }
}

public class TypeElement : IdeElement
{
    public TypeKind Kind { get; }
    public IReadOnlyList<IdeElement> Elements { get; }

    public TypeElement(string name, TypeKind kind, IReadOnlyList<IdeElement> elements)
        : base(name)
    {
        Kind = kind;
        Elements = elements;
    }
}

// ==========================================
// 2. METODA PRO PRŮCHOD STRUKTUROU (Rekurze + Composite)
// ==========================================

public static class IdeOperations
{
    // Řešení je založeno na průchodu stromovou strukturou návrhového vzoru Composite.
    // Pro reprezentaci operace je použit funkcionální typ / delegát Action<IdeElement>.
    public static void ApplyOperation(TypeElement type, Action<IdeElement> operation)
    {
        if (type == null || operation == null) return;

        // Aplikujeme operaci na samotný typ
        operation(type);

        // Aplikujeme operaci na všechny podelementy
        foreach (var element in type.Elements)
        {
            if (element is TypeElement nestedType)
            {
                // Vnořený typ: rekurzivně projdeme i jeho elementy
                ApplyOperation(nestedType, operation);
            }
            else
            {
                operation(element);
            }
        }
    }
}

// ==========================================
// 3. VOLÁNÍ METODY S LAMBDA VÝRAZEM (Pattern matching)
// ==========================================

// Použijeme lambda výraz s C# pattern matchingem (is):
IdeOperations.ApplyOperation(rootType, element =>
{
    // Vytisknout název, pouze pokud jde o FieldElement nebo TypeElement (vč. vnořených)
    if (element is FieldElement or TypeElement)
    {
        Console.WriteLine(element.Name);
    }
});
```

</details>

---

## Úloha 5: Knihovna pro výpočty s maticemi (MFF termín Jaro 2025 – 4. 2. 2025)

*Zdroj: [jaro-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2025.pdf) (Úloha 2)*

Poznámky, jak odpovídat na otázku:
- Pro odpověď si vyberte jeden z jazyků Java, C++ nebo C#.
- Snažte se použít co možná nejnovější syntaxi (a idiomy, atd.) vybraného jazyka.

Představte si, že vyvíjíte **knihovnu pro výpočty s maticemi**.

1. Definujte kontrakt (bez implementace) pro reprezentaci dvourozměrné matice. Tento kontrakt musí poskytovat *prostředky* (tj. metody, funkce, vlastnosti apod. podle zvoleného jazyka) alespoň pro:
   - získání velikosti jednotlivých rozměrů,
   - získání hodnoty z matice na základě souřadnic dané hodnoty,
   - provádění aritmetických operací (sčítání s jinou maticí, odčítání, násobení, atd.).

2. Vytvořte implementaci svého kontraktu, která je vhodná pro velmi velké, ale **řídké** (tzv. *sparse*) matice (tj. matice obsahující převážně nuly). Okomentujte svou implementaci tak, aby bylo zřejmé, jak funguje. Z metod (funkcí, atd.) implementujte pouze ty, které vrací velikosti rozměrů a hodnotu z matice na základě souřadnic.
Definujte prostorovou složitost své implementace ve stylu $O(something)$.

3. Představte si, že máte více implementací svého kontraktu pro matice (např. pro řídké matice a pro husté matice). Dále si představte, že máte metodu (nebo funkci, atd.), která dostane soubor s hodnotami matice a určí, která implementace je pro danou matici ideální.
S využitím vhodného *návrhového vzoru* implementujte *prostředek*, který dostane soubor a vrátí instanci kontraktu matice s ideální implementací.

> **Tvé řešení:**
public interface IMatrix {
    long Rows { get; }
    long Columns { get; }
    static double [,] (long Row, long Column) { get; }

    IMatrix Operation(Func<IMatrix,IMatrix,IMatrix>, IMatrix matrix)
}

public struct DataCell {
    double value;
    long column;
}

public class SparseMatrix : IMatrix {
    long Rows { get; } // Počet řádků a sloupců inicializujeme jako properties které je potřeba nastavit při konstruktoru
    long Columns { get; }
    private LinkedList<DataCell>[] data; // Pro data použijeme pro každý řádek LinkedList a tyto Linked listy dáme do pole neb ty reference mají jen lineární prostorovou složitost O(Rows)
    // Samotná data jsou pak v linked listech abychom neplýtvali místem, celková prostorová složitost je tedy O(Rows + Počet prvků v matici)
    public SparseMatrix(long Rows, long Columns) {
        this.Rows = Rows
        this.Columns = Columns
        this.data = new LinkedList[Rows];
    }

    public static double [,] (long Row, long Column) {
        get => () {
            if (Row >= Rows || Column >= Colums) {
                throw new IndexOutOfRangeException();
            }
            foreach (cell in data[Row]) {
                if (cell.column == Column) {
                    return cell.value;
                }
            }
            return 0;
        }
    }
}

public enum MatrixType {
    Dense, Sparse
}

public struct MatrixMetadata {
    public MatrixType matrixType;
    public long Rows;
    public long Columns;
}

public class MatrixFactory {
    public IMatrix CreateMatrixFrom(string FilePath) {
        MatrixMetadata matrixMetadata = GetOptimalMatrixImplementation(string FilePath)
        switch matrixMetadata.matrixType {
            Dense => return new DenseMatrix(matrixMetadata.Rows, matrixMetadata.Columns)
            Sparse => return new SparseMatrix(matrixMetadata.Rows, matrixMetadata.Columns)
        }
    }
}

---

## Úloha 6: Jednoduchý správce paměti – Heap (MFF termín Léto 2025 – 23. 6. 2025)

*Zdroj: [leto-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/leto-2025.pdf) (Úloha 2)*

Předpokládejte v celé otázce pouze kontext 32-bitového **little endian** procesoru, **bitem 0 rozumíme LSb**.

Naším cílem je v souvislém bloku paměti implementovat jednoduchý heap pro dynamickou alokaci podbloků paměti (neplést s haldou jako datovou strukturou). Celý náš heap bude mít pevnou velikost danou při inicializaci a nebude používat žádné optimalizace nad rámec zde popsaného. Paměť našeho heapu si chceme organizovat jako souvislou posloupnost podbloků, kde každý podblok má být vždy **zarovnaný na 2 byty**. Každý podblok heapu je buď *volný* nebo *obsazený* (naalokovaný).

**Volné podbloky** mají následující strukturu:
* `+0` : `Size` [16-bit] = velikost podbloku **včetně této hlavičky**. Jelikož z výše uvedeného vyplývá, že bit 0 této položky by byl vždy 0, tak tuto nulu neukládáme. Místo toho pro nás bude mít bit 0 položky `Size` speciální význam – bude označovat, zda je podblok volný nebo obsazený: `0` = *volný*, `1` = *obsazený*.
* `+2` : `Next` [16-bit] = offset dalšího volného podbloku od začátku celého heapu – tedy volné podbloky tvoří vlastně jednosměrně vázaný seznam. Poslední volný podblok má v této položce vyplněnou hodnotu `-1`.
* `+4` : zbytek podbloku je nevyužitý a je vyplněn nulovými byty.

**Obsazené podbloky** mají následující strukturu:
* `+0` : `Size` [16-bit] = má stejný význam jako u volného podbloku, s tím rozdílem, že zde: `bit 0` : `1` = obsazený.
* `+2` : `Payload` – samotná data podbloku (náš alokátor vrací všechny tyto byty vynulované). Obsazené podbloky tedy nemají položku `Next` – místo v paměti se stane součástí `Payload`u.

Pro celý heap si pamatujeme offset prvního volného podbloku od začátku celého heapu. Na počátku se heap skládá právě z 1 volného podbloku, jehož velikost odpovídá velikosti celého heapu. Při požadavku na alokaci použijeme první dostatečně velký volný podblok na nejnižším offsetu od začátku heapu (strategie *first-fit*).

Předpokládejte následující kostru třídy v C# (nebo Java / C++):

```csharp
class Heap {
    private ushort _firstFreeOffset = 0;
    private byte[] _heap;

    public Heap(byte[] availableMemory) {
        _heap = availableMemory;
        // TODO
    }

    private ushort FindFirstFree(ushort payloadSize) {
        // TODO
    }

    private void Mark(ushort offset, bool isFree) {
        // TODO
    }

    public void SetUshort(ushort offset, ushort value) { ... }
    public ushort GetUshort(ushort offset) { ... }
    public ushort Alloc(ushort payloadSize) { ... }
    public void Free(ushort payloadOffset) { ... }
}
```

Metody `SetUshort` a `GetUshort` **ne**programujte, ale naopak je vhodně využijte ve svém kódu. Metoda `SetUshort` na `offset` od začátku heapu uloží `value` v little endian pořadí. Metoda `GetUshort` vrátí 16-bitovou hodnotu uloženou na heapu od daného `offset`u.

Metody `Alloc` a `Free` **ne**programujte – tyto metody bude programovat někdo jiný s využitím vašich metod.

**Úkoly:**
1. Doplňte implementaci konstruktoru, který inicializuje prázdný heap.
2. Napište implementaci metody `FindFirstFree`, která vrátí offset prvního volného podbloku vhodné velikosti. Stav podbloku tato funkce nijak nemění.
3. Napište implementaci metody `Mark`, která očekává, že na `offset`u je platný podblok haldy, a změní jeho stav na „obsazený“ nebo „volný“ dle parametru `isFree`. Funkce nebude manipulovat s položkou `Next`.
4. Předpokládejte, že jsme pro náš heap dostali k dispozici 22 bytů – tato paměť je předem vyplněna nulovými byty. Předpokládejte, že provedeme s heapem následující operace:
   ```
   A = Alloc(2)
   B = Alloc(4)
   C = Alloc(2)
   Free(B)
   ```
   Napište hexdump 22 bytů paměti konečného stavu heapu po provedení všech těchto operací.

> **Tvé řešení:**
> 
> 
> 

---

## Úloha 7: Ukládání dat v binárním souboru (MFF termín Podzim 2025 – 8. 9. 2025)

*Zdroj: [podzim-2025.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/podzim-2025.pdf) (Úloha 2)*

Aplikace ukládá svá data do binárního souboru:

Logicky soubor obsahuje *uzly*. Každý uzel obsahuje stejnou sadu *atributů*. Typy atributů jsou určeny *hlavičkou* souboru umístěnou na jeho začátku, která se skládá ze dvou bajtů udávajících počet atributů (v příkladu 6), následovaných typy atributů, kódovanými jedním bajtem pro každý atribut:

```csharp
enum AttrType { TUInt16 = 0x48, TLink = 0x4C, TString = 0x53, TSInt16 = 0x68 };
```

Vícebajtová čísla uložená v souboru jsou vždy v **big-endian** pořadí. Bezprostředně za hlavičkou se nachází *kořenový uzel*. Každý uzel začíná dvěma bajty obsahujícími délku dat uzlu v bajtech. Data uzlu obsahují hodnoty atributů, kódované podle typů atributů deklarovaných v hlavičce:
* Pro typy `TUInt16` a `TSInt16` je atribut uložen jako dva bajty obsahující 16bitové celé číslo bez znaménka nebo se znaménkem (dvojkový doplněk).
* Atributy typu `TString` jsou ASCII řetězce proměnné délky kódované jako dva bajty určující počet znaků, následované znaky (jeden bajt na znak).
* Pro `TLink` je uloženo 8 bajtů obsahujících pozici jiného uzlu v souboru.

Binární soubor je reprezentován třídou `BinaryFile`, která poskytuje metodu:

```csharp
void readBytes(long filepos, byte[] buf, int len); // Java, C#
```

1. Napište deklaraci třídy `Reader`, včetně jejích privátních dat a implementace následujících metod: Konstruktor obdrží otevřený objekt `BinaryFile` jako parametr; okamžitě načte hlavičku. Metoda `attributes` vrací počet atributů. Metoda `getType` vrací typ $i$-tého atributu, číslováno od nuly. Metoda `getRoot` vrací pozici kořenového uzlu. Metoda `readNode` vrátí nový objekt `Node` reprezentující uzel uložený na pozici `filepos`. Objekt je vracen odkazem v Java/C#. Data uzlu se načítají ze souboru pouze touto funkcí.

2. Deklarujte a implementujte privátní datové prvky a konstruktor třídy `Node`. Třída má ukládat data uzlu jako pole bajtů, tj. tak, jak jsou uložena v souboru. Navíc má obsahovat strukturu, která umožní lokalizovat libovolný atribut v konstantním čase. Konverze bajtů na celá čísla nebo řetězce se provádí pouze při volání odpovídajících metod `get...` třídy `Node`.

3. Napište implementaci následujících metod třídy `Node` pro získání hodnoty celočíselných atributů se znaménkem a bez znaménka (16bit), použijte přitom pouze vestavěné operátory zvoleného jazyka:
```csharp
int getUInt16(int i);
int getSInt16(int i);
```
Každá metoda čte $i$-tý atribut; je odpovědností volajícího zajistit, že volání odpovídá typu atributu. Typ `int` se považuje za dostatečně velký, aby obsahoval rozsah $\langle -32768, 65535 \rangle$.

> **Tvé řešení:**
> 
> 
> 

---

## Úloha 8: Semafor mezi procesy (MFF termín Jaro 2026 – 2. 2. 2026)

*Zdroj: [jaro-2026.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/jaro-2026.pdf) (Úloha 2)*

Uvažujte dva procesy běžící současně v operačním systému. Tyto procesy spolu komunikují prostřednictvím:
- Semafory (pracující přes hranice procesů)
- Implementace bufferu s kapacitou $N$, která poskytuje následující rozhraní:

```c
void buffer_push(byte ch);
byte buffer_pop();
```

Funkce `buffer_push` (volaná procesem odesílatele) a funkce `buffer_pop` (volaná procesem příjemce) jsou atomické (tj. mohou být bezpečně volány současně) a umožňují předávání bajtů přes hranice procesů (např. pomocí sdílené paměti a atomických instrukcí). Tyto funkce však neposkytují synchronizaci (vždy se vracejí okamžitě). Funkce `buffer_push` nesmí být volána, pokud je buffer plný, a funkce `buffer_pop` nesmí být volána, pokud je buffer prázdný.

Vaším úkolem není řešit vytvoření semaforů a bufferu, předpokládejte, že oba procesy mohou přistupovat k těmto objektům, jako by existovaly uvnitř těchto procesů.

1. Napište implementaci funkcí `send` a `receive` v některém z jazyků C, C++, C# nebo Java. Implementace nesmí používat žádné statické nebo globální proměnné ani žádné další knihovny kromě semaforů a výše popsaného bufferu. Implementace nesmí využívat aktivní čekání (polling). Specifikujte také počáteční stav(y) semaforu/ů (v závislosti na kapacitě bufferu $N$); buffer je na počátku prázdný.
2. Definujte invariant(y) platné pro stav(y) semaforu/ů ve vztahu k počtu platných elementů v bufferu (a jeho kapacitě $N$). Všechny tyto invarianty musí být platné po celou dobu mezi voláními funkcí `send` nebo `receive`.
3. Vysvětlete, jak se platnost invariantů mění uvnitř funkcí `send` a `receive` (např. pomocí pozměněných invariantů platných mezi jednotlivými příkazy uvnitř těchto funkcí). Pro jednoduchost předpokládejte, že tyto funkce nejsou volány zároveň.

> **Tvé řešení:**
> 
> 
> 

---

## Úloha 9: Průchod spojovým seznamem (MFF termín Léto 2026 – 22. 6. 2026)

*Zdroj: [leto-2026.pdf](file:///c:/Users/nagyl/Projects/memizy/code/courses/course-mff-informatika/bakalarske-statnice/minula-zadani/spolecna-cast/leto-2026.pdf) (Úloha 2)*

Uvažujte jednoduchý 16-bitový procesor (adresy i registry jsou 16-bitové). Procesor provádí kód, který prochází jednosměrně vázaný seznam struktur reprezentujících výskyty různých hodnot:

```c
typedef struct freq freq_t;
struct freq {
    uint16_t number;
    uint16_t count;
    freq_t *next;
};
// next je u posledniho prvku nastaveno na 0
freq_t *head;
```

Proměnná `head` je uložena v paměti na adrese `0x900a` (tj. v tomto místě je pointer na první skutečný prvek seznamu).

Sada instrukcí procesoru:
* `LI RD, imm` – `RD := imm` (načtení konstanty)
* `LW RD, offset(RS)` – `RD := memory[RS + offset]` (načtení z paměti)
* `SW RS1, offset(RS2)` – `memory[RS2 + offset] := RS1` (zápis do paměti)
* `ADD RD, RS1, RS2` – `RD := RS1 + RS2`
* `OR RD, RS1, RS2` – `RD := RS1 bitwise or RS2`
* `BEZ RS, label` – `if RS == 0: jump to label`
* `BNEZ RS, label` – `if RS != 0: jump to label`
* `JMP label` – nepodmíněný skok na label

`imm` a `offset` jsou konstanty.

Doplňte posloupnost instrukcí tak, aby v registru `R3` bylo uloženo celkové množství prvků, tj. součet položek `count` ve výše uvedené struktuře. Okomentujte využití jednotlivých registrů.

Váš kód musí být napsán obecně pro libovolný platný seznam (nesmí obsahovat pevné adresy kromě adresy hlavy `0x900a`). Kód nemá řešit přetečení při sčítání.

```asm
LI R1, 0x900a
LW R2, 0(R1)
LI R3, 0
// <-- sem doplňte vhodný kód

end:
// v registru R3 je součet položek count
```

> **Tvé řešení:**
> 
> 
> 

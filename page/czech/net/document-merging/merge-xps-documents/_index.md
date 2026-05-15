---
date: 2026-01-15
description: Naučte se, jak sloučit XPS dokumenty pomocí Aspose.Page pro .NET – krok
  za krokem průvodce pro bezproblémové slučování dokumentů.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Jak sloučit XPS dokumenty pomocí Aspose.Page pro .NET
url: /cs/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak sloučit XPS dokumenty pomocí Aspose.Page pro .NET

## Úvod

Hledáte spolehlivý způsob **jak sloučit XPS** soubory programově? V tomto tutoriálu vás provede přesné kroky ke sloučení XPS dokumentů pomocí Aspose.Page pro .NET. Ať už potřebujete spojit zprávy, faktury nebo jakékoli jiné XPS‑založené soubory, proces je jednoduchý a plně automatizovaný. Ponořme se a podívejme se, jak můžete dosáhnout čistého, sloučeného XPS výstupu pomocí několika řádků C# kódu.

## Rychlé odpovědi
- **Jaká knihovna zpracovává sloučení XPS?** Aspose.Page for .NET  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut  
- **Potřebuji licenci?** Licence je vyžadována pro produkční použití; k dispozici je bezplatná zkušební verze  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Mohu sloučit šifrované XPS soubory?** Ano – Aspose.Page dokáže zpracovat šifrované dokumenty

## Co je sloučení XPS dokumentů?
XPS (XML Paper Specification) je formát dokumentu s pevnou rozložením vytvořený společností Microsoft. Sloučení XPS souborů znamená spojení více XPS dokumentů do jediného, souvislého souboru při zachování původního rozvržení, fontů a grafiky.

## Proč použít Aspose.Page pro .NET?
- **Plná kontrola** nad procesem sloučení bez potřeby Microsoft XPS Viewer  
- **Žádné externí závislosti** – vše běží uvnitř vaší .NET aplikace  
- **Vysoký výkon** – funguje efektivně i u velkých dokumentů  
- **Cross‑platform** – kompatibilní s .NET Framework, .NET Core a .NET 5+

## Požadavky

Předtím, než začnete, ujistěte se, že máte:

- Základní znalost C# a ekosystému .NET.  
- **Aspose.Page for .NET** nainstalováno – můžete jej stáhnout [zde](https://releases.aspose.com/page/net/).  
- Jeden nebo více XPS souborů, které chcete sloučit.

## Importujte jmenné prostory

Ve vašem C# projektu importujte jmenný prostor, který vám poskytne přístup k XPS API:

```csharp
using Aspose.Page.XPS;
```

## Krok 1: Nastavte svůj projekt

Vytvořte nový C# konzolový nebo knihovní projekt ve Visual Studio, Rideru nebo ve vašem preferovaném IDE. Přidejte odkaz na Aspose.Page DLL (nebo nainstalujte NuGet balíček `Aspose.Page`). Tím získáte přístup ke třídě `XpsDocument`, která bude použita později.

## Krok 2: Inicializujte proudy

Otevřete zdrojové XPS soubory jako vstupní proudy a vytvořte výstupní proud pro sloučený dokument. Příkazy `using` zajišťují, že všechny proudy jsou po operaci správně uzavřeny.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Krok 3: Načtěte XPS dokument

Vytvořte instanci `XpsDocument` z hlavního vstupního proudu. Objekt `XpsLoadOptions` vám umožní přizpůsobit chování načítání, pokud je to potřeba.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Krok 4: Vytvořte pole XPS souborů

Připravte pole řetězců, které uvádí každý XPS soubor, který chcete sloučit. Pořadí pole určuje pořadí ve finálním dokumentu.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Krok 5: Sloučte XPS soubory

Zavolejte metodu `Merge`, předáte pole cest k souborům a výstupní proud. Aspose.Page se postará o veškeré těžké operace – spojení stránek, zachování zdrojů a zápis finálního XPS souboru.

```csharp
document.Merge(filesToMerge, outStream);
```

## Časté problémy a tipy

- **Soubor nenalezen** – Dvakrát zkontrolujte cesty v `filesToMerge`. Použití `Path.Combine` může pomoci vyhnout se chybám s oddělovači cest.  
- **Využití paměti** – Při sloučení velkého počtu souborů zvažte jejich zpracování po dávkách, aby se udržela nízká spotřeba paměti.  
- **Šifrované dokumenty** – Pokud je některý zdrojový XPS chráněn heslem, načtěte jej s odpovídajícími přihlašovacími údaji před sloučením.

## Často kladené otázky

**Q1: Mohu sloučit XPS soubory s různými velikostmi stránek?**  
A: Ano. Aspose.Page automaticky normalizuje rozměry stránek během sloučení.

**Q2: Existuje limit, kolik XPS souborů mohu spojit?**  
A: Neexistuje pevný limit, ale velmi velké kolekce mohou ovlivnit výkon; sledujte využití paměti.

**Q3: Potřebuji speciální licenci pro sloučení šifrovaných XPS dokumentů?**  
A: Pro jakoukoli funkci na úrovni produkce, včetně zpracování šifrovaných dokumentů, je vyžadována plná licence Aspose.Page.

**Q4: Jak přidám vlastní zápatí na každou stránku po sloučení?**  
A: Po sloučení můžete znovu otevřít výsledný XPS pomocí `XpsDocument` a použít kreslicí API k vložení zápatí.

**Q5: Podporuje Aspose.Page .NET Core?**  
A: Rozhodně. Knihovna je kompatibilní s .NET Core 3.1 a novějšími verzemi, stejně jako s .NET 5/6/7.

## Závěr

Nyní jste se naučili **jak sloučit XPS** dokumenty efektivně pomocí Aspose.Page pro .NET. Dodržením výše uvedených kroků můžete automatizovat konsolidaci dokumentů v jakékoli .NET aplikaci, ušetřit čas a snížit ruční úsilí. Prozkoumejte API dále, abyste mohli přidat vodoznaky, zašifrovat finální soubor nebo manipulovat s jednotlivými stránkami podle potřeby.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Page for .NET (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Přidejte položky pole pomocí Aspose.Page
linktitle: Přidat položky pole
second_title: Aspose.Page .NET API
description: Prozkoumejte, jak přidat položky pole do souborů EPS pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou manipulaci s dokumenty.
type: docs
weight: 11
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---
## Úvod

oblasti manipulace a zpracování dokumentů v .NET vyniká Aspose.Page jako mocný nástroj. Mezi jeho mnoha funkcemi je běžným požadavkem manipulace s položkami pole v souboru EPS. V tomto tutoriálu prozkoumáme krok za krokem proces přidávání položek pole pomocí Aspose.Page v prostředí .NET. Ať už jste ostřílený vývojář nebo nováček, tento průvodce vás procesem provede s jasností a přesností.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Základní znalost programování .NET.
-  Aspose.Page for .NET nainstalován. Pokud ne, můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).
- Editor kódu, jako je Visual Studio, podle příkladů.

## Import jmenných prostorů

Ve svém projektu .NET se ujistěte, že jste importovali potřebné jmenné prostory, abyste mohli využívat funkce Aspose.Page. Na začátek kódu přidejte následující řádky:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tyto jmenné prostory poskytují přístup k základním třídám a metodám potřebným pro manipulaci se soubory EPS.

## Krok 1: Inicializujte vstupní proud souboru EPS

```csharp
// Start: 3
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Vytvořte instanci PsDocument ze streamu
PsDocument document = new PsDocument(psStream);            
// Rozšířit:3
```

 Zde nastavujeme počáteční vstupní proud pro soubor EPS a vytváříme a`PsDocument` instance.

## Krok 2: Získejte metadata XMP

```csharp
// Start: 4
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, získáme nový soubor vyplněný hodnotami z komentářů k metadatům PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.GetXmpMetadata();
// Rozšíření:4
```

Načtěte metadata XMP ze souboru EPS. Pokud soubor EPS postrádá metadata XMP, vytvoří se nový s hodnotami z komentářů metadat PS.

## Krok 3: Změňte hodnoty metadat XMP

```csharp
// Start: 5
// Změňte hodnoty metadat XMP

// Přidejte ještě jeden titul. Ve výchozím nastavení bude přidán na konec pole.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Přidejte ještě jednoho tvůrce. Bude přidán do pole pomocí indexu (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// Rozšíření:5
```

Upravte metadata XMP přidáním nových názvů a tvůrců do pole.

## Krok 4: Uložte soubor EPS se změněnými metadaty XMP

```csharp
// Start: 6
// Uložte soubor EPS se změněnými metadaty XMP

// Vytvořte výstupní proud
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Uložit soubor EPS
    document.Save(outPsStream);
}
// Konec:6
```

Nakonec uložte soubor EPS s aktualizovanými metadaty XMP. Změny provedené v položkách pole se projeví ve výstupním souboru.

## Závěr

Přidání položek pole pomocí Aspose.Page v .NET je jednoduchý proces, jak je ukázáno v tomto tutoriálu. Se správnými předpoklady a podrobným průvodcem mohou vývojáři bez problémů manipulovat se soubory EPS a zajistit, aby jejich dokumenty splňovaly specifické požadavky na metadata.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi prostředími .NET?

Odpověď 1: Ano, Aspose.Page je navržena tak, aby bezproblémově fungovala se všemi prostředími .NET a poskytovala konzistentní funkce napříč platformami.

### Q2: Mohu používat Aspose.Page zdarma?

 A2: Aspose.Page nabízí bezplatnou zkušební verzi, která uživatelům umožňuje prozkoumat její funkce. Pro pokračování v používání je nutné zakoupit licenci[tady](https://purchase.aspose.com/buy).

### Q3: Jsou k dispozici dočasné licence pro Aspose.Page?

 A3: Ano, dočasné licence lze získat od[tady](https://purchase.aspose.com/temporary-license/) pro potřeby krátkodobých projektů.

### Q4: Kde najdu podporu komunity pro Aspose.Page?

A4: Pro diskuse a podporu komunity navštivte stránku[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).

### Q5: Jaká je nejnovější verze Aspose.Page pro .NET?

 A5: Chcete-li získat přístup k nejnovější verzi Aspose.Page pro .NET, podívejte se na[dokumentace](https://reference.aspose.com/page/net/).
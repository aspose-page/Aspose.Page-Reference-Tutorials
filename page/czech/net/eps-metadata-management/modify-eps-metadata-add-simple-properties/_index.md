---
title: Přidejte jednoduché vlastnosti pomocí Aspose.Page pro .NET
linktitle: Přidat jednoduché vlastnosti
second_title: Aspose.Page .NET API
description: Vylepšete soubory EPS pomocí Aspose.Page for .NET. Přidejte jednoduché vlastnosti bez námahy pro přizpůsobená metadata dokumentu.
type: docs
weight: 14
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Úvod

V oblasti manipulace a vylepšování dokumentů se Aspose.Page for .NET ukazuje jako výkonný nástroj, který vývojářům poskytuje možnost bezproblémově přidávat a upravovat metadata XMP v souborech EPS. Tento tutoriál vás provede procesem přidávání jednoduchých vlastností do souboru EPS pomocí Aspose.Page for .NET.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Page for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou aplikaci Aspose.Page for .NET. Pokud ne, můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

2.  Adresář dokumentů: Nastavte adresář pro ukládání souborů EPS. Aktualizujte`dataDir` proměnnou v poskytnutém fragmentu kódu s cestou k adresáři vašeho dokumentu.

## Import jmenných prostorů

Chcete-li začít, naimportujte potřebné jmenné prostory pro umožnění komunikace s Aspose.Page for .NET. Na začátek souboru kódu přidejte následující řádky:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Inicializujte vstupní datový proud souboru EPS

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Vytvořte instanci PsDocument ze streamu
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Získejte metadata XMP

```csharp
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, získáme nový soubor vyplněný hodnotami z komentářů metadat PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: Změňte hodnoty metadat XMP

```csharp
// Změňte hodnoty metadat XMP
DateTime now = DateTime.UtcNow;

// Přidat vlastnost Integer
xmp.Add("xmp:Intg1", new XmpValue(111));

// Přidejte vlastnost DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Přidat vlastnost Double
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Přidat vlastnost String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Krok 4: Uložte soubor EPS se změněnými metadaty XMP

```csharp
// Uložte soubor EPS se změněnými metadaty XMP

// Vytvořte výstupní proud
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Uložit soubor EPS
    document.Save(outPsStream);
}
```

## Krok 5: Zavřete FileStream

```csharp
finally
{
    psStream.Close();
}
```

Podle těchto kroků můžete bez námahy začlenit jednoduché vlastnosti do souborů EPS pomocí Aspose.Page for .NET.

## Závěr

Závěrem lze říci, že Aspose.Page for .NET se ukazuje jako neocenitelný přínos pro vývojáře, kteří se snaží vylepšit soubory EPS pomocí vlastních metadat XMP. Přidáním jednoduchých vlastností můžete upravovat a obohacovat své dokumenty tak, aby splňovaly specifické požadavky, čímž se otevírá svět možností pro manipulaci s dokumenty.

## FAQ

### Q1: Je Aspose.Page for .NET kompatibilní se všemi soubory EPS?

Odpověď 1: Aspose.Page for .NET podporuje širokou škálu souborů EPS. Kompatibilita se však může lišit v závislosti na složitosti a struktuře jednotlivých souborů.

### Q2: Mohu upravit existující metadata XMP pomocí Aspose.Page for .NET?

A2: Rozhodně! Jak je ukázáno v tomto tutoriálu, můžete snadno změnit stávající hodnoty metadat XMP nebo přidat nové, aby vyhovovaly vašim potřebám.

### Otázka 3: Existují nějaká omezení pro typy vlastností, které mohu přidat?

A3: Aspose.Page for .NET podporuje různé datové typy pro vlastnosti, včetně celých čísel, dat, dvojic a řetězců. Máte flexibilitu při výběru vhodného typu pro svá metadata.

### Q4: Jak mohu získat technickou podporu pro Aspose.Page for .NET?

 A4: Pro technickou pomoc navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) nebo prozkoumat[dokumentace](https://reference.aspose.com/page/net/) za komplexní návod.

### Q5: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

 A5: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
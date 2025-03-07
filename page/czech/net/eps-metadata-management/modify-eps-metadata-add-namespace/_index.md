---
title: Přidejte jmenný prostor s Aspose.Page pro .NET
linktitle: Přidat jmenný prostor
second_title: Aspose.Page .NET API
description: Vylepšete soubory EPS pomocí Aspose.Page for .NET. Bez námahy přidávejte jmenné prostory, upravujte metadata XMP a zlepšujte pracovní postup vývoje .NET.
weight: 13
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte jmenný prostor s Aspose.Page pro .NET

## Úvod

V dynamickém světě vývoje .NET vyniká Aspose.Page jako výkonný nástroj pro práci se soubory EPS. Aspose.Page for .NET umožňuje vývojářům bezproblémově manipulovat s metadaty XMP a poskytuje flexibilitu pro přidávání jmenných prostorů a vylepšení metadat souborů EPS.

V tomto tutoriálu se ponoříme do procesu přidávání jmenných prostorů pomocí Aspose.Page for .NET. Postupujte podle pokynů krok za krokem, od importu jmenných prostorů po uložení upraveného souboru EPS. Začněme!

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Page for .NET Library: Stáhněte a nainstalujte knihovnu z[Dokumentace Aspose.Page](https://reference.aspose.com/page/net/).

2. Vývojové prostředí: Mějte na svém počítači nastavené funkční vývojové prostředí .NET.

Nyní se pojďme vrhnout do vzrušujícího světa Aspose.Page pro .NET.

## Import jmenných prostorů

Chcete-li věci začít, musíte importovat potřebné jmenné prostory pro přístup k funkcím Aspose.Page. Můžete to udělat takto:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Inicializujte svůj projekt

Ve svém .NET projektu otevřete požadovaný soubor a inicializujte knihovnu Aspose.Page. Použijte následující fragment kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

## Krok 2: Otevřete soubor EPS

Vytvořte FileStream a otevřete soubor EPS, jak je znázorněno níže:

```csharp
// Inicializujte vstupní proud souboru EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

//Vytvořte instanci PsDocument ze streamu
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Získejte metadata XMP

Načtěte metadata XMP ze souboru EPS pomocí následujícího kódu:

```csharp
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, vytvoří se nový s hodnotami z komentářů metadat PS.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 4: Změňte metadata XMP

Podle potřeby upravte stávající metadata XMP nebo přidejte nové hodnoty. Zde je příklad přidání nového jmenného prostoru XML a vlastnosti řetězce:

```csharp
// Přidejte nový jmenný prostor XML "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Přidejte novou vlastnost řetězce do nového jmenného prostoru.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## Krok 5: Uložte soubor EPS

Uložte soubor EPS s aktualizovanými metadaty XMP pomocí následujícího kódu:

```csharp
// Vytvořte výstupní proud
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Uložit soubor EPS
    document.Save(outPsStream);
}
```

## Závěr

Gratulujeme! Úspěšně jste přidali jmenné prostory do souboru EPS pomocí Aspose.Page for .NET. Tato výkonná knihovna otevírá svět možností pro manipulaci s metadaty XMP a poskytuje bezproblémový zážitek pro vývojáře pracující se soubory EPS.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi verzemi .NET?

Odpověď 1: Aspose.Page for .NET je kompatibilní s různými verzemi rozhraní .NET, což zajišťuje flexibilitu pro vývojáře.

### Q2: Mohu použít Aspose.Page k extrahování metadat ze souborů EPS?

A2: Rozhodně! Aspose.Page umožňuje extrahovat a upravovat metadata XMP ze souborů EPS bez námahy.

### Q3: Kde najdu další podporu nebo pomoc?

 A3: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.

### Q4: Je k dispozici bezplatná zkušební verze pro Aspose.Page?

 A4: Ano, můžete prozkoumat bezplatnou zkušební verzi Aspose.Page[tady](https://releases.aspose.com/).

### Q5: Jak mohu získat dočasnou licenci pro Aspose.Page?

 A5: Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testovací účely.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

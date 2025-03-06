---
title: Přidejte pojmenovanou hodnotu pomocí Aspose.Page
linktitle: Přidat pojmenovanou hodnotu
second_title: Aspose.Page .NET API
description: Naučte se přidávat pojmenované hodnoty do souborů EPS v .NET pomocí Aspose.Page. Tento komplexní návod vás provede procesem krok za krokem.
weight: 12
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte pojmenovanou hodnotu pomocí Aspose.Page

## Úvod

V oblasti zpracování dokumentů pomocí .NET vyniká Aspose.Page jako výkonný nástroj pro práci se soubory EPS. Aspose.Page umožňuje vývojářům manipulovat s metadaty XMP a usnadňuje úkoly, jako je přidávání pojmenovaných hodnot. Tento tutoriál vás krok za krokem provede procesem přidávání pojmenovaných hodnot do souboru EPS pomocí Aspose.Page.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Nainstalované integrované vývojové prostředí (IDE), jako je Visual Studio.
-  Aspose.Page pro knihovnu .NET. Pokud není nainstalován, můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).

## Import jmenných prostorů

Nejprve importujme potřebné jmenné prostory do vašeho kódu C#. Tyto jmenné prostory jsou životně důležité pro přístup k funkcím poskytovaným Aspose.Page:

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

 Počáteční krok zahrnuje inicializaci vstupního proudu pro soubor EPS. Nahradit`"Your Document Directory"` s cestou k vašemu adresáři dokumentů:

```csharp
// Start: 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Získejte metadata XMP

Načtěte metadata XMP ze souboru EPS. Pokud soubor EPS postrádá metadata XMP, bude vytvořen nový, naplněný hodnotami z komentářů k metadatům PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: Změňte hodnoty metadat XMP

Nyní provedeme změny v metadatech XMP. V tomto příkladu přidáme pojmenovanou hodnotu do struktury "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Krok 4: Uložte soubor EPS se změněnými metadaty XMP

Uložte soubor EPS s aktualizovanými metadaty XMP. Vytvořte výstupní proud a uložte upravený soubor EPS:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Závěr

Gratulujeme! Úspěšně jste přidali pojmenovanou hodnotu do souboru EPS pomocí Aspose.Page v .NET. Tento tutoriál vás provede základními kroky a ukáže jednoduchost a efektivitu Aspose.Page při manipulaci s dokumenty.

## FAQ

### Q1: Je Aspose.Page kompatibilní s různými verzemi souborů EPS?

A1: Aspose.Page podporuje různé verze souborů EPS, což zajišťuje kompatibilitu s širokou škálou dokumentů.

### Q2: Mohu použít Aspose.Page pro komerční projekty?

 Odpověď 2: Ano, Aspose.Page je dodáván s komerční licencí a můžete si ji zakoupit[tady](https://purchase.aspose.com/buy).

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Page?

 A3: Ano, můžete prozkoumat Aspose.Page s bezplatnou zkušební verzí[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat podporu nebo se spojit s komunitou Aspose?

 A4: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) získat podporu a spojit se s komunitou.

### Q5: Co je dočasná licence a jak ji mohu získat?

 A5: Pokud potřebujete dočasnou licenci pro účely testování nebo hodnocení, můžete si ji zakoupit[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

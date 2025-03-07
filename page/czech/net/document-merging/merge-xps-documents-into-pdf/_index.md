---
title: Sloučit dokumenty XPS do PDF pomocí Aspose.Page pro .NET
linktitle: Sloučit dokumenty XPS do PDF
second_title: Aspose.Page .NET API
description: Bez námahy slučujte dokumenty XPS do vysoce kvalitních souborů PDF pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro hladký převod dokumentů.
weight: 11
url: /cs/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sloučit dokumenty XPS do PDF pomocí Aspose.Page pro .NET

## Úvod

neustále se vyvíjejícím prostředí zpracování dokumentů se Aspose.Page for .NET ukazuje jako výkonný nástroj pro bezproblémové slučování dokumentů XPS do formátu PDF. Tento tutoriál vás provede celým procesem a rozebere každý krok, abyste zajistili hladké a efektivní provedení.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).

- Soubory dokumentů: Mějte dokument XPS (`input.xps`) připravené ve vámi určeném adresáři.

## Import jmenných prostorů

Ve svém projektu .NET zahrňte potřebné jmenné prostory pro práci s Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Tento krok zajistí, že budete mít přístup ke třídám a metodám požadovaným pro převod dokumentu.

## Krok 1: Inicializujte streamy

```csharp
// Start: 3
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Inicializujte výstupní proud PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Inicializujte vstupní proud XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Rozšířit:3
```

Tento krok zahrnuje nastavení vstupních a výstupních datových proudů pro soubory XPS a PDF. Ujistěte se, že jsou použity správné cesty a názvy souborů.

## Krok 2: Načtěte dokument XPS

```csharp
// Start: 4
// Načtěte dokument XPS ze streamu
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// nebo načíst dokument XPS přímo ze souboru. Pak není potřeba žádný xpsStream.
//XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// Rozšíření:4
```

 Zde načteme dokument XPS do`XpsDocument` objekt, připravuje jej k dalšímu zpracování.

## Krok 3: Inicializujte možnosti uložení

```csharp
// Start: 5
// Inicializujte objekt voleb s potřebnými parametry.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Rozšíření:5
```

 Přizpůsobte si`PdfSaveOptions` objekt na základě vašich preferencí, zadáním parametrů, jako je komprese obrazu, komprese textu a čísla stránek.

## Krok 4: Vytvořte vykreslovací zařízení

```csharp
// Start: 6
// Vytvořte vykreslovací zařízení pro formát PDF
PdfDevice device = new PdfDevice(pdfStream);
// Konec:6
```

 The`PdfDevice` je nástroj zodpovědný za vykreslení dokumentu XPS do formátu PDF.

## Krok 5: Uložte dokument

```csharp
// Start: 7
document.Save(device, options);
// Konec:7
```

Nakonec uložte dokument pomocí vykreslovacího zařízení a zadaných možností.

## Závěr

Gratulujeme! Úspěšně jste sloučili dokumenty XPS do PDF pomocí Aspose.Page for .NET. Tento bezproblémový proces zajišťuje zachování kvality a formátování dokumentu.

## FAQ

### Q1: Mohu sloučit více souborů XPS do jednoho PDF?

 A1: Ano, můžete. Jednoduše upravte`PageNumbers` parametr v`PdfSaveOptions` zahrnout požadované stránky z různých souborů XPS.

### Q2: Je k dispozici dočasná licence pro Aspose.Page for .NET?

 A2: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testovací účely.

### Q3: Existují nějaká omezení velikosti souboru při použití Aspose.Page pro převod dokumentů?

Odpověď 3: Aspose.Page for .NET neukládá přísná omezení velikosti souboru, ale optimálního výkonu je dosaženo s přiměřenou velikostí souborů.

### Q4: Mohu si výstupní PDF dále přizpůsobit, například přidáním vodoznaků nebo anotací?

Odpověď 4: Ano, Aspose.Page for .NET poskytuje rozsáhlé funkce pro manipulaci s PDF. Pokročilé možnosti přizpůsobení naleznete v dokumentaci.

### Q5: Podporuje Aspose.Page for .NET vývoj napříč platformami?

Odpověď 5: Ano, Aspose.Page for .NET je navržena tak, aby bezproblémově fungovala na různých platformách.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

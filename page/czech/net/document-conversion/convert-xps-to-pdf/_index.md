---
title: Převeďte XPS do PDF pomocí Aspose.Page pro .NET
linktitle: Převést XPS do PDF
second_title: Aspose.Page .NET API
description: Snadno převádějte XPS do PDF v .NET pomocí Aspose.Page. Stáhněte si knihovnu, prozkoumejte dokumentaci a získejte bezplatnou zkušební verzi.
weight: 11
url: /cs/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převeďte XPS do PDF pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu se ponoříme do procesu převodu dokumentů XPS (XML Paper Specification) do PDF (Portable Document Format) pomocí výkonné knihovny Aspose.Page for .NET. Aspose.Page for .NET poskytuje robustní sadu funkcí pro práci se soubory XPS, což umožňuje vývojářům bezproblémově je převádět do formátu PDF s různými možnostmi přizpůsobení.

## Předpoklady

Než se pustíme do této konverzní cesty, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout z[Dokumentace Aspose.Page](https://reference.aspose.com/page/net/).

- Vývojové prostředí: Nastavte vývojové prostředí .NET pomocí sady Visual Studio nebo jiného kompatibilního IDE.

- Dokument XPS: Připravte dokument XPS, který chcete převést do PDF. Může to být váš ukázkový soubor XPS uložený v určeném adresáři.

## Import jmenných prostorů

Než se ponoříme do kódu, importujme potřebné jmenné prostory, abychom zpřístupnili funkce Aspose.Page for .NET v našem kódu:

```csharp
using Aspose.Page.XPS;
```

## Krok 1: Inicializujte adresář dokumentů

```csharp
string dataDir = "Your Document Directory";
```

Nahraďte "Your Document Directory" cestou k adresáři obsahujícímu váš dokument XPS.

## Krok 2: Inicializujte PDF a XPS streamy

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Otevřete streamy pro výstupní soubor PDF i vstupní soubor XPS. Ujistěte se, že máte nastavené správné cesty k souboru.

## Krok 3: Načtěte dokument XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Načtěte dokument XPS pomocí knihovny Aspose.Page for .NET.

## Krok 4: Inicializujte možnosti uložení PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Nastavte možnosti uložení PDF, včetně parametrů, jako je úroveň kvality JPEG, komprese obrazu, komprese textu a konkrétní čísla stránek, která se mají zahrnout.

## Krok 5: Vytvořte zařízení pro vykreslování PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Vytvořte vykreslovací zařízení pro formát PDF pomocí knihovny Aspose.Page for .NET.

## Krok 6: Uložte dokument do PDF

```csharp
document.Save(device, options);
```

Uložte dokument XPS do PDF pomocí zadaného vykreslovacího zařízení a možností.

## Závěr

Gratulujeme! Úspěšně jste převedli dokument XPS do PDF pomocí Aspose.Page for .NET. Tato všestranná knihovna poskytuje vývojářům výkonnou sadu nástrojů pro snadnou manipulaci s různými formáty dokumentů.

## FAQ

### Q1: Mohu převést více souborů XPS do jednoho PDF pomocí Aspose.Page for .NET?

Odpověď 1: Ano, můžete procházet více soubory XPS a pomocí stejných kroků je sloučit do jednoho PDF.

### Q2: Existují další výstupní formáty podporované Aspose.Page pro .NET?

Odpověď 2: Ano, Aspose.Page for .NET podporuje různé výstupní formáty, včetně TIFF, JPEG, PNG a dalších.

### Otázka 3: Jak mohu přizpůsobit vzhled převedeného dokumentu PDF?

A3: Můžete vyladit parametry objektu voleb, jako je komprese obrazu a komprese textu, abyste dosáhli požadovaného vzhledu.

### Q4: Je k dispozici zkušební verze pro Aspose.Page pro .NET?

 A4: Ano, můžete prozkoumat možnosti Aspose.Page pro .NET získáním bezplatné zkušební verze od[tady](https://releases.aspose.com/).

### Q5: Kde mohu získat podporu komunity pro Aspose.Page for .NET?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za komunitní diskuse a podporu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

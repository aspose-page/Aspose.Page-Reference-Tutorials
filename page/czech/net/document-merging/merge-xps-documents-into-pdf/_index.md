---
date: 2026-01-20
description: Jednoduše přidejte čísla stránek do PDF při slučování dokumentů XPS do
  vysoce kvalitních PDF pomocí Aspose.Page pro .NET. Postupujte podle našeho krok‑za‑krokem
  průvodce pro převod XPS na PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Přidat čísla stránek PDF – Sloučit XPS do PDF pomocí Aspose.Page
url: /cs/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání číslování stránek PDF – Sloučení XPS do PDF pomocí Aspose.Page

## Úvod

Pokud potřebujete **přidat číslování stránek PDF** při sloučení XPS souborů, Aspose.Page pro .NET proces značně usnadní. V tomto tutoriálu vás provedeme kompletním, připraveným pro produkční nasazení příkladem, který převádí XPS dokument na vysoce kvalitní PDF, umožňuje řídit kompresi obrázků a automaticky vkládá číslování stránek do finálního PDF. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do libovolného C# projektu.

## Rychlé odpovědi
- **Mohu přidat číslování stránek při sloučení XPS do PDF?** Ano – vlastnost `PdfSaveOptions.PageNumbers` dělá právě to.  
- **Která knihovna provádí konverzi?** Aspose.Page pro .NET.  
- **Potřebuji licenci pro produkční použití?** Je vyžadována platná licence Aspose.Page; dočasná licence je k dispozici pro testování.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6+.  
- **Je možné získat výstup obrázků ve vysoké kvalitě?** Rozhodně – nastavte `JpegQualityLevel` na 100 a vyberte `PdfImageCompression.Jpeg`.

## Předpoklady

Před zahájením tutoriálu se ujistěte, že máte připraveny následující předpoklady:

- Aspose.Page pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).

- Soubory dokumentu: Mějte XPS dokument (`input.xps`) připravený ve vámi určeném adresáři.

## Importování jmenných prostorů

Váš .NET projekt musí zahrnovat potřebné jmenné prostory pro práci s Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Tento krok zajišťuje, že máte přístup ke třídám a metodám potřebným pro konverzi dokumentu.

## Jak přidat číslování stránek PDF při sloučení XPS dokumentů

Kolekce `PdfSaveOptions.PageNumbers` vám umožňuje přesně určit, které stránky (nebo rozsahy stránek) se mají objevit ve výstupním PDF. Po naplnění požadovanými čísly stránek Aspose.Page automaticky vloží správné číslování.

### Krok 1: Inicializace streamů

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Tento krok zahrnuje nastavení vstupních a výstupních streamů pro soubory XPS a PDF. Ujistěte se, že jsou použity správné cesty a názvy souborů.

### Krok 2: Načtení XPS dokumentu

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Zde načteme XPS dokument do objektu `XpsDocument`, připravujeme jej pro další zpracování.

### Krok 3: Inicializace možností uložení (sloučení xps do pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Přizpůsobte objekt `PdfSaveOptions` podle svých preferencí, specifikujte parametry jako komprese obrázků, komprese textu a **čísla stránek**, která chcete, aby se objevila ve finálním PDF. Nastavení `JpegQualityLevel` na 100 zajišťuje **vysoce kvalitní PDF obrázky**.

### Krok 4: Vytvoření renderovacího zařízení

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` je nástroj odpovědný za renderování XPS dokumentu do formátu PDF.

### Krok 5: Uložení dokumentu (c# xps do pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Nakonec dokument uložíme pomocí renderovacího zařízení a specifikovaných možností. Výstupní PDF bude obsahovat vybrané stránky s automaticky přidaným číslováním.

## Proč použít Aspose.Page pro tuto konverzi?

- **Spolehlivost** – Zpracovává složité funkce XPS bez ztráty věrnosti.  
- **Výkon** – Zpracování založené na streamech zabraňuje načítání celých souborů do paměti.  
- **Flexibilita** – Jemná kontrola kvality obrázků, komprese a číslování stránek.  
- **Cross‑platform** – Funguje na Windows, Linuxu a macOS s .NET Core.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Výstupní PDF je prázdný** | Ověřte, že cesta k souboru XPS je správná a že soubor není poškozený. |
| **Číslování stránek se nezobrazuje** | Ujistěte se, že `PageNumbers` je nastaven na správné nulové indexy stránek (např. `new int[] {1,2,6}`). |
| **Obrázky nízké kvality** | Zvyšte `JpegQualityLevel` a vyberte `PdfImageCompression.Jpeg`. |
| **Velké soubory XPS způsobují tlak na paměť** | Zpracovávejte XPS v menších částech nebo zvyšte limit paměti aplikace. |

## Často kladené otázky

### Q1: Mohu sloučit více XPS souborů do jednoho PDF?

Ano, můžete. Jednoduše upravte parametr `PageNumbers` v `PdfSaveOptions`, aby zahrnoval požadované stránky z různých XPS souborů, nebo načtěte každý XPS sekvenčně a zavolejte `document.Save` na stejném `PdfDevice`.

### Q2: Je k dispozici dočasná licence pro Aspose.Page pro .NET?

Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/) pro testovací účely.

### Q3: Existují nějaká omezení velikosti souboru při použití Aspose.Page pro konverzi dokumentů?

Aspose.Page pro .NET neklade přísná omezení na velikost souboru, ale optimální výkon je dosažen u rozumně velkých souborů. U velmi velkých XPS dokumentů zvažte zpracování v streamech, aby se snížila spotřeba paměti.

### Q4: Mohu dále přizpůsobit výstupní PDF, například přidáním vodoznaků nebo anotací?

Ano, Aspose.Page pro .NET poskytuje rozsáhlé funkce pro manipulaci s PDF. Po konverzi můžete použít knihovnu Aspose.PDF k přidání vodoznaků, anotací nebo dalších vylepšení.

### Q5: Podporuje Aspose.Page pro .NET vývoj napříč platformami?

Ano, Aspose.Page pro .NET je navržen tak, aby bez problémů fungoval na různých platformách, včetně Windows, Linuxu a macOS, při použití s .NET Core nebo .NET 5/6.

**Poslední aktualizace:** 2026-01-20  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
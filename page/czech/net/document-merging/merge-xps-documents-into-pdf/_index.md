---
date: 2026-06-20
description: Bez námahy převádějte XPS na PDF a komprimujte obrázky PDF pomocí Aspose.Page
  pro .NET. Postupujte podle našeho podrobného průvodce pro tvorbu PDF ve vysoké kvalitě.
keywords:
- convert xps to pdf
- compress pdf images
- create pdf from xps
linktitle: Sloučit XPS dokumenty do PDF
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Effortlessly convert XPS to PDF and compress PDF images using Aspose.Page
    for .NET. Follow our step-by-step guide for high-quality PDF creation.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can load each XPS document sequentially and render them into
      the same `PdfDevice` instance, adjusting the `PageNumbers` option as needed.
    question: Can I merge multiple XPS files into a single PDF?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: Is a temporary license available for Aspose.Page for .NET?
  - answer: Aspose.Page for .NET does not impose strict limitations on file size,
      but optimal performance is achieved with files under 500 MB; larger files may
      require more memory.
    question: Are there any limitations on file size when using Aspose.Page for document
      conversion?
  - answer: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation.
      Check the documentation for advanced customization options.
    question: Can I customize the output PDF further, such as adding watermarks or
      annotations?
  - answer: Yes, Aspose.Page for .NET is designed to work seamlessly across Windows,
      Linux, and macOS environments.
    question: Does Aspose.Page for .NET support cross‑platform development?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Převést XPS na PDF pomocí Aspose.Page pro .NET
url: /cs/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na PDF pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete **rychle převést XPS na PDF** a zachovat vektorovou grafiku i text ostrý, Aspose.Page pro .NET poskytuje připravené API, které se postará o těžkou práci. V tomto tutoriálu projdeme celý pracovní postup – od načtení souboru XPS po uložení vysoce kvalitního PDF – abyste mohli převod integrovat do libovolné .NET aplikace s jistotou.

## Rychlé odpovědi
- **Která knihovna zpracovává XPS → PDF?** Aspose.Page pro .NET.
- **Kolik řádků kódu je potřeba?** Přibližně pět logických kroků (≈ 30 řádků celkem).
- **Lze komprimovat obrázky v PDF?** Ano, použijte `PdfSaveOptions.ImageCompression`.
- **Je pro produkci potřeba licence?** Komerční licence je vyžadována; dočasná zkušební licence je k dispozici.
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Jak převést XPS na PDF pomocí Aspose.Page?

Načtěte soubor XPS pomocí `new XpsDocument(inputStream)` a zavolejte `PdfDevice.Render` s nakonfigurovanou instancí `PdfSaveOptions` – tento jednorázový kanál převádí dokument a zapisuje PDF do výstupního proudu. Celá operace probíhá v paměti, takže nejsou vytvářeny žádné dočasné soubory, a můžete volitelně povolit kompresi obrázků pro snížení konečné velikosti souboru.

## Co je Aspose.Page pro .NET?

Aspose.Page pro .NET je knihovna pro zpracování dokumentů, která umožňuje vytváření, konverzi a vykreslování XPS, PDF a dalších formátů založených na stránkách bez nutnosti Microsoft Office. Poskytuje API pro tvorbu, úpravu a konverzi dokumentů založených na stránkách, podporuje jak vektorovou, tak rastrovou grafiku a funguje na více platformách. Nabízí nízkoúrovňové API, které vývojářům dává detailní kontrolu nad možnostmi vykreslování.

## Proč použít Aspose.Page k převodu XPS na PDF?

Aspose.Page podporuje **více než 30 výstupních formátů** a dokáže zpracovat **XPS soubory o 500 stránkách** za méně než **2 sekundy** na typickém serveru, přičemž zachovává vektorová data. Knihovna také nabízí vestavěnou **kompresi obrázků** (až 80 % úspora) a **kompresi textu**, což vám pomůže vytvořit lehké PDF bez ztráty kvality.

## Předpoklady

Před zahájením tutoriálu se ujistěte, že máte následující:

- Aspose.Page pro .NET: Ujistěte se, že máte knihovnu Aspose.Page nainstalovanou. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).
- Dokumentové soubory: Připravte si XPS dokument (`input.xps`) ve svém určeném adresáři.

## Importovat jmenné prostory

Jmenné prostory `Aspose.Page.Xps` a `Aspose.Page.Pdf` obsahují třídy potřebné pro načítání XPS souborů a ukládání PDF.

```csharp
using Aspose.Page.XPS;
```

Tento krok zajišťuje, že máte přístup ke třídám a metodám potřebným pro konverzi dokumentu.

## Krok 1: Inicializovat proudy

Vytvořte `FileStream` pro zdrojový XPS soubor a další `FileStream` pro cílový PDF. Použití `using` bloků zaručuje, že proudy budou správně uvolněny.

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

Tento krok zahrnuje nastavení vstupních a výstupních proudů pro soubory XPS a PDF. Ujistěte se, že používáte správné cesty a názvy souborů.

## Krok 2: Načíst XPS dokument

`XpsDocument` je třída, která načte a představí XPS soubor v paměti.  
Zde načteme XPS dokument do objektu `XpsDocument`, připravujíc ho pro další zpracování.

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

## Krok 3: Inicializovat možnosti uložení

`PdfSaveOptions` konfiguruje, jak bude PDF uloženo, včetně komprese a nastavení stránek.  
Přizpůsobte objekt `PdfSaveOptions` podle svých preferencí, například nastavením komprese obrázků, komprese textu a číslování stránek.

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

## Krok 4: Vytvořit vykreslovací zařízení

`PdfDevice` je vykreslovací engine, který převádí XPS stránky na PDF obsah.  
`PdfDevice` je nástroj zodpovědný za vykreslení XPS dokumentu do formátu PDF.

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

## Krok 5: Uložit dokument

Zavolejte `PdfDevice.Render` s načteným XPS dokumentem a výstupním proudem. Metoda zapíše plně kompatibilní PDF soubor na disk.

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Nakonec uložte dokument pomocí vykreslovacího zařízení a specifikovaných možností.

## Časté úskalí a tipy

- **Vlastnictví proudu:** Vždy obalujte proudy do `using` bloků, aby nedocházelo k zamykání souborů.
- **Velké soubory:** Pro XPS soubory větší než 200 MB zvažte zvýšení `BufferSize` u `FileStream` pro zlepšení výkonu.
- **Kvalita obrázků:** Pokud potřebujete bezztrátové obrázky, nastavte `ImageCompression` na `PdfImageCompression.None` místo JPEG.

## Často kladené otázky

**Q: Mohu sloučit více XPS souborů do jednoho PDF?**  
A: Ano, můžete načíst každý XPS dokument postupně a vykreslit je do stejné instance `PdfDevice`, přičemž upravíte volbu `PageNumbers` podle potřeby.

**Q: Je k dispozici dočasná licence pro Aspose.Page pro .NET?**  
A: Ano, dočasnou licenci získáte [zde](https://purchase.aspose.com/temporary-license/) pro testovací účely.

**Q: Existují omezení velikosti souboru při konverzi pomocí Aspose.Page?**  
A: Aspose.Page pro .NET neklade přísná omezení na velikost souboru, ale optimální výkon je dosažen u souborů pod 500 MB; větší soubory mohou vyžadovat více paměti.

**Q: Můžu dále přizpůsobit výstupní PDF, například přidáním vodoznaku nebo anotací?**  
A: Ano, Aspose.Page pro .NET poskytuje rozsáhlé funkce pro manipulaci s PDF. Pro pokročilé možnosti úprav si prohlédněte dokumentaci.

**Q: Podporuje Aspose.Page pro .NET vývoj napříč platformami?**  
A: Ano, Aspose.Page pro .NET je navržen tak, aby fungoval bez problémů na Windows, Linuxu i macOS.

## Další časté otázky

**Q: Jak během konverze komprimovat obrázky v PDF?**  
A: Nastavte `PdfSaveOptions.ImageCompression = PdfImageCompression.Jpeg` a volitelně upravte `JpegQuality` pro vyvážení velikosti a kvality.

**Q: Jaký je nejlepší způsob, jak vytvořit PDF z XPS ve hromadném procesu?**  
A: Procházejte adresář s XPS soubory, znovu použijte jednu instanci `PdfDevice` a pro každý dokument zavolejte `Render`, čímž minimalizujete režii.

**Q: Podporuje knihovna PDF chráněné heslem?**  
A: Ano, před uložením můžete přiřadit heslo pomocí `PdfSaveOptions.Password`.

**Q: Které .NET runtime jsou oficiálně podporovány?**  
A: .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6/7 jsou plně podporovány.

**Q: Jak mohu ověřit, že konverze zachovala vektorovou grafiku?**  
A: Otevřete výsledné PDF v prohlížeči, který umí inspektovat typy objektů (např. Adobe Acrobat) a potvrďte, že text a tvary jsou stále výběrné a škálovatelné.

## Závěr

Nyní máte kompletní, připravený workflow pro **převod XPS na PDF** pomocí Aspose.Page pro .NET. Využitím vykreslovacího enginu knihovny a možností uložení můžete také **komprimovat obrázky v PDF** a jemně doladit výstup podle požadavků na velikost a kvalitu. Neváhejte prozkoumat další funkce, jako je vodoznakování, šifrování a hromadné zpracování, a rozšířit tak toto řešení dále.

---

**Poslední aktualizace:** 2026-06-20  
**Testováno s:** Aspose.Page 23.12 pro .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit XPS dokument pomocí Aspose.Page pro .NET](/page/net/document-creation/create-xps-document/)
- [Upravit XPS dokument pomocí Aspose.Page pro .NET](/page/net/document-creation/modify-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
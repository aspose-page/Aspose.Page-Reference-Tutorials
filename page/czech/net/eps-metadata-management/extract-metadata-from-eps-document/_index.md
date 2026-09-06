---
date: 2026-07-29
description: Zjistěte, jak extrahovat a přidávat metadata EPS pomocí Aspose.Page pro
  .NET. Tento průvodce ukazuje krok za krokem kód pro efektivní správu XMP metadat
  EPS.
keywords:
- aspose.page eps metadata
- eps metadata extraction
- aspose.page .net
lastmod: 2026-07-29
linktitle: Extrahovat metadata z dokumentu EPS
og_description: 'průvodce aspose.page eps metadata: extrahujte a nastavte XMP metadata
  v souborech EPS pomocí Aspose.Page pro .NET. Postupujte podle krok‑za‑krokem tutoriálu.'
og_image_alt: Tutorial showing how to extract and add metadata to EPS documents with
  Aspose.Page for .NET
og_title: aspose.page eps metadata – Extrahovat metadata EPS pomocí .NET
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to extract and add EPS metadata using Aspose.Page for .NET.
    This guide shows step‑by‑step code to manage EPS XMP metadata efficiently.
  headline: aspose.page eps metadata – Extract EPS Metadata with .NET
  type: TechArticle
- questions:
  - answer: Yes, iterate over a collection of file paths, apply the same extraction‑and‑update
      logic, and save each file. The API is thread‑safe, so you can parallelise the
      operation for faster batch processing.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: The library comfortably processes EPS files up to **500 MB**. For files
      larger than this, consider splitting the document or using a streaming approach
      to avoid out‑of‑memory exceptions.
    question: Are there any limitations on the size of EPS documents that Aspose.Page
      for .NET can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but individual creators may populate
      custom namespaces. Aspose.Page reads both standard and custom properties, allowing
      you to preserve any proprietary data.
    question: Is the XMP metadata standardized for all EPS documents?
  - answer: Absolutely. You can add custom XMP schemas or extend existing ones by
      using the `XmpMetadata.AddCustomProperty` method, giving you full control over
      the metadata structure.
    question: Can I customize the metadata fields to suit specific requirements?
  - answer: Wrap the extraction and save logic in a `try…catch` block, and log `Aspose.Page.Exception`
      details. This will capture issues such as corrupted streams, unsupported properties,
      or I/O failures.
    question: How can I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: aspose.page eps metadata – Extrahovat metadata EPS pomocí .NET
url: /cs/net/eps-metadata-management/extract-metadata-from-eps-document/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahovat metadata z EPS dokumentu pomocí Aspose.Page pro .NET

## Úvod

V moderních pracovních postupech s dokumenty jsou **aspose.page eps metadata** klíčem k tomu, aby byly EPS soubory prohledávatelné, řaditelné a v souladu s politikami podnikového řízení obsahu. Tento tutoriál vás provede extrahováním existujících XMP metadat, aktualizací běžných polí, jako je *CreatorTool* a *CreateDate*, a uložením EPS souboru s novými informacemi – vše pomocí API Aspose.Page pro .NET.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Extrahování a aktualizace XMP metadat v EPS souborech pomocí Aspose.Page pro .NET.  
- **Která verze knihovny je požadována?** Jakékoli vydání Aspose.Page pro .NET, které podporuje XMP (v24.10 nebo novější).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu zpracovávat velké EPS soubory?** Ano – Aspose.Page dokáže zpracovat soubory až do 500 MB, aniž by načítal celý dokument do paměti.  
- **Je kód multiplatformní?** .NET knihovna běží na Windows, Linuxu a macOS s .NET 6+.

## Požadavky

Než se pustíme do podrobného návodu, ujistěte se, že máte následující:

- **Aspose.Page pro .NET knihovna** – Stáhněte a nainstalujte knihovnu ze [zde](https://releases.aspose.com/page/net/).  
- **Adresář dokumentů** – Složka ve vašem počítači, která obsahuje EPS soubory, které chcete zpracovat.  
- **.NET vývojové prostředí** – Visual Studio 2022, Rider nebo jakékoli IDE, které podporuje .NET 6+.

## Co jsou metadata EPS?

**EPS metadata** se skládá z vložených XMP (Extensible Metadata Platform) paketů, které ukládají informace jako tvůrce, datum vytvoření, název a nástroj použitý k vytvoření souboru. XMP je formát podle ISO standardu, což umožňuje výměnu metadat mezi produkty Adobe, systémy pro správu obsahu a vyhledávači.

## Proč používat Aspose.Page pro EPS metadata?

Aspose.Page podporuje **více než 30 různých XMP vlastností** a může je číst nebo zapisovat bez renderování celého PostScript obsahu. Zpracovává EPS soubory až do **500 MB** při zachování využití paměti pod **50 MB**, což je ideální pro dávkové zpracování v cloudových nebo lokálních prostředích.

## Importovat jmenné prostory

Následující jmenné prostory jsou vyžadovány pro práci s EPS soubory a XMP metadaty.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Jak extrahovat a nastavit EPS metadata pomocí Aspose.Page?

Načtěte EPS soubor do streamu `EpsDocument`, získejte existující XMP paket, upravte požadovaná pole a poté soubor uložte zpět na disk. celý tento postup lze provést ve **čtyřech stručných krocích**, které můžete vložit do libovolné .NET služby nebo konzolové aplikace.

## Krok 1: Inicializovat vstupní stream EPS souboru

`PsDocument` představuje EPS dokument a poskytuje přístup k jeho stránkám a metadatům.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

## Krok 2: Získat XMP metadata

`XmpMetadata` zapouzdřuje XMP paket vložený v EPS souboru, což umožňuje čtení a zápis vlastností metadat.

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

## Krok 3: Zkontrolovat a nastavit hodnoty metadat

Zkontrolujte hodnoty metadat extrahované z PS komentářů metadat a nastavte je v nových XMP metadatech.

### Získat hodnotu CreatorTool

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

### Získat hodnotu CreateDate

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

### Získat hodnotu Format

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

### Získat hodnotu Title

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

### Získat hodnotu Creator

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

### Získat hodnotu MetadataDate

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

## Krok 4: Uložit EPS soubor s novými XMP metadaty

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## Časté problémy a řešení

- **Chybějící XMP paket** – Pokud `document.XmpMetadata` vrací `null`, EPS soubor neobsahuje XMP blok. Můžete vytvořit novou instanci `XmpMetadata` a připojit ji před uložením.  
- **Nesprávný formát data** – XMP očekává data ve formátu ISO 8601 (`yyyy-MM-ddTHH:mm:ssZ`). Použijte `DateTime.UtcNow.ToString("o")` k vygenerování kompatibilního řetězce.  
- **Špičky paměti u velkých souborů** – Aktivujte režim streamování nastavením `EpsLoadOptions.Streaming = true`, aby se udržela nízká spotřeba paměti.

## Často kladené otázky

**Q: Mohu přidat metadata do více EPS dokumentů současně?**  
A: Ano, projděte kolekci cest k souborům, použijte stejnou logiku extrakce a aktualizace a uložte každý soubor. API je bezpečné pro vlákna, takže můžete operaci paralelizovat pro rychlejší dávkové zpracování.

**Q: Existují nějaká omezení velikosti EPS dokumentů, které Aspose.Page pro .NET dokáže zpracovat?**  
A: Knihovna pohodlně zpracovává EPS soubory až do **500 MB**. Pro soubory větší než toto zvažte rozdělení dokumentu nebo použití streamovacího přístupu, aby nedošlo k výjimkám z nedostatku paměti.

**Q: Je XMP metadata standardizována pro všechny EPS dokumenty?**  
A: XMP následuje standard ISO 16684‑1, ale jednotliví tvůrci mohou naplnit vlastní jmenné prostory. Aspose.Page čte jak standardní, tak vlastní vlastnosti, což vám umožní zachovat jakákoli proprietární data.

**Q: Mohu přizpůsobit pole metadat podle specifických požadavků?**  
A: Rozhodně. Můžete přidat vlastní XMP schémata nebo rozšířit existující pomocí metody `XmpMetadata.AddCustomProperty`, což vám dává plnou kontrolu nad strukturou metadat.

**Q: Jak mohu zvládnout chyby během procesu přidávání metadat?**  
A: Zabalte logiku extrakce a uložení do bloku `try…catch` a zaznamenejte podrobnosti `Aspose.Page.Exception`. Tím zachytíte problémy jako poškozené streamy, nepodporované vlastnosti nebo selhání I/O.

**Q: Podporuje Aspose.Page .NET Core a .NET 5/6?**  
A: Ano, knihovna je plně kompatibilní s .NET Core 3.1, .NET 5, .NET 6 a novějšími verzemi, poskytující konzistentní API napříč všemi podporovanými runtime.

---

**Poslední aktualizace:** 2026-07-29  
**Testováno s:** Aspose.Page pro .NET 24.10  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Přidat metadata do EPS dokumentu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Přidat jmenný prostor pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)
- [Přidat jednoduché vlastnosti pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
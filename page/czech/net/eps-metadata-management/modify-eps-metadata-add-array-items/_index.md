---
date: 2026-08-08
description: Naučte se, jak přidat položky pole do EPS metadata pomocí Aspose.Page
  EPS metadata. Tento krok‑za‑krokem .NET průvodce ukazuje, jak přidávat položky pole
  a efektivně číst soubory EPS.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Přidat položky pole
og_description: Objevte, jak přidat položky pole do EPS metadata pomocí Aspose.Page
  EPS metadata. Postupujte podle tohoto stručného .NET tutoriálu, abyste mohli číst
  soubory EPS a efektivně spravovat metadata.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Přidání položek pole pomocí Aspose.Page EPS metadata v .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Přidání položek pole pomocí Aspose.Page EPS metadata v .NET
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání položek pole s metadaty Aspose.Page EPS v .NET

## Úvod

V tomto tutoriálu se naučíte, jak přidat položky pole do metadat EPS pomocí **Aspose.Page EPS metadata**. Ať už potřebujete obohatit soubor EPS o další názvy, autory nebo vlastní značky, Aspose.Page usnadňuje tuto úlohu pro jakéhokoli vývojáře .NET. Provedeme vás každým krokem, od otevření EPS proudu až po uložení aktualizovaného XMP balíčku, abyste mohli s jistotou integrovat správu metadat do svých aplikací.

## Rychlé odpovědi
- **Co vám umožňuje Aspose.Page EPS metadata?** Umožňuje čtení a zápis XMP metadatových polí uvnitř souborů EPS z .NET.  
- **Která třída představuje dokument EPS?** `PsDocument` je hlavní třída pro načítání a ukládání obsahu EPS.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu upravit metadata bez změny grafiky EPS?** Ano, mění se pouze XMP paket, zatímco obsah stránky zůstává nedotčen.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je Aspose.Page EPS metadata?
Aspose.Page EPS metadata je blok informací založený na XMP, vložený do souboru EPS. Uchovává popisné vlastnosti jako názvy, autory, klíčová slova a vlastní značky podle standardu ISO 16684‑1. K metadatům lze přistupovat a upravovat programově pomocí Aspose.Page API, což umožňuje automatizovanou správu dokumentů a optimalizaci vyhledávání.

## Proč upravovat metadata EPS?
Aspose.Page dokáže zpracovat **více než 30 polí metadat** a pracovat se soubory EPS až do **200 MB** bez načítání celého dokumentu do paměti, což snižuje využití CPU až o 40 % ve srovnání s úplným parsováním souboru. Aktualizace metadat zlepšuje vyhledatelnost, soulad a automatizaci následných pracovních postupů.

## Požadavky

- Základní znalost programování v .NET.  
- Aspose.Page pro .NET nainstalováno – stáhněte jej z [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (nebo jakékoli IDE kompatibilní s .NET) pro spuštění ukázkového kódu.  

## Jak přidat položky pole do metadat EPS?
Pro přidání položek pole nejprve načtěte soubor EPS do `PsDocument`, poté získáte jeho XMP paket pomocí `GetXmpMetadata()`. Použijte metodu `AddArrayItem()` na požadované XMP pole, například `dc:title` nebo `dc:creator`, pro přidání nových hodnot. Nakonec zavolejte `Save()`, aby se aktualizovaná metadata zapsala zpět do souboru při zachování grafického obsahu beze změny.

### Krok 1: inicializace vstupního proudu EPS souboru
`PsDocument` představuje dokument EPS a poskytuje metody pro přístup k jeho obsahu. Následující kód otevře soubor EPS jako stream a vytvoří instanci `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Krok 2: získání XMP metadat
`GetXmpMetadata()` získá XMP paket vložený do souboru EPS. Pokud paket neexistuje, API vygeneruje nový na základě existujících PostScript komentářů.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Krok 3: změna hodnot XMP metadat
`AddArrayItem()` přidá novou hodnotu do existujícího XMP pole, aniž by přepsal ostatní položky. Použijte ji k přidání názvů, autorů nebo vlastních značek do metadat.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Krok 4: uložení EPS souboru se změněnými XMP metadaty
`Save()` zapíše upravený XMP paket zpět do souboru EPS při zachování původního PostScript obsahu. Zadejte výstupní cestu pro vytvoření nového souboru nebo přepsání zdroje.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Časté problémy a řešení

- **Null XMP packet** – Pokud `GetXmpMetadata()` vrátí `null`, ujistěte se, že soubor EPS obsahuje alespoň jeden blok komentářů; jinak vytvořte novou instanci `XmpMetadata` ručně.  
- **Problémy s kódováním** – Používejte UTF‑8 při přidávání řetězcových hodnot, aby nedošlo k poškození znaků v ne‑ASCII jazycích.  
- **Velké soubory** – Pro soubory EPS větší než 150 MB zvažte streamování vstupu pomocí `FileStream` s vyrovnávací pamětí, aby byl nízký odběr paměti.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi .NET prostředími?**  
A: Ano, Aspose.Page funguje napříč .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6/7 a poskytuje konzistentní chování API na Windows, Linuxu i macOS.

**Q: Můžu používat Aspose.Page zdarma?**  
A: Knihovnu můžete vyzkoušet pomocí bezplatného stažení z [Aspose purchase page](https://purchase.aspose.com/buy). Pro produkční nasazení je vyžadována komerční licence.

**Q: Jsou k dispozici dočasné licence pro Aspose.Page?**  
A: Dočasné licence lze získat na [temporary license page](https://purchase.aspose.com/temporary-license/) pro krátkodobé projekty nebo evaluační období.

**Q: Kde mohu najít komunitní podporu pro Aspose.Page?**  
A: Připojte se k diskuzi na [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde můžete klást otázky a sdílet řešení s ostatními vývojáři.

**Q: Jaká je nejnovější verze Aspose.Page pro .NET?**  
A: Podívejte se na oficiální [documentation](https://reference.aspose.com/page/net/) pro nejnovější poznámky k vydání a odkazy ke stažení.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Související tutoriály

- [Change Array Items with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Add Simple Properties with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Add Namespace with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
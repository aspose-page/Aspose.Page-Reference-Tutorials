---
date: 2026-08-13
description: Naučte se, jak použít Aspose.Page ke změně hodnot EPS v aplikacích .NET,
  včetně podrobných aktualizací XMP metadat.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Změnit hodnoty
og_description: Tutoriál Aspose.Page – změna hodnot EPS ukazuje, jak pomocí .NET upravit
  XMP metadata uvnitř souborů EPS. Postupujte podle podrobného návodu a okamžitě aktualizujte
  autora, název a datum úpravy.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page – změna hodnot EPS pomocí .NET – tutoriál
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page – změna hodnot EPS pomocí .NET – tutoriál
url: /cs/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page změna hodnot eps pomocí .NET – tutoriál

## Úvod

V tomto tutoriálu se dozvíte, jak **aspose.page change eps values** upravit úpravou XMP metadat vložených do souboru EPS. Ať už potřebujete aktualizovat jméno tvůrce, upravit název nebo opravit datum úpravy, Aspose.Page pro .NET vám poskytuje čisté API založené na kódu, které funguje na Windows, Linuxu i macOS. Na konci průvodce budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolné .NET služby nebo konzolové aplikace.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Změna XMP metadat (tvůrce, název, datum úpravy) uvnitř souborů EPS pomocí Aspose.Page pro .NET.  
- **Která verze knihovny je požadována?** Jakékoli vydání Aspose.Page pro .NET, které podporuje XMP (v24.10+).  
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná licence; pro vývoj stačí bezplatná zkušební verze.  
- **Mohu to spustit na .NET Core?** Ano – API je kompatibilní s .NET 5, .NET 6 a .NET Core 3.1+.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní aktualizaci metadat.

## Co jsou XMP metadata?

XMP metadata jsou standardizovaný XML blok, který ukládá popisné informace (autor, název, data) uvnitř souborů EPS a dalších grafických formátů. Je vložen přímo v hlavičce souboru a může být čten mnoha nástroji pro design a publikaci, což umožňuje konzistentní správu metadat napříč platformami. Aktualizací XMP umožníte následným aplikacím zobrazit správné vlastnosti dokumentu, aniž byste měnili vizuální obsah.

## Proč použít Aspose.Page pro EPS metadata?

Aspose.Page dokáže zpracovat **30+** grafických formátů a pracuje se soubory EPS až do **1 GB** bez načítání celého souboru do paměti, což přináší **70 %** úsporu RAM oproti naivnímu streamovému parsování. Knihovna také zaručuje, že vizuální vykreslení EPS zůstane po úpravě metadat nezměněno.

## Požadavky

Před začátkem se ujistěte, že máte připraveno následující:

1. **Aspose.Page for .NET library** – stáhněte ji z oficiální stránky vydání Aspose.Page pro .NET [here](https://releases.aspose.com/page/net/). Můžete také prozkoumat další vydání produktů Aspose [here](https://releases.aspose.com/).  
2. **Document directory** – vytvořte složku na svém počítači, kde budou umístěny zdrojové soubory EPS a výstupní soubory.

Nyní, když je prostředí nastaveno, importujme jmenné prostory, které budete potřebovat.

## Importovat jmenné prostory

Jmenný prostor `Aspose.Page` poskytuje základní třídy, zatímco `System.IO` vám umožňuje práci se streamy.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Jak změnit hodnoty EPS metadat?

Načtěte soubor EPS, získejte jeho XMP paket, upravte požadovaná pole a zapište aktualizovaný EPS zpět na disk. Proces nevyžaduje vykreslování obsahu stránky, takže je rychlý a paměťově úsporný. Postupujte podle podrobných kroků a podívejte se na ukázky kódu pro každou operaci. Tento end‑to‑end tok je popsán v následujících krocích.

### Krok 1: inicializovat vstupní stream souboru EPS

Vytvořte jen pro čtení `FileStream`, který ukazuje na zdrojový soubor EPS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Krok 2: vytvořit instanci PsDocument ze streamu

`PsDocument` je objekt nejvyšší úrovně představující EPS dokument v paměti. Poskytuje vám přístup jak k obsahu stránky, tak k vloženým XMP metadatům.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Krok 3: získat XMP metadata

Vlastnost `XmpMetadata` vrací objekt `XmpPacket`, který můžete dotazovat a upravovat.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Krok 4: upravit hodnoty XMP metadat

Nyní změníte tři běžná pole: **ModifyDate**, **Creator** a **Title**.

#### Krok 4.1: změnit hodnotu ModifyDate

Nastavte `ModifyDate` na aktuální UTC časové razítko.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Krok 4.2: změnit hodnotu Creator

Nahraďte existujícího tvůrce názvem vaší aplikace.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Krok 4.3: změnit hodnotu Title

Aktualizujte název tak, aby odrážel nový účel obsahu.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Krok 5: uložit EPS soubor se změněnými XMP metadaty

Po úpravě zapište dokument zpět.

#### Krok 5.1: vytvořit výstupní stream

Otevřete `FileStream` pro cílový soubor EPS.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Krok 5.2: uložit EPS soubor

Zavolejte `Save` na instanci `PsDocument` a předávejte výstupní stream.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Nakonec zavřete vstupní stream, aby se uvolnila manipulace se souborem.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Gratulujeme! Úspěšně jste **aspose.page change eps values** aktualizovali XMP metadata uvnitř souboru EPS.

## Časté úskalí a řešení problémů

- **Empty XMP packet** – Některé soubory EPS jsou generovány bez XMP. V takovém případě vytvořte nový `XmpPacket` pomocí `new XmpPacket()` před přiřazením hodnot.  
- **Large files** – Pro EPS soubory větší než 500 MB povolte bufferování streamu nastavením `PsDocumentOptions.UseMemoryMappedFiles = true`, aby se předešlo `OutOfMemoryException`.  
- **Incorrect date format** – XMP očekává formát ISO 8601. Použijte `DateTime.UtcNow.ToString("o")` k vytvoření kompatibilního řetězce.

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro .NET s jinými grafickými formáty?**  
A: Ano, knihovna podporuje více než 30 formátů včetně PDF, SVG a AI, ale API pro úpravu XMP jsou specifické pro EPS a PDF.

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete vyzkoušet Aspose.Page pro .NET pomocí bezplatné zkušební verze dostupné na stránce vydání Aspose [here](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci?**  
A: Komplexní referenci Aspose.Page .NET API najdete [here](https://reference.aspose.com/page/net/).

**Q: Jak získám dočasnou licenci?**  
A: Dočasnou licenci můžete získat [here](https://purchase.aspose.com/temporary-license/).

**Q: Mohu zakoupit Aspose.Page pro .NET?**  
A: Samozřejmě! Navštivte stránku nákupu Aspose.Page [here](https://purchase.aspose.com/buy) pro možnosti licencování.

---

**Poslední aktualizace:** 2026-08-13  
**Testováno s:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Související tutoriály

- [Přidat metadata do EPS dokumentu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extrahovat metadata z EPS dokumentu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Změnit pojmenovanou hodnotu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
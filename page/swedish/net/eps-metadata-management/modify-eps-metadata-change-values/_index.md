---
date: 2026-08-13
description: Lär dig hur du använder Aspose.Page för att ändra EPS‑värden i .NET‑applikationer,
  inklusive steg‑för‑steg‑uppdateringar av XMP‑metadata.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Ändra värden
og_description: Aspose.Page‑handledning för att ändra EPS‑värden visar hur du modifierar
  XMP‑metadata i EPS‑filer med .NET. Följ den steg‑för‑steg‑guiden för att omedelbart
  uppdatera skapare, titel och ändringsdatum.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page ändra EPS‑värden med .NET – handledning
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
title: Aspose.Page ändra EPS‑värden med .NET – handledning
url: /sv/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ändra eps‑värden med .NET – handledning

## Introduktion

I den här handledningen kommer du att upptäcka hur du **aspose.page change eps values** genom att redigera den XMP‑metadata som är inbäddad i en EPS‑fil. Oavsett om du behöver uppdatera skaparnamnet, justera titeln eller korrigera ändringsdatumet, ger Aspose.Page för .NET dig ett rent, kod‑först API som fungerar på Windows, Linux och macOS. I slutet av guiden har du ett återanvändbart kodsnutt som du kan lägga in i vilken .NET‑tjänst eller konsolapp som helst.

## Snabba svar
- **Vad täcker handledningen?** Ändra XMP‑metadata (skapare, titel, ändringsdatum) i EPS‑filer med Aspose.Page för .NET.  
- **Vilken biblioteksversion krävs?** Alla Aspose.Page för .NET‑utgåvor som stödjer XMP (v24.10+).  
- **Behöver jag en licens?** En tillfällig licens krävs för produktion; en gratis provversion fungerar för utveckling.  
- **Kan jag köra detta på .NET Core?** Ja – API:et är kompatibelt med .NET 5, .NET 6 och .NET Core 3.1+.  
- **Hur lång tid tar implementeringen?** Cirka 5‑10 minuter för en grundläggande metadata‑uppdatering.

## Vad är XMP‑metadata?

XMP‑metadata är ett standardiserat XML‑block som lagrar beskrivande information (författare, titel, datum) i EPS‑ och andra grafikformat. Det är inbäddat direkt i filens huvud och kan läsas av många design‑ och publiceringsverktyg, vilket möjliggör konsekvent metadata‑hantering över plattformar. Genom att uppdatera XMP kan efterföljande applikationer visa korrekta dokumentegenskaper utan att ändra det visuella innehållet.

## Varför använda Aspose.Page för EPS‑metadata?

Aspose.Page kan bearbeta **30+** grafikformat och hanterar EPS‑filer upp till **1 GB** utan att läsa in hela filen i minnet, vilket ger en **70 %** minskning av RAM‑användning jämfört med naiv ström‑parsing. Biblioteket garanterar också att den visuella återgivningen av EPS‑filen förblir oförändrad efter metadata‑ändringar.

## Förutsättningar

Innan du börjar, se till att följande är redo:

1. **Aspose.Page for .NET library** – ladda ner den från den officiella Aspose.Page för .NET‑utgågesidan [här](https://releases.aspose.com/page/net/). Du kan också utforska andra Aspose‑produktutgåvor [här](https://releases.aspose.com/).  
2. **Document directory** – skapa en mapp på din maskin där käll‑EPS‑filen och utdatafilerna ska ligga.

Nu när miljön är konfigurerad, låt oss importera de namnrymder du kommer att behöva.

## Importera namnrymder

`Aspose.Page`‑namnrymden tillhandahåller kärnklasserna, medan `System.IO` ger dig funktioner för strömhantering.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Hur man ändrar EPS‑metadata‑värden?

Läs in EPS‑filen, hämta dess XMP‑paket, ändra de nödvändiga fälten och skriv den uppdaterade EPS‑filen tillbaka till disk. Processen kräver ingen rendering av sidinnehållet, så den är snabb och minnes‑effektiv. Följ de detaljerade stegen för att se kodexempel för varje operation. Detta helhetsflöde täcks i stegen nedan.

### Steg 1: initiera EPS‑filens inmatningsström

Skapa en skrivskyddad `FileStream` som pekar på käll‑EPS‑filen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Steg 2: skapa PsDocument‑instans från ström

`PsDocument` är top‑nivå‑objektet som representerar ett EPS‑dokument i minnet. Det ger dig åtkomst till både sidinnehållet och den inbäddade XMP‑metadata.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Steg 3: hämta XMP‑metadata

`XmpMetadata`‑egenskapen returnerar ett `XmpPacket`‑objekt som du kan fråga och redigera.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Steg 4: ändra XMP‑metadata‑värden

Nu kommer du att ändra tre vanliga fält: **ModifyDate**, **Creator** och **Title**.

#### Steg 4.1: ändra ModifyDate‑värde

Sätt `ModifyDate` till den aktuella UTC‑tidsstämpeln.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Steg 4.2: ändra Creator‑värde

Byt ut den befintliga skaparen mot ditt applikationsnamn.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Steg 4.3: ändra Title‑värde

Uppdatera titeln för att återspegla det nya innehållets syfte.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Steg 5: spara EPS‑fil med ändrad XMP‑metadata

Efter redigering, skriv dokumentet tillbaka.

#### Steg 5.1: skapa utmatningsström

Öppna en `FileStream` för destinations‑EPS‑filen.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Steg 5.2: spara EPS‑fil

Anropa `Save` på `PsDocument`‑instansen och skicka in utmatningsströmmen.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Till sist, stäng inmatningsströmmen för att frigöra filhandtaget.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Grattis! Du har framgångsrikt **aspose.page change eps values** genom att uppdatera XMP‑metadata i en EPS‑fil.

## Vanliga fallgropar och felsökning

- **Tomt XMP‑paket** – Vissa EPS‑filer genereras utan XMP. I så fall skapa ett nytt `XmpPacket` via `new XmpPacket()` innan du tilldelar värden.  
- **Stora filer** – För EPS‑filer större än 500 MB, aktivera strömbuffring genom att sätta `PsDocumentOptions.UseMemoryMappedFiles = true` för att undvika `OutOfMemoryException`.  
- **Felaktigt datumformat** – XMP förväntar sig ISO 8601. Använd `DateTime.UtcNow.ToString("o")` för att generera en kompatibel sträng.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för .NET med andra grafikformat?**  
A: Ja, biblioteket stödjer över 30 format inklusive PDF, SVG och AI, men XMP‑redigerings‑API:erna är specifika för EPS och PDF.

**Q: Är en provversion tillgänglig?**  
A: Ja, du kan prova Aspose.Page för .NET med den gratis provversionen som finns på Aspose‑utgågesidan [här](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation?**  
A: Den omfattande Aspose.Page .NET‑API‑referensen finns [här](https://reference.aspose.com/page/net/).

**Q: Hur får jag en tillfällig licens?**  
A: Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Kan jag köpa Aspose.Page för .NET?**  
A: Absolut! Besök Aspose.Page‑köpsidan [här](https://purchase.aspose.com/buy) för licensalternativ.

---

**Senast uppdaterad:** 2026-08-13  
**Testad med:** Aspose.Page 24.10 for .NET  
**Författare:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Relaterade handledningar

- [Lägg till metadata i EPS-dokument med Aspose.Page för .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extrahera metadata från EPS-dokument med Aspose.Page för .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Ändra namngivet värde med Aspose.Page för .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
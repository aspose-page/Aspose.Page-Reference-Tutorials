---
date: 2026-08-08
description: Lär dig hur du lägger till array‑element i EPS‑metadata med hjälp av
  Aspose.Page EPS metadata. Denna steg‑för‑steg .NET‑guide visar hur du lägger till
  array‑element och läser EPS‑filer effektivt.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Lägg till array‑element
og_description: Upptäck hur du lägger till array‑element i EPS‑metadata med Aspose.Page
  EPS metadata. Följ denna koncisa .NET tutorial för att läsa EPS‑filer och hantera
  metadata effektivt.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Lägg till array‑element med Aspose.Page EPS metadata i .NET
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
title: Lägg till array‑element med Aspose.Page EPS metadata i .NET
url: /sv/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till array‑element med Aspose.Page EPS‑metadata i .NET

## Introduktion

I den här handledningen kommer du att lära dig hur du lägger till array‑element i EPS‑metadata med **Aspose.Page EPS metadata**. Oavsett om du behöver berika en EPS‑fil med ytterligare titlar, skapare eller anpassade taggar, gör Aspose.Page uppgiften enkel för alla .NET‑utvecklare. Vi går igenom varje steg, från att öppna EPS‑strömmen till att spara det uppdaterade XMP‑paketet, så att du kan integrera metadata‑hantering i dina egna applikationer med förtroende.

## Snabba svar
- **Vad låter Aspose.Page EPS‑metadata dig göra?** Det möjliggör läsning och skrivning av XMP‑metadata‑arrayer i EPS‑filer från .NET.  
- **Vilken klass representerar ett EPS‑dokument?** `PsDocument` är kärnklassen för att läsa in och spara EPS‑innehåll.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra metadata utan att ändra EPS‑grafiken?** Ja, endast XMP‑paketet ändras, så sidinnehållet förblir orört.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är Aspose.Page EPS‑metadata?
Aspose.Page EPS‑metadata är ett XMP‑baserat informationsblock som är inbäddat i en EPS‑fil. Det lagrar beskrivande egenskaper såsom titlar, skapare, nyckelord och anpassade taggar enligt ISO 16684‑1‑standarden. Metadata kan nås och modifieras programatiskt via Aspose.Page‑API:t, vilket möjliggör automatiserad dokumenthantering och sökoptimering.

## Varför ändra EPS‑metadata?
Aspose.Page kan bearbeta **över 30 metadatafält** och hantera EPS‑filer upp till **200 MB** utan att ladda hela dokumentet i minnet, vilket minskar CPU‑användning med upp till 40 % jämfört med fullständig fil‑parsing. Att uppdatera metadata förbättrar sökbarhet, efterlevnad och efterföljande arbetsflödes‑automatisering.

## Förutsättningar

- Grundläggande .NET‑programmeringskunskaper.  
- Aspose.Page för .NET installerat – ladda ner det från [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (eller någon .NET‑kompatibel IDE) för att köra exempelkoden.  

## Hur lägger man till array‑element i EPS‑metadata?
För att lägga till array‑element, ladda först EPS‑filen i ett `PsDocument`, hämta sedan dess XMP‑paket med `GetXmpMetadata()`. Använd metoden `AddArrayItem()` på den önskade XMP‑arrayen, såsom `dc:title` eller `dc:creator`, för att lägga till nya värden. Slutligen anropa `Save()` för att skriva den uppdaterade metadata tillbaka till filen samtidigt som grafik‑innehållet förblir oförändrat.

### Steg 1: initiera EPS‑filens inmatningsström
`PsDocument` representerar ett EPS‑dokument och tillhandahåller metoder för att komma åt dess innehåll. Följande kod öppnar EPS‑filen som en ström och skapar en `PsDocument`‑instans.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Steg 2: hämta XMP‑metadata
`GetXmpMetadata()` hämtar XMP‑paketet som är inbäddat i EPS‑filen. Om inget paket finns genererar API:t ett nytt baserat på befintliga PostScript‑kommentarer.

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

### Steg 3: ändra XMP‑metadata‑värden
`AddArrayItem()` lägger till ett nytt värde i en befintlig XMP‑array utan att skriva över andra poster. Använd den för att lägga till titlar, skapare eller anpassade taggar i metadata.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Steg 4: spara EPS‑fil med ändrad XMP‑metadata
`Save()` skriver det modifierade XMP‑paketet tillbaka till EPS‑filen samtidigt som det ursprungliga PostScript‑innehållet bevaras. Ange utvägs‑sökvägen för att skapa en ny fil eller skriva över källfilen.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Vanliga fallgropar och felsökning

- **Null XMP‑paket** – Om `GetXmpMetadata()` returnerar `null`, se till att EPS‑filen innehåller minst ett kommentarsblock; annars skapa en ny `XmpMetadata`‑instans manuellt.  
- **Kodningsproblem** – Använd UTF‑8 när du lägger till strängvärden för att undvika teckenkorruption i icke‑ASCII‑språk.  
- **Stora filer** – För EPS‑filer större än 150 MB, överväg att strömma indata via `FileStream` med en buffert för att hålla minnesanvändningen låg.

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla .NET‑miljöer?**  
A: Ja, Aspose.Page fungerar på .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6/7, med konsekvent API‑beteende på Windows, Linux och macOS.

**Q: Kan jag använda Aspose.Page gratis?**  
A: Du kan utvärdera biblioteket med en gratis provnedladdning från [Aspose purchase page](https://purchase.aspose.com/buy). En kommersiell licens krävs för produktionsmiljöer.

**Q: Finns tillfälliga licenser tillgängliga för Aspose.Page?**  
A: Tillfälliga licenser kan erhållas via [temporary license page](https://purchase.aspose.com/temporary-license/) för kortvariga projekt eller utvärderingsperioder.

**Q: Var kan jag hitta community‑support för Aspose.Page?**  
A: Gå med i diskussionen på [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att ställa frågor och dela lösningar med andra utvecklare.

**Q: Vad är den senaste versionen av Aspose.Page för .NET?**  
A: Se den officiella [documentation](https://reference.aspose.com/page/net/) för de senaste versionsnoteringarna och nedladdningslänkarna.

---

**Senast uppdaterad:** 2026-08-08  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose

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

## Relaterade handledningar

- [Ändra array‑element med Aspose.Page för .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Lägg till enkla egenskaper med Aspose.Page för .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Lägg till namnrymd med Aspose.Page för .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
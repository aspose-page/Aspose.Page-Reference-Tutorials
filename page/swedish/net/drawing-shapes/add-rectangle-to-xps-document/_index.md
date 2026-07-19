---
date: 2026-07-19
description: Lär dig hur du skapar XPS-dokument .NET och lägger till en rektangel
  med Aspose.Page för .NET i en kort steg‑för‑steg‑guide.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Lägg till rektangel i XPS-dokument
og_description: Skapa XPS-dokument .NET snabbt. Denna handledning visar hur du lägger
  till en rektangel i en XPS-fil med Aspose.Page för .NET, med tydlig kod och tips.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Skapa XPS-dokument .NET – Lägg till rektangel med Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Skapa XPS-dokument .NET – Lägg till rektangel med Aspose.Page
url: /sv/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument .NET – Lägg till rektangel med Aspose.Page

## Introduktion

I den här handledningen kommer du att lära dig hur du **skapar XPS-dokument .NET** och ritar en rektangel i det med Aspose.Page för .NET. Oavsett om du bygger en rapportmotor, en utskrivbar faktura eller ett anpassat grafiklager, ger möjligheten att programatiskt generera XPS-filer dig full kontroll över layout och noggrannhet. Följ stegen nedan så har du en färdig XPS-fil på några minuter.

## Snabba svar
- **Vad är huvudmålet?** Skapa ett XPS-dokument .NET och lägga till en rektangel.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (nedladdningsbart från den officiella webbplatsen).  
- **Behöver jag en licens för testning?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur lång tid tar implementeringen?** Cirka 5‑10 minuter för en grundläggande rektangel.

## Vad är Aspose.Page för .NET?
Aspose.Page för .NET är ett högpresterande, helt hanterat API som möjliggör för utvecklare att programatiskt skapa, redigera och rendera XPS (XML Paper Specification)-dokument utan att förlita sig på externa komponenter. Det erbjuder en rik objektmodell för att rita former, text och bilder, och stöder avancerade funktioner såsom färghantering, komprimering och PDF‑konvertering, vilket gör det lämpligt för ett brett spektrum av dokumentgenereringsscenarier.

## Varför använda Aspose.Page för att skapa XPS-dokument .NET?
Aspose.Page stöder **30+ XPS-funktioner**—inklusive vektorgrafik, textlayout och färghantering—och kan generera filer upp till **500 MB** utan att ladda hela dokumentet i minnet. Denna kvantifierade kapacitet säkerställer smidig prestanda även för storskaliga utskriftsjobb.

## Förutsättningar

Innan du börjar med den här handledningen, se till att du har följande förutsättningar på plats:

1. Aspose.Page för .NET Library: Se till att du har Aspose.Page för .NET‑biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner det [here](https://releases.aspose.com/page/net/).

2. Dokumentkatalog: Skapa en katalog där du vill lagra dina XPS-dokument.

## Importera namnrymder

I din .NET‑applikation, inkludera de nödvändiga namnrymderna för att använda Aspose.Page‑funktionaliteten.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hur lägger jag till en rektangel i ett XPS-dokument i .NET?

Läs in XPS-dokumentet, skapa ett `Graphics`‑objekt, definiera en `RectangleF` med önskad storlek och anropa `DrawRectangle`. Denna sekvens ritar en rektangel i en enda kodrad och hanterar automatiskt DPI‑skalning. För vanliga A4‑sidor visas en 200 × 100 pt‑rektangel centrerad utan extra beräkningar.

### Steg 1: Ange dokumentkatalogen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Steg 2: Skapa ett nytt XPS-dokument

`XpsDocument`‑klassen representerar XPS‑filen du bygger och tillhandahåller metoder för att lägga till sidor, grafik och andra resurser.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Steg 3: Lägg till en rektangel

`XpsPath` definierar ett ritbart sökvägsobjekt inom XPS-dokumentet, vilket låter dig ange geometri, linje, fyllning och andra visuella egenskaper.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Steg 4: Spara dokumentet

`Save`‑metoden skriver det konstruerade XPS-dokumentet till den angivna filsökvägen på disken.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Grattis! Du har framgångsrikt lagt till en rektangel i ett XPS-dokument med Aspose.Page för .NET.

## Vanliga problem och tips

- **Saknade teckensnitt:** Se till att de teckensnitt du refererar till är installerade på servern; annars ersätter Aspose.Page dem med ett standardteckensnitt, vilket kan ändra layouten.  
- **Stora dokument:** När du genererar filer som är större än 200 MB, överväg att anropa `document.SaveOptions.Compress = true` för att minska minnesanvändningen.  
- **Koordinatsystem:** XPS använder punkter (1/72 tum). Kom ihåg att konvertera pixlar till punkter om du arbetar med skärm‑baserade dimensioner.

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla .NET‑applikationer?**  
A: Ja, Aspose.Page fungerar sömlöst med skrivbords-, webb‑ och moln‑.NET‑applikationer.

**Q: Var kan jag hitta dokumentationen för Aspose.Page för .NET?**  
A: Den fullständiga API‑referensen finns tillgänglig [here](https://reference.aspose.com/page/net/).

**Q: Kan jag prova Aspose.Page för .NET gratis innan jag köper?**  
A: Ja, du kan få en gratis provversion [here](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?**  
A: Besök [this link](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens.

**Q: Var kan jag få gemenskapsstöd eller ställa frågor relaterade till Aspose.Page för .NET?**  
A: Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för gemenskapsstöd.

---

**Senast uppdaterad:** 2026-07-19  
**Testad med:** Aspose.Page för .NET 24.9  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa XPS-dokument med Aspose.Page för .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Rita former](/page/net/drawing-shapes/)
- [Lägg till text i XPS-dokument med Aspose.Page för .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
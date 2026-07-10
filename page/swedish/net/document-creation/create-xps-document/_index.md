---
date: 2026-07-10
description: Lär dig hur du aspose.page skapa xps-dokument med Aspose.Page för .NET
  – en steg‑för‑steg‑guide för att generera högkvalitativa XPS-filer.
keywords:
- aspose.page create xps
- XPS document generation
- Aspose.Page .NET
lastmod: 2026-07-10
linktitle: Skapa XPS-dokument
og_description: aspose.page skapa xps snabbt med Aspose.Page för .NET. Följ den här
  guiden för att producera högkvalitativa XPS-filer på under 20 kodrader.
og_image_alt: 'Guide: Create XPS document using Aspose.Page for .NET'
og_title: aspose.page skapa xps – Generera XPS-dokument med .NET
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: Learn how to aspose.page create xps documents using Aspose.Page for
    .NET – a step‑by‑step guide to generate high‑quality XPS files.
  headline: aspose.page create xps – Generate XPS Documents with .NET
  type: TechArticle
- questions:
  - answer: Yes. Provide the exact font family name when calling `AddGlyphs`; the
      font must be installed on the runtime machine.
    question: Can I use custom fonts in my XPS document?
  - answer: Absolutely. The library works on .NET Core 3.1, .NET 5, .NET 6 and later,
      enabling cross‑platform XPS generation.
    question: Is Aspose.Page compatible with .NET Core?
  - answer: Use the `AddImage` method of the `XpsPage` class. The API accepts PNG,
      JPEG, BMP, and GIF formats.
    question: How do I add images to an XPS document?
  - answer: Yes. Instantiate multiple `XpsPage` objects, populate each with glyphs
      or images, and then save the document once.
    question: Can I create multi‑page XPS documents?
  - answer: Yes, you can explore the full feature set by downloading the [free trial](https://releases.aspose.com/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- create xps
- XPS document
- .NET document generation
title: aspose.page skapa xps – Generera XPS-dokument med .NET
url: /sv/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page create xps – Skapa XPS-dokument med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att lära dig **aspose.page create xps**‑dokument steg för steg med hjälp av Aspose.Page‑biblioteket för .NET. Oavsett om du bygger en rapportmotor, en fakturagenerator eller något system som behöver högkvalitativa elektroniska dokument, är XPS ett pålitligt, XML‑baserat format som bevarar layouten över plattformar. Vi går igenom allt från förutsättningar till att spara den slutliga filen, med praktiska tips som du kan använda omedelbart.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page for .NET  
- **Kan jag köra detta på .NET Core?** Ja – fullt stöd på .NET Core 3.1, .NET 5, .NET 6 och senare  
- **Hur många kodrader?** Färre än 20 rader för en grundläggande “Hello World”-XPS‑fil  
- **Behöver jag en licens för testning?** En gratis provversion fungerar för utveckling; en licens krävs för produktionsdistributioner  
- **Vilket format har utdata?** XPS (XML Paper Specification)  

## Hur skapar jag ett XPS-dokument med Aspose.Page för .NET?

Läs in Aspose.Page‑biblioteket, skapa en instans av `XpsDocument`, lägg till en enda sida med glyfer, sätt fyllningsfärgen och anropa `Save`. Detta kompletta arbetsflöde kräver bara några metodanrop och producerar en standard‑kompatibel XPS‑fil som kan öppnas i Windows Reader, Adobe Acrobat eller någon XPS‑medveten visare. Metoden fungerar på Windows, Linux och macOS utan ytterligare beroenden.

## Vad är aspose.page create xps?

`aspose.page create xps` avser processen att programatiskt generera en XPS (XML Paper Specification)-fil med hjälp av Aspose.Page‑API:n för .NET. API:n abstraherar låg‑nivå PDF/XPS‑strukturer, så att du kan fokusera på innehållet snarare än filformatets detaljer. Den stöder inställning av sidstorlek, typsnitt, färger och inbäddning av bilder, vilket möjliggör för utvecklare att skapa rika, utskrivbara dokument direkt från kod.

## Varför använda Aspose.Page för XPS‑generering?

Aspose.Page stöder **30+ utdataformat** och kan rendera XPS‑filer upp till **500 MB** utan att ladda hela dokumentet i minnet, vilket ger hög prestanda för server‑sidiga arbetsbelastningar. Biblioteket garanterar pixel‑perfekt layout‑fidelitet, automatisk inbäddning av typsnitt och full Unicode‑stöd, vilket eliminerar behovet av tredjeparts‑konverterare.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

1. **Aspose.Page for .NET Library** – ladda ner den från [download link](https://releases.aspose.com/page/net/).  
2. **Target Directory** – bestäm var den genererade XPS‑filen ska sparas på din maskin.  

Nu när miljön är klar, låt oss importera de nödvändiga namnutrymmena.

## Importera namnrymder

För att använda Aspose.Page för .NET måste du importera de nödvändiga namnrymderna i ditt projekt. Följ dessa steg:

### Steg 1: Lägg till referens till Aspose.Page

I ditt projekt, lägg till en referens till Aspose.Page for .NET‑biblioteket. Du kan hitta den nödvändiga DLL‑filen i det nedladdade paketet.

### Steg 2: Importera namnrymder

Inkludera följande namnrymder i din kodfil:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ställ in dokumentkatalog

Variabeln `directoryPath` talar om för API:n var den resulterande XPS‑filen ska skrivas.

```csharp
string dir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den faktiska mappvägen på ditt system, t.ex. `C:\\Docs\\Output`.

## Steg 2: Skapa XPS-dokument

`XpsDocument`‑klassen representerar rotobjektet för en XPS‑fil.

```csharp
XpsDocument xDocs = new XpsDocument();
```

Initiera den med målfilens namn så skapas en ny sida automatiskt.

## Steg 3: Lägg till glyfer i dokumentet

`AddGlyphs`‑metoden infogar text (glyfer) på den aktuella sidan.

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Du kan styra teckensnittsfamilj, storlek, stil och exakta koordinater för att placera texten exakt.

## Steg 4: Ställ in fyllningsfärg för glyfer

`SetFillColor`‑metoden definierar penseln som används för att måla glyferna.

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

I det här exemplet använder vi svart (`Color.Black`), men alla ARGB‑färger stöds.

## Steg 5: Spara resultatet

Genom att anropa `Save` skrivs XPS‑dokumentet till disk.

```csharp
xDocs.Save(dir + "output.xps");
```

Filen kommer att innehålla texten “Hello World!” som du lade till i de föregående stegen.

## Vanliga tips & fallgropar

- **Directory Path** – Använd `Path.Combine(dir, \"output.xps\")` för att undvika saknade sökvägsavgränsare på Windows, Linux eller macOS.  
- **Font Availability** – Det angivna teckensnittet måste vara installerat på värddatorn; annars ersätter Aspose det med ett reservteckensnitt, vilket kan påverka layouten.  
- **Multiple Pages** – För flersidig utdata, skapa ytterligare `XpsPage`‑objekt, lägg till innehåll i varje och anropa sedan `Save` en gång.  

## Vanliga frågor

**Q: Kan jag använda anpassade teckensnitt i mitt XPS‑dokument?**  
A: Ja. Ange det exakta teckensnittsfamiljenamnet när du anropar `AddGlyphs`; teckensnittet måste vara installerat på körningsmaskinen.

**Q: Är Aspose.Page kompatibel med .NET Core?**  
A: Absolut. Biblioteket fungerar på .NET Core 3.1, .NET 5, .NET 6 och senare, vilket möjliggör plattformsoberoende XPS‑generering.

**Q: Hur lägger jag till bilder i ett XPS‑dokument?**  
A: Använd `AddImage`‑metoden i `XpsPage`‑klassen. API:n accepterar PNG, JPEG, BMP och GIF‑format.

**Q: Kan jag skapa flersidiga XPS‑dokument?**  
A: Ja. Skapa flera `XpsPage`‑objekt, fyll varje med glyfer eller bilder och spara sedan dokumentet en gång.

**Q: Finns det en provversion tillgänglig?**  
A: Ja, du kan utforska hela funktionsuppsättningen genom att ladda ner [free trial](https://releases.aspose.com/).

## Slutsats

Du har nu ett komplett, produktionsklart arbetsflöde för **aspose.page create xps**‑dokument med Aspose.Page för .NET. Experimentera med olika typsnitt, färger och sidlayouter för att anpassa utdata efter din applikations behov. För mer avancerade scenarier—såsom inbäddning av vektorgrafik eller hantering av stora batchjobb—se den officiella API‑referensen.

---

**Last Updated:** 2026-07-10  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Lägg till text i XPS-dokument med Aspose.Page för .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Lägg till bild i XPS-dokument med Aspose.Page för .NET](/page/net/image-management/add-image-to-xps-document/)
- [Lägg till rektangel i XPS-dokument med Aspose.Page för .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
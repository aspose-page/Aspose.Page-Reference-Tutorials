---
date: 2026-06-25
description: Lär dig hur du enkelt transformerar XPS-dokument – den definitiva guiden
  om hur du transformerar XPS med Aspose.Page för .NET, med kodfria steg och praktiska
  tips.
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: XPS-transformationer
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Hur du transformerar XPS med Aspose.Page för .NET
url: /sv/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man transformerar XPS med Aspose.Page för .NET

## Introduktion

I den här omfattande guiden kommer du att lära dig **hur man transformerar XPS**‑dokument med Aspose.Page för .NET. Oavsett om du behöver flytta, skala, rotera eller kombinera flera grafikobjekt på en enda sida, ger biblioteket dig matrisbaserad kontroll utan att gräva i rå XML. Vi går igenom varje steg, förklarar varför varje transformation är viktig och delar praktiska tips som du kan kopiera rakt in i produktionskod.

## Snabba svar
- **Vad kan du uppnå?** Skapa, flytta, skala och rotera XPS‑canvas‑element programatiskt.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (senaste versionen).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Stödda plattformar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementeringstid?** Ungefär 10‑15 minuter för de grundläggande transformationerna som visas nedan.

## Vad är “how to transform xps”?
Frasen *how to transform xps* beskriver att programatiskt förändra layout, storlek och orientering av element i ett XPS (XML Paper Specification)-dokument. Med Aspose.Page applicerar du matrisbaserade transformationer på canvases, vilket ger dig pixelperfekt kontroll över positionering, skalning och rotation utan att manuellt redigera XPS‑markup.

## Varför använda Aspose.Page för XPS‑transformationer?
Läs in din XPS‑fil, applicera en serie transformationer och spara – allt i två kodrader. Aspose.Page stödjer **50+ in‑ och utdataformat**, kan bearbeta **200‑sidiga XPS‑filer på under 2 sekunder**, och kräver **inga externa beroenden**. Detta gör det idealiskt för att generera fakturor, rapporter eller annan utskrivbar grafik i farten.

## Förutsättningar

- **Aspose.Page for .NET Library** – ladda ner den från den officiella dokumentationen: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio, Visual Studio Code, Rider eller någon IDE som riktar sig mot .NET.  
- **Dokumentkatalog** – en mapp på din maskin där du läser/skriver XPS‑filer. Ersätt platshållaren i koden med den faktiska sökvägen.

Nu när vi har allt på plats, låt oss dyka ner i koden.

## Importera namnrymder

Följande namnrymder exponerar de centrala Aspose.Page‑typerna du kommer att arbeta med:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hur man transformerar XPS med Aspose.Page?

Läs in din käll‑XPS (eller starta med ett nytt dokument), applicera sedan en sekvens av matristransformationer – flytta, skala och rotera – direkt på canvas‑objekt. Varje transformation appliceras i den ordning du anropar den, vilket låter dig bygga komplexa layouter med bara några metodanrop.

## Hur man transformerar XPS – Steg‑för‑steg‑guide

I det här avsnittet går vi igenom ett komplett exempel som skapar en XPS‑fil, lägger till flera canvases och applicerar en rad transformationer såsom translation, skalning och rotation. Varje steg innehåller ett kort kodexempel (representerat av platshållare) och förklarar varför operationen utförs, så att du enkelt kan reproducera den.

### Steg 1: Skapa ett nytt XPS‑dokument

`XpsDocument` är Aspose.Page‑objektet som representerar en XPS‑fil i minnet.  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Förklaring*: Vi börjar med att definiera mappen som innehåller våra käll‑ och utdatafiler, och sedan instansierar vi ett tomt `XpsDocument`. Detta objekt blir canvasen för alla efterföljande transformationer.

### Steg 2: Skapa en huvud‑canvas

`Canvas` är ritytan som grupperar former, text och andra grafiska element.  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Varför detta är viktigt*: Huvud‑canvasen fungerar som en behållare för alla andra canvases. Genom att applicera ett litet offset säkerställer vi att innehållet inte klipps av vid sidans kant.

### Steg 3: Skapa en rektangel‑Path‑geometri

`PathGeometry` definierar vektorgrafik med XPS‑path‑syntax (M = move, L = line, Z = close).  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tips*: Path‑strängen följer den standard XPS‑path‑syntaxen. Justera koordinaterna för att ändra rektangelns storlek.

### Steg 4: Lägg till en fyllning för rektanglar

`SolidColorBrush` skapar en solid‑färgsfyllning som kan återanvändas i flera former.  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro‑tips*: Använd `CreateColor` med RGB‑värden för att matcha ditt varumärkespalett.

### Steg 5: Lägg till en ny canvas utan transformationer

`Canvas` utan transform fungerar som ett baslinje‑element för jämförelse.  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Här placerar vi helt enkelt en rektangel på sidan utan extra transformation—användbart som ett baslinje‑element.

### Steg 6: Lägg till en ny canvas med Translate‑transformation

`TranslateTransform` flyttar objekt längs X‑ och Y‑axlarna.  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Vad händer?* Den första matrisen flyttar rektangeln neråt med 200 enheter. Den efterföljande `Translate`‑anropet förflyttar den 500 enheter åt höger, vilket visar hur flera translationer kan kedjas ihop.

### Steg 7: Lägg till en ny canvas med dubbel Scale‑transformation

`ScaleTransform` multiplicerar bredden och höjden på canvasen med de angivna faktorerna.  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Varför skala?* Skalning med 2 dubblar rektangelns bredd och höjd, så att du kan skapa större grafik utan att omdefiniera geometrin.

### Steg 8: Lägg till en ny canvas med Rotation Around a Point‑transformation

`RotateAroundTransform` roterar canvasen kring en anpassad punkt (här (100, 50)).  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Viktig insikt*: `RotateAround` roterar canvasen kring en anpassad punkt, vilket ger dig fin kontroll över rotationsankare.

### Steg 9: Spara resulterande XPS‑dokument

`Save` sparar det minnes‑dokumentet till disk i XPS‑format.  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Efter att alla transformationer har tillämpats sparas dokumentet till `output1.xps`. Öppna filen i en XPS‑visare för att se de staplade rektanglarna med deras respektive translationer, skalning och rotation.

## Vanliga problem & felsökning

| Symtom | Trolig orsak | Åtgärd |
|--------|--------------|--------|
| Tom utdatafil | `dataDir` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller använd en absolut sökväg |
| Rektanglar är inte placerade som förväntat | Felaktiga matrisvärden | Dubbelkolla ordningen på `Translate`, `Scale` och `RotateAround`‑anrop |
| Färger visas felaktigt | RGB‑värden utanför 0‑255‑intervallet | Använd giltiga byte‑värden för varje kanal |

## Vanliga frågor

**Q: Är Aspose.Page för .NET kompatibel med alla .NET‑utvecklingsmiljöer?**  
A: Ja, den fungerar sömlöst med Visual Studio, Visual Studio Code, Rider och alla IDE:er som stödjer .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

**Q: Var kan jag hitta ytterligare exempel och detaljerad API‑dokumentation?**  
A: Besök den officiella dokumentationen på [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Kan jag prova Aspose.Page innan jag köper en licens?**  
A: Absolut. En gratis provversion finns här: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Hur får jag en tillfällig licens för testning?**  
A: Begär en via sidan för tillfällig licens: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa en full licens?**  
A: Köp direkt i Aspose‑butiken: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-06-25  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa XPS-dokument med Aspose.Page för .NET](/page/net/document-creation/create-xps-document/)
- [Hur man beskär XPS med Aspose.Page för .NET](/page/net/canvas-manipulation/clippingxps/)
- [Konvertera XPS till PDF med Aspose.Page för .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
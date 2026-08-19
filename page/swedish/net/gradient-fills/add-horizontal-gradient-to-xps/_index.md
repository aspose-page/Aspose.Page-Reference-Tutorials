---
date: 2026-02-25
description: Lär dig hur du skapar en XPS-gradient med horisontell fyllning med Aspose.Page
  för .NET. Höj det visuella intrycket enkelt i dina dokument.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Skapa XPS-gradient: Horisontell fyllning med Aspose.Page för .NET'
url: /sv/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-gradient – Lägg till horisontell gradient till XPS med Aspose.Page för .NET

## Introduktion

## Snabba svar
- **Vad täcker den här handledningen?** Lägga till en horisontell gradient i ett XPS-dokument med Aspose.Page för .NET.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (valfri nyare version).  
- **Behöver jag en licens?** En provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Cirka 5–10 minuter för en grundläggande gradient.  
- **Kan jag ändra gradientens riktning?** Ja – ändra start-/slutpunkterna för `LinearGradientBrush`.

## Hur man skapar XPS-gradient med Aspose.Page för .NET

Nedan hittar du en steg‑för‑steg‑guide som förklarar **varför** varje kodrad finns, inte bara **vad** den gör. Känn dig fri att följa med i Visual Studio eller din föredragna .NET‑redigerare.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Page för .NET-bibliotek: Säkerställ att du har Aspose.Page för .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner det från [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
2. Utvecklingsmiljö: Ställ in en lämplig utvecklingsmiljö, inklusive en kodredigerare som Visual Studio.

## Importera namnrymder

Börja med att importera de nödvändiga namnrymderna i ditt projekt. Dessa namnrymder är nödvändiga för att arbeta med Aspose.Page för .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Nu ska vi dela upp det givna exemplet i flera steg.

## Steg 1: Ange dokumentkatalogens sökväg

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Steg 2: Skapa ett nytt XPS-dokument

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Steg 3: Initiera gradientstopp

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Steg 4: Skapa en ny bana

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Steg 5: Spara det resulterande XPS-dokumentet

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Nu har du framgångsrikt lagt till en horisontell gradient i ditt XPS-dokument med Aspose.Page för .NET.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Gradienten visas som en solid färg | Gradientstopp har inte lagts till korrekt | Se till att `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` körs efter att penseln har ställts in. |
| Den sparade filen är tom | `dataDir` pekar på en icke‑existerande mapp | Verifiera att mappen finns eller använd en absolut sökväg. |
| Kompileringsfel på `PointF` | Saknad `System.Drawing`-referens | Lägg till en referens till `System.Drawing.Common` (för .NET Core/5+). |

## Vanliga frågor

### Q1: Var kan jag hitta dokumentationen för Aspose.Page för .NET?

A1: Du kan hitta dokumentationen [här](https://reference.aspose.com/page/net/).

### Q2: Hur laddar jag ner Aspose.Page för .NET?

A2: Du kan ladda ner biblioteket från [Aspose.Page för .NET nedladdningssida](https://releases.aspose.com/page/net/).

### Q3: Var kan jag köpa Aspose.Page för .NET?

A3: Du kan köpa Aspose.Page för .NET från [köpsidan](https://purchase.aspose.com/buy).

### Q4: Finns det en gratis provversion tillgänglig?

A4: Ja, du kan få en gratis provversion [här](https://releases.aspose.com/).

### Q5: Hur får jag en tillfällig licens för Aspose.Page för .NET?

A5: Du kan skaffa en tillfällig licens via [denna länk](https://purchase.aspose.com/temporary-license/).

## Vanliga frågor och svar

**Q: Kan jag använda denna gradientteknik med XPS-dokument som redan innehåller bilder?**  
A: Absolut. Gradienten appliceras på ett banlager, så befintliga bilder förblir orörda.

**Q: Är det möjligt att skapa en vertikal gradient istället?**  
A: Ja. Ändra `LinearGradientBrush` start- och slutpunkter så att Y‑koordinaterna skiljer sig åt medan X hålls konstant.

**Q: Stöder Aspose.Page .NET Core?**  
A: Biblioteket är fullt kompatibelt med .NET Core, .NET 5 och senare versioner.

**Q: Hur kan jag återanvända samma gradient på flera sidor?**  
A: Skapa `XpsLinearGradientBrush` en gång, lagra den i en variabel och tilldela den till banor på varje sida.

## Slutsats

Att förbättra dina XPS-dokument med gradienter förbättrar inte bara det visuella intrycket utan ger också en mer engagerande användarupplevelse. Med Aspose.Page för .NET kan du **skapa XPS-gradient**‑fyllningar snabbt och pålitligt, vilket ger dina rapporter, broschyrer eller e‑böcker en professionell finish.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose
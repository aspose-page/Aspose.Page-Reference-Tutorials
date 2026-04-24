---
date: 2026-01-05
description: Lär dig hur du lägger till en urklippsbana i PostScript med Aspose.Page
  för .NET – steg‑för‑steg‑guide med tekniker för att sätta pensel och rita streckade
  rektanglar.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Lägg till klippningsväg i PS med Aspose.Page för .NET
url: /sv/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till urklippsväg i PS med Aspose.Page för .NET

## Introduktion

I den här omfattande handledningen kommer du att upptäcka hur du **lägger till urklippsväg** i ett PostScript (PS)-dokument med Aspose.Page för .NET. Vi går igenom varje steg, visar dig hur du **ställer in pensel**, och demonstrerar hur du **ritar en streckad rektangel** runt det urklippta innehållet. I slutet har du en fullt funktionell PS-fil som illustrerar urklippning med form, vilket gör dina grafik mer dynamisk och professionell.

## Snabba svar
- **Vad gör “add clipping path”?** Det begränsar ritoperationer till en definierad form och döljer allt utanför den formen.  
- **Vilket bibliotek hanterar urklippning i .NET?** Aspose.Page för .NET erbjuder ett rikt API för PS/EPS-manipulation.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag ändra penselfärgen?** Ja, använd `SetPaint` med vilken `SolidBrush` eller gradient du föredrar.  
- **Är det möjligt att rita en streckad rektangel?** Absolut – skapa en `Pen` med `DashStyle.Dash` och använd `Draw`.  

## Vad är en urklippsväg i PostScript?
En urklippsväg definierar den synliga regionen för efterföljande ritkommandon. Allt som ritas utanför vägen ignoreras, vilket låter dig skapa komplexa maskerade grafik utan att ändra det ursprungliga innehållet.

## Varför använda Aspose.Page för urklippning?
- **Inga externa beroenden** – rent .NET-bibliotek.  
- **Full kontroll** över grafikstatus (save/restore, translate, rotate).  
- **Rika ritprimitive** såsom `SetPaint`, `Clip` och `Draw` med anpassningsbara pennor och penslar.  

## Förutsättningar

- Grundläggande kunskap i C#-programmering.  
- Aspose.Page för .NET-biblioteket installerat – du kan ladda ner det [here](https://releases.aspose.com/page/net/).  
- Visual Studio eller någon annan föredragen .NET-IDE.  

## Importera namnrymder

Först importerar du de namnrymder som krävs för grafikmanipulation:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nu ska vi bryta ner exemplet i tydliga, numrerade steg.

### Steg 1: Ange dokumentkatalog

Definiera mappen där dina käll- och utdatafiler kommer att ligga.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Steg 2: Skapa utdataflöde för PostScript-dokument

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Steg 3: Skapa sparalternativ

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Steg 4: Skapa ett nytt 1‑sidigt PS-dokument

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Steg 5: Skapa grafikväg från rektangeln

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Steg 6: Urklippning med form

Här **lägger vi till urklippsväg** med en cirkel, **ställer in pensel** till blå och fyller rektangeln inom det urklippta området.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Steg 7: Flytta övre grafikstatus & rita streckad rektangel

Efter att ha återställt föregående status flyttar vi grafikmarkören igen, **ritar en streckad rektangel** och applicerar en blå kontur.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Steg 8: Stäng och spara dokumentet

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Du har nu framgångsrikt **lagt till urklippsväg**, ställt in en anpassad pensel och ritat en streckad rektangel runt din grafik med Aspose.Page för .NET.

## Vanliga problem och lösningar

- **Urklippning syns inte:** Se till att du anropar `WriteGraphicsSave()` innan du översätter och `WriteGraphicsRestore()` efter fyllning.  
- **Fel färger:** Verifiera att `SetPaint` anropas efter `Clip` och före `Fill`.  
- **Streckade linjer visas som solida:** Se till att `Pen`ens `DashStyle` är satt till `DashStyle.Dash` innan `SetStroke`.  

## Vanliga frågor

### Q1: Kan jag använda Aspose.Page för .NET med andra programmeringsspråk?
A: Aspose.Page är främst avsedd för .NET-applikationer. Aspose erbjuder dock liknande bibliotek för andra programmeringsspråk.

### Q2: Var kan jag hitta ytterligare exempel och dokumentation för Aspose.Page för .NET?
A: Du kan utforska fler exempel och detaljerad dokumentation på [Aspose.Page documentation](https://reference.aspose.com/page/net/).

### Q3: Finns det en gratis provversion av Aspose.Page för .NET?
A: Ja, du kan få en gratis provversion av Aspose.Page för .NET [here](https://releases.aspose.com/).

### Q4: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?
A: Du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Q5: Var kan jag få support eller diskutera frågor relaterade till Aspose.Page?
A: Besök [Aspose.Page forums](https://forum.aspose.com/c/page/39) för community‑support och diskussioner.

**Senast uppdaterad:** 2026-01-05  
**Testat med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
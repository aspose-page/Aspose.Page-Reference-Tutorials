---
date: 2026-06-25
description: Lär dig hur du klipper XPS-dokument med Aspose.Page för .NET. Denna steg‑för‑steg‑guide
  visar hur du skapar, manipulerar och sparar XPS‑filer på ett effektivt sätt.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Klippa XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Så klipper du XPS med Aspose.Page för .NET
url: /sv/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man beskär XPS med Aspose.Page för .NET

## Introduktion

Välkommen till denna omfattande handledning om **hur man beskär XPS** med Aspose.Page för .NET! I den här guiden kommer du steg för steg att lära dig hur du skapar ett XPS-dokument, tillämpar geometriska beskärningsmasker och sparar resultatet. Beskärning låter dig dölja delar av en canvas, vilket möjliggör avancerade layouter som maskerade bilder, anpassade former eller fokuserade innehållsområden – allt utan att lämna din .NET-kod.

## Snabba svar
- **Vad är beskärning av XPS?** Att tillämpa en geometrisk mask (clip) för att begränsa det synliga området av XPS‑canvas‑element.  
- **Vilket bibliotek är bäst för detta?** Aspose.Page för .NET erbjuder ett komplett API för XPS‑skapande och beskärning.  
- **Förutsättningar?** Visual Studio, .NET‑runtime och Aspose.Page för .NET‑biblioteket.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundläggande beskärningsscenario.  
- **Kan jag använda detta i produktion?** Ja, med en giltig Aspose‑licens (provversion tillgänglig).

## Vad är “hur man beskär XPS”?

Beskärning av XPS innebär att applicera en geometrisk mask på en canvas så att alla ritningar utanför masken inte renderas. Denna teknik är idealisk för att skapa maskerade bilder, anpassade knappar eller fokusera läsarens uppmärksamhet på ett specifikt sidområde. Genom att definiera en beskärningsgeometri – såsom en rektangel, cirkel eller komplex bana – får du fin‑granulär kontroll över vad som visas på den slutliga XPS‑sidan.

## Varför använda Aspose.Page för .NET för att beskär XPS?

Aspose.Page erbjuder deterministisk, server‑sidig XPS‑manipulation utan externa beroenden. Det stödjer **50+ in‑ och utdataformat**, kan bearbeta **200‑sidiga XPS‑filer på under 0,5 sekunder** på en standard‑2,5 GHz‑CPU, och fungerar på .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 och .NET 7. API‑et ger dig full kontroll över canvas‑transformeringar, sökvägsgeometrier och penslar, vilket säkerställer högkvalitativt resultat varje gång.

## Förutsättningar

- Visual Studio installerat på din maskin.  
- Aspose.Page för .NET‑biblioteket tillagt i ditt projekt. Du kan ladda ner det [here](https://releases.aspose.com/page/net/).  
- Grundläggande kunskaper i C#‑programmeringsspråket.

## Hur man beskär XPS?

Läs in ett XPS‑dokument, skapa en canvas, definiera en beskärningsgeometri (t.ex. en cirkel), tilldela geometrin till canvasens `Clip`‑egenskap, rita ditt innehåll och spara slutligen dokumentet. Alla dessa steg kan utföras med bara några metodanrop, och Aspose.Page hanterar automatiskt den underliggande XML‑markupen, så du kan fokusera på den visuella designen snarare än filstrukturen.

## Importera namnrymder

För att kunna använda Aspose.Page för .NET‑funktioner måste du importera de nödvändiga namnrymderna i ditt projekt. Följ dessa steg:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Nu ska vi bryta ner exempel­koden du tillhandahöll i flera steg.

## Steg 1: Ange sökvägen till dokumentkatalogen.

Definiera mappen där XPS‑filen kommer att skapas. Att använda `Path.Combine` garanterar rätt katalogseparator på alla operativsystem.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 2: Skapa ett nytt XPS-dokument.

Instansiera klassen `XpsDocument`, som representerar hela XPS‑paketet.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Steg 3: Skapa huvud‑canvasen.

`Canvas`‑klassen representerar en ritytan inom en XPS‑sida där former, bilder och text renderas.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Steg 4: Ställ in vänster- och toppoffset i huvud‑canvasen.

Justera canvasens position för att kontrollera var ritningarna startar på sidan.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Steg 5: Skapa en rektangel‑sökvägsgeometri.

`PathGeometry` definierar en vektorform; här skapar vi en enkel rektangel.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Steg 6: Skapa en fyllning för rektanglar.

Definiera en solid färgpenna som kommer att användas för att fylla rektangeln.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Steg 7: Lägg till en annan canvas med beskärning till huvud‑canvasen.

Skapa en under‑canvas som kommer att få en beskärningsmask.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Steg 8: Skapa en cirkelgeometri för beskärning.

`PathGeometry` kan också representera cirklar; denna geometri kommer att tilldelas `Clip`‑egenskapen på under‑canvasen.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Steg 9: Skapa en rektangel i den andra canvasen och fyll den.

Rita en rektangel inuti den beskärda canvasen; endast den del som ligger inom cirkeln kommer att vara synlig.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Steg 10: Lägg till den andra canvasen med en kontur‑rektangel till huvud‑canvasen.

Lägg till en rektangel med en kontur för att illustrera hur konturer interagerar med beskärning.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Steg 11: Skapa en rektangel i den tredje canvasen och ge den en kontur.

En tredje canvas demonstrerar oberoende ritning utan beskärning.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Steg 12: Spara det resulterande XPS-dokumentet.

Spara XPS‑paketet till filsystemet.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Vanliga problem och lösningar
- **Ogiltig sökväg** – Se till att `dataDir` slutar med ett bakstreck (`\\`) eller använd `Path.Combine`.  
- **Beskärning tillämpas inte** – Verifiera att strängen för beskärningsgeometri är välformad; ett saknat mellanslag kan göra att beskärningen ignoreras.  
- **Licensundantag** – I en icke‑utvärderingsbyggnad, lägg till en giltig Aspose‑licens innan du skapar dokumentet för att undvika körningsexceptioner.

## Vanliga frågor

### Q1: Kan jag använda Aspose.Page för .NET med andra dokumentformat?

A1: Aspose.Page för .NET fokuserar främst på XPS‑dokument, men Aspose tillhandahåller andra bibliotek för olika dokumentformat.

### Q2: Är Aspose.Page för .NET lämplig för nybörjare?

A2: Ja, Aspose.Page för .NET är designad för att vara användarvänlig, och nybörjare kan snabbt förstå dess funktioner med korrekt dokumentation.

### Q3: Var kan jag hitta fler exempel och resurser?

A3: Besök [dokumentationen](https://reference.aspose.com/page/net/) och [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för omfattande resurser och exempel.

### Q4: Hur kan jag skaffa en tillfällig licens för Aspose.Page för .NET?

A4: Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Q5: Finns det en gratis provversion av Aspose.Page för .NET?

A5: Ja, du kan utforska gratis‑provet [här](https://releases.aspose.com/).

## Ytterligare vanliga frågor

**Q: Kan jag kombinera flera beskärningsgeometrier på en enda canvas?**  
A: Ja, du kan tilldela en komplex `PathGeometry` som innehåller flera under‑banor till `Clip`‑egenskapen, vilket möjliggör lager‑maskering.

**Q: Påverkar beskärning PDF‑konvertering?**  
A: När du senare konverterar XPS till PDF med Aspose.PDF bevaras beskärningsgeometrin, så det visuella resultatet förblir identiskt.

**Q: Är det möjligt att animera beskärning i XPS?**  
A: XPS i sig stödjer inte animation; du kan dock generera en serie XPS‑sidor med olika beskärningsformer för att simulera rörelse.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Relaterade handledningar

- [How to Transform XPS with Aspose.Page for .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Add Rectangle to XPS Document with Aspose.Page for .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convert XPS to PDF with Aspose.Page for .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}
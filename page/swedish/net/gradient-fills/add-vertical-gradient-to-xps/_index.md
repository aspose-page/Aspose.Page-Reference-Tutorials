---
title: Lägg till Vertical Gradient till XPS med Aspose.Page för .NET
linktitle: Lägg till Vertical Gradient till XPS
second_title: Aspose.Page .NET API
description: Lär dig hur du förbättrar XPS-dokument med vertikala gradienter med Aspose.Page för .NET. Följ vår steg-för-steg-guide för sömlös integration.
weight: 15
url: /sv/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Vertical Gradient till XPS med Aspose.Page för .NET

## Introduktion

Välkommen till denna steg-för-steg handledning om hur man lägger till en vertikal gradient till ett XPS-dokument med Aspose.Page för .NET. Aspose.Page är ett kraftfullt API som låter dig arbeta med XPS-filer (XML Paper Specification) i dina .NET-applikationer. I den här handledningen guidar vi dig genom processen att skapa ett nytt XPS-dokument, lägga till en vertikal gradient till en sökväg och spara resultatet.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar:

-  Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner den[här](https://releases.aspose.com/page/net/).

- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö med din föredragna IDE, som Visual Studio.

Låt oss nu börja med att lägga till en vertikal gradient till ett XPS-dokument med Aspose.Page för .NET.

## Importera namnområden

I din .NET-applikation, inkludera de nödvändiga namnområdena för att komma åt Aspose.Page-klasser och -metoder.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Steg 1: Konfigurera din dokumentkatalog

Innan du börjar, ställ in sökvägen till din dokumentkatalog där du vill spara det resulterande XPS-dokumentet.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// Exend:3
```

## Steg 2: Skapa ett nytt XPS-dokument

Initiera ett nytt XPS-dokument med följande kod:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// Exend:4
```

## Steg 3: Definiera gradientstopp

Skapa en lista med gradientstopp, ange färg och position för varje stopp. I det här exemplet definierar vi en vertikal gradient med fem stopp.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Exend:5
```

## Steg 4: Skapa en bana med gradient

Definiera en bana genom att ange dess geometri och applicera en linjär gradientpensel på den.

```csharp
// ExStart: 6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Exend:6
```

## Steg 5: Spara det resulterande XPS-dokumentet

Spara det modifierade XPS-dokumentet i din angivna katalog.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Exend:7
```

Grattis! Du har framgångsrikt lagt till en vertikal gradient till ett XPS-dokument med Aspose.Page för .NET.

## Slutsats

I den här handledningen undersökte vi hur man kan utnyttja Aspose.Page för .NET för att förbättra XPS-dokument med vertikala gradienter. Aspose.Page förenklar komplexa uppgifter och ger utvecklare ett smidigt sätt att manipulera XPS-filer i sina .NET-applikationer.

## FAQ's

### F1: Är Aspose.Page kompatibel med Visual Studio 2019?

S1: Ja, Aspose.Page är kompatibel med Visual Studio 2019. Se till att du har rätt version av biblioteket installerad.

### F2: Kan jag använda Aspose.Page för kommersiella projekt?

 S2: Ja, Aspose.Page kan användas för kommersiella projekt. Besök[här](https://purchase.aspose.com/buy) för att utforska licensalternativ.

### F3: Finns det en gratis provperiod?

 S3: Ja, du kan få en gratis provversion av Aspose.Page[här](https://releases.aspose.com/).

### F4: Var kan jag hitta Aspose.Page-dokumentation?

 S4: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/net/).

### F5: Hur kan jag få support eller ställa frågor?

 A5: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

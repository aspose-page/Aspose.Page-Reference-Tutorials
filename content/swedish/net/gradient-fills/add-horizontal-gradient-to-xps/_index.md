---
title: Lägg till horisontell gradient till XPS med Aspose.Page för .NET
linktitle: Lägg till horisontell gradient till XPS
second_title: Aspose.Page .NET API
description: Lär dig hur du lägger till fantastiska horisontella gradienter till dina XPS-dokument med Aspose.Page för .NET. Öka visuellt tilltal utan ansträngning.
type: docs
weight: 13
url: /sv/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Introduktion

I den här handledningen kommer vi att utforska hur man förbättrar XPS-dokument genom att lägga till en horisontell gradient med Aspose.Page för .NET. Aspose.Page för .NET är ett kraftfullt bibliotek som ger sömlös hantering av XPS (XML Paper Specification)-dokument i .NET-applikationer. Att lägga till övertoningar kan tilltala dina dokument visuellt, och den här guiden leder dig genom processen steg för steg.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1.  Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner den från[Aspose.Page för .NET-dokumentation](https://reference.aspose.com/page/net/).

2. Utvecklingsmiljö: Sätt upp en lämplig utvecklingsmiljö, inklusive en kodredigerare som Visual Studio.

## Importera namnområden

Börja med att importera de nödvändiga namnrymden till ditt projekt. Dessa namnområden är viktiga för att arbeta med Aspose.Page för .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Låt oss nu dela upp exemplet i flera steg.

## Steg 1: Ställ in dokumentkatalogsökvägen

```csharp
// ExStart:3
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Exend:3
```

## Steg 2: Skapa ett nytt XPS-dokument

```csharp
// ExStart:4
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
// Exend:4
```

## Steg 3: Initiera gradientstopp

```csharp
// ExStart:5
// Initiera lista över XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Exend:5
```

## Steg 4: Skapa en ny sökväg

```csharp
// ExStart: 6
//Skapa ny väg genom att definiera geometri i förkortningsform
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Exend:6
```

## Steg 5: Spara det resulterande XPS-dokumentet

```csharp
// ExStart:7
// Spara resulterande XPS-dokument
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Exend:7
```

Nu har du framgångsrikt lagt till en horisontell gradient till ditt XPS-dokument med Aspose.Page för .NET.

## Slutsats

Att förbättra dina XPS-dokument med övertoningar förbättrar inte bara deras visuella dragningskraft utan ger också en mer engagerande användarupplevelse. Aspose.Page för .NET förenklar denna process, vilket gör att du kan uppnå professionella resultat utan ansträngning.

## FAQ's

### F1: Var kan jag hitta Aspose.Page för .NET-dokumentationen?

 A1: Du kan hitta dokumentationen[här](https://reference.aspose.com/page/net/).

### F2: Hur laddar jag ner Aspose.Page för .NET?

 A2: Du kan ladda ner biblioteket från[Aspose.Page för .NET nedladdningssida](https://releases.aspose.com/page/net/).

### F3: Var kan jag köpa Aspose.Page för .NET?

 S3: Du kan köpa Aspose.Page för .NET från[köpsidan](https://purchase.aspose.com/buy).

### F4: Finns det en gratis provperiod?

 A4: Ja, du kan få en gratis provperiod från[här](https://releases.aspose.com/).

### F5: Hur får jag en tillfällig licens för Aspose.Page för .NET?

 S5: Du kan få en tillfällig licens från[den här länken](https://purchase.aspose.com/temporary-license/).
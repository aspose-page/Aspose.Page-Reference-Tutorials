---
title: Lägg till Circle Ellipse till XPS-dokument med Aspose.Page för .NET
linktitle: Lägg till Circle Ellipse till XPS-dokument
second_title: Aspose.Page .NET API
description: Förbättra XPS-dokument med livfulla radiella gradienter med Aspose.Page för .NET. Följ vår steg-för-steg-guide för fantastiska visuella effekter.
weight: 11
url: /sv/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Circle Ellipse till XPS-dokument med Aspose.Page för .NET

## Introduktion

Att skapa visuellt tilltalande XPS-dokument är ett vanligt krav i olika applikationer. Aspose.Page för .NET tillhandahåller en kraftfull uppsättning funktioner för att manipulera XPS-dokument effektivt. I den här handledningen kommer vi att fokusera på att lägga till en cirkelellips till ett XPS-dokument med Aspose.Page för .NET. Följ stegen nedan för att förbättra dina XPS-dokument med levande radiella övertoningar.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Installerade Aspose.Page för .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/page/net/).
- En utvecklingsmiljö, helst Visual Studio eller något annat .NET-utvecklingsverktyg.
- Grundläggande kunskaper i C#-programmering.

## Importera namnområden

Börja med att inkludera de nödvändiga namnrymden i din C#-kod:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Låt oss nu dela upp exemplet i flera steg:

## Steg 1: Konfigurera dokumentet

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```

Här initierar vi ett nytt XPS-dokument med Aspose.Page för .NET.

## Steg 2: Definiera radiell gradientellips

```csharp
// Radiell gradient strök ellips i nedre vänstra delen
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Detta steg innebär att definiera en radiell gradientellips med olika färgstopp.

## Steg 3: Ställ in Radial Gradient Brush

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Här ställer vi in ellipsens slag till en radiell gradientborste, förser den med nödvändiga parametrar.

## Steg 4: Justera slagtjockleken

```csharp
path.StrokeThickness = 12f;
```

Detta steg innebär att justera tjockleken på slaget för bättre visualisering.

## Steg 5: Spara det resulterande XPS-dokumentet

```csharp
// Spara resulterande XPS-dokument
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Exend:1
```

Spara slutligen det modifierade XPS-dokumentet på önskad plats.

## Slutsats

Grattis! Du har framgångsrikt lagt till en cirkelellips med radiella gradienter till ditt XPS-dokument med Aspose.Page för .NET. Experimentera med olika parametrar och färger för att uppnå önskade visuella effekter i dina dokument.

## FAQ's

### F1: Kan jag använda Aspose.Page för .NET med andra dokumentformat?

S1: Aspose.Page för .NET handlar specifikt om XPS-dokumentmanipulation. För andra format, överväg att använda relaterade Aspose-bibliotek.

### F2: Är en tillfällig licens tillgänglig för teständamål?

 A2: Ja, du kan få en tillfällig licens för testning genom att besöka[den här länken](https://purchase.aspose.com/temporary-license/).

### F3: Var kan jag hitta ytterligare hjälp och diskussioner?

 A3: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd och diskussioner.

### F4: Finns det några exempeldokument tillgängliga för referens?

 A4: Utforska[dokumentation](https://reference.aspose.com/page/net/) för omfattande exempel och riktlinjer.

### F5: Kan jag köpa Aspose.Page för .NET?

 A5: Ja, du kan köpa biblioteket[här](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

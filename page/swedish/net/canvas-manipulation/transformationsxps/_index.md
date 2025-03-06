---
title: Transformationer XPS med Aspose.Page för .NET
linktitle: Transformationer XPS
second_title: Aspose.Page .NET API
description: Förvandla XPS-dokument utan ansträngning med Aspose.Page för .NET. Följ vår steg-för-steg-guide för sömlösa transformationer.
weight: 13
url: /sv/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformationer XPS med Aspose.Page för .NET

## Introduktion

Välkommen till Aspose.Page för .NET-världen, ett kraftfullt bibliotek som låter dig utföra olika transformationer på XPS-dokument utan ansträngning. I den här handledningen kommer vi att dyka in i processen att transformera XPS-dokument med Aspose.Page för .NET. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att leda dig genom varje steg, vilket säkerställer att du enkelt förstår koncepten.

## Förutsättningar

Innan vi börjar, se till att du har följande på plats:

-  Aspose.Page för .NET Library: Ladda ner och installera biblioteket från[Aspose.Page för .NET-dokumentation](https://reference.aspose.com/page/net/).

- Utvecklingsmiljö: Konfigurera en kompatibel utvecklingsmiljö, som Visual Studio eller något annat .NET-utvecklingsverktyg.

- Din dokumentkatalog: Ersätt platshållaren i koden med den faktiska sökvägen till din dokumentkatalog.

Nu, låt oss hoppa in i handledningen!

## Importera namnområden

Se först till att du importerar de nödvändiga namnområdena för att göra Aspose.Page för .NET-funktionerna tillgängliga i din kod. Lägg till följande namnrymder i början av ditt skript:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Skapa ett nytt XPS-dokument

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";

// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```

## Steg 2: Skapa en huvudduk

```csharp
// Skapa huvudduk, gemensam för alla sidelement
XpsCanvas canvas1 = doc.AddCanvas();

// Gör vänster- och toppförskjutningar i huvudduken
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Steg 3: Skapa en rektangelväggeometri

```csharp
// Skapa rektangelvägsgeometri
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Steg 4: Lägg till en fyllning för rektanglar

```csharp
// Skapa en fyllning för rektanglar
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Steg 5: Lägg till en ny duk utan transformationer

```csharp
// Lägg till ny duk utan några transformationer på huvudduken
XpsCanvas canvas2 = canvas1.AddCanvas();

// Skapa rektangel i denna duk och fyll den
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Steg 6: Lägg till en ny duk med Translate Transformation

```csharp
// Lägg till ny duk med translate-transformation till huvudduken
XpsCanvas canvas3 = canvas1.AddCanvas();

// Översätt den här duken för att placera en ny rektangel under den föregående rektangeln
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Översätt denna duk till höger sida på sidan
canvas3.RenderTransform.Translate(500, 0);

// Skapa rektangel i denna duk och fyll den
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Steg 7: Lägg till en ny duk med dubbelskalig transformation

```csharp
//Lägg till ny duk med dubbelskalig transformation till huvudduken
XpsCanvas canvas4 = canvas1.AddCanvas();

// Översätt den här duken för att placera en ny rektangel under den föregående rektangeln
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Skala denna duk
canvas4.RenderTransform.Scale(2, 2);

// Skapa rektangel i denna duk och fyll den
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Steg 8: Lägg till en ny duk med rotation runt en punkttransformation

```csharp
// Lägg till ny duk med rotation runt en punkttransformation till huvudduken
XpsCanvas canvas5 = canvas1.AddCanvas();

// Översätt den här duken för att placera en ny rektangel under den föregående rektangeln
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotera duken runt en punkt i 45 grader
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Skapa rektangel i denna duk och fyll den
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Steg 9: Spara det resulterande XPS-dokumentet

```csharp
// Spara resulterande XPS-dokument
doc.Save(dataDir + "output1.xps");
// Exend:1
```

## Slutsats

Grattis! Du har framgångsrikt transformerat ett XPS-dokument med Aspose.Page för .NET. Den här guiden täckte viktiga steg, från att ställa in förutsättningar till att utföra olika transformationer. Experimentera med dessa tekniker och lås upp den fulla potentialen hos Aspose.Page för .NET i dina projekt.

## FAQ's

### F1: Är Aspose.Page för .NET kompatibelt med alla .NET-utvecklingsmiljöer?

S1: Ja, Aspose.Page för .NET är utformad för att fungera sömlöst med olika .NET-utvecklingsmiljöer, inklusive Visual Studio.

### F2: Var kan jag hitta ytterligare exempel och dokumentation för Aspose.Page för .NET?

 A2: Besök[Aspose.Page för .NET-dokumentation](https://reference.aspose.com/page/net/) för omfattande dokumentation och exempel.

### F3: Kan jag prova Aspose.Page för .NET innan jag köper?

 A3: Ja, du kan utforska en gratis testversion genom att besöka[Aspose.Page gratis provperiod](https://releases.aspose.com/).

### F4: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?

 A4: Få en tillfällig licens genom att besöka[Tillfällig licens](https://purchase.aspose.com/temporary-license/).

### F5: Var kan jag köpa Aspose.Page för .NET?

 S5: Köp Aspose.Page för .NET på[Aspose.Page Köp](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Lägg till rektangel till XPS-dokument med Aspose.Page för .NET
linktitle: Lägg till rektangel till XPS-dokument
second_title: Aspose.Page .NET API
description: Förbättra dokumentskapandet med Aspose.Page för .NET. Lär dig hur du lägger till rektanglar till XPS-dokument i denna steg-för-steg-handledning.
type: docs
weight: 13
url: /sv/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Introduktion

Aspose.Page for .NET är ett kraftfullt bibliotek som tillhandahåller en mängd olika funktioner för att arbeta med XPS-dokument (XML Paper Specification) i .NET-applikationer. I den här handledningen kommer vi att fokusera på att lägga till en rektangel till ett XPS-dokument med Aspose.Page för .NET. Följ den här steg-för-steg-guiden för att förbättra din process för att skapa dokument.

## Förutsättningar

Innan du börjar med den här handledningen, se till att du har följande förutsättningar på plats:

1.  Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner den[här](https://releases.aspose.com/page/net/).

2. Dokumentkatalog: Skapa en katalog där du vill lagra dina XPS-dokument.

## Importera namnområden

I din .NET-applikation, inkludera de nödvändiga namnområdena för att använda Aspose.Page-funktioner.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ställ in dokumentkatalogen

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

## Steg 3: Lägg till en rektangel

```csharp
// ExStart:5
// CMYK (blå) enfärgad rektangel i den nedre vänstra delen
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Exend:5
```

## Steg 4: Spara dokumentet

```csharp
// ExStart: 6
// Spara resulterande XPS-dokument
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Exend:6
```

Grattis! Du har framgångsrikt lagt till en rektangel till ett XPS-dokument med Aspose.Page för .NET.

## Slutsats

Aspose.Page för .NET förenklar dokumenthanteringsuppgifter, vilket gör att utvecklare kan skapa och ändra XPS-dokument utan ansträngning. Denna steg-för-steg-guide visar hur du lägger till en rektangel till ditt XPS-dokument, vilket ger en solid grund för vidare utforskning.

## FAQ's

### F1: Är Aspose.Page kompatibel med alla .NET-applikationer?

S1: Ja, Aspose.Page är designad för att fungera sömlöst med alla .NET-applikationer.

### F2: Var kan jag hitta dokumentationen för Aspose.Page för .NET?

 S2: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/net/).

### F3: Kan jag prova Aspose.Page för .NET gratis innan jag köper?

 A3: Ja, du kan få en gratis provperiod[här](https://releases.aspose.com/).

### F4: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?

 A4: Besök[den här länken](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens.

### F5: Var kan jag söka stöd från communityn eller ställa frågor relaterade till Aspose.Page för .NET?

 A5: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd.
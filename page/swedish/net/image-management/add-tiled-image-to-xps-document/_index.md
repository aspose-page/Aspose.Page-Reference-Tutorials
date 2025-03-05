---
title: Lägg till sida vid sida i XPS-dokument med Aspose.Page för .NET
linktitle: Lägg till sida vid sida i XPS-dokument
second_title: Aspose.Page .NET API
description: Utforska att lägga till sida vid sida i XPS-dokument utan ansträngning med Aspose.Page för .NET. Förbättra visuella tilltal och skapa fantastiska dokument.
type: docs
weight: 12
url: /sv/net/image-management/add-tiled-image-to-xps-document/
---
## Introduktion

Vill du förbättra dina XPS-dokument genom att lägga till visuellt tilltalande sida vid sida? Aspose.Page för .NET ger utvecklare möjlighet att uppnå detta sömlöst. I den här steg-för-steg-guiden går vi igenom processen att lägga till en sida vid sida i ett XPS-dokument med Aspose.Page för .NET.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page för .NET: Se till att du har Aspose.Page-biblioteket installerat. Du kan hitta detaljerad dokumentation och ladda ner biblioteket[här](https://reference.aspose.com/page/net/).
- Utvecklingsmiljö: Konfigurera din föredragna .NET-utvecklingsmiljö, som Visual Studio.

## Importera namnområden

Börja med att importera de nödvändiga namnrymden till ditt projekt. Detta säkerställer att du har tillgång till de klasser och metoder som krävs för att arbeta med Aspose.Page. Lägg till följande namnrymder i början av din kod:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Låt oss nu dela upp exemplet i flera steg.

## Steg 1: Definiera dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
```

Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen dit du vill spara ditt XPS-dokument.

## Steg 2: Skapa ett nytt XPS-dokument

```csharp
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```

 Instantiera ett nytt XPS-dokument med hjälp av`XpsDocument` klass.

## Steg 3: Lägg till en sida vid sida

```csharp
// Kakelbild
// ImageBrush fylld rektangel längst upp till höger nedan
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Detta steg lägger till en sida vid sida i XPS-dokumentet. Justera koordinaterna och bildfilens sökväg enligt dina krav.

## Steg 4: Spara det resulterande XPS-dokumentet

```csharp
// Spara resulterande XPS-dokument
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Spara det modifierade XPS-dokumentet i den angivna katalogen.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du lägger till en sida vid sida i ett XPS-dokument med Aspose.Page för .NET. Denna enkla men kraftfulla funktion låter dig förbättra det visuella tilltalandet av dina dokument utan ansträngning.

## FAQ's

### F1: Är Aspose.Page kompatibel med alla .NET-utvecklingsmiljöer?

S1: Ja, Aspose.Page är designad för att fungera sömlöst med olika .NET-utvecklingsmiljöer, inklusive Visual Studio.

### F2: Kan jag justera opaciteten för den sida vid sida bilden?

A2: Visst, som visas i exemplet, kan du ställa in opaciteten för den fyllda rektangeln med`Opacity` fast egendom.

### F3: Finns det andra kakellägen tillgängliga i Aspose.Page för .NET?

 S3: Ja, Aspose.Page erbjuder olika bricklägen. I den här handledningen använde vi`XpsTileMode.Tile`, men du kan utforska andra alternativ i dokumentationen.

### F4: Hur hanterar jag tillfälliga licenser för Aspose.Page?

 A4: Se[tillfällig licens](https://purchase.aspose.com/temporary-license/) sida på Asposes webbplats för vägledning om att erhålla och implementera tillfälliga licenser.

### F5: Var kan jag söka hjälp eller få kontakt med Aspose.Page-communityt?

 A5: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) att engagera sig i samhället, ställa frågor och hitta lösningar.
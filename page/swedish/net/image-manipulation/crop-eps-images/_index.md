---
title: Beskär EPS-bilder med Aspose.Page för .NET
linktitle: Beskär EPS-bilder
second_title: Aspose.Page .NET API
description: Utforska den sömlösa världen av EPS-bildmanipulation i .NET med Aspose.Page. Beskär och ändra storlek på bilder utan ansträngning för fantastiska resultat.
type: docs
weight: 10
url: /sv/net/image-manipulation/crop-eps-images/
---
## Introduktion

Kämpar du med att manipulera EPS-bilder i dina .NET-applikationer? Kolla inte vidare! I den här handledningen guidar vi dig genom processen att beskära EPS-bilder med det kraftfulla Aspose.Page for .NET-biblioteket. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här steg-för-steg-guiden dig att uppnå exakt beskärning av bilder utan ansträngning.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- En praktisk kunskap om .NET-utveckling.
-  Aspose.Page för .NET-biblioteket installerat. Om inte kan du ladda ner den[här](https://releases.aspose.com/page/net/).
- Ett exempel på EPS-bild (ersätt "input.eps" i koden med din faktiska fil).

## Importera namnområden

Låt oss börja med att importera de nödvändiga namnrymden för att vår kod ska fungera smidigt. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Låt oss nu dela upp handledningen i flera steg.

## Steg 1: Initiera PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Initiera a`PsDocument` objekt med den ingående EPS-strömmen.

## Steg 2: Extrahera Bounding Box

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Hämta den initiala begränsningsrutan för EPS-bilden.

## Steg 3: Skapa utdataström

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Skapa en utdataström för den beskurna EPS-bilden.

## Steg 4: Definiera ny avgränsningsruta

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Definiera en ny begränsningsram för beskärning. Se till att de nya värdena ligger inom den initiala begränsningsrutan.

## Steg 5: Beskär och spara

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Beskär EPS-bilden med den nya begränsningsrutan och spara den i utdataströmmen.

Upprepa dessa steg för olika scenarier för att ändra storlek.

## Ändra storlek på EPS-bilder

### Ändra storlek i tum

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Ändra storlek på EPS-bilden och spara den med de angivna måtten i tum.

### Ändra storlek i millimeter

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Ändra storlek på EPS-bilden och spara den med de angivna måtten i millimeter.

### Ändra storlek i procent

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Ändra storlek på EPS-bilden och spara den med de angivna måtten i procent.

## Slutsats

Grattis! Du har framgångsrikt lärt dig att beskära och ändra storlek på EPS-bilder med Aspose.Page för .NET. Förbättra nu dina bildmanipuleringsmöjligheter och ta dina .NET-applikationer till nästa nivå.

## Vanliga frågor

### F1: Kan jag använda Aspose.Page för .NET med andra bildformat?

S1: Aspose.Page fokuserar främst på EPS-bilder, men Aspose tillhandahåller olika bibliotek för olika format. Kontrollera deras dokumentation för specifika format.

### F2: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?

 A2: Besök[den här länken](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens för provning.

### F3: Finns det några begränsningar för bildstorleken jag kan bearbeta med Aspose.Page för .NET?

A3: Aspose.Page är designad för att hantera bilder i olika storlekar. Prestandan kan dock variera beroende på bildens komplexitet.

### F4: Finns det ett communityforum för Aspose.Page-diskussioner?

 S4: Ja, du kan engagera dig i Aspose.Page-communityt[här](https://forum.aspose.com/c/page/39).

### F5: Var kan jag hitta detaljerad dokumentation för Aspose.Page för .NET?

 S5: Se dokumentationen[här](https://reference.aspose.com/page/net/).
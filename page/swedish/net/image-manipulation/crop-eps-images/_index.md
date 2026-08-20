---
date: 2026-03-16
description: Lär dig hur du beskär EPS‑bilder och ändrar storlek på EPS‑bildfiler
  i .NET med Aspose.Page. Följ den här steg‑för‑steg‑guiden för att enkelt beskära
  EPS och ändra storlek på EPS‑bilder.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Hur man beskär EPS‑bilder med Aspose.Page för .NET
url: /sv/net/image-manipulation/crop-eps-images/
weight: 10
---

top-button >}}

We need to keep these unchanged.

Now produce final content with all translations.

Check for any other text: "step‑by‑step guide" we translated.

Make sure to keep markdown formatting.

Let's construct final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man beskär EPS‑bilder med Aspose.Page för .NET

## Introduktion

Om du behöver veta **hur man beskär EPS**‑bilder i en .NET‑applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom hur du beskär och ändrar storlek på EPS‑filer med det kraftfulla Aspose.Page för .NET‑biblioteket. Oavsett om du finputsar ett rapportverktyg eller förbereder grafik för en webbtjänst, kommer behärskning av denna teknik att spara dig tid och ge dig pixelperfekta resultat.

## Snabba svar
- **Vilket bibliotek hanterar EPS‑beskärning?** Aspose.Page for .NET  
- **Primär metod?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Kan jag också ändra storlek på EPS?** Ja – använd `ResizeEps` med tum, millimeter eller procent.  
- **Förutsättningar?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page installerat, en EPS‑fil.  
- **Typisk implementeringstid?** Ungefär 10 minuter för ett grundläggande beskär‑och‑storleksändringsflöde.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

- En fungerande kunskap om .NET‑utveckling.  
- Aspose.Page för .NET‑biblioteket installerat. Om inte, kan du ladda ner det [här](https://releases.aspose.com/page/net/).  
- En exempel‑EPS‑bild (ersätt `"input.eps"` i koden med din faktiska fil).

## Importera namnrymder

Låt oss börja med att importera namnrymderna som ger oss åtkomst till EPS‑hanteringsklasserna.

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

## Så här beskär du EPS‑bilder – steg‑för‑steg‑guide

### Steg 1: Initiera `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Vi skapar en `PsDocument`‑instans från den inkommande EPS‑strömmen. Detta objekt representerar EPS‑filen i minnet och ger oss åtkomst till beskärnings‑ och storleksändringsmetoder.

### Steg 2: Extrahera den ursprungliga begränsningsrutan

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Begränsningsrutan visar de aktuella dimensionerna på EPS‑duken. Att känna till dessa värden hjälper dig att definiera en säker beskärningsrektangel.

### Steg 3: Skapa en utdata‑ström

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Vi öppnar en skrivbar ström där den beskärda EPS‑filen kommer att sparas. Genom att använda ett `using`‑block garanteras att strömmen stängs korrekt.

### Steg 4: Definiera en ny begränsningsruta

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Ersätt siffrorna med de koordinater du vill behålla. Se till att de nya värdena ligger inom den ursprungliga begränsningsrutan; annars kommer operationen att misslyckas.

### Steg 5: Beskär och spara EPS‑filen

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Denna enda rad utför beskärningen och skriver resultatet till `output_crop.eps`. Metoden modifierar dokumentet i minnet, så du kan kedja ytterligare operationer om så behövs.

## Ändra storlek på EPS‑bild

Efter beskärning vill du ofta ändra storleken på EPS‑filen för visning eller utskrift. Aspose.Page stödjer tre måttenheter.

### Ändra storlek i tum

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Ändra storlek i millimeter

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Ändra storlek i procent

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Varje anrop skriver över den föregående utdata, så se till att skapa en ny ström om du behöver separata filer för varje storlek.

## Vanliga problem & felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| **Bounding box values out of range** | Ny ruta överskrider de ursprungliga dimensionerna | Verifiera `initialBoundingBox`‑värdena och välj koordinater inom det intervallet. |
| **Output file is empty** | Utdataströmmen har inte spolas eller stängts | Se till att `using`‑blocket slutförs innan du får åtkomst till filen, eller anropa `outputEpsStream.Flush()`. |
| **Unexpected scaling** | Blandning av enheter (t.ex. tum vs. millimeter) | Ange alltid rätt `Units`‑enum som matchar dina storleksvärden. |

## Vanliga frågor

### Q1: Kan jag använda Aspose.Page för .NET med andra bildformat?

A1: Aspose.Page fokuserar främst på EPS‑bilder, men Aspose tillhandahåller olika bibliotek för olika format. Kontrollera deras dokumentation för specifika format.

### Q2: Hur kan jag skaffa en tillfällig licens för Aspose.Page för .NET?

A2: Besök [denna länk](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens för testning.

### Q3: Finns det några begränsningar för bildstorleken jag kan bearbeta med Aspose.Page för .NET?

A3: Aspose.Page är designat för att hantera bilder av olika storlekar. Prestandan kan dock variera beroende på bildens komplexitet.

### Q4: Finns det ett community‑forum för Aspose.Page‑diskussioner?

A5: Ja, du kan engagera dig i Aspose.Page‑communityn [här](https://forum.aspose.com/c/page/39).

### Q5: Var kan jag hitta detaljerad dokumentation för Aspose.Page för .NET?

A5: Se dokumentationen [här](https://reference.aspose.com/page/net/).

---

**Senast uppdaterad:** 2026-03-16  
**Testat med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
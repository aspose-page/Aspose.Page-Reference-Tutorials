---
title: Ändra storlek på EPS-bilder med Aspose.Page för .NET
linktitle: Ändra storlek på EPS-bilder
second_title: Aspose.Page .NET API
description: Utforska den sömlösa processen att ändra storlek på EPS-bilder i .NET med Aspose.Page. Uppnå precision i punkter, tum, millimeter och procent utan ansträngning.
type: docs
weight: 11
url: /sv/net/image-manipulation/resize-eps-images/
---
## Introduktion

Vill du ändra storlek på EPS-bilder sömlöst med Aspose.Page för .NET? Denna handledning är din omfattande guide för att enkelt manipulera storleken på EPS-bilder i olika enheter som punkter, tum, millimeter och procent. Aspose.Page för .NET tillhandahåller en kraftfull uppsättning verktyg, och i den här handledningen går vi igenom processen steg för steg.

## Förutsättningar

Innan du dyker in i storleksändringsmagin, se till att du har följande förutsättningar på plats:

-  Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/page/net/).

- Dokumentkatalog: Skapa en katalog där du lagrar din EPS-inmatningsfil och utdatafiler med ändrad storlek.

Nu när du har ställt in allt, låt oss fortsätta att importera de nödvändiga namnrymden och fördjupa oss i steg-för-steg-guiden.

## Importera namnområden

I ditt .NET-projekt börjar du med att importera de nödvändiga namnområdena för att arbeta med Aspose.Page. Lägg till följande kod i början av filen:

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

## Steg 1: Ändra storlek i poäng

Låt oss börja med att ändra storlek på en EPS-bild i punkter. Poäng är en standardmåttenhet inom den grafiska industrin.

```csharp
public static void ResizeInPoints()
{
    // Din dokumentkatalog
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Steg 2: Ändra storlek i tum

Låt oss nu ändra storlek på en EPS-bild i tum, en vanlig enhet som används i grafisk design.

```csharp
public static void ResizeInInches()
{
    // Din dokumentkatalog
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Steg 3: Ändra storlek i millimeter

Låt oss nu ändra storlek på en EPS-bild i millimeter, en annan mycket använd enhet inom design och tryck.

```csharp
public static void ResizeInMillimeters()
{
    // Din dokumentkatalog
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Steg 4: Ändra storlek i procent

Låt oss slutligen ändra storlek på en EPS-bild med hjälp av procentsatser, vilket ger en flexibel metod för att justera bildstorleken.

```csharp
public static void ResizeInPercents()
{
    // Din dokumentkatalog
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Integrera gärna dessa metoder i ditt projekt, så kommer du att ändra storlek på EPS-bilder utan ansträngning. Experimentera med olika enheter för att uppnå önskade dimensioner.

## Slutsats

Grattis! Du har bemästrat konsten att ändra storlek på EPS-bilder med Aspose.Page för .NET. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för att manipulera vektorgrafik. Oavsett om du designar för tryckta eller digitala medier, ger Aspose.Page dig möjlighet att uppnå exakta och anpassade resultat.

## FAQ's

### F1: Kan jag ändra storlek på flera EPS-bilder samtidigt?

S1: Ja, du kan gå igenom en samling EPS-filer och tillämpa metoderna för storleksändring i enlighet därmed.

### F2: Är Aspose.Page kompatibel med andra bildformat?

S2: Aspose.Page fokuserar främst på PostScript- och EPS-format. För andra bildformat, överväg att använda Aspose.Imaging.

### F3: Finns det några licensöverväganden för kommersiella projekt?

 A3: Ja, se till att du har en giltig licens. Besök[här](https://purchase.aspose.com/buy) för licensinformation.

### F4: Kan jag prova Aspose.Page innan jag köper?

 A4: Absolut! Du kan få en gratis provperiod[här](https://releases.aspose.com/).

### F5: Var kan jag söka ytterligare hjälp eller diskutera frågor?

 A5: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) att få kontakt med samhället och få hjälp.
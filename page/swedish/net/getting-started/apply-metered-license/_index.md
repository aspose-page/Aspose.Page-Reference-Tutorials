---
title: Tillämpa mätlicens med Aspose.Page för .NET
linktitle: Tillämpa mätlicens
second_title: Aspose.Page .NET API
description: Utforska den sömlösa integrationen av Aspose.Page för .NET med den här steg-för-steg-guiden om hur du ansöker om en uppmätt licens. Optimera dokumentbehandlingen utan ansträngning.
weight: 10
url: /sv/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tillämpa mätlicens med Aspose.Page för .NET

## Introduktion

Lås upp den fulla potentialen hos Aspose.Page för .NET genom att tillämpa en uppmätt licens. Den här handledningen guidar dig genom processen att ställa in och tillämpa den uppmätta licensen, vilket säkerställer smidig och optimerad användning av detta kraftfulla .NET-bibliotek.

## Förutsättningar

Innan du dyker in i stegen, se till att du har följande förutsättningar på plats:

-  En giltig Aspose.Page för .NET-licens: Du kan få den från[buy.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page-bibliotek installerat: Se[dokumentation](https://reference.aspose.com/page/net/) för installationsanvisningar.
- .NET-utvecklingsmiljö: Se till att du har en fungerande .NET-miljö inställd på din dator.

## Importera namnområden

I ditt .NET-projekt importerar du de nödvändiga namnområdena för att komma åt Aspose.Page-funktioner:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Steg 1: Ställ in uppmätta offentliga och privata nycklar

 Initiera`Aspose.Page.Metered` klass och ställ in de uppmätta offentliga och privata nycklarna. Byta ut`<type public key here>` och`<type private key here>` med dina faktiska nycklar.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Steg 2: Ladda EPS-fil och skapa dokument

 Ange sökvägen till din EPS-fil och skapa en ström för att läsa dess innehåll. Skapa sedan en instans av`PsDocument` klass från strömmen.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Steg 3: Konvertera EPS till PNG-bild

 Skapa en`ImageDevice` för att konvertera EPS-filen till en PNG-bild. Spara EPS-filen som en bild med hjälp av`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Steg 4: Hämta bildbytes

Hämta bildbyte, där varje byte-array representerar en sida. I det här fallet har vi en sida.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Steg 5: Spara bildbytes till fil

Spara bildbytes till en fil, vilket säkerställer framgångsrik konvertering från EPS till PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Steg 6: Verifiera mätlicens

Kontrollera visuellt om den uppmätta licensen tillämpas framgångsrikt. Om den resulterande bilden inte innehåller det röda utvärderingsmeddelandet, indikerar det att den uppmätta licensen tillämpas utan några problem.

Nu är du redo att dra nytta av alla funktioner i Aspose.Page för .NET med en uppmätt licens!

## Slutsats

Denna steg-för-steg-guide har utrustat dig med kunskapen att sömlöst tillämpa en uppmätt licens med Aspose.Page för .NET. Förbättra dina dokumentbehandlingsmöjligheter och utforska de stora funktionerna som erbjuds av detta kraftfulla bibliotek.

## FAQ's

### F1: Hur får jag en mätlicens för Aspose.Page för .NET?

 A1: Besök[buy.aspose.com](https://purchase.aspose.com/buy) att skaffa en giltig licens.

### F2: Var kan jag hitta dokumentationen för Aspose.Page för .NET?

 A2: Se[Aspose.Page .NET](https://reference.aspose.com/page/net/) för omfattande dokumentation.

### F3: Finns det ett forum för Aspose.Page-diskussioner och support?

 A3: Ja, besök[forum](https://forum.aspose.com/c/page/39) att engagera sig i samhället och söka hjälp.

### F4: Kan jag prova Aspose.Page för .NET innan jag köper?

 A4: Absolut! Få tillgång till den kostnadsfria provperioden på[här](https://releases.aspose.com/).

### F5: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?

 A5: Besök[tillfällig licens/](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

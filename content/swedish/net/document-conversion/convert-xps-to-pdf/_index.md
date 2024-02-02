---
title: Konvertera XPS till PDF med Aspose.Page för .NET
linktitle: Konvertera XPS till PDF
second_title: Aspose.Page .NET API
description: Konvertera enkelt XPS till PDF i .NET med Aspose.Page. Ladda ner biblioteket, utforska dokumentationen och få en gratis provperiod.
type: docs
weight: 11
url: /sv/net/document-conversion/convert-xps-to-pdf/
---
## Introduktion

I den här handledningen kommer vi att fördjupa oss i processen att konvertera XPS-dokument (XML Paper Specification) till PDF (Portable Document Format) med hjälp av det kraftfulla Aspose.Page for .NET-biblioteket. Aspose.Page för .NET tillhandahåller en robust uppsättning funktioner för att arbeta med XPS-filer, vilket gör det möjligt för utvecklare att sömlöst konvertera dem till PDF-format med olika anpassningsalternativ.

## Förutsättningar

Innan vi ger oss ut på denna omvandlingsresa, se till att du har följande förutsättningar på plats:

-  Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner den från[Aspose.Page dokumentation](https://reference.aspose.com/page/net/).

- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö med Visual Studio eller någon annan kompatibel IDE.

- XPS-dokument: Förbered XPS-dokumentet som du vill konvertera till PDF. Detta kan vara din exempel-XPS-fil som lagras i en angiven katalog.

## Importera namnområden

Innan vi dyker in i koden, låt oss importera de nödvändiga namnområdena för att göra Aspose.Page för .NET-funktionerna tillgängliga i vår kod:

```csharp
using Aspose.Page.XPS;
```

## Steg 1: Initiera dokumentkatalogen

```csharp
string dataDir = "Your Document Directory";
```

Ersätt "Din dokumentkatalog" med sökvägen till katalogen som innehåller ditt XPS-dokument.

## Steg 2: Initiera PDF- och XPS-strömmar

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Öppna strömmar för både den utgående PDF-filen och den ingående XPS-filen. Se till att du har angett rätt filsökvägar.

## Steg 3: Ladda XPS-dokument

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Ladda XPS-dokumentet med Aspose.Page for .NET-biblioteket.

## Steg 4: Initiera PDF-sparalternativ

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Ställ in PDF-sparalternativen, inklusive parametrar som JPEG-kvalitetsnivå, bildkomprimering, textkomprimering och specifika sidnummer som ska inkluderas.

## Steg 5: Skapa PDF-renderingsenhet

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Skapa en renderingsenhet för PDF-formatet med Aspose.Page för .NET-biblioteket.

## Steg 6: Spara dokument till PDF

```csharp
document.Save(device, options);
```

Spara XPS-dokumentet till PDF med den angivna renderingsenheten och alternativen.

## Slutsats

Grattis! Du har framgångsrikt konverterat ett XPS-dokument till PDF med Aspose.Page för .NET. Detta mångsidiga bibliotek ger utvecklare en kraftfull verktygsuppsättning för att hantera olika dokumentformat utan ansträngning.

## FAQ's

### F1: Kan jag konvertera flera XPS-filer till en enda PDF med Aspose.Page för .NET?

S1: Ja, du kan gå igenom flera XPS-filer och följa samma steg för att slå samman dem till en enda PDF.

### F2: Finns det andra utdataformat som stöds av Aspose.Page för .NET?

S2: Ja, Aspose.Page för .NET stöder olika utdataformat, inklusive TIFF, JPEG, PNG och mer.

### F3: Hur kan jag anpassa utseendet på det konverterade PDF-dokumentet?

S3: Du kan justera alternativobjektets parametrar, såsom bildkomprimering och textkomprimering, för att uppnå önskat utseende.

### F4: Finns det en testversion tillgänglig för Aspose.Page för .NET?

 S4: Ja, du kan utforska funktionerna hos Aspose.Page för .NET genom att få en gratis provperiod från[här](https://releases.aspose.com/).

### F5: Var kan jag få communitysupport för Aspose.Page för .NET?

 A5: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsdiskussioner och stöd.
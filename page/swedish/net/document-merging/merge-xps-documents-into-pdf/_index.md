---
title: Slå ihop XPS-dokument till PDF med Aspose.Page för .NET
linktitle: Slå ihop XPS-dokument till PDF
second_title: Aspose.Page .NET API
description: Slå enkelt ihop XPS-dokument till högkvalitativa PDF-filer med Aspose.Page för .NET. Följ vår steg-för-steg-guide för en smidig dokumentkonverteringsupplevelse.
type: docs
weight: 11
url: /sv/net/document-merging/merge-xps-documents-into-pdf/
---
## Introduktion

det ständigt föränderliga landskapet för dokumentbehandling framstår Aspose.Page för .NET som ett kraftfullt verktyg för att sömlöst sammanfoga XPS-dokument till PDF-format. Den här handledningen guidar dig genom processen och delar upp varje steg för att säkerställa ett smidigt och effektivt genomförande.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page för .NET: Se till att du har Aspose.Page-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/page/net/).

- Dokumentfiler: Ha XPS-dokumentet (`input.xps`) redo i din angivna katalog.

## Importera namnområden

I ditt .NET-projekt, inkludera de nödvändiga namnrymden för att arbeta med Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Detta steg säkerställer att du har tillgång till de klasser och metoder som krävs för dokumentkonverteringen.

## Steg 1: Initiera strömmar

```csharp
// ExStart:3
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Initiera PDF-utdataström
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initiera XPS-indataström
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Exend:3
```

Det här steget innebär att ställa in in- och utströmmarna för XPS- och PDF-filerna. Se till att rätt sökvägar och filnamn används.

## Steg 2: Ladda XPS-dokument

```csharp
// ExStart:4
// Ladda XPS-dokument från strömmen
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// eller ladda XPS-dokument direkt från filen. Då behövs ingen xpsStream.
//XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// Exend:4
```

 Här laddar vi XPS-dokumentet i`XpsDocument` objekt, förbereda det för vidare bearbetning.

## Steg 3: Initiera sparalternativ

```csharp
// ExStart:5
// Initiera alternativobjekt med nödvändiga parametrar.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Exend:5
```

 Anpassa`PdfSaveOptions` objekt baserat på dina preferenser, och anger parametrar som bildkomprimering, textkomprimering och sidnummer.

## Steg 4: Skapa renderingsenhet

```csharp
// ExStart: 6
// Skapa renderingsenhet för PDF-format
PdfDevice device = new PdfDevice(pdfStream);
// Exend:6
```

 De`PdfDevice` är verktyget som ansvarar för att rendera XPS-dokumentet till PDF-format.

## Steg 5: Spara dokumentet

```csharp
// ExStart:7
document.Save(device, options);
// Exend:7
```

Slutligen sparar du dokumentet med hjälp av renderingsenheten och de angivna alternativen.

## Slutsats

Grattis! Du har framgångsrikt slagit samman XPS-dokument till PDF med Aspose.Page för .NET. Denna sömlösa process säkerställer bevarandet av dokumentkvalitet och formatering.

## FAQ's

### F1: Kan jag slå samman flera XPS-filer till en enda PDF?

 A1: Ja, det kan du. Justera helt enkelt`PageNumbers` parametern i`PdfSaveOptions` för att inkludera önskade sidor från olika XPS-filer.

### F2: Finns en tillfällig licens tillgänglig för Aspose.Page för .NET?

 A2: Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för teständamål.

### F3: Finns det några begränsningar för filstorleken när du använder Aspose.Page för dokumentkonvertering?

S3: Aspose.Page för .NET sätter inga strikta begränsningar på filstorleken, men optimal prestanda uppnås med rimliga filstorlekar.

### F4: Kan jag anpassa utdata-PDF-filen ytterligare, som att lägga till vattenstämplar eller kommentarer?

S4: Ja, Aspose.Page för .NET tillhandahåller omfattande funktioner för PDF-manipulering. Se dokumentationen för avancerade anpassningsalternativ.

### F5: Stöder Aspose.Page för .NET utveckling över plattformar?

S5: Ja, Aspose.Page för .NET är utformad för att fungera sömlöst på olika plattformar.
---
title: Lägg till enkla egenskaper med Aspose.Page för .NET
linktitle: Lägg till enkla egenskaper
second_title: Aspose.Page .NET API
description: Förbättra EPS-filer med Aspose.Page för .NET. Lägg till enkla egenskaper utan ansträngning för anpassade dokumentmetadata.
type: docs
weight: 14
url: /sv/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Introduktion

När det gäller dokumentmanipulation och förbättring framstår Aspose.Page för .NET som ett kraftfullt verktyg som ger utvecklare möjlighet att lägga till och ändra XMP-metadata i EPS-filer sömlöst. Denna handledning guidar dig genom processen att lägga till enkla egenskaper till en EPS-fil med Aspose.Page för .NET.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

1.  Aspose.Page for .NET: Se till att du har Aspose.Page for .NET installerat i din utvecklingsmiljö. Om inte kan du ladda ner den[här](https://releases.aspose.com/page/net/).

2.  Dokumentkatalog: Skapa en katalog för att lagra dina EPS-filer. Uppdatera`dataDir` variabel i det medföljande kodavsnittet med sökvägen till din dokumentkatalog.

## Importera namnområden

Till att börja, importera nödvändiga namnområden för att möjliggöra kommunikation med Aspose.Page för .NET. Lägg till följande rader i början av din kodfil:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Steg 1: Initiera EPS File Input Stream

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Initiera EPS-filinmatningsström
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Skapa PsDocument-instans från stream
PsDocument document = new PsDocument(psStream);
```

## Steg 2: Hämta XMP-metadata

```csharp
// Skaffa XMP-metadata. Om EPS-filen inte innehåller XMP-metadata får vi en ny fylld med värden från PS-metadatakommentarer (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Steg 3: Ändra XMP-metadatavärden

```csharp
// Ändra XMP-metadatavärden
DateTime now = DateTime.UtcNow;

// Lägg till heltalsegenskap
xmp.Add("xmp:Intg1", new XmpValue(111));

// Lägg till DateTime-egenskap
xmp.Add("xmp:Date1", new XmpValue(now));

// Lägg till dubbel egendom
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Lägg till strängegenskap
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Steg 4: Spara EPS-fil med ändrad XMP-metadata

```csharp
// Spara EPS-fil med ändrade XMP-metadata

// Skapa utdataström
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Spara EPS-fil
    document.Save(outPsStream);
}
```

## Steg 5: Stäng FileStream

```csharp
finally
{
    psStream.Close();
}
```

Genom att följa dessa steg kan du enkelt infoga enkla egenskaper i dina EPS-filer med Aspose.Page för .NET.

## Slutsats

Sammanfattningsvis visar sig Aspose.Page för .NET vara en ovärderlig tillgång för utvecklare som vill förbättra EPS-filer med anpassade XMP-metadata. Genom att lägga till enkla egenskaper kan du anpassa och berika dina dokument för att möta specifika krav, vilket öppnar upp en värld av möjligheter för dokumentmanipulation.

## FAQ's

### F1: Är Aspose.Page för .NET kompatibel med alla EPS-filer?

S1: Aspose.Page för .NET stöder ett brett utbud av EPS-filer. Men kompatibiliteten kan variera beroende på komplexiteten och strukturen hos enskilda filer.

### F2: Kan jag ändra befintliga XMP-metadata med Aspose.Page för .NET?

A2: Absolut! Som visas i denna handledning kan du enkelt ändra befintliga XMP-metadatavärden eller lägga till nya för att passa dina behov.

### F3: Finns det några begränsningar för vilka typer av egenskaper jag kan lägga till?

S3: Aspose.Page för .NET stöder olika datatyper för egenskaper, inklusive heltal, datum, dubblar och strängar. Du har flexibilitet att välja lämplig typ för din metadata.

### F4: Hur kan jag få teknisk support för Aspose.Page för .NET?

 S4: För teknisk hjälp, besök[Aspose.Page Forum](https://forum.aspose.com/c/page/39) eller utforska[dokumentation](https://reference.aspose.com/page/net/) för omfattande vägledning.

### F5: Finns det en gratis testversion tillgänglig för Aspose.Page för .NET?

 A5: Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).
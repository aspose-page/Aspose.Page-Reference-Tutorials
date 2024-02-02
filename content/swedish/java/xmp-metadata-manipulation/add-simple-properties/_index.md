---
title: Lägg till enkla egenskaper i XMP med Java
linktitle: Lägg till enkla egenskaper i XMP med Java
second_title: Aspose.Page Java API
description: Lås upp Aspose.Page för Javas potential med vår guide om att lägga till egenskaper till XMP-metadata i EPS-filer. Lyft dokumentbehandlingen utan ansträngning!
type: docs
weight: 14
url: /sv/java/xmp-metadata-manipulation/add-simple-properties/
---
## Introduktion
det ständigt föränderliga landskapet för dokumentbehandling är det avgörande att hantera metadata effektivt. Aspose.Page för Java ger utvecklare möjlighet att manipulera XMP-data (Extensible Metadata Platform) sömlöst. I den här handledningen kommer vi att utforska processen att lägga till enkla egenskaper till XMP med hjälp av Java, vilket ger dig en omfattande steg-för-steg-guide.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Page för Java-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/page/java/).
- Ett exempel på EPS-fil som innehåller metadata. Om du inte har en, använd gärna den medföljande filen "xmp3.eps".
## Importera paket
Se till att du importerar de nödvändiga paketen för att kickstarta ditt projekt:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Steg 1: Hämta XMP-metadata
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Initiera indata EPS-filström
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Skaffa XMP-metadata. Om EPS-filen inte innehåller XMP-metadata får vi en ny fylld med värden från PS-metadatakommentarer (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Steg 2: Lägg till Date Property
```java
// Lägg till värdet för datumegenskapen "xmp:Date1".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Steg 3: Lägg till heltalsegenskap
```java
// Lägg till heltalsegenskapens värde "xmp:Intg1".
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Steg 4: Lägg till dubbel egendom
```java
// Lägg till dubbelegenskapsvärdet "xmp:Double1".
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Steg 5: Lägg till strängegenskap
```java
// Lägg till strängegenskapens värde "xmp:String1".
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Steg 6: Spara dokument
```java
// Initiera utdata EPS-filström
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Spara dokument med ändrade XMP-metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Steg 7: Stäng strömmar
```java
// Stäng ingångs EPS-ström
psStream.close();
```
## Slutsats
Aspose.Page för Java förenklar processen att manipulera XMP-metadata i EPS-filer. Genom att följa denna steg-för-steg-guide kan du enkelt lägga till enkla egenskaper för att förbättra ditt dokuments metadata.
## Vanliga frågor
### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Aspose.Page stöder i första hand Java, men det finns versioner tillgängliga för andra språk som .NET.
### Finns en gratis testversion tillgänglig för Aspose.Page för Java?
 Ja, du kan utforska funktionerna i Aspose.Page genom att få en gratis provperiod[här](https://releases.aspose.com/).
### Var kan jag hitta detaljerad dokumentation för Aspose.Page för Java?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/java/).
### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 En tillfällig licens kan förvärvas[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa Aspose.Page för Java?
 Du kan köpa produkten[här](https://purchase.aspose.com/buy).
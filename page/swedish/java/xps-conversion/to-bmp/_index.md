---
title: Konvertera XPS till BMP i Java
linktitle: Konvertera XPS till BMP i Java
second_title: Aspose.Page Java API
description: Lär dig hur du konverterar XPS till BMP i Java med Aspose.Page. Följ vår enkla guide för effektiv och högkvalitativ dokumentkonvertering.
type: docs
weight: 10
url: /sv/java/xps-conversion/to-bmp/
---
## Introduktion
Välkommen till denna steg-för-steg-guide för att konvertera XPS-filer (XML Paper Specification) till BMP-format (Bitmap) i Java med Aspose.Page. Aspose.Page för Java är ett kraftfullt bibliotek som tillhandahåller omfattande funktioner för att arbeta med XPS-dokument. I den här handledningen går vi igenom processen att konvertera XPS-filer till BMP-bilder utan ansträngning.
## Förutsättningar
Innan du dyker in i konverteringsprocessen, se till att du har följande förutsättningar:
- Java Development Environment: Se till att du har Java installerat på ditt system.
-  Aspose.Page for Java Library: Ladda ner och inkludera Aspose.Page for Java-biblioteket i ditt projekt. Du hittar biblioteket[här](https://releases.aspose.com/page/java/).
- Exempel på XPS-fil: Förbered ett exempel på ett XPS-dokument som du vill konvertera till BMP.
## Importera paket
Inkludera de nödvändiga Aspose.Page-paketen i din Java-kod:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
Låt oss dela upp konverteringsprocessen i enkla steg:
## Steg 1: Ladda XPS-dokument
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Ladda XPS-dokument
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Steg 2: Initiera alternativ
```java
// Initiera alternativobjekt med nödvändiga parametrar.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[]{1, 2, 6});
```
## Steg 3: Skapa renderingsenhet
```java
// Skapa renderingsenhet för BMP-format
ImageDevice device = new ImageDevice();
```
## Steg 4: Spara dokument
```java
// Spara XPS-dokument till BMP med hjälp av alternativ och enhet
document.save(device, options);
```
## Steg 5: Iterera och spara bilder
```java
// Iterera genom dokumentpartitioner
for (int i = 0; i < device.getResult().length; i++) {
    // Iterera genom partitionssidor
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initiera bildutgångsström
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Skriv bild
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
Upprepa dessa steg för ytterligare anpassning eller modifiering du kan behöva i konverteringsprocessen.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du konverterar XPS-filer till BMP i Java med Aspose.Page. Flexibiliteten och användarvänligheten som tillhandahålls av Aspose.Page gör det till ett värdefullt verktyg för att hantera dokumentkonverteringsuppgifter.
## Vanliga frågor
### F: Kan jag anpassa upplösningen på BMP-bilderna?
 S: Ja, du kan justera upplösningen genom att ändra`options.setResolution()`parameter i koden.
### F: Är Aspose.Page kompatibel med olika Java-versioner?
S: Ja, Aspose.Page stöder ett brett utbud av Java-versioner. Se till att du har en kompatibel version installerad.
### F: Hur kan jag konvertera XPS-filer från ett specifikt sidintervall?
 A: Använd`options.setPageNumbers()` metod för att ange sidnumren du vill konvertera.
### F: Finns det andra utdataformat som stöds av Aspose.Page?
S: Ja, Aspose.Page stöder olika utdataformat. Se dokumentationen för en fullständig lista.
### F: Var kan jag hitta ytterligare hjälp eller support?
 A: Besök[Aspose.Page Forum](https://forum.aspose.com/c/page/39) för samhällsstöd och diskussioner.
---
title: Konvertera XPS till PNG i Java
linktitle: Konvertera XPS till PNG i Java
second_title: Aspose.Page Java API
description: Konvertera enkelt XPS till PNG i Java med Aspose.Page. Effektivisera dokumentuppgifter med denna pålitliga och utvecklarvänliga lösning.
type: docs
weight: 13
url: /sv/java/xps-conversion/to-png/
---
## Introduktion
I den dynamiska världen av mjukvaruutveckling uppstår behovet av att konvertera XPS-dokument (XML Paper Specification) till PNG-bilder (Portable Network Graphics) ofta. För att utföra denna uppgift sömlöst i Java erbjuder Aspose.Page en kraftfull lösning. I den här handledningen kommer vi att gå igenom processen att konvertera XPS till PNG med Aspose.Page för Java.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar inställda:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Page för Java: Ladda ner och installera Aspose.Page-biblioteket. Du hittar nedladdningslänken[här](https://releases.aspose.com/page/java/).
3. Integrated Development Environment (IDE): Välj en Java-kompatibel IDE som IntelliJ IDEA eller Eclipse.
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för att använda Aspose.Page-funktionerna. Lägg till följande importsatser i början av din Java-fil:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Steg 1: Ställ in dokumentkatalog
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
```
## Steg 2: Ladda XPS-dokument
```java
// Ladda XPS-dokument
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Steg 3: Initiera alternativ
```java
// Initiera alternativobjekt med nödvändiga parametrar.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Steg 4: Skapa renderingsenhet
```java
// Skapa renderingsenhet för PDF-format
ImageDevice device = new ImageDevice();
```
## Steg 5: Spara och iterera
```java
// Spara XPS-dokument till PNG med hjälp av alternativ och enhet
document.save(device, options);
//Iterera genom dokumentpartitioner (fasta dokument, i XPS-termer)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterera genom partitionssidor
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initiera bildutgångsström
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Skriv bild
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Stäng strömmen
        imageStream.close();
    }
}
```
Genom att följa dessa steg kan du enkelt konvertera XPS-dokument till PNG-bilder med Aspose.Page för Java.
## Slutsats
Sammanfattningsvis förenklar Aspose.Page för Java konverteringsprocessen från XPS till PNG, vilket ger utvecklare ett pålitligt och effektivt verktyg. Inkludera det här biblioteket i dina Java-projekt för att effektivisera dokumentmanipuleringsuppgifter.
## Vanliga frågor
### Kan jag använda Aspose.Page för Java i kommersiella projekt?
 Ja, Aspose.Page är en kommersiell produkt. Du kan hitta licensinformation[här](https://purchase.aspose.com/buy).
### Finns det en gratis provperiod?
 Ja, du kan utforska en gratis provperiod[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentationen för Aspose.Page för Java?
 Den omfattande dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/java/).
### Hur får jag en tillfällig licens för teständamål?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Finns det gemenskapsforum för Aspose.Page-diskussioner?
 Ja, besök community-forumen[här](https://forum.aspose.com/c/page/39).
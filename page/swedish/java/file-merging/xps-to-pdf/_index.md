---
title: Konvertera XPS till PDF i Java
linktitle: Konvertera XPS till PDF i Java
second_title: Aspose.Page Java API
description: Lär dig hur du enkelt konverterar XPS till PDF i Java med Aspose.Page. Följ vår steg-för-steg-guide för effektiv dokumentkonvertering.
weight: 11
url: /sv/java/file-merging/xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera XPS till PDF i Java

## Introduktion
När det gäller Java-utveckling är det en vanlig uppgift att konvertera XPS till PDF, och att ha ett tillförlitligt verktyg för att uppnå detta sömlöst är av största vikt. Aspose.Page för Java är ett exemplariskt bibliotek som erbjuder robusta funktioner för hantering av XPS-dokument. Denna handledning guidar dig genom processen att konvertera XPS till PDF med Aspose.Page, vilket säkerställer enkelhet och effektivitet.
## Förutsättningar
Innan du går in i konverteringsprocessen, se till att du har följande förutsättningar på plats:
1. Java Development Kit (JDK): Se till att du har den senaste JDK installerad på ditt system.
2.  Aspose.Page for Java Library: Ladda ner och inkludera Aspose.Page for Java-biblioteket i ditt projekt. Du hittar biblioteket och dess dokumentation[här](https://reference.aspose.com/page/java/).
## Importera paket
När du har ställt in ditt projekt, importera de nödvändiga paketen för att arbeta med Aspose.Page. Här är ett utdrag som vägleder dig:
```java

import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Steg 1: Ange sökväg för dokumentkatalog
```java
String dataDir = "Your Document Directory";
```
Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen till ditt XPS-dokument.
## Steg 2: Initiera PDF Output Stream
```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```
Skapa ett FileOutputStream-objekt för PDF-filen och ange önskad utdatasökväg.
## Steg 3: Ladda XPS-dokument
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
Ladda XPS-dokumentet med klassen XpsDocument.
## Steg 4: Initiera PDF-sparalternativ
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
Konfigurera PDF-sparalternativen baserat på dina krav, såsom bild- och textkomprimeringsinställningar.
## Steg 5: Skapa renderingsenhet för PDF-format
```java
PdfDevice device = new PdfDevice(pdfStream);
```
Initiera ett PdfDevice-objekt för att rendera XPS-dokumentet till PDF.
## Steg 6: Spara dokumentet
```java
document.save(device, options);
```
Slutligen, spara XPS-dokumentet till PDF med hjälp av sparmetoden.
Genom att följa dessa enkla steg kan du sömlöst konvertera XPS till PDF i Java med Aspose.Page, vilket ger en pålitlig och effektiv lösning för dina dokumentkonverteringsbehov.
## Slutsats
Sammanfattningsvis förenklar Aspose.Page för Java konverteringsprocessen från XPS till PDF, vilket gör det möjligt för Java-utvecklare att sömlöst integrera denna funktionalitet i sina applikationer. Steg-för-steg-guiden säkerställer en smidig upplevelse, vilket gör den tillgänglig för både nybörjare och erfarna utvecklare.
## Vanliga frågor
### F: Är Aspose.Page kompatibel med olika versioner av Java?
S: Ja, Aspose.Page är designad för att vara kompatibel med olika Java-versioner.
### F: Kan jag anpassa komprimeringsinställningarna för den konverterade PDF-filen?
S: Absolut, Aspose.Page erbjuder alternativ för att anpassa bild- och textkomprimeringsinställningar.
### F: Var kan jag hitta ytterligare stöd eller diskussioner i samhället?
 A: Besök[Aspose.Page Forum](https://forum.aspose.com/c/page/39) för samhällsdiskussioner och stöd.
### F: Finns det en gratis testversion tillgänglig för Aspose.Page?
 S: Ja, du kan utforska en gratis provperiod[här](https://releases.aspose.com/).
### F: Hur kan jag få en tillfällig licens för Aspose.Page?
 S: Du kan skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

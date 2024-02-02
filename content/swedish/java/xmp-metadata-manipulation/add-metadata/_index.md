---
title: Lägg till metadata i XMP med Java
linktitle: Lägg till metadata i XMP med Java
second_title: Aspose.Page Java API
description: Utforska den sömlösa integrationen av Aspose.Page för Java och lär dig hur du lägger till XMP-metadata till dina EPS-filer utan ansträngning. Lyft ditt dokumenthanteringsspel idag!
type: docs
weight: 11
url: /sv/java/xmp-metadata-manipulation/add-metadata/
---
## Introduktion
Vill du förbättra ditt dokuments metadata genom att lägga till XMP-information med Java? Kolla inte vidare! Den här steg-för-steg-guiden leder dig genom processen att lägga till metadata till en EPS-fil med hjälp av Aspose.Page for Java-biblioteket. Aspose.Page är ett kraftfullt verktyg som förenklar dokumentmanipuleringsuppgifter i Java-applikationer.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Page för Java-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/page/java/).
- En EPS-fil som du vill ändra.
## Importera paket
Importera först de nödvändiga paketen till ditt Java-program:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Steg 1: Hämta XMP-metadata
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Initiera indata EPS-filström
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Skaffa XMP-metadata. Om EPS-filen inte innehåller XMP-metadata skapas en ny med värden från PS-metadatakommentarer (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen där dina dokument lagras.

## Steg 2: Hämta CreatorTool-värde
```java
// Få "CreatorTool"-värdet
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Steg 3: Hämta CreateDate-värde
```java
// Få värdet "CreateDate".
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Steg 4: Hämta titelvärde
```java
// Få värdet "Titel".
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Steg 5: Hämta formatvärde
```java
//Få "format" värde
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Steg 6: Hämta skaparvärde
```java
// Få "creator"-värde
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Steg 7: Hämta MetadataDate Value
```java
// Få värdet "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Steg 8: Spara dokument med nya XMP-metadata
```java
// Initiera utdata EPS-filström
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Spara dokument med nya XMP-metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Slutligen, glöm inte att stänga EPS-inmatningsströmmen:
```java
// Stäng ingångs EPS-ström
psStream.close();
```
Nu har du framgångsrikt lagt till metadata till din EPS-fil med Aspose.Page för Java!
## Slutsats
I den här handledningen utforskade vi processen att lägga till XMP-metadata till en EPS-fil med Aspose.Page for Java-biblioteket. Detta kraftfulla verktyg gör att du kan manipulera dokument sömlöst, vilket förbättrar din övergripande dokumenthanteringsupplevelse.
## Vanliga frågor
### F: Är Aspose.Page för Java gratis att använda?
 A: Aspose.Page för Java är en kommersiell produkt. Du kan utforska dess funktioner genom en gratis provperiod[här](https://releases.aspose.com/).
### F: Var kan jag hitta dokumentationen för Aspose.Page för Java?
 S: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/java/).
### F: Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 S: Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### F: Vilka filformat stöder Aspose.Page för Java?
S: Aspose.Page för Java stöder olika format, inklusive EPS, PDF och XPS.
### F: Kan jag köpa Aspose.Page för Java?
 S: Ja, du kan köpa Aspose.Page för Java[här](https://purchase.aspose.com/buy).
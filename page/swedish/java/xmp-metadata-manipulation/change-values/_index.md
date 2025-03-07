---
title: Ändra värden i XMP med Java
linktitle: Ändra värden i XMP med Java
second_title: Aspose.Page Java API
description: Förbättra EPS-dokument med Aspose.Page för Java. Ändra XMP-metadata enkelt för skräddarsytt och professionellt innehåll. #Javautveckling
weight: 17
url: /sv/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändra värden i XMP med Java

## Introduktion
När det gäller dokumentbearbetning och manipulation framstår Aspose.Page för Java som ett kraftfullt verktyg. Den här handledningen fördjupar sig i processen att ändra XMP-värden (Extensible Metadata Platform) i EPS-dokument (Encapsulated PostScript) med hjälp av Java med Aspose.Page-biblioteket. Genom att följa den medföljande steg-för-steg-guiden kommer du att lära dig hur du enkelt ändrar metadata och säkerställer att dina dokument är skräddarsydda för dina specifika krav.
## Förutsättningar
Innan vi börjar med den här handledningen, se till att du har följande förutsättningar på plats:
1. Java-utvecklingsmiljö: Se till att du har en fungerande Java-utvecklingsmiljö på din maskin.
2.  Aspose.Page for Java Library: Ladda ner och installera Aspose.Page for Java-biblioteket. Du kan hitta det nödvändiga paketet[här](https://releases.aspose.com/page/java/).
## Importera paket
Börja med att importera de nödvändiga paketen till ditt Java-projekt. Dessa paket är viktiga för att interagera med och manipulera EPS-dokument.
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
Hämta XMP-metadata från EPS-dokumentet. Om EPS-filen inte innehåller XMP-metadata kommer en ny att skapas med värden från PS-metadatakommentarer som %%Creator, %%CreateDate och %%Title.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Initiera indata EPS-filström
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Skaffa XMP-metadata. Om EPS-filen inte innehåller XMP-metadata skapas en ny med värden från PS-metadatakommentarer
XmpMetadata xmp = document.getXmpMetadata();
```
## Steg 2: Ändra "ModifyDate"-värde
Ändra värdet "ModifyDate" i XMP-metadata för att återspegla det önskade datumet.
```java
// Ändra "ModifyDate"-värdet
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Steg 3: Ändra "Creator"-värde
Uppdatera värdet "Creator" i XMP-metadata för att ange skaparen av dokumentet.
```java
// Ändra värdet för "skapare".
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Steg 4: Ändra "Titel"-värde
Ändra "Titel"-värdet i XMP-metadata för att ställa in en lämplig titel för dokumentet.
```java
//Ändra "titel"-värdet
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Steg 5: Spara dokument med ändrad XMP-metadata
Spara dokumentet med den uppdaterade XMP-metadatan till en ny EPS-fil.
```java
// Initiera utdata EPS-filström
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Spara dokument med ändrade XMP-metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Slutsats
Grattis! Du har framgångsrikt navigerat processen för att ändra XMP-värden i EPS-dokument med Aspose.Page för Java. Denna handledning har utrustat dig med kunskapen att ändra metadata, vilket säkerställer att dina dokument sömlöst stämmer överens med dina specifika krav.
## Vanliga frågor
### F: Hur kan jag hantera tidszonsöverväganden när jag ändrar XMP-värden?
 Utnyttja`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` för att säkerställa konsekvens i tidszonsinställningar.
### F: Kan jag ändra flera XMP-värden i en enda operation?
 Ja, genom att använda`put` metod för varje önskat värde kan du ändra flera XMP-värden samtidigt.
### F: Var kan jag hitta ytterligare dokumentation för Aspose.Page för Java?
 Utforska den omfattande dokumentationen[här](https://reference.aspose.com/page/java/).
### F: Finns det en gratis testversion tillgänglig för Aspose.Page för Java?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### F: Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

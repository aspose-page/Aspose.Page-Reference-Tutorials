---
title: Lägg till Array-objekt i XMP-metadata med Java
linktitle: Lägg till Array-objekt i XMP-metadata med Java
second_title: Aspose.Page Java API
description: Förbättra EPS-filer med Aspose.Page för Java. Lär dig att lägga till arrayobjekt till XMP-metadata utan ansträngning. Följ vår steg-för-steg-guide nu!
weight: 10
url: /sv/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Array-objekt i XMP-metadata med Java

## Introduktion
Välkommen till vår steg-för-steg-guide om hur du använder Aspose.Page för Java för att lägga till matrisobjekt i XMP-metadata. Aspose.Page är ett kraftfullt Java-bibliotek som låter dig manipulera och arbeta med olika dokumentformat, inklusive EPS-filer. I den här handledningen kommer vi att fokusera på den specifika uppgiften att lägga till arrayobjekt i XMP-metadata med hjälp av Java.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar:
- Aspose.Page för Java-biblioteket installerat.
- Grundläggande förståelse för Java-programmering.
- En giltig EPS-fil med befintlig XMP-metadata eller PS-metadatakommentarer.
## Importera paket
För att komma igång måste du importera de nödvändiga paketen för att arbeta med Aspose.Page. Inkludera följande rader i början av din Java-fil:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
det här steget hämtar vi befintlig XMP-metadata från EPS-filen. Om EPS-filen inte redan innehåller XMP-metadata genererar Aspose.Page en ny och fyller den med värden från PS-metadatakommentarer.
## Steg 2: Lägg till "dc:title" Array-objekt
```java
// Lägg till ytterligare ett "dc:title" arrayobjekt
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nu lägger vi till ett nytt arrayobjekt till egenskapen "dc:title" i XMP-metadata. Ersätt "NewTitle" med önskad titel.
## Steg 3: Lägg till "dc:creator" Array-objekt
```java
// Lägg till ytterligare ett "dc:creator"-arrayobjekt
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
På samma sätt lägger vi till ett nytt arrayobjekt till egenskapen "dc:creator" i XMP-metadata. Ersätt "NewCreator" med önskad skaparinformation.
## Steg 4: Initiera Output EPS File Stream
```java
// Initiera utdata EPS-filström
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Förbered EPS-filströmmen där det ändrade dokumentet med uppdaterad XMP-metadata kommer att sparas.
## Steg 5: Spara dokument med ändrad XMP-metadata
```java
//Spara dokument med ändrade XMP-metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Spara dokumentet med den uppdaterade XMP-metadatan till EPS-utdatafilen.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till matrisobjekt i XMP-metadata med Aspose.Page för Java. Detta kraftfulla bibliotek förenklar processen att manipulera EPS-filer och ger omfattande funktionalitet för dokumentbehandling.
## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra dokumentformat?
Ja, Aspose.Page stöder olika dokumentformat, inklusive EPS, PDF och XPS.
### Finns det en gratis testversion tillgänglig för Aspose.Page för Java?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentationen för Aspose.Page för Java?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/java/).
### Hur kan jag köpa Aspose.Page för Java?
 Du kan köpa produkten[här](https://purchase.aspose.com/buy).
### Finns tillfälliga licenser tillgängliga för Aspose.Page för Java?
 Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

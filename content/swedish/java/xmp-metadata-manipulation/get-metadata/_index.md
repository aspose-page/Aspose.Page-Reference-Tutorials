---
title: Få metadata från XMP med Java
linktitle: Få metadata från XMP med Java
second_title: Aspose.Page Java API
description: Lås upp kraften i Aspose.Page för Java för att enkelt extrahera XMP-metadata. Lyft dokumentanalys med vår steg-för-steg-guide!
type: docs
weight: 18
url: /sv/java/xmp-metadata-manipulation/get-metadata/
---
## Introduktion
Välkommen till vår steg-för-steg-guide om hur du använder Aspose.Page för Java för att extrahera metadata från XMP-filer. XMP (Extensible Metadata Platform) tillhandahåller ett standardiserat sätt att lagra metadata i filer. Den här handledningen fokuserar på att hämta viktig information från XMP med Java, och ger insikter i dokumentdetaljer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Java Development Kit (JDK): Se till att du har Java installerat på din maskin.
-  Aspose.Page för Java: Ladda ner och installera Aspose.Page-biblioteket, som du kan hitta[här](https://releases.aspose.com/page/java/).
## Importera paket
Importera nödvändiga paket i ditt Java-projekt:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Steg 1: Initiera Input EPS File Stream
Börja med att ange sökvägen till din dokumentkatalog och initialisera EPS-filströmmen.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Steg 2: Hämta XMP-metadata
Hämta XMP-metadata från EPS-filen. Om filen saknar XMP-metadata kommer en ny att genereras med värden från PS-metadatakommentarer.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Steg 3: Extrahera CreatorTool-information
Kontrollera och skriv ut "CreatorTool"-värdet från XMP-metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Steg 4: Extrahera CreateDate-information
Kontrollera och skriv ut "CreateDate"-värdet från XMP-metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Steg 5: Hämta miniatyrbildsbredd
Om det finns miniatyrer, extrahera och skriv ut bredden på den första miniatyren.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Steg 6: Extrahera formatinformation
Kontrollera och skriv ut "format"-värdet från XMP-metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Steg 7: Skaffa DocumentID
Kontrollera och skriv ut "DocumentID"-värdet från XMP-metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du extraherar XMP-metadata med Aspose.Page för Java. Den här guiden ger en omfattande översikt över processen, vilket säkerställer att du effektivt kan hämta viktig information från dina dokument.
## Vanliga frågor
### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
 Ja, Aspose.Page stöder flera språk, inklusive Java, .NET och mer. Kolla[dokumentation](https://reference.aspose.com/page/java/) för detaljer.
### Finns en gratis testversion tillgänglig för Aspose.Page för Java?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### Var kan jag hitta support för Aspose.Page för Java?
 Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd.
### Hur får jag en tillfällig licens för Aspose.Page för Java?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Finns det ytterligare resurser för Aspose.Page för Java?
 Utforska hela[dokumentation](https://reference.aspose.com/page/java/) och ladda ner biblioteket[här](https://releases.aspose.com/page/java/).
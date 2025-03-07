---
title: Lägg till sida vid sida i Java XPS
linktitle: Lägg till sida vid sida i Java XPS
second_title: Aspose.Page Java API
description: Utforska sömlös Java XPS-dokumentmanipulation med Aspose.Page. Lär dig att lägga till sida vid sida med bilder utan ansträngning med hjälp av denna steg-för-steg-guide.
weight: 11
url: /sv/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till sida vid sida i Java XPS

## Introduktion
Java-utvecklingens dynamiska värld växer behovet av effektiv dokumenthantering och skapande ständigt. Aspose.Page för Java framstår som ett kraftfullt verktyg som ger utvecklare möjlighet att arbeta med XPS-dokument sömlöst. Denna handledning fokuserar på en specifik uppgift – att lägga till en sida vid sida i ett Java XPS-dokument.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Page for Java: Ladda ner och installera Aspose.Page for Java från[hemsida](https://releases.aspose.com/page/java/).
3. Din dokumentkatalog: Välj eller skapa en katalog där du vill spara ditt XPS-dokument.
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för att använda Aspose.Page-funktionerna:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Låt oss nu dela upp processen att lägga till en sida vid sida i ett Java XPS-dokument i tydliga, hanterbara steg.
## Steg 1: Konfigurera ditt projekt
Börja med att ställa in ditt Java-projekt och se till att Aspose.Page för Java är korrekt integrerat.
## Steg 2: Skapa XPS-dokument
Initiera ett nytt XPS-dokument med följande kod:
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```
## Steg 3: Definiera sökväg för sida vid sida
Ange sökvägen till den sida vid sida som du vill lägga till i XPS-dokumentet.
## Steg 4: Lägg till sida vid sida
Använd kodavsnittet nedan för att lägga till en sida vid sida i XPS-dokumentet:
```java
// Kakelbild
// ImageBrush fylld rektangel längst upp till höger nedan
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Steg 5: Spara dokumentet
Spara slutligen det resulterande XPS-dokumentet med koden nedan:
```java
// Spara resulterande XPS-dokument
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Upprepa dessa steg för att enkelt infoga en sida vid sida i ditt Java XPS-dokument med Aspose.Page.
## Slutsats
Aspose.Page för Java effektiviserar processen att arbeta med XPS-dokument, och erbjuder utvecklare en effektiv lösning för dokumentmanipulation. Genom att följa denna steg-för-steg-guide kan du enkelt lägga till en sida vid sida i ditt Java XPS-dokument.

## Vanliga frågor
### Är Aspose.Page kompatibel med alla Java-versioner?
 Aspose.Page är designad för att fungera med olika Java-versioner. Säkerställ kompatibilitet genom att kontrollera dokumentationen[här](https://reference.aspose.com/page/java/).
### Kan jag använda Aspose.Page för kommersiella projekt?
Ja, Aspose.Page erbjuder kommersiella licenser. Köp dem[här](https://purchase.aspose.com/buy).
### Finns det en gratis provperiod?
 Ja, utforska Aspose.Page-funktionerna med en gratis provperiod[här](https://releases.aspose.com/).
### Var kan jag hitta gemenskapsstöd och diskussioner?
 Engagera dig med Aspose.Page-communityt på[forum](https://forum.aspose.com/c/page/39).
### Hur kan jag få en tillfällig licens för Aspose.Page?
 Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

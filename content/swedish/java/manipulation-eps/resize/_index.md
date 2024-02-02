---
title: Ändra storlek på EPS-filer i Java med Aspose.Page
linktitle: Ändra storlek på EPS-fil i Java
second_title: Aspose.Page Java API
description: Lär dig hur du ändrar storlek på EPS-filer i Java utan ansträngning med Aspose.Page för Java. Följ vår omfattande guide för steg-för-steg-instruktioner.
type: docs
weight: 11
url: /sv/java/manipulation-eps/resize/
---
## Introduktion
Välkommen till vår steg-för-steg-guide om storleksändring av EPS-filer i Java med hjälp av det kraftfulla biblioteket Aspose.Page. Om du någonsin har behövt justera dimensionerna på dina EPS-bilder programmatiskt, är du på rätt plats. I den här handledningen kommer vi att utforska olika storleksändringsalternativ, inklusive punkter, tum, millimeter och procent, vilket ger dig den flexibilitet du behöver för dina specifika krav.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:
- Java Development Kit (JDK) installerat på din maskin.
-  Aspose.Page för Java-biblioteket. Du kan ladda ner den[här](https://releases.aspose.com/page/java/).
- En grundläggande förståelse för Java-programmering.
## Importera paket
Se till att du har nödvändiga importer i ditt Java-projekt för att använda Aspose.Page-funktioner. Här är ett exempel:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Låt oss nu dela upp handledningen i flera steg för varje storleksändringsalternativ:
## Ändra storlek på EPS med poäng
### Steg 1: Ställ in ingångsströmmen
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Steg 2: Initiera PsDocument-objekt
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Steg 3: Extrahera den aktuella storleken på EPS-bilden
```java
Dimension oldSize = doc.extractEpsSize();
```
### Steg 4: Skapa en utdataström
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Steg 5: Ändra storlek och spara poäng
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Ändra storlek på EPS med tum
Följ liknande steg som i exempel 1, ersätt "Points" med "Inches" och justera den nya storleken därefter.
## Ändra storlek på EPS med millimeter
Följ liknande steg som i exempel 1, ersätt "Points" med "Millimeters" och justera den nya storleken därefter.
## Ändra storlek på EPS med procentsatser
Följ liknande steg som i exempel 1, ersätt "Poäng" med "Procentandelar" och justera den nya storleken därefter.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du ändrar storlek på EPS-filer i Java med Aspose.Page. Den här guiden ger dig mångsidiga alternativ, vilket säkerställer att du kan skräddarsy storleksändringsprocessen för att möta dina specifika behov.

## Vanliga frågor
### Kan jag använda det här biblioteket för andra bildformat?
Nej, Aspose.Page är speciellt utformad för att hantera PostScript- och EPS-filer.
### Finns det en gratis testversion tillgänglig för Aspose.Page för Java?
Ja, du kan utforska den kostnadsfria provperioden[här](https://releases.aspose.com/).
### Var kan jag hitta ytterligare hjälp och diskussioner?
 Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd.
### Hur kan jag få en tillfällig licens?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Finns det några exempel på projekt?
 Ja, kontrollera dokumentationen[här](https://reference.aspose.com/page/java/).
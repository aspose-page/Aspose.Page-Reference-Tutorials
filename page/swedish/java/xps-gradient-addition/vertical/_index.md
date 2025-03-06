---
title: Lägg till Vertical Gradient i Java XPS
linktitle: Lägg till Vertical Gradient i Java XPS
second_title: Aspose.Page Java API
description: Lär dig hur du lägger till en vertikal gradient till Java XPS-dokument med Aspose.Page. Förbättra visuella tilltal utan ansträngning. Steg-för-steg guide inuti.
weight: 12
url: /sv/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Vertical Gradient i Java XPS

## Introduktion
den här handledningen kommer vi att utforska hur man lägger till en vertikal gradient i Java XPS med Aspose.Page för Java. Att lägga till övertoningar till dina XPS-dokument kan förbättra det visuella tilltalandet av ditt innehåll, vilket gör det mer engagerande och estetiskt tilltalande.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En fungerande Java-utvecklingsmiljö.
-  Aspose.Page för Java-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/page/java/).
- En grundläggande förståelse för Java-programmering.
## Importera paket
Börja med att importera de nödvändiga paketen för ditt Java-projekt. Se till att du har inkluderat Aspose.Page for Java-biblioteket i dina projektberoenden.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
        
// Importera Aspose.Page för Java
```
## Steg 1: Initiera dokumentet
Börja med att initiera XPS-dokumentet. Detta lägger grunden för att lägga till element som banor och övertoningar till ditt dokument.
```java
// Initiera dokument
XpsDocument doc = new XpsDocument();
```
## Steg 2: Skapa en bana med vertikal gradient
Låt oss nu skapa en bana med en vertikal gradient. Detta innebär att definiera bangeometrin och specificera gradientstoppen.
```java
// Skapa en bana med geometri
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definiera vertikala gradientstopp
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Applicera den vertikala gradienten på banan
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Steg 3: Spara dokumentet
Slutligen, spara XPS-dokumentet med den tillagda vertikala gradienten till din önskade katalog.
```java
// Spara dokumentet
doc.save(dataDir + "VerticalGradient.xps");
```
Grattis! Du har framgångsrikt lagt till en vertikal gradient till ditt Java XPS-dokument med Aspose.Page.
## Slutsats
Att förbättra dina XPS-dokument med övertoningar kan avsevärt förbättra deras visuella tilltalande. Aspose.Page för Java förenklar denna process, så att du enkelt kan skapa fantastiska dokument.

### Vanliga frågor
### Kan jag använda Aspose.Page för Java i kommersiella projekt?
 Ja, Aspose.Page för Java är tillgänglig för kommersiellt bruk. Du kan köpa den[här](https://purchase.aspose.com/buy).
### Finns det en gratis testversion tillgänglig för Aspose.Page för Java?
 Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentationen för Aspose.Page för Java?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/page/java/).
### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Behöver du hjälp eller har frågor?
 Besök Aspose.Page-communityt[forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

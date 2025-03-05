---
title: Lägg till horisontell gradient i Java PostScript
linktitle: Lägg till horisontell gradient i Java PostScript
second_title: Aspose.Page Java API
description: Lär dig hur du lägger till en horisontell gradient i Java PostScript med Aspose.Page för Java. Skapa visuellt fantastiska dokument utan ansträngning.
type: docs
weight: 11
url: /sv/java/postscript-gradient-addition/horizontal/
---
## Introduktion
Välkommen till denna omfattande handledning om att lägga till en horisontell gradient i Java PostScript med Aspose.Page för Java. Aspose.Page är ett kraftfullt Java-bibliotek som låter utvecklare arbeta med PostScript och andra dokumentformat. I den här självstudien guidar vi dig genom processen att skapa ett PostScript-dokument med en horisontell gradient med hjälp av steg-för-steg-exempel.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Java Development Kit (JDK) installerat på din maskin.
- Aspose.Page för Java-biblioteket. Du kan ladda ner den från[Aspose.Page Java-dokumentation](https://reference.aspose.com/page/java/).
## Importera paket
Börja med att importera de nödvändiga paketen i ditt Java-projekt. Dessa paket är avgörande för att arbeta med Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Steg 1: Skapa en rektangel
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa utdataström för PostScript-dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();
// Skapa ett nytt PS-dokument med sidan öppen
PsDocument document = new PsDocument(outPsStream, options, false);
//Skapa en rektangel
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Steg 2: Skapa horisontell linjär gradientfärg
```java
// Skapa horisontell linjär gradientfärg. Skalkomponenter i transformationen måste vara lika med rektangelns bredd och höjd.
// Översättningskomponenter är förskjutningar av rektangeln.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Ställ in färg
document.setPaint(paint);
```
## Steg 3: Fyll rektangeln
```java
// Fyll rektangeln
document.fill(rectangle);
```
## Steg 4: Fyll en text med övertoningen
```java
// Fyll en text med gradienten
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Steg 5: Stryk en text med övertoningen
```java
// Stryk en text med övertoningen
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Slutsats
Grattis! Du har framgångsrikt lagt till en horisontell gradient i Java PostScript med Aspose.Page för Java. Denna handledning gav dig en detaljerad steg-för-steg-guide som hjälper dig att skapa visuellt tilltalande PostScript-dokument.
## Vanliga frågor
### Kan jag använda Aspose.Page för Java i kommersiella projekt?
Ja, Aspose.Page för Java kan användas i kommersiella projekt. För licensinformation, besök[Aspose.Purchase](https://purchase.aspose.com/buy).
### Finns det en gratis provperiod?
 Ja, du kan få tillgång till en gratis testversion av Aspose.Page för Java[här](https://releases.aspose.com/).
### Var kan jag hitta ytterligare dokumentation och support?
 Besök[Aspose.Page Java-dokumentation](https://reference.aspose.com/page/java/) för omfattande resurser. För samhällsstöd, kolla[Aspose.Page forum](https://forum.aspose.com/c/page/39).
### Hur kan jag få en tillfällig licens?
 Du kan få en tillfällig licens från[Aspose.Purchase](https://purchase.aspose.com/temporary-license/).
### Vilka är systemkraven för Aspose.Page för Java?
 Referera till[dokumentation](https://reference.aspose.com/page/java/) för detaljerade systemkrav.
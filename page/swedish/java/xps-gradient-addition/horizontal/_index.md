---
title: Lägg till horisontell gradient i Java XPS
linktitle: Lägg till horisontell gradient i Java XPS
second_title: Aspose.Page Java API
description: Lär dig hur du lägger till en fantastisk horisontell gradient till XPS-dokument i Java med Aspose.Page. Följ vår steg-för-steg-guide för sömlös integration.
type: docs
weight: 11
url: /sv/java/xps-gradient-addition/horizontal/
---
## Introduktion
Välkommen till denna steg-för-steg-guide för att lägga till en horisontell gradient i Java XPS med Aspose.Page för Java. Aspose.Page för Java är ett kraftfullt bibliotek som låter utvecklare arbeta med XPS-dokument (XML Paper Specification) sömlöst.
I den här handledningen går vi igenom processen att skapa en Java-applikation för att lägga till en horisontell gradient till ett XPS-dokument. Följ stegen nedan för att uppnå detta enkelt.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar på plats:
1. Java Development Environment: Se till att du har Java installerat på ditt system. Om inte, ladda ner och installera den senaste versionen av Java från[java.com](https://www.java.com).
2.  Aspose.Page for Java Library: Du måste ha Aspose.Page for Java-biblioteket. Du kan ladda ner den från[Aspose.Page för Java-dokumentation](https://reference.aspose.com/page/java/).
## Importera paket
Börja med att importera de nödvändiga paketen för din Java-applikation. Inkludera Aspose.Page för Java-biblioteket i ditt projekt. Du kan göra detta genom att lägga till följande kodrader:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Steg 1: Initiera dokument
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
//Initiera dokument
XpsDocument doc = new XpsDocument();
```
## Steg 2: Skapa horisontell gradient
```java
// Horisontell gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Steg 3: Lägg till sökväg med gradient
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Steg 4: Spara dokumentet
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Upprepa dessa steg vid behov, justera parametrar baserat på dina specifika krav.
## Slutsats
Grattis! Du har framgångsrikt lagt till en horisontell gradient till ett XPS-dokument med Aspose.Page för Java. Denna handledning gav en omfattande guide för utvecklare som vill förbättra sina Java-applikationer med gradienteffekter.
## Vanliga frågor
### F: Kan jag använda flera övertoningar i ett enda XPS-dokument?
Ja, du kan lägga till flera banor med olika gradienter för att skapa komplexa mönster.
### F: Är Aspose.Page kompatibel med de senaste Java-versionerna?
Aspose.Page för Java uppdateras regelbundet för att säkerställa kompatibilitet med de senaste Java-versionerna.
### F: Finns det andra gradienttyper tillgängliga i Aspose.Page?
Ja, förutom linjära gradienter stöder Aspose.Page radiella gradienter för fler olika effekter.
### F: Kan jag anpassa färgerna och positionerna för gradientstopp?
Absolut! Du har full kontroll över färgerna och positionerna för varje gradientstopp.
### F: Finns det ett communityforum för Aspose.Page där jag kan söka hjälp?
 Ja, du kan besöka[Aspose.Page forum](https://forum.aspose.com/c/page/39) att få kontakt med samhället och få hjälp.
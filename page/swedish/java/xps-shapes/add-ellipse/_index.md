---
title: Lägg till Radial Gradient Ellipse med Aspose.Page
linktitle: Lägg till Ellipse i Java XPS
second_title: Aspose.Page Java API
description: Utforska steg-för-steg-guiden för att lägga till en ellips med radiell gradient i Java XPS med Aspose.Page för Java. Förbättra ditt dokumentskapande utan ansträngning.
type: docs
weight: 10
url: /sv/java/xps-shapes/add-ellipse/
---
## Introduktion
Välkommen till vår steg-för-steg-guide för att lägga till en ellips i Java XPS med Aspose.Page för Java. Aspose.Page är ett kraftfullt Java-bibliotek som låter utvecklare arbeta med XPS-dokument utan ansträngning. I den här handledningen går vi igenom processen att skapa en ellips med radiell gradient och spara den som ett XPS-dokument.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
- Java Development Kit (JDK) installerat på din maskin.
-  Aspose.Page för Java-biblioteket har laddats ner. Du kan få det[här](https://releases.aspose.com/page/java/).
- En valfri kodredigerare (Eclipse, IntelliJ, etc.) för att skriva och köra Java-kod.
## Importera paket
Se till att du har de nödvändiga paketen importerade i ditt Java-projekt för att använda Aspose.Page. Lägg till följande importsatser överst i din Java-fil:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Steg 1: Konfigurera dokumentkatalog
Definiera sökvägen till din dokumentkatalog där XPS-dokumentet ska sparas:
```java
String dataDir = "Your Document Directory";
```
## Steg 2: Skapa XPS-dokument
Initiera ett nytt XPS-dokument med följande kod:
```java
XpsDocument doc = new XpsDocument();
```
## Steg 3: Definiera radiella gradientstopp
Skapa en lista med gradientstopp för den radiella gradientsträckta ellipsen:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Steg 4: Skapa sökvägsgeometri
Definiera en radiell gradient streckad ellips med hjälp av bangeometri:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Steg 5: Lägg till Canvas och Path
Lägg till en ny arbetsyta till dokumentet och lägg till sökvägen med den definierade geometrin:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Steg 6: Ställ in Stroke och Gradient
Konfigurera banans linje med en radiell gradientpensel:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Steg 7: Ställ in slagtjocklek
Ange banans slagtjocklek:
```java
path.setStrokeThickness(12f);
```
## Steg 8: Spara dokumentet
Spara det resulterande XPS-dokumentet:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Grattis! Du har framgångsrikt lagt till en ellips med radiell gradient i Java XPS med Aspose.Page för Java.
## Slutsats
I den här handledningen utforskade vi stegen för att skapa ett XPS-dokument med en visuellt tilltalande radiell gradientsträckt ellips. Aspose.Page för Java förenklar XPS-dokumenthantering och ger utvecklare en kraftfull verktygsuppsättning.
## Vanliga frågor
### Kan jag använda Aspose.Page för Java med andra Java-bibliotek?
Ja, Aspose.Page för Java kan integreras med andra Java-bibliotek sömlöst.
### Är Aspose.Page lämplig för storskalig dokumentbehandling?
Absolut! Aspose.Page är utformad för att hantera storskalig dokumentbehandling effektivt.
### Var kan jag hitta fler handledningar och exempel för Aspose.Page för Java?
 Besök[Aspose.Page för Java-dokumentation](https://reference.aspose.com/page/java/)för omfattande handledningar och exempel.
### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Finns det gemenskapsforum för Aspose.Page-diskussioner?
 Ja, gå med i[Aspose.Page gemenskapsforum](https://forum.aspose.com/c/page/39) att engagera sig med andra utvecklare och få hjälp.
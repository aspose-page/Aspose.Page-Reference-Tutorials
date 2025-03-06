---
title: Voeg Radiale Gradiënt-ellips toe met Aspose.Page
linktitle: Voeg Ellipse toe in Java XPS
second_title: Aspose.Page Java-API
description: Verken de stapsgewijze handleiding voor het toevoegen van een ellips met een radiale verlooplijn in Java XPS met behulp van Aspose.Page voor Java. Verbeter moeiteloos uw documentcreatie.
weight: 10
url: /nl/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg Radiale Gradiënt-ellips toe met Aspose.Page

## Invoering
Welkom bij onze stapsgewijze handleiding voor het toevoegen van een ellips in Java XPS met behulp van Aspose.Page voor Java. Aspose.Page is een krachtige Java-bibliotheek waarmee ontwikkelaars moeiteloos met XPS-documenten kunnen werken. In deze zelfstudie leiden we u door het proces van het maken van een ellips met een radiale verlooplijn en deze op te slaan als een XPS-document.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Page voor Java-bibliotheek gedownload. Je kan het krijgen[hier](https://releases.aspose.com/page/java/).
- Een code-editor naar keuze (Eclipse, IntelliJ, etc.) voor het schrijven en uitvoeren van Java-code.
## Pakketten importeren
Zorg ervoor dat u de benodigde pakketten in uw Java-project hebt geïmporteerd om Aspose.Page te gebruiken. Voeg de volgende importinstructies toe bovenaan uw Java-bestand:
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
## Stap 1: Documentmap instellen
Definieer het pad naar uw documentmap waar het XPS-document wordt opgeslagen:
```java
String dataDir = "Your Document Directory";
```
## Stap 2: Maak een XPS-document
Initialiseer een nieuw XPS-document met de volgende code:
```java
XpsDocument doc = new XpsDocument();
```
## Stap 3: Definieer radiale verloopstops
Maak een lijst met verloopstops voor de ellips met radiale verlooplijnen:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Stap 4: Creëer padgeometrie
Definieer een ellips met radiale verlooplijnen met behulp van padgeometrie:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Stap 5: Canvas en pad toevoegen
Voeg een nieuw canvas toe aan het document en voeg het pad toe met de gedefinieerde geometrie:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Stap 6: Stel lijn en verloop in
Configureer de streek van het pad met een radiale gradiëntborstel:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Stap 7: Stel de lijndikte in
Geef de lijndikte van het pad op:
```java
path.setStrokeThickness(12f);
```
## Stap 8: Bewaar het document
Sla het resulterende XPS-document op:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Gefeliciteerd! U hebt met succes een ellips met een radiale verlooplijn toegevoegd in Java XPS met behulp van Aspose.Page voor Java.
## Conclusie
In deze zelfstudie hebben we de stappen onderzocht voor het maken van een XPS-document met een visueel aantrekkelijke ellips met radiale verlooplijnen. Aspose.Page voor Java vereenvoudigt de manipulatie van XPS-documenten en biedt ontwikkelaars een krachtige toolset.
## Veel Gestelde Vragen
### Kan ik Aspose.Page voor Java gebruiken met andere Java-bibliotheken?
Ja, Aspose.Page voor Java kan naadloos worden geïntegreerd met andere Java-bibliotheken.
### Is Aspose.Page geschikt voor grootschalige documentverwerking?
Absoluut! Aspose.Page is ontworpen om grootschalige documentverwerking efficiënt af te handelen.
### Waar kan ik meer tutorials en voorbeelden vinden voor Aspose.Page voor Java?
 Bezoek de[Aspose.Page voor Java-documentatie](https://reference.aspose.com/page/java/)voor uitgebreide tutorials en voorbeelden.
### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor Java?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Zijn er communityforums voor Aspose.Page-discussies?
 Ja, sluit je aan bij de[Aspose.Page-communityforum](https://forum.aspose.com/c/page/39) om met andere ontwikkelaars in contact te komen en hulp te krijgen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

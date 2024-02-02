---
title: Java PostScript Radiaal verloop met Aspose.Page
linktitle: Java PostScript Radiaal verloop met Aspose.Page
second_title: Aspose.Page Java-API
description: Verken de stapsgewijze handleiding om Radiaal verloop toe te voegen aan Java PostScript met behulp van Aspose.Page voor verbluffende afbeeldingen in uw Java-toepassingen.
type: docs
weight: 13
url: /nl/java/postscript-gradient-addition/radial2/
---
## Invoering
Welkom bij onze stapsgewijze handleiding voor het toevoegen van Radial Gradient 2 in Java PostScript met behulp van Aspose.Page voor Java. Deze tutorial leidt u door het proces van het maken van een PostScript-document met een prachtig radiaal verloop, waardoor uw Java-toepassingen worden uitgebreid met visueel aantrekkelijke afbeeldingen.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Een praktische kennis van Java-programmeren.
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Page voor de Java-bibliotheek, die u kunt downloaden van de[Aspose.Page Java-documentatie](https://reference.aspose.com/page/java/).
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten voor Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Stap 1: Documentmap instellen
Definieer het pad naar uw documentmap:
```java
String dataDir = "Your Document Directory";
```
## Stap 2: Maak een uitvoerstroom
Maak een uitvoerstroom voor het PostScript-document:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Stap 3: Creëer opslagopties
Creëer opslagopties met A4-formaat:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Stap 4: Maak een PS-document
Maak een nieuw PS-document met de pagina geopend:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Stap 5: Maak een cirkel
Definieer een cirkel met behulp van de klasse Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Stap 6: Definieer verloopkleuren
Maak reeksen kleuren en breuken voor de radiale gradiënt:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Stap 7: Maak AffineTransform
Maak een AffineTransform voor de radiale gradiënt:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Stap 8: Maak radiale verloopverf
Maak een RadialGradientPaint met de opgegeven parameters:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Stap 9: Stel de verf- en vulcirkel in
Plaats de verf en vul de cirkel met het radiale verloop:
```java
document.setPaint(paint);
document.fill(circle);
```
## Stap 10: Sluit de pagina en sla het document op
Sluit de huidige pagina en sla het document op:
```java
document.closePage();
document.save();
```
Gefeliciteerd! U hebt Radial Gradient 2 met succes toegevoegd aan Java PostScript met behulp van Aspose.Page voor Java.
## Conclusie
In deze zelfstudie hebben we onderzocht hoe u uw Java-toepassingen kunt verbeteren met radiale verlopen in PostScript-documenten. Aspose.Page voor Java biedt een krachtige set tools waarmee u verbluffende grafische afbeeldingen kunt maken, zodat u uw Java-projecten naar een hoger niveau kunt tillen.
## Veelgestelde vragen
### Vraag: Waar kan ik de documentatie voor Aspose.Page voor Java vinden?
 A: De documentatie is beschikbaar[hier](https://reference.aspose.com/page/java/).
### Vraag: Hoe kan ik Aspose.Page voor Java downloaden?
 A: U kunt het downloaden van de[releases pagina](https://releases.aspose.com/page/java/).
### Vraag: Is er een gratis proefversie beschikbaar?
 A: Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Kan ik een tijdelijke licentie krijgen voor Aspose.Page voor Java?
 A: Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik gemeenschapssteun zoeken en deelnemen aan discussies?
 A: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39).
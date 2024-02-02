---
title: Horizontaal verloop toevoegen in Java PostScript
linktitle: Horizontaal verloop toevoegen in Java PostScript
second_title: Aspose.Page Java-API
description: Leer hoe u een horizontaal verloop toevoegt in Java PostScript met Aspose.Page voor Java. Creëer moeiteloos visueel verbluffende documenten.
type: docs
weight: 11
url: /nl/java/postscript-gradient-addition/horizontal/
---
## Invoering
Welkom bij deze uitgebreide tutorial over het toevoegen van een horizontaal verloop in Java PostScript met behulp van Aspose.Page voor Java. Aspose.Page is een krachtige Java-bibliotheek waarmee ontwikkelaars met PostScript en andere documentformaten kunnen werken. In deze zelfstudie begeleiden we u door het proces van het maken van een PostScript-document met een horizontaal verloop aan de hand van stapsgewijze voorbeelden.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
- Aspose.Pagina voor Java-bibliotheek. Je kunt het downloaden van de[Aspose.Page Java-documentatie](https://reference.aspose.com/page/java/).
## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-project. Deze pakketten zijn cruciaal voor het werken met Aspose.Page.
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
## Stap 1: Maak een rechthoek
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een uitvoerstroom voor een PostScript-document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Creëer opslagopties met A4-formaat
PsSaveOptions options = new PsSaveOptions();
// Maak een nieuw PS-document met de pagina geopend
PsDocument document = new PsDocument(outPsStream, options, false);
//Maak een rechthoek
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Stap 2: Maak horizontale lineaire verloopverf
```java
// Maak horizontale lineaire gradiëntverf. Schaalcomponenten in de transformatie moeten gelijk zijn aan de breedte en hoogte van de rechthoek.
// Translatiecomponenten zijn verschuivingen van de rechthoek.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Verf instellen
document.setPaint(paint);
```
## Stap 3: Vul de rechthoek
```java
// Vul de rechthoek
document.fill(rectangle);
```
## Stap 4: Vul een tekst met het verloop
```java
// Vul een tekst met het verloop
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Stap 5: Strijk een tekst met het verloop
```java
// Strijk een tekst met het verloop
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusie
Gefeliciteerd! U hebt met succes een horizontaal verloop toegevoegd in Java PostScript met behulp van Aspose.Page voor Java. In deze zelfstudie vindt u een gedetailleerde stapsgewijze handleiding waarmee u visueel aantrekkelijke PostScript-documenten kunt maken.
## Veel Gestelde Vragen
### Kan ik Aspose.Page voor Java gebruiken in commerciële projecten?
Ja, Aspose.Page voor Java kan in commerciële projecten worden gebruikt. Ga voor licentiegegevens naar[Aspose.Aankoop](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar?
 Ja, u heeft toegang tot een gratis proefversie van Aspose.Page voor Java[hier](https://releases.aspose.com/).
### Waar kan ik aanvullende documentatie en ondersteuning vinden?
 Bezoek de[Aspose.Page Java-documentatie](https://reference.aspose.com/page/java/) voor uitgebreide bronnen. Voor community-ondersteuning, kijk op de[Aspose.Page-forum](https://forum.aspose.com/c/page/39).
### Hoe kan ik een tijdelijke licentie verkrijgen?
 Een tijdelijke licentie kunt u verkrijgen bij[Aspose.Aankoop](https://purchase.aspose.com/temporary-license/).
### Wat zijn de systeemvereisten voor Aspose.Page voor Java?
 Verwijs naar de[documentatie](https://reference.aspose.com/page/java/) voor gedetailleerde systeemvereisten.
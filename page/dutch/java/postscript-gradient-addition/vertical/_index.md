---
title: Voeg verticaal verloop toe in Java PostScript
linktitle: Voeg verticaal verloop toe in Java PostScript
second_title: Aspose.Page Java-API
description: Ontdek de stapsgewijze handleiding voor het toevoegen van verticale verlopen in Java PostScript met Aspose.Page voor Java. Verbeter uw documenten moeiteloos met levendige beelden.
weight: 14
url: /nl/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg verticaal verloop toe in Java PostScript

## Invoering
Welkom bij deze stapsgewijze handleiding voor het toevoegen van een verticaal verloop in Java PostScript met behulp van Aspose.Page voor Java. Als u uw document wilt verfraaien met opvallende verlopen, dan is deze tutorial iets voor u. Aspose.Page voor Java biedt krachtige tools om PostScript-documenten naadloos te manipuleren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Pagina voor Java-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/page/java/).
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten om aan de slag te gaan:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Laten we nu het proces van het toevoegen van een verticaal verloop in Java PostScript in meerdere stappen opsplitsen.
## Stap 1: Stel uw documentenmap in
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
```
## Stap 2: Maak een uitvoerstroom voor een PostScript-document
```java
// Maak een uitvoerstroom voor een PostScript-document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Stap 3: Creëer opslagopties met A4-formaat
```java
// Creëer opslagopties met A4-formaat
PsSaveOptions options = new PsSaveOptions();
```
## Stap 4: Maak een nieuw PS-document
```java
// Maak een nieuw PS-document met de pagina geopend
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Stap 5: Maak een rechthoek
```java
//Maak een rechthoek
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Stap 6: Stel kleuren en breuken in voor het verloop
```java
// Maak reeksen kleuren en breuken voor het verloop.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Stap 7: Maak de verlooptransformatie
```java
// Maak de verlooptransformatie. Schaalcomponenten in de transformatie moeten gelijk zijn aan de breedte en hoogte van de rechthoek.
// Translatiecomponenten zijn verschuivingen van de rechthoek.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Roteer het verloop 90 graden rond een oorsprong
transform.rotate(90 * (Math.PI / 180));
```
## Stap 8: Maak verticale lineaire verloopverf
```java
// Maak verticale lineaire gradiëntverf.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Stap 9: Stel Paint in en vul de rechthoek
```java
// Verf instellen
document.setPaint(paint);
// Vul de rechthoek
document.fill(rectangle);
```
## Stap 10: Sluit de huidige pagina en sla het document op
```java
// Sluit huidige pagina
document.closePage();
// Bewaar het document
document.save();
```
Gefeliciteerd! U hebt met succes een verticaal verloop aan uw Java PostScript-document toegevoegd met Aspose.Page voor Java.
## Conclusie
In deze zelfstudie hebben we het proces onderzocht waarmee u uw documenten kunt verbeteren met levendige verticale verlopen met behulp van Aspose.Page voor Java. Nu kunt u uw documentmanipulaties naar een hoger niveau tillen door verbluffende beelden op te nemen.
## Veel Gestelde Vragen
### Kan ik Aspose.Page voor Java gebruiken met andere Java-bibliotheken?
Ja, Aspose.Page voor Java is ontworpen om naadloos samen te werken met andere Java-bibliotheken.
### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).
### Waar kan ik aanvullende documentatie vinden?
 Gedetailleerde documentatie is beschikbaar[hier](https://reference.aspose.com/page/java/).
### Hoe kan ik Aspose.Page voor Java kopen?
 U kunt Aspose.Page voor Java kopen[hier](https://purchase.aspose.com/buy).
### Is er een forum voor Aspose.Page-discussies?
 Ja, u kunt lid worden van het communityforum[hier](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

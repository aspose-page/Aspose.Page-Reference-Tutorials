---
date: 2026-09-04
description: Leer hoe u horizontal gradient java maakt in een PostScript‑bestand met
  Linear Gradient Paint Java en Aspose.Page voor Java. Stapsgewijze code, veelvoorkomende
  valkuilen en veelgestelde vragen.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Creëer horizontal gradient java in PostScript met Aspose
og_description: Creëer horizontal gradient java in PostScript met Linear Gradient
  Paint Java. Deze Aspose.Page‑tutorial laat u de exacte stappen, vereisten en probleemoplossingstips
  zien in minder dan 15 minuten.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Creëer horizontal gradient java in PostScript met Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Creëer horizontal gradient java in PostScript met Aspose
url: /nl/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een horizontale gradiënt toe te voegen in Java PostScript met Linear Gradient Paint

## Inleiding
In deze uitgebreide tutorial leer je **hoe je een horizontale gradiënt in Java** maakt in een PostScript‑document door gebruik te maken van de **Linear Gradient Paint Java**‑klasse die wordt geleverd met Aspose.Page for Java. We lopen elke stap door—van het opzetten van het project tot het renderen van de gradiënt op zowel vormen als tekst—zodat je in enkele minuten gepolijste, afdrukklare graphics kunt produceren. Of je nu een rapportage‑engine, een ontwerp‑automatiseringstool of een aangepaste printerdriver bouwt, deze gids geeft je de exacte code die je nodig hebt.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java (bevat Linear Gradient Paint Java).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basis horizontale gradiënt.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.  
- **Welke JDK‑versie werkt?** Java 8 of nieuwer.  
- **Kan ik de gradiënt gebruiken op zowel vormen als tekst?** Ja – dezelfde `LinearGradientPaint`‑instantie kan vormen vullen en worden toegepast op tekstcontouren of vullingen.

## Wat is een horizontale gradiënt en waarom gebruiken?
Een horizontale gradiënt mengt kleuren van de linkerrand van een object naar de rechterrand, waardoor een vloeiende overgang ontstaat die diepte en visueel belang toevoegt. Het is ideaal voor moderne UI‑componenten, uitgelichte koppen of subtiele achtergrondschaduwen in PDF‑ of PostScript‑rapporten. Met **Linear Gradient Paint Java** kun je nauwkeurig de begin‑ en eindkleuren, doorzichtigheid en schaal bepalen, zodat het resultaat scherp uitziet op elk apparaat of elke printer.

## Vereisten
Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java‑bibliotheek. Je kunt deze downloaden van de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Pakketten importeren
Begin met het importeren van de benodigde pakketten in je Java‑project. Deze imports geven je toegang tot grafische primitieve, gradiëntverwerking en de Aspose.Page‑API.

De `PsDocument`‑klasse vertegenwoordigt een PostScript‑document waarop je graphics kunt tekenen.

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

## Stap 1: een rechthoek maken
Eerst stel je de output‑stream, het document en een rechthoek in die de gradiënt zal bevatten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Stap 2: horizontale lineaire gradiëntverf maken
`LinearGradientPaint` is de kernklasse die een lineaire kleurverandering definieert.  
De `LinearGradientPaint`‑klasse vertegenwoordigt een verfobject dat een gradiënt langs een rechte lijn rendert; je specificeert start‑/eindpunten, kleurstops en een optionele `AffineTransform` om deze op je vorm te schalen.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Stap 3: de rechthoek vullen
Vul nu de rechthoek met de gradiënt die we zojuist hebben gedefinieerd.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Stap 4: tekst vullen met de gradiënt
Je kunt dezelfde gradiënt ook toepassen op tekst, waardoor een opvallend visueel effect ontstaat.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Stap 5: tekst omtrekken met de gradiënt
Tenslotte omtrek je tekst met de gradiënt als de lijnkleur.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Gradiënt lijkt uitgerekt | Onjuiste `AffineTransform`‑schaal | Zorg ervoor dat de breedte en hoogte van de transformatie overeenkomen met de afmetingen van de rechthoek (200 × 100 in het voorbeeld). |
| Kleuren lijken vervaagd | Alfa‑waarden zijn te laag ingesteld | Verhoog de alfa‑component (de vierde waarde in `new Color(r,g,b,alpha)`). |
| Tekst is niet zichtbaar | Verf niet ingesteld vóór het tekenen van tekst | Roep `document.setPaint(paint)` **vóór** enige `fillAndStrokeText`‑ of `outlineText`‑aanroepen aan. |

## Veelgestelde vragen
**Q:** Kan ik Aspose.Page for Java gebruiken in commerciële projecten?  
**A:** Ja, Aspose.Page for Java kan worden gebruikt in commerciële projecten. Voor licentie‑details, bezoek de [Aspose.Purchase](https://purchase.aspose.com/buy) pagina.

**Q:** Is er een gratis proefversie beschikbaar?  
**A:** Ja, je kunt een gratis proefversie van Aspose.Page for Java krijgen op de [Aspose.Page for Java free trial](https://releases.aspose.com/) pagina.

**Q:** Waar kan ik extra documentatie en ondersteuning vinden?  
**A:** Bezoek de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) voor uitgebreide bronnen. Voor community‑hulp, bekijk het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Hoe kan ik een tijdelijke licentie verkrijgen?  
**A:** Je kunt een tijdelijke licentie verkrijgen via de [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** Wat zijn de systeemvereisten voor Aspose.Page for Java?  
**A:** Raadpleeg de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) voor gedetailleerde systeemvereisten.

**Laatst bijgewerkt:** 2026-09-04  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose

## Gerelateerde tutorials

- [PostScript‑gradiënt maken in Java – Voeg verticale gradiënt toe](/page/java/postscript-gradient-addition/vertical/)
- [Hoe een gradiënt toe te voegen: Diagonale gradiënt in Java PostScript met Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [PostScript‑gradiënt maken – Radiale gradiënt in Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
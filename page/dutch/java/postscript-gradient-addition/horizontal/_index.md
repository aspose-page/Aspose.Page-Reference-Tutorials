---
date: 2025-12-07
description: Leer hoe u een horizontale gradient toevoegt in Java PostScript met Linear
  Gradient Paint Java en Aspose.Page voor Java.
language: nl
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Gradient toevoegen in Java PostScript met Linear Gradient Paint Java
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gradient toevoegen in Java PostScript met Linear Gradient Paint Java

## Inleiding
In deze uitgebreide tutorial ontdek je hoe je een mooie horizontale gradient kunt maken in een PostScript‑document door gebruik te maken van **Linear Gradient Paint Java**. Aspose.Page for Java maakt het eenvoudig om met PostScript, PDF en andere vectorformaten te werken, en de `LinearGradientPaint`‑klasse biedt je fijne controle over kleurovergangen. Aan het einde van deze gids kun je gradients toepassen op vormen **en** tekst, waardoor je documenten er professioneel en opvallend uitzien.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java (ondersteunt Linear Gradient Paint Java).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisgradient.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.  
- **Welke JDK‑versie werkt?** Java 8 of nieuwer.  
- **Kan ik de gradient gebruiken op zowel vormen als tekst?** Ja – je kunt vormen vullen en tekst contouren of vullen met dezelfde gradient.

## Vereisten
Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java bibliotheek. Je kunt deze downloaden van de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Pakketten importeren
Begin met het importeren van de benodigde pakketten in je Java‑project. Deze imports geven je toegang tot grafische primitieve, gradient‑verwerking en de Aspose.Page‑API.

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

## Stap 1: Een rechthoek maken
Eerst stel je de output‑stream, het document en een rechthoek in die de gradient zal bevatten.

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

## Stap 2: Horizontale Linear Gradient Paint maken
Hier bouwen we het **Linear Gradient Paint Java**‑object dat een horizontale kleurovergang definieert. De `AffineTransform` schaalt de gradient zodat deze overeenkomt met de breedte en hoogte van de rechthoek.

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

## Stap 3: De rechthoek vullen
Vul nu de rechthoek met de gradient die we zojuist hebben gedefinieerd.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Stap 4: Tekst vullen met de gradient
Je kunt dezelfde gradient ook toepassen op tekst, waardoor een opvallend visueel effect ontstaat.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Stap 5: Tekst omtrekken met de gradient
Ten slotte kun je tekst omtrekken met de gradient als de lijnkleur.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Gradient lijkt uitgerekt | Onjuiste `AffineTransform`-schaling | Zorg ervoor dat de breedte en hoogte van de transformatie overeenkomen met de afmetingen van de rechthoek (200 × 100 in het voorbeeld). |
| Kleuren zien er vervaagd uit | Alfawaarden zijn te laag ingesteld | Verhoog de alfacomponent (de vierde waarde in `new Color(r,g,b,alpha)`). |
| Tekst is niet zichtbaar | Paint niet ingesteld vóór het tekenen van tekst | Roep `document.setPaint(paint)` **aan** vóór enige `fillAndStrokeText`- of `outlineText`‑aanroepen. |

## Veelgestelde vragen
### Kan ik Aspose.Page for Java gebruiken in commerciële projecten?
Ja, Aspose.Page for Java kan worden gebruikt in commerciële projecten. Voor licentie‑details, bezoek [Aspose.Purchase](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar?
Ja, je kunt een gratis proefversie van Aspose.Page for Java [hier](https://releases.aspose.com/) krijgen.

### Waar kan ik extra documentatie en ondersteuning vinden?
Bezoek de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) voor uitgebreide bronnen. Voor community‑ondersteuning, bekijk het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### Hoe kan ik een tijdelijke licentie verkrijgen?
Je kunt een tijdelijke licentie verkrijgen via [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Wat zijn de systeemvereisten voor Aspose.Page for Java?
Raadpleeg de [documentation](https://reference.aspose.com/page/java/) voor gedetailleerde systeemvereisten.

---

**Laatst bijgewerkt:** 2025-12-07  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
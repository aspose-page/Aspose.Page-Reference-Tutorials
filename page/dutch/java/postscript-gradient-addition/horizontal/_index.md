---
date: 2026-02-13
description: Leer hoe u een gradient kunt toevoegen in Java PostScript met Linear
  Gradient Paint Java en Aspose.Page voor Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Hoe een verloop toe te voegen in Java PostScript met lineaire verloopverf
url: /nl/java/postscript-gradient-addition/horizontal/
weight: 11
---

 Paint" translate to Dutch: "Hoe een verloop toe te voegen in Java PostScript met Linear Gradient Paint". Keep same heading level.

Proceed.

I'll produce translation.

Be careful to keep code block placeholders unchanged.

Also keep markdown tables.

Translate bullet points.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een verloop toe te voegen in Java PostScript met Linear Gradient Paint

## Inleiding
In deze uitgebreide tutorial ontdek je **hoe je een verloop** kunt toevoegen aan een PostScript‑document met Java. We lopen stap voor stap door het maken van een mooie horizontale gradient door gebruik te maken van **Linear Gradient Paint Java**, een klasse die je pixel‑perfecte controle geeft over kleurverlopen. Met Aspose.Page for Java kun je verlopen renderen op zowel vormen **als** tekst, waardoor je documenten een gepolijste, opvallende uitstraling krijgen.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java (ondersteunt Linear Gradient Paint Java).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisverloop.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.  
- **Welke JDK‑versie werkt?** Java 8 of nieuwer.  
- **Kan ik het verloop gebruiken op zowel vormen als tekst?** Ja – je kunt vormen vullen en tekst vullen of omlijnen met hetzelfde verloop.

## Wat is een horizontale gradient en waarom gebruiken?
Een horizontale gradient mengt kleuren vloeiend van links naar rechts over een vorm of tekst. Het is ideaal voor het creëren van moderne UI‑elementen, uitgelichte koppen of subtiele achtergrondeffecten in rapporten. Met **Linear Gradient Paint Java** kun je de exacte begin‑ en eindkleuren, doorzichtigheid en schaal bepalen, zodat het resultaat scherp uitziet op elk apparaat.

## Voorvereisten
Voordat je in de code duikt, zorg dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java‑bibliotheek. Je kunt deze downloaden via de [Aspose.Page Java‑documentatie](https://reference.aspose.com/page/java/).

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
Stel eerst de output‑stream, het document en een rechthoek in die het verloop zal bevatten.

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
Hier bouwen we het **Linear Gradient Paint Java**‑object dat een horizontale kleurverandering definieert. De `AffineTransform` schaalt het verloop zodat het overeenkomt met de breedte en hoogte van de rechthoek.

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
Vul nu de rechthoek met het verloop dat we zojuist hebben gedefinieerd.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Stap 4: Tekst vullen met het verloop
Je kunt hetzelfde verloop ook toepassen op tekst, waardoor een opvallend visueel effect ontstaat.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Stap 5: Tekst omlijnen met het verloop
Tot slot kun je tekst omlijnen waarbij het verloop wordt gebruikt als de lijnkleur.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Verloop lijkt uitgerekt | Onjuiste `AffineTransform`‑schaal | Zorg ervoor dat de breedte en hoogte van de transformatie overeenkomen met de afmetingen van de rechthoek (200 × 100 in het voorbeeld). |
| Kleuren lijken vervaagd | Alpha‑waarden te laag ingesteld | Verhoog de alfa‑component (de vierde waarde in `new Color(r,g,b,alpha)`). |
| Tekst is niet zichtbaar | Paint niet ingesteld vóór het tekenen van tekst | Roep `document.setPaint(paint)` **voordat** je `fillAndStrokeText` of `outlineText` aanroept. |

## Veelgestelde vragen
**V:** Kan ik Aspose.Page for Java gebruiken in commerciële projecten?  
**A:** Ja, Aspose.Page for Java kan worden gebruikt in commerciële projecten. Voor licentie‑details, bezoek [Aspose.Purchase](https://purchase.aspose.com/buy).

**V:** Is er een gratis proefversie beschikbaar?  
**A:** Ja, je kunt een gratis proefversie van Aspose.Page for Java [hier](https://releases.aspose.com/) verkrijgen.

**V:** Waar vind ik extra documentatie en ondersteuning?  
**A:** Bezoek de [Aspose.Page Java‑documentatie](https://reference.aspose.com/page/java/) voor uitgebreide bronnen. Voor community‑ondersteuning, kijk op het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39).

**V:** Hoe kan ik een tijdelijke licentie verkrijgen?  
**A:** Je kunt een tijdelijke licentie verkrijgen via [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**V:** Wat zijn de systeemvereisten voor Aspose.Page for Java?  
**A:** Raadpleeg de [documentatie](https://reference.aspose.com/page/java/) voor gedetailleerde systeemvereisten.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-09
description: Leer hoe je een radiale gradient kunt maken in Java PostScript met Aspose.Page.
  Deze stap‑voor‑stap gids laat zien hoe je een color stops gradient toevoegt, de
  radii instelt en snel een PS‑bestand genereert.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Meesterschap in radiale gradients in Java
og_description: Leer hoe je een radiale gradient maakt in Java PostScript met Aspose.Page.
  Deze gids legt uit hoe je een color stops gradient toevoegt, de radii instelt en
  in enkele minuten een PS‑bestand genereert.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Hoe een radiale gradient te maken in Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Hoe een radiale gradient te maken in Java PostScript
url: /nl/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een radiale gradiënt te maken in Java PostScript met Aspose.Page

## Introductie
Als je een **radiale gradiënt** moet maken in een PostScript‑bestand, ben je op de juiste plek. In deze tutorial lopen we stap voor stap door alles wat nodig is om een PostScript‑document te genereren dat een vloeiende radiale gradiënt bevat, met behulp van **Aspose.Page for Java**. Aan het einde begrijp je de API, zie je een volledig uitvoerbaar voorbeeld, en weet je hoe je kleuren, posities en stralen kunt aanpassen voor elk ontwerpscenario.

## Snelle antwoorden
- **Welke bibliotheek maakt radiale gradiënten in PostScript?** Aspose.Page for Java.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik de vorm van de gradiënt wijzigen?** Ja – pas de straal en het middelpunt aan in de `RadialGradientPaint` constructor.

## Hoe een radiale gradiënt te maken in Java
Laad je Java‑project, importeer de benodigde klassen, en volg de stap‑voor‑stap‑gids hieronder. Het kernantwoord is dat je een `RadialGradientPaint` instantiate met je kleurstops en deze vervolgens toepast op een rechthoek die getekend wordt op een `PsDocument`. Deze twee‑objectbenadering behandelt alle low‑level PostScript‑commando's voor je.

## Wat is een radiale gradiënt?
`RadialGradientPaint` is een Java AWT‑klasse die een cirkelvormige kleurverloop definieert van een centraal punt naar buiten. Het creëert een vloeiende mengeling van meerdere kleurstops, waardoor het ideaal is voor spotlights, zachte achtergronden, of elk effect waarbij kleuren uitstralen vanuit een focuspunt.

## Waarom Aspose.Page gebruiken voor radiale gradiënten?
Aspose.Page geeft je volledige programmatische controle over PostScript‑output terwijl het de zware taak van low‑level PS‑syntaxis afhandelt. Het ondersteunt **meer dan 50 invoer‑ en uitvoerformaten**, kan documenten met honderden pagina's renderen zonder het volledige bestand in het geheugen te laden, en draait op elk besturingssysteem dat Java 8+ ondersteunt. Deze gekwantificeerde mogelijkheid maakt het een betrouwbare keuze voor enterprise‑grade grafiekgeneratie.

## Vereisten
- **Java Development Kit (JDK) 8+** – controleer met `java -version`.  
- **Aspose.Page for Java** – download de nieuwste JAR van de officiële [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE naar keuze** – Eclipse, IntelliJ IDEA, of VS Code met Java‑extensies.  
- **Een schrijfbare map** – waar het gegenereerde `.ps`‑bestand wordt opgeslagen.

## Importeer pakketten
Eerst importeer je de klassen die we nodig hebben. Het `java.awt`‑pakket levert de gradient‑paint‑objecten, terwijl `com.aspose.eps` de klassen voor het verwerken van PostScript‑documenten bevat.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stapsgewijze gids

### Stap 1: maak een rechthoek en open een PS‑document
`PsDocument` is de klasse van Aspose.Page die een PostScript‑document vertegenwoordigt en methoden biedt om vormen, tekst en afbeeldingen te tekenen. We beginnen met het maken van een output‑stream, het configureren van de paginagrootte (standaard A4), en het definiëren van een rechthoek die de gradiënt zal bevatten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** Pas de coördinaten van de rechthoek (`200, 100, 200, 200`) aan om de gradiënt overal op de pagina te positioneren.

### Stap 2: definieer kleuren en fracties
Een radiale gradiënt wordt opgebouwd uit *kleurstops* (de kleuren) en *fracties* (de relatieve posities van die stops). Hier maken we een array van zes kleuren en hun bijbehorende fracties.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Waarom dit belangrijk is:** Door `fractions` aan te passen, bepaal je hoe snel de kleuren overgaan, waardoor je subtiele of dramatische effecten kunt creëren.

### Stap 3: maak radiale gradient paint
`RadialGradientPaint` is de kernklasse die een radiale kleurgradiënt beschrijft, inclusief middelpunt, straal, focuspunt, fracties, kleuren, cyclismethode en kleurenruimte. Nu bouwen we het `RadialGradientPaint`‑object met behulp van de hierboven gedefinieerde arrays.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Opmerking:** `transform` kan `null` zijn als je geen extra schaal of rotatie nodig hebt. Voel je vrij om te experimenteren met `AffineTransform` voor scheve gradiënten.

### Stap 4: stel paint in en vul de rechthoek
Met de paint klaar, vertellen we het `PsDocument` om deze te gebruiken en vullen we vervolgens de eerder gedefinieerde rechthoek.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Op dit punt bevat de PostScript‑pagina een rechthoek die soepel is gevuld met de radiale gradiënt die we hebben geconfigureerd.

### Stap 5: sluit het document en sla het op
Tenslotte sluit je de huidige pagina en schrijf je het bestand naar schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Open `RadialGradient1_outPS.ps` in een PostScript‑viewer (bijv. Ghostscript) en je ziet de gradiënt precies zoals gedefinieerd weergegeven.

## Veelvoorkomende problemen & oplossingen
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|---------|--------------|-----|
| Gradiënt verschijnt als een effen kleur | `fractions`‑array begint niet met `0.0f` of eindigt niet op `1.0f` | Zorg ervoor dat de eerste fractie `0.0f` is en de laatste `1.0f`. |
| Kleuren zien er flets uit | Het verkeerde `ColorSpaceType` gebruiken | Schakel over naar `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` voor levendiger resultaat. |
| Geen uitvoerbestand gegenereerd | `FileOutputStream`‑pad is ongeldig of niet schrijfbaar | Controleer of `dataDir` bestaat en de applicatie schrijfrechten heeft. |

## Veelgestelde vragen

**V: Kan ik Aspose.Page for Java gebruiken in commerciële projecten?**  
A: Ja. Een commerciële licentie is vereist voor productiegebruik. Je kunt er een aanschaffen via de [Aspose licensing page](https://purchase.aspose.com/buy).

**V: Waar kan ik de officiële API‑referentie vinden?**  
A: De volledige documentatie is beschikbaar op [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**V: Is er een gratis proefversie beschikbaar voor testen?**  
A: Absoluut. Download een proefversie van de [Aspose.Page releases page](https://releases.aspose.com/).

**V: Hoe krijg ik een tijdelijke licentie voor evaluatie?**  
A: Een tijdelijke licentie kan worden aangevraagd via de [temporary license request page](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik community‑ondersteuning krijgen?**  
A: Word lid van het Aspose.Page community‑forum op [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusie
Je weet nu **hoe je een radiale gradiënt** kunt maken in een Java‑PostScript‑document met Aspose.Page. Door de grootte van de rechthoek, kleurstops en de straal van de gradiënt aan te passen, kun je talloze visuele effecten creëren – van subtiele achtergrondvullingen tot gedurfde spotlights. Voel je vrij om te experimenteren met verschillende `AffineTransform`‑waarden om de gradiënt te roteren of te scheefzetten, en combineer deze techniek met tekst en afbeeldingen voor rijkere PDF‑ of EPS‑output.

---

**Laatst bijgewerkt:** 2026-09-09  
**Getest met:** Aspose.Page for Java latest (as of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Vorm vullen met gradiënt: Java PostScript Radiaal voorbeeld](/page/java/postscript-gradient-addition/radial2/)
- [PostScript‑gradiënt maken in Java – Voeg verticale gradiënt toe](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparantie‑tutorial – Transparantie toevoegen in Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
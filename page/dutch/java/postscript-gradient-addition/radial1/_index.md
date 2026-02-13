---
date: 2026-02-13
description: Leer hoe je een PostScript‑gradient maakt met een radiale kleurstops‑gradient
  met behulp van Aspose.Page voor Java. Deze stapsgewijze handleiding laat je zien
  hoe je een kleurstops‑gradient aan je documenten toevoegt.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Maak PostScript‑verloop – Radiale verloop in Java
url: /nl/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een radiale gradiënt toe te voegen in Java PostScript met Aspose.Page

## Inleiding
Als je ooit een **PostScript‑gradiënt** moest **maken** met een vloeiende, opvallende kleurovergang, is leren hoe je een radiale gradiënt toevoegt de perfecte plek om te beginnen. In deze tutorial lopen we stap voor stap door alles wat nodig is om een PostScript‑bestand te genereren dat een prachtige radiale gradiënt bevat, met behulp van de **Aspose.Page for Java**‑bibliotheek. Aan het einde begrijp je de API, zie je een volledig uitvoerbaar voorbeeld, en weet je hoe je kleuren, posities en stralen kunt aanpassen aan elk ontwerp.

## Snelle antwoorden
- **Welke bibliotheek maakt radiale gradiënten in PostScript?** Aspose.Page for Java.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik de vorm van de gradiënt wijzigen?** Ja – pas de straal en het middelpunt aan in de `RadialGradientPaint`‑constructor.

## Hoe een PostScript‑gradiënt met radiale vulling te maken
Hieronder vind je een beknopte, stap‑voor‑stap walkthrough die precies laat zien hoe je **PostScript‑gradiënt**‑inhoud maakt met een radiale vulling. Elke stap bevat een korte uitleg gevolgd door het oorspronkelijke code‑blok (onveranderd).

## Wat is een radiale gradiënt?
Een radiale gradiënt schildert kleuren die uitstralen vanuit een centraal punt, geleidelijk vervagend naar de randen. In tegenstelling tot lineaire gradiënten volgt de kleurovergang een cirkel‑ (of elliptisch) patroon, wat ideaal is voor highlights, spotlights of zachte achtergrondvullingen.

## Waarom Aspose.Page gebruiken voor radiale gradiënten?
- **Volledige controle over PostScript‑output** – geen noodzaak om low‑level PS‑commando’s handmatig te schrijven.  
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.  
- **Rijke kleurbeheer** – ondersteunt meerdere kleurstops, verschillende kleurruimtes en cyclische methoden.  
- **Klaar voor integratie** – combineer met andere Aspose.Page‑functies zoals tekst, afbeeldingen en vectorvormen.

## Voorvereisten
Voordat we in de code duiken, zorg dat je het volgende klaar hebt staan:

- **Java Development Kit (JDK) 8+** – controleer met `java -version`.  
- **Aspose.Page for Java** – download de nieuwste JAR van de officiële [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE naar keuze** – Eclipse, IntelliJ IDEA, of VS Code met Java‑extensies.  
- **Een beschrijfbare map** – waar het gegenereerde `.ps`‑bestand wordt opgeslagen.

## Pakketten importeren
Eerst importeren we de klassen die we nodig hebben. Het `java.awt`‑pakket levert de gradiënt‑paint‑objecten, terwijl `com.aspose.eps` de PostScript‑documentverwerkingsklassen bevat.

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

## Stapsgewijze handleiding

### Stap 1: Een rechthoek maken en een PS‑document openen
We beginnen met het aanmaken van een output‑stream, het configureren van de paginagrootte (standaard A4), en het definiëren van een rechthoek die de gradiënt zal bevatten.

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

### Stap 2: Kleuren en fracties definiëren
Een radiale gradiënt wordt opgebouwd uit *kleurstops* (de kleuren) en *fracties* (de relatieve posities van die stops). Hier maken we een array van zes kleuren en hun bijbehorende fracties.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Waarom dit belangrijk is:** Door `fracties` aan te passen bepaal je hoe snel de kleuren overgaan, waardoor je subtiele of dramatische effecten kunt bereiken.

### Kleurstops‑gradiënt toevoegen aan je radiale vulling
Wanneer je een **kleurstops‑gradiënt** moet **toevoegen**, zijn de `colors`‑ en `fractions`‑arrays de sleutel. Voel je vrij om de volgorde te wijzigen, items toe te voegen of te verwijderen om je visuele ontwerp te passen.

### Stap 3: RadialGradientPaint maken
Nu bouwen we het `RadialGradientPaint`‑object. De constructor neemt het middelpunt van de gradiënt, de straal, het focuspunt, fracties, kleuren, cyclische methode, kleurruimte en een optionele transformatie.

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

> **Opmerking:** `transform` kan `null` zijn als je geen extra schaal- of rotatie‑transformatie nodig hebt. Experimenteer gerust met `AffineTransform` voor scheve gradiënten.

### Stap 4: Paint instellen en de rechthoek vullen
Met de paint klaar, vertellen we het `PsDocument` deze te gebruiken en vullen we vervolgens de eerder gedefinieerde rechthoek.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Op dit moment bevat de PostScript‑pagina een rechthoek die soepel is gevuld met de radiale gradiënt die we hebben geconfigureerd.

### Stap 5: Document sluiten en opslaan
Tot slot sluiten we de huidige pagina en schrijven we het bestand naar schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Open `RadialGradient1_outPS.ps` in een PostScript‑viewer (bijv. Ghostscript) en je ziet de gradiënt precies zoals gedefinieerd.

## Veelvoorkomende problemen & oplossingen
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Gradiënt verschijnt als een effen kleur | `fractions`‑array begint niet met `0.0f` of eindigt niet op `1.0f` | Zorg dat de eerste fractie `0.0f` is en de laatste `1.0f`. |
| Kleuren zien er vervaagd uit | Verkeerde `ColorSpaceType` gebruikt | Schakel over naar `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` voor levendigere output. |
| Geen uitvoerbestand gegenereerd | Pad van `FileOutputStream` is ongeldig of niet beschrijfbaar | Controleer of `dataDir` bestaat en de applicatie schrijfrechten heeft. |

## Veelgestelde vragen

**V: Kan ik Aspose.Page for Java gebruiken in commerciële projecten?**  
A: Ja. Een commerciële licentie is vereist voor productiegebruik. Je kunt er een aanschaffen via de [Aspose licensing page](https://purchase.aspose.com/buy).

**V: Waar vind ik de officiële API‑referentie?**  
A: De volledige documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**V: Is er een gratis proefversie beschikbaar voor testen?**  
A: Absoluut. Download een proefversie van de [Aspose.Page releases page](https://releases.aspose.com/).

**V: Hoe verkrijg ik een tijdelijke licentie voor evaluatie?**  
A: Een tijdelijke licentie kan worden aangevraagd [hier](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik community‑ondersteuning krijgen?**  
A: Word lid van het Aspose.Page community‑forum op [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusie
Je weet nu **hoe je een radiale gradiënt** kunt toevoegen aan een Java‑PostScript‑document met Aspose.Page. Door de grootte van de rechthoek, kleurstops en de straal van de gradiënt aan te passen, kun je ontelbare visuele effecten creëren – van subtiele achtergrondvullingen tot gedurfde spotlight‑graphics. Experimenteer gerust met verschillende `AffineTransform`‑waarden om de gradiënt te roteren of te scheefzetten, en combineer deze techniek met tekst en afbeeldingen voor rijkere PDF‑ of EPS‑output.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Page for Java latest (as of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
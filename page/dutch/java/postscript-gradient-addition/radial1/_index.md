---
date: 2025-12-08
description: Leer hoe u een radiale gradient toevoegt in Java PostScript met Aspose.Page.
  Deze stapsgewijze gids laat u zien hoe u verbluffende gradient‑effecten in uw documenten
  kunt creëren.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Hoe een radiale gradiënt toe te voegen in Java PostScript met Aspose.Page
url: /nl/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een radiale gradiënt toe te voegen in Java PostScript met Aspose.Page

## Introduction
Als je ooit een soepele, opvallende kleurverloop aan je PostScript‑output wilt geven, is het leren **hoe je een radiale gradiënt toevoegt** de perfecte plek om te beginnen. In deze tutorial lopen we stap voor stap door alles wat nodig is om een PostScript‑bestand te genereren dat een prachtige radiale gradiënt bevat, met behulp van de **Aspose.Page for Java** bibliotheek. Aan het einde begrijp je de API, zie je een volledig uitvoerbaar voorbeeld, en weet je hoe je kleuren, posities en stralen kunt aanpassen voor elk ontwerp.

## Quick Answers
- **Welke bibliotheek maakt radiale gradiënten in PostScript?** Aspose.Page for Java.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik de vorm van de gradiënt wijzigen?** Ja – pas de straal en het middelpunt aan in de `RadialGradientPaint`‑constructor.

## What is a Radial Gradient?
Een radiale gradiënt schildert kleuren die vanuit een centraal punt naar buiten stralen, geleidelijk vervagend naar de randen. In tegenstelling tot lineaire gradiënten volgt de kleurverloop een cirkelvormig (of ellipsvormig) patroon, wat ideaal is voor highlights, spotlights of zachte achtergrondvullingen.

## Why Use Aspose.Page for Radial Gradients?
- **Volledige controle over PostScript‑output** – geen handmatige low‑level PS‑commando's nodig.  
- **Cross‑platform** – werkt op elk OS dat Java draait.  
- **Rijke kleurbeheer** – ondersteunt meerdere kleurstops, verschillende kleurenschema's en cyclische methoden.  
- **Klaar voor integratie** – combineer met andere Aspose.Page‑functies zoals tekst, afbeeldingen en vectorvormen.

## Prerequisites
Voor je in de code duikt, zorg dat je het volgende klaar hebt staan:

- **Java Development Kit (JDK) 8+** – controleer met `java -version`.  
- **Aspose.Page for Java** – download de nieuwste JAR van de officiële [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE naar keuze** – Eclipse, IntelliJ IDEA, of VS Code met Java‑extensies.  
- **Een schrijfbare map** – waar het gegenereerde `.ps`‑bestand wordt opgeslagen.

## Import Packages
Eerst importeren we de klassen die we nodig hebben. Het `java.awt`‑pakket levert de gradient‑paint‑objecten, terwijl `com.aspose.eps` de klassen voor het verwerken van PostScript‑documenten bevat.

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

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
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

> **Pro tip:** Pas de coördinaten van de rechthoek (`200, 100, 200, 200`) aan om de gradiënt overal op de pagina te plaatsen.

### Step 2: Define Colors and Fractions
Een radiale gradiënt wordt opgebouwd uit *color stops* (de kleuren) en *fractions* (de relatieve posities van die stops). Hier maken we een array van zes kleuren en hun bijbehorende fractions.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Waarom dit belangrijk is:** Door `fractions` aan te passen bepaal je hoe snel de kleuren overgaan, waardoor subtiele of dramatische effecten mogelijk zijn.

### Step 3: Create Radial Gradient Paint
Nu bouwen we het `RadialGradientPaint`‑object. De constructor neemt het middelpunt van de gradiënt, de straal, het focuspunt, fractions, kleuren, cyclische methode, kleurenschema en een optionele transformatie.

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

> **Opmerking:** `transform` kan `null` zijn als je geen extra schaal- of rotatie nodig hebt. Voel je vrij om te experimenteren met `AffineTransform` voor scheve gradiënten.

### Step 4: Set Paint and Fill the Rectangle
Met de paint klaar, vertellen we het `PsDocument` deze te gebruiken en vullen we vervolgens de eerder gedefinieerde rechthoek.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Op dit punt bevat de PostScript‑pagina een rechthoek die soepel is gevuld met de radiale gradiënt die we hebben geconfigureerd.

### Step 5: Close and Save the Document
Tot slot sluiten we de huidige pagina en schrijven we het bestand naar schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Open `RadialGradient1_outPS.ps` in een PostScript‑viewer (bijv. Ghostscript) en je ziet de gradiënt precies zoals gedefinieerd.

## Common Issues & Solutions
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Gradiënt verschijnt als een effen kleur | `fractions`‑array begint niet bij `0.0f` of eindigt niet op `1.0f` | Zorg dat de eerste fraction `0.0f` is en de laatste `1.0f`. |
| Kleuren zien er vervaagd uit | Gebruik van de verkeerde `ColorSpaceType` | Schakel over naar `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` voor een levendiger resultaat. |
| Geen uitvoerbestand gegenereerd | `FileOutputStream`‑pad is ongeldig of niet schrijfbaar | Controleer of `dataDir` bestaat en de applicatie schrijfrechten heeft. |

## Frequently Asked Questions

**Q: Kan ik Aspose.Page for Java gebruiken in commerciële projecten?**  
A: Ja. Een commerciële licentie is vereist voor productiegebruik. Je kunt er een aanschaffen via de [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Waar kan ik de officiële API‑referentie vinden?**  
A: De volledige documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**Q: Is er een gratis proefversie beschikbaar voor testen?**  
A: Absoluut. Download een proefversie van de [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor evaluatie?**  
A: Een tijdelijke licentie kan worden aangevraagd [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik community‑ondersteuning krijgen?**  
A: Word lid van het Aspose.Page community‑forum op [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
Je weet nu **hoe je een radiale gradiënt toevoegt** aan een Java PostScript‑document met Aspose.Page. Door de grootte van de rechthoek, de kleurstops en de straal van de gradiënt aan te passen, kun je talloze visuele effecten creëren – van subtiele achtergrondvullingen tot gedurfde spotlight‑graphics. Voel je vrij om te experimenteren met verschillende `AffineTransform`‑waarden om de gradiënt te roteren of te scheefzetten, en combineer deze techniek met tekst en afbeeldingen voor rijkere PDF‑ of EPS‑output.

---

**Laatst bijgewerkt:** 2025-12-08  
**Getest met:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
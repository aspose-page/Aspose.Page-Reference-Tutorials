---
date: 2026-09-14
description: Leer hoe je postscript gradient java maakt met Aspose.Page. Deze stapsgewijze
  gids laat je zien hoe je een vertical gradient toevoegt aan een PostScript‑bestand
  in slechts een paar regels Java‑code.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Voeg Vertical Gradient toe in Java PostScript
og_description: Leer hoe je postscript gradient java maakt met Aspose.Page. Deze stapsgewijze
  gids laat je zien hoe je een vertical gradient toevoegt aan een PostScript‑bestand
  in slechts een paar regels Java‑code.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Maak postscript gradient java – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Maak postscript gradient java – vertical gradient
url: /nl/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak postscript gradient java – verticale gradient

## Introductie
Aspose.Page for Java is een bibliotheek die het mogelijk maakt om PostScript- en PDF-bestanden programmatisch te maken en te bewerken. In deze uitgebreide tutorial leer je hoe je **create postscript gradient java** kunt gebruiken met die bibliotheek. Het toevoegen van een verticale gradient kan je documenten er levendiger en professioneler uit laten zien, en met slechts een paar regels code kun je verbluffende visuele effecten bereiken. We lopen elke stap met je door, leggen uit waarom elk onderdeel belangrijk is, en geven praktische tips om veelvoorkomende valkuilen te vermijden. Aan het einde van deze gids kun je PostScript-bestanden genereren met vloeiende, opvallende verticale kleurovergangen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java  
- **Kan ik kleuren aanpassen?** Ja, elke `java.awt.Color` kan worden gebruikt  
- **Wordt rotatie ondersteund?** Ja, je kunt de gradient roteren met een `AffineTransform`  
- **Welk uitvoerformaat wordt geproduceerd?** Een standaard PostScript (.ps) bestand  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist  

## Waarom een verticale gradient toevoegen aan een PostScript-document?
Het toevoegen van een verticale gradient geeft je pagina's diepte, verbetert de visuele hiërarchie en houdt de bestandsgrootte laag omdat de gradient in vectorvorm wordt gedefinieerd in plaats van rasterafbeeldingen. Deze techniek is perfect voor rapportkoppen, technische handleidingen of elke flyer die een moderne uitstraling nodig heeft zonder in te boeten op schaalbaarheid.

## Vereisten
Voordat je aan de tutorial begint, zorg ervoor dat je de volgende vereisten hebt:
- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java bibliotheek. Je kunt deze downloaden van de [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Import pakketten
Importeer in je Java-project de benodigde pakketten om te beginnen:
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

Laten we nu stap voor stap het proces van het toevoegen van een verticale gradient doorlopen.

## Hoe postscript gradient java te maken
Laad je Java-omgeving, maak een `PsSaveOptions`-instantie aan en roep `Document.save` aan – dat is de kernreeks die een PostScript-bestand met een verticale gradient maakt. De API verwerkt kleurinterpolatie, coördinatentransformaties en het flushen van pagina's voor je, zodat je je alleen hoeft te concentreren op het definiëren van de rechthoek en de gradientparameters.

### Stap 1: stel uw documentmap in
`File`-objecten vertegenwoordigen de map waarin de output wordt geschreven. De map moet bestaan voordat de stream wordt geopend, anders wordt een `IOException` gegooid.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Stap 2: maak een outputstream voor het PostScript-document
`FileOutputStream` schrijft de binaire PostScript-gegevens naar de schijf. Het gebruik van een `try‑with‑resources`-blok garandeert dat de stream wordt gesloten, zelfs als er een uitzondering optreedt.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Stap 3: maak opslaanopties met A4-grootte
`PsSaveOptions` stelt je in staat om paginagrootte, DPI en of lettertypen moeten worden ingesloten te specificeren. Het instellen van de grootte op A4 (595 × 842 points) komt overeen met de meeste afdrukbare documenten.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Stap 4: maak een nieuw PS-document
`Document` is het object op het hoogste niveau dat een enkel PostScript-bestand in het geheugen vertegenwoordigt. Alle tekenopdrachten worden op dit object uitgevoerd.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Stap 5: maak een rechthoek
`Rectangle2D.Double` definieert het gebied dat met de gradient wordt gevuld. De coördinaten van de rechthoek worden uitgedrukt in points (1 point = 1/72 inch).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Stap 6: stel kleuren en fracties in voor de gradient
Een `float[]`-array definieert de positie van elke kleurstopping (van 0.0 tot 1.0). `Color`-objecten bevatten de feitelijke RGB-waarden. Je kunt elke `java.awt.Color` gebruiken die je wilt.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Stap 7: maak de gradienttransformatie
`AffineTransform` schaalt en roteert de gradient. Voor een pure verticale gradient hoef je alleen de Y-as te schalen; rotatie kan later worden toegevoegd indien gewenst.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Stap 8: maak verticale lineaire gradientverf
`LinearGradientPaint` koppelt de rechthoek, de kleurstops en de transformatie. Dit object wordt later doorgegeven aan de graphics-context.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Stap 9: stel verf in en vul de rechthoek
`Graphics2D.setPaint` past de gradient toe, en `fill` rendert deze binnen de rechthoek die je eerder hebt gedefinieerd.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Stap 10: sluit de huidige pagina en sla het document op
Het aanroepen van `document.save` schrijft de volledige PostScript-stream naar het uitvoerbestand en geeft alle native resources vrij.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gefeliciteerd! Je hebt met succes een verticale gradient toegevoegd aan je Java PostScript-document met behulp van Aspose.Page for Java.

## Veelvoorkomende problemen en oplossingen
- **Gradient lijkt vlak:** Zorg ervoor dat de `AffineTransform`-schaling overeenkomt met de afmetingen van de rechthoek.  
- **Kleuren zien er vaal uit:** Controleer of je de juiste `ColorSpaceType` (SRGB) gebruikt en dat de fractions-array geordend is van 0.0 tot 1.0.  
- **Bestand niet gegenereerd:** Controleer of de outputdirectory (`dataDir`) bestaat en of de applicatie schrijfrechten heeft.  

## Veelgestelde vragen
**Q: Kan ik Aspose.Page for Java gebruiken met andere Java-bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos samen te werken met andere Java-bibliotheken zoals Apache Commons of Spring.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie krijgen via de [free trial download page](https://releases.aspose.com/).

**Q: Waar kan ik aanvullende documentatie vinden?**  
A: Gedetailleerde documentatie is beschikbaar via de [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik Aspose.Page for Java aanschaffen?**  
A: Je kunt Aspose.Page for Java kopen via de [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**Q: Is er een forum voor Aspose.Page discussies?**  
A: Ja, je kunt deelnemen aan het communityforum via de [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## Aanvullende veelgestelde vragen

**Q: Kan ik andere gradientrichtingen maken (horizontaal, diagonaal)?**  
A: Zeker. Pas de start- en eindpunten aan in `LinearGradientPaint` en wijzig de rotatiehoek in de `AffineTransform`.

**Q: Werkt dit ook met PDF-uitvoer?**  
A: Dezelfde gradientlogica kan worden toegepast bij het opslaan naar PDF door `PdfSaveOptions` te gebruiken in plaats van `PsSaveOptions`.

**Q: Hoe kan ik de grootte van de gradient dynamisch wijzigen?**  
A: Bereken de afmetingen van de rechthoek tijdens runtime en geef die waarden door aan zowel de `Rectangle2D` als de `AffineTransform`-constructor.

**Laatst bijgewerkt:** 2026-09-14  
**Getest met:** Aspose.Page for Java 24.11 (latest)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak radiale gradient in PostScript met Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Hoe PostScript naar PDF te converteren met Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page transparantie tutorial – Transparantie toevoegen in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-02-13
description: Leer hoe je een PostScript‑verloop maakt in Java met Aspose.Page. Deze
  stapsgewijze handleiding laat je zien hoe je moeiteloos een verticale verloop aan
  je PostScript‑documenten toevoegt.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Maak PostScript‑verloop in Java – Voeg verticale verloop toe
url: /nl/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak PostScript Gradient in Java – Voeg verticale gradient toe

## Inleiding
In deze uitgebreide tutorial leer je hoe je **een PostScript gradient in Java maakt** met Aspose.Page for Java. Het toevoegen van een verticale gradient kan je documenten levendiger en professioneler laten lijken, en met slechts een paar regels code kun je verbluffende visuele effecten bereiken. We lopen elke stap met je door, leggen uit waarom elk onderdeel belangrijk is, en geven praktische tips om veelvoorkomende valkuilen te vermijden. Aan het einde van deze gids kun je PostScript‑bestanden genereren met vloeiende, opvallende verticale kleurverlopen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java  
- **Kan ik kleuren aanpassen?** Ja, elke `java.awt.Color` kan worden gebruikt  
- **Wordt rotatie ondersteund?** Ja, je kunt het verloop roteren met een `AffineTransform`  
- **Welk uitvoerformaat wordt geproduceerd?** Een standaard PostScript‑bestand (.ps)  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist  

## Waarom een verticale gradient toevoegen aan een PostScript‑document?
Verticale gradients geven je pagina's diepte zonder de bestandsgrootte op te blazen. Ze zijn perfect voor:

* Kop‑ of voetteksten van rapporten die een subtiele achtergrondkleur nodig hebben.  
* Het accentueren van secties in technische handleidingen of white‑papers.  
* Het geven van een moderne uitstraling aan grafieken, diagrammen of promotieflyers.

Omdat het verloop in vectorvorm wordt gedefinieerd, blijft de output scherp bij elke resolutie.

## Vereisten
Zorg ervoor dat je de volgende zaken gereed hebt voordat je aan de tutorial begint:
- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java‑bibliotheek. Je kunt deze downloaden [hier](https://releases.aspose.com/page/java/).

## Pakketten importeren
Importeer in je Java‑project de benodigde pakketten om te beginnen:
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

Laten we nu stap voor stap het toevoegen van een verticale gradient doorlopen.

## Hoe maak je een PostScript gradient in Java
Hieronder vind je een stap‑voor‑stap‑gids die precies laat zien hoe je **een PostScript gradient in Java maakt** met de Aspose.Page‑API.

### Stap 1: Stel je documentmap in
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Stap 2: Maak een output‑stream voor het PostScript‑document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Stap 3: Maak opslaan‑opties met A4‑formaat
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Stap 4: Maak een nieuw PS‑document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Stap 5: Maak een rechthoek
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Stap 6: Stel kleuren en fracties in voor het verloop
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Stap 7: Maak de gradient‑transformatie
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Stap 8: Maak een verticale lineaire gradient‑paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Stap 9: Stel de paint in en vul de rechthoek
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Stap 10: Sluit de huidige pagina en sla het document op
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gefeliciteerd! Je hebt met succes een verticale gradient toegevoegd aan je Java‑PostScript‑document met Aspose.Page for Java.

## Veelvoorkomende problemen en oplossingen
- **Gradient lijkt plat:** Zorg ervoor dat de `AffineTransform`‑schaling overeenkomt met de afmetingen van de rechthoek.  
- **Kleuren zien er flets uit:** Controleer of je de juiste `ColorSpaceType` (SRGB) gebruikt en dat de fracties‑array geordend is van 0.0 tot 1.0.  
- **Bestand wordt niet gegenereerd:** Controleer of de output‑directory (`dataDir`) bestaat en of de applicatie schrijfrechten heeft.  

## Veelgestelde vragen
### Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?
Ja, Aspose.Page for Java is ontworpen om naadloos samen te werken met andere Java‑bibliotheken.

### Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?
Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

### Waar vind ik extra documentatie?
Gedetailleerde documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

### Hoe kan ik Aspose.Page for Java aanschaffen?
Je kunt Aspose.Page for Java aanschaffen [hier](https://purchase.aspose.com/buy).

### Is er een forum voor discussies over Aspose.Page?
Ja, je kunt deelnemen aan het community‑forum [hier](https://forum.aspose.com/c/page/39).

## Aanvullende veelgestelde vragen

**V: Kan ik andere gradient‑richtingen maken (horizontaal, diagonaal)?**  
A: Absoluut. Pas de start‑ en eindpunten in `LinearGradientPaint` aan en wijzig de rotatiehoek in de `AffineTransform`.

**V: Werkt dit ook met PDF‑output?**  
A: Dezelfde gradient‑logica kan worden toegepast bij het opslaan naar PDF door `PdfSaveOptions` te gebruiken in plaats van `PsSaveOptions`.

**V: Hoe wijzig ik de grootte van het gradient dynamisch?**  
A: Bereken de afmetingen van de rechthoek tijdens runtime en geef die waarden door aan zowel de `Rectangle2D` als de `AffineTransform`‑constructor.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Page for Java 24.11 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
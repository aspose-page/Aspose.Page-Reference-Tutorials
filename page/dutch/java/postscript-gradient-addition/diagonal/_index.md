---
date: 2026-02-13
description: Verbeter uw Java PostScript‑documenten met diagonale verlopen met Aspose.Page
  Java. Leer hoe u gradient‑effecten kunt toevoegen met LinearGradientPaint in Java
  en moeiteloos levendige kleurovergangen kunt creëren.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'Hoe een kleurverloop toe te voegen: Diagonaal kleurverloop in Java PostScript
  met Aspose.Page Java'
url: /nl/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagonale Gradient toevoegen in Java PostScript met Aspose.Page Java

## Introductie
Als je een PostScript‑bestand wilt verrijken met een vloeiende diagonale kleurverloop, maakt **Aspose.Page Java** het verrassend eenvoudig. In deze tutorial lopen we stap‑voor‑stap door **hoe je gradient‑effecten toevoegt**, met behulp van de `LinearGradientPaint`‑klasse uit Java 2D. Aan het einde heb je een kant‑klaar fragment dat een PostScript‑document maakt met een levendige diagonale gradient.

## Hoe voeg je een gradient toe in Java PostScript
Een gradient toevoegen klinkt misschien als een zuiver grafische taak, maar met Aspose.Page krijg je volledige controle over de onderliggende PostScript‑commando’s terwijl je in pure Java blijft. Deze sectie legt uit waarom de aanpak werkt en wat je wint ten opzichte van handmatig ruwe PostScript schrijven.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java.  
- **Welke klasse maakt de gradient?** `LinearGradientPaint`.  
- **Kan ik de kleuren aanpassen?** Ja – wijzig de `Color[]`‑array.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Hoe lang duurt de implementatie?** Ongeveer 10 minuten voor een basisgradient.

## Wat is Aspose.Page Java?
Aspose.Page Java is een krachtige API waarmee ontwikkelaars PostScript‑ en PDF‑bestanden kunnen genereren, bewerken en converteren zonder externe software. Het biedt de volledige grafische mogelijkheden van de PostScript‑taal via een nette, object‑georiënteerde Java‑interface.

## Waarom een diagonale gradient gebruiken?
Een diagonale gradient voegt diepte en visuele interesse toe aan diagrammen, banners of elk grafisch element dat een moderne uitstraling nodig heeft. Omdat de gradient van de ene hoek naar de tegenoverliggende loopt, werkt hij uitstekend voor achtergronden, knop‑skins en decoratieve vormen.

## Voorvereisten
Zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) 8 of hoger.  
- Een IDE zoals Eclipse, IntelliJ IDEA, of VS Code.  
- **Aspose.Page for Java**‑bibliotheek – download de nieuwste versie van de [officiële downloadpagina](https://releases.aspose.com/page/java/).

## Importpakketten
Importeer eerst de Java 2D‑ en Aspose‑klassen die je nodig hebt. Deze imports geven toegang tot kleurdefinities, geometrische vormen, gradient‑painting en de PostScript‑document‑API.

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

## Stap 1: Output‑stream maken voor PostScript‑document
We definiëren de map waarin het bestand wordt opgeslagen en openen een `FileOutputStream`. Deze stream ontvangt de gegenereerde PostScript‑data.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Stap 2: Save‑options maken met A4‑formaat
`PsSaveOptions` laat je paginagrootte, resolutie en andere uitvoerinstellingen specificeren. Hier gebruiken we het standaard A4‑formaat.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Stap 3: Nieuw PS‑document aanmaken
Instantieer een `PsDocument` met de output‑stream en de save‑options. De `false`‑vlag vertelt de constructor om niet automatisch een nieuwe pagina te openen – dat doen we later.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 4: Een rechthoek maken
Definieer de rechthoek die de gradient‑vulling krijgt. De positie (200, 100) en grootte (200 × 100) zijn gekozen zodat de gradient duidelijk zichtbaar is.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Stap 5: Gradient‑transformatie maken
Een `AffineTransform` stelt ons in staat de gradient te roteren, schalen en verplaatsen zodat deze diagonaal over de rechthoek loopt. De onderstaande wiskunde berekent de hypotenusa en past de schaalverhouding dienovereenkomstig aan.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Stap 6: Diagonale Linear Gradient Paint maken
Hier is de kern van **hoe je gradient toevoegt** – we bouwen een `LinearGradientPaint` die loopt van de linkerbovenhoek van de rechthoek naar de rechteronderhoek, met de eerder gedefinieerde transformatie. `MultipleGradientPaint.CycleMethod.NO_CYCLE` zorgt ervoor dat de gradient niet herhaalt.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Stap 7: Paint instellen en de rechthoek vullen
Pas de gradient‑paint toe op het document en vul de rechthoekvorm. Deze stap rendert de diagonale kleurverloop op de PostScript‑pagina.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Stap 8: Huidige pagina sluiten en document opslaan
Sluit tenslotte de pagina, flush de stream en sla het bestand op. Het resulterende bestand `DiagonalGradient_outPS.ps` kan met elke PostScript‑viewer worden geopend.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Veelvoorkomende problemen & tips
- **Gradient lijkt vlak** – controleer de rotatiehoek; een rotatie van 45° creëert een echte diagonal.  
- **Kleuren zien er vervaagd uit** – zorg ervoor dat je `MultipleGradientPaint.ColorSpaceType.SRGB` gebruikt voor nauwkeurige kleurweergave.  
- **Bestand niet gevonden‑fout** – controleer of `dataDir` naar een bestaande map wijst en of de applicatie schrijfrechten heeft.

## Veelgestelde vragen

**V: Kan ik deze bibliotheek gebruiken voor andere grafische bewerkingen in Java?**  
A: Ja, Aspose.Page for Java biedt een volledige set teken‑primitieven, tekstweergave en beeldverwerkingsmogelijkheden.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Page Java?**  
A: Absoluut. Je kunt een volledig functionele proefversie downloaden via de [Aspose gratis proefpagina](https://releases.aspose.com/).

**V: Waar vind ik documentatie voor Aspose.Page Java?**  
A: De officiële API‑referentie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**V: Hoe kan ik een licentie aanschaffen voor Aspose.Page Java?**  
A: Licenties kunnen rechtstreeks worden gekocht via het [Aspose aankoopportaal](https://purchase.aspose.com/buy).

**V: Hulp nodig of vragen?**  
A: Bezoek het door de community beheerde [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor ondersteuning van zowel Aspose‑engineers als mededevelopers.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-04
description: Leer hoe u een gradient kunt toevoegen in Java PostScript met Aspose.Page
  Java, waarbij u diagonale kleurovergangen maakt met LinearGradientPaint voor levendige
  documenten.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Hoe een gradient toe te voegen: diagonale gradient in Java PostScript
  met Aspose.Page Java'
og_description: Leer hoe u een gradient kunt toevoegen in Java PostScript met Aspose.Page
  Java. Deze gids laat zien hoe u in slechts een paar stappen een diagonale gradient
  maakt met LinearGradientPaint.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Hoe een gradient toe te voegen in Java PostScript met Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Hoe een gradient toe te voegen: diagonale gradient in Java PostScript met
  Aspose.Page Java'
url: /nl/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg diagonale gradiënt toe in Java PostScript met Aspose.Page Java

## Introductie
Als je een PostScript‑bestand wilt verrijken met een soepele diagonale kleurverloop, maakt **Aspose.Page Java** het verrassend eenvoudig. In deze tutorial leer je **hoe je een gradiënt** stap‑voor‑stap toevoegt, met behulp van de `LinearGradientPaint`‑klasse uit Java 2D. Aan het einde heb je een kant‑klaar fragment dat een PostScript‑document maakt met een levendige diagonale gradiënt, en begrijp je waarom deze aanpak onderhoudsvriendelijker is dan het handmatig coderen van ruwe PostScript‑commando's.

## Hoe een gradiënt toe te voegen in Java PostScript
Het toevoegen van een gradiënt klinkt misschien als een taak die alleen met graphics te maken heeft, maar met Aspose.Page krijg je volledige controle over de onderliggende PostScript‑commando's terwijl je in pure Java blijft. Deze sectie legt uit waarom de aanpak werkt en wat je wint ten opzichte van handmatig coderen van ruwe PostScript.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java.  
- **Welke klasse maakt de gradiënt?** `LinearGradientPaint`.  
- **Kan ik de kleuren wijzigen?** Ja – wijzig de `Color[]`‑array.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Hoe lang duurt de implementatie?** Ongeveer 10 minuten voor een basisgradiënt.

## Wat is Aspose.Page Java?
Aspose.Page Java is een volledig uitgeruste API die ontwikkelaars in staat stelt PostScript- en PDF-bestanden te genereren, bewerken en converteren zonder externe software. De bibliotheek ondersteunt **50+ invoer- en uitvoerformaten** en kan documenten met **500+ pagina's** verwerken terwijl het geheugenverbruik onder de 100 MB blijft.

## Waarom een diagonale gradiënt gebruiken?
Een diagonale gradiënt voegt diepte en visueel belang toe aan diagrammen, banners of elk grafisch element dat een moderne uitstraling nodig heeft. Omdat de gradiënt van de ene hoek naar de tegenoverliggende loopt, werkt hij goed voor achtergronden, knopskins en decoratieve vormen, en geeft hij een professionele afwerking zonder extra afbeeldingsbestanden.

## Voorvereisten
- Java Development Kit (JDK) 8 of hoger.  
- Een IDE zoals Eclipse, IntelliJ IDEA of VS Code.  
- **Aspose.Page for Java** bibliotheek – download de nieuwste versie van de [officiële downloadpagina](https://releases.aspose.com/page/java/).

## Pakketten importeren
Het `java.awt`‑pakket levert de kern‑grafiekklassen, terwijl het `com.aspose.page`‑pakket toegang geeft tot PostScript‑specifieke API's.

De `LinearGradientPaint`‑klasse is de brug van Aspose.Page naar de Java 2D‑gradiëntfunctionaliteit.  
`AffineTransform` maakt rotatie en schaling van de gradiënt mogelijk zodat deze diagonaal uitgelijnd wordt.

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

## Stap 1: maak output‑stream voor PostScript‑document
Definieer eerst de map waarin het bestand wordt opgeslagen en open een `FileOutputStream`. Deze stream ontvangt de gegenereerde PostScript‑gegevens.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Stap 2: maak opslaan‑opties met A4‑grootte
`PsSaveOptions` stelt je in staat paginagrootte, resolutie en andere uitvoerinstellingen te specificeren. Hier gebruiken we de standaard A4‑grootte, die 595 × 842 punten is bij 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Stap 3: maak nieuw PS‑document
De `PsDocument`‑klasse vertegenwoordigt een PostScript‑document en biedt methoden om pagina's te maken en grafische elementen te tekenen.  
Instantieer een `PsDocument` met de output‑stream en de opslaan‑opties. De `false`‑vlag vertelt de constructor om niet automatisch een nieuwe pagina te openen – we doen dat later.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 4: maak een rechthoek
Definieer de rechthoek die de gradiëntvulling ontvangt. De positie (200, 100) en grootte (200 × 100) zijn gekozen zodat de gradiënt duidelijk zichtbaar is.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Stap 5: maak gradiënt‑transformatie
Een `AffineTransform` laat ons de gradiënt roteren, schalen en verplaatsen zodat deze diagonaal over de rechthoek loopt. De onderstaande wiskunde berekent de hypotenusa en past de schaalverhouding dienovereenkomstig aan.

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

## Stap 6: maak diagonale lineaire gradiënt‑paint
`LinearGradientPaint` is de kernklasse die de kleurverloop genereert. Hij loopt van de linkerbovenhoek van de rechthoek naar de rechteronderhoek, met gebruik van de eerder gedefinieerde transformatie. De `MultipleGradientPaint.CycleMethod.NO_CYCLE` zorgt ervoor dat de gradiënt niet herhaalt.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Stap 7: stel paint in en vul de rechthoek
Pas de gradiënt‑paint toe op het document en vul de rechthoekvorm. Deze stap rendert de diagonale kleurverloop op de PostScript‑pagina.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Stap 8: sluit de huidige pagina en sla het document op
Sluit tenslotte de pagina, flush de stream en sla het bestand op. Het resulterende bestand `DiagonalGradient_outPS.ps` kan worden geopend met elke PostScript‑viewer.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Veelvoorkomende problemen & tips
- **Gradiënt lijkt vlak** – controleer de rotatiehoek; een rotatie van 45° creëert een echte diagonale.  
- **Kleuren zien er flets uit** – zorg ervoor dat je `MultipleGradientPaint.ColorSpaceType.SRGB` gebruikt voor nauwkeurige kleurrendering.  
- **Bestand niet gevonden‑fout** – controleer of `dataDir` naar een bestaande map wijst en dat de applicatie schrijfrechten heeft.  
- **Grote documenten veroorzaken geheugenpieken** – gebruik `PsSaveOptions.setCompress(true)` om de geheugenvoetafdruk te verkleinen.

## Veelgestelde vragen

**Q: Kan ik deze bibliotheek gebruiken voor andere grafische bewerkingen in Java?**  
A: Ja, Aspose.Page for Java biedt een volledige set tekenprimitieven, tekstreeksen en beeldverwerkingsmogelijkheden.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page Java?**  
A: Absoluut. Je kunt een volledig functionele proefversie downloaden van de [Aspose gratis proefversie pagina](https://releases.aspose.com/).

**Q: Waar kan ik documentatie vinden voor Aspose.Page Java?**  
A: De officiële API‑referentie is beschikbaar op [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik een licentie aanschaffen voor Aspose.Page Java?**  
A: Licenties kunnen direct worden gekocht via het [Aspose aankoopportaal](https://purchase.aspose.com/buy).

**Q: Hulp nodig of vragen?**  
A: Bezoek het door de community beheerde [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor hulp van zowel Aspose‑ingenieurs als mede‑ontwikkelaars.

---

**Laatste update:** 2026-09-04  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Radiale gradiënt maken in PostScript met Aspose.Page voor Java](/page/java/postscript-gradient-addition/)
- [Hoe een gradiënt toe te voegen in Java PostScript met Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [PostScript‑gradiënt maken in Java – Voeg verticale gradiënt toe](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
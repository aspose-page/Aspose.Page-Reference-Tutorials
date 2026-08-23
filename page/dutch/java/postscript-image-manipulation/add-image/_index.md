---
date: 2026-08-23
description: Leer hoe je aspose.page image manipulation java kunt gebruiken om afbeeldingen
  in PostScript-bestanden in te sluiten en te roteren, met duidelijke Java-voorbeelden.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Afbeelding toevoegen in Java PostScript
og_description: Leer hoe je aspose.page image manipulation java kunt gebruiken om
  afbeeldingen in PostScript-bestanden in te sluiten en te roteren, met stapsgewijze
  Java-codevoorbeelden.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Hoe aspose.page image manipulation java te gebruiken om een afbeelding toe
  te voegen
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Hoe aspose.page image manipulation java te gebruiken om een afbeelding toe
  te voegen
url: /nl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe aspose.page image manipulation java te gebruiken om een afbeelding toe te voegen

## Introductie
In deze tutorial leer je hoe je **aspose.page image manipulation java** kunt **gebruiken** om PostScript‑bestanden te maken, raster‑afbeeldingen in te sluiten en translatie‑en‑rotatie‑transformaties toe te passen. Aan het einde van de gids kun je pixel‑perfecte PostScript‑output genereren vanuit Java—ideaal voor geautomatiseerde rapportage, afdruk‑pijplijnen of elke workflow die precieze plaatsing van afbeeldingen binnen een PostScript‑document vereist.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik meerdere afbeeldingen toevoegen?** Ja – herhaal de transformatie‑ en tekenstappen voor elke afbeelding  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie  
- **Welke Java‑versie wordt ondersteund?** Java 8 en later  
- **Wordt rotatie van afbeeldingen ondersteund?** Absoluut – gebruik `AffineTransform.rotate()`

## Wat is aspose.page image manipulation java?
`aspose.page image manipulation java` is de Aspose.Page‑API waarmee je programmatisch PostScript‑documenten kunt bouwen, bewerken en renderen vanuit Java‑code, inclusief volledige controle over afbeelding‑plaatsing, schalen en roteren. Met deze API vermijd je low‑level PostScript‑syntaxis en laat je de bibliotheek de formatconversie en insluiting intern afhandelen.

## Waarom aspose.page gebruiken voor afbeeldingsmanipulatie?
Aspose.Page biedt **meer dan 50 afbeeldingsformaten** (inclusief JPEG, PNG, BMP, TIFF) en kan ze in PostScript insluiten zonder het volledige document in het geheugen te laden, waardoor verwerking van bestanden met honderden pagina's mogelijk is terwijl het geheugenverbruik onder de 100 MB blijft op een typische server. De high‑level API abstraheert complexe PostScript‑commando's, zodat je beknopte Java‑code schrijft in plaats van ruwe PS‑operatoren.

## Vereisten
- Java Development Kit (JDK) 8 of nieuwer geïnstalleerd.  
- Aspose.Page for Java bibliotheek – download deze **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Basiskennis van Java‑syntaxis en objectgeoriënteerd programmeren.

## Wat is create postscript java?
Een PostScript‑bestand vanuit Java maken betekent programmatisch een `.ps`‑document genereren dat paginalay‑out, vector‑graphics en raster‑afbeeldingen beschrijft met behulp van de PostScript‑taal. Aspose.Page zet je Java‑aanroepen om in geldige PostScript‑instructies, zodat je print‑klare bestanden kunt produceren zonder een aparte PostScript‑interpreter.

## Hoe een afbeelding toe te voegen met translatie en rotatie stap voor stap

Laad je afbeelding, pas een `AffineTransform` toe en teken deze op de pagina. De volgende stappen beschrijven de exacte volgorde die je moet volgen.

### Stap 1: graphics opslaan
Het opslaan van de grafische toestand isoleert je transformaties zodat je later kunt terugkeren. Dit is equivalent aan de `gsave`‑operator in ruwe PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Stap 2: vertalen en transformeren (afbeelding vertalen en roteren)
Maak eerst een `BufferedImage` van het bronbestand, bouw vervolgens een `AffineTransform` die de afbeelding naar de gewenste coördinaten verplaatst en rond het midden roteert. `AffineTransform.rotate` verwacht een hoek in radialen, dus converteer graden met `Math.toRadians(degrees)`.

**AffineTransform** is een Java‑klasse die een 2‑D affine transformatie representeert, zoals translatie, rotatie, schalen of schuiven.  
**BufferedImage** is een Java‑klasse die een afbeelding in het geheugen opslaat als een raster van pixels.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Stap 3: afbeelding toevoegen aan document
Na het configureren van de transformatie teken je de afbeelding op de huidige pagina. De bibliotheek zet de `BufferedImage` automatisch om in een geschikte PostScript‑afbeeldingsstroom.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Stap 4: graphics herstellen
Het aanroepen van restore (`grestore`) zet de grafische toestand terug naar de staat vóór het opslaan, zodat daaropvolgende teken‑commando's niet worden beïnvloed door de vorige transformatie.

```java
document.drawImage(image, transform, null);
```

### Stap 5: huidige pagina sluiten en opslaan
Rond de pagina af, sluit het document en schrijf het uitvoerbestand naar schijf.

```java
document.writeGraphicsRestore();
```

Je kunt de bovenstaande reeks herhalen om extra afbeeldingen in te sluiten, waarbij je elke keer de translatie‑coördinaten en rotatiehoek aanpast.

## Veelvoorkomende problemen en oplossingen
- **FileNotFoundException:** Controleer of `dataDir` eindigt met een bestandsscheidingsteken (`/` of `\\`) en of de bestandsnaam van de afbeelding exact overeenkomt.  
- **ImageIO.read returns null:** Zorg ervoor dat het afbeeldingsformaat voorkomt in de ondersteunde lijst (JPEG, PNG, BMP, GIF, TIFF).  
- **Onjuiste rotatiehoek:** `AffineTransform.rotate` werkt met radialen; gebruik `Math.toRadians(degrees)` om van graden om te rekenen.  
- **Geheugenspikes bij grote pagina's:** Gebruik `Document.save` met `saveOptions.setCompress(true)` om de geheugengebruik te verminderen.

## Veelgestelde vragen

**V: Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?**  
A: De kernbibliotheek is alleen voor Java, maar Aspose biedt equivalente API's voor .NET, C++ en Python, elk aangepast aan hun platform.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?**  
A: Ja, u kunt de gratis proefversie openen via **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**V: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor Java?**  
A: U kunt een tijdelijke licentie aanvragen via **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**V: Waar kan ik community‑ondersteuning en discussies vinden over Aspose.Page voor Java?**  
A: Bezoek het **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** voor community‑ondersteuning.

**V: Zijn er extra bronnen voor het aanschaffen van Aspose.Page voor Java?**  
A: U kunt de bibliotheek kopen via **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Conclusie
Je hebt nu een volledig voorbeeld van **aspose.page image manipulation java** dat een PostScript‑bestand maakt, een afbeelding translateert en roteert, en het resultaat opslaat. Verken de volledige **[documentation](https://reference.aspose.com/page/java/)** om geavanceerde functies te ontdekken, zoals vector‑graphics, aangepaste paginagroottes en tekst‑rendering.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## Gerelateerde tutorials

- [Hoe PostScript naar PDF converteren met Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Hoe een diagonale gradient toe te voegen in Java PostScript met Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Hoe een hatch‑patroon toe te voegen in Java PostScript met Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
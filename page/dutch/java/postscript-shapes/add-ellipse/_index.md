---
date: 2026-10-31
description: Leer hoe u paint color instelt en een ellipse vult in Java PostScript
  met behulp van Aspose.Page. Deze gids toont hoe u een ellipse vult, een ellipse
  outline tekent en stroke thickness instelt met duidelijke code steps.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Ellipse toevoegen in Java PostScript
og_description: Leer hoe u een ellipse vult en paint color instelt in Java PostScript
  met behulp van Aspose.Page. Volg step-by-step code om filled and outlined ellipses
  in seconden te tekenen.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Hoe een ellipse te vullen en paint color in te stellen in Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Hoe een ellipse te vullen en paint color in te stellen in Java PostScript
url: /nl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een ellips vullen en verfkleur instellen in Java PostScript

## Introductie
Als je **verfkleur moet instellen** tijdens het tekenen van vectorafbeeldingen, biedt de Aspose.Page for Java‑bibliotheek volledige controle over elke lijn en vulling. In deze tutorial ontdek je hoe je **verfkleur instelt**, **een ellips vult** en **de omtrek van een ellips tekent** met een eenvoudige, stapsgewijze aanpak. Aan het einde kun je hoogwaardige PostScript‑ellipsen toevoegen aan facturen, rapporten of elk afdrukbaar document.

## Snelle antwoorden
- **Welke bibliotheek is het beste voor het tekenen van PostScript‑graphics in Java?** Aspose.Page for Java.  
- **Kan ik een ellips vullen met een effen kleur?** Ja – gebruik `document.setPaint(Color.YOUR_COLOR)` vóór `fill`.  
- **Hoe teken ik alleen de omtrek van een ellips?** Stel de verf en de lijn in, en roep vervolgens `document.draw(...)` aan.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist; een tijdelijke licentie is beschikbaar voor testen.  
- **Welke Java‑versie wordt ondersteund?** Elke Java 8+ runtime werkt met de huidige Aspose.Page‑release.

## Wat is een PostScript‑ellips?
Een PostScript‑ellips is een vectorvorm die wordt gedefinieerd door een begrenzende rechthoek. In tegenstelling tot rasterafbeeldingen schaalt hij zonder kwaliteitsverlies, waardoor hij ideaal is voor hoge‑resolutie‑afdrukken en PDF‑conversie. Omdat de vorm wiskundig wordt beschreven, kan hij op elke grootte of resolutie worden gerenderd terwijl scherpe randen en vloeiende krommen behouden blijven.

## Waarom Aspose.Page gebruiken om een PostScript‑ellips te maken?
Aspose.Page geeft je deterministische controle over elk teken‑primitive. Het ondersteunt **3 belangrijke besturingssystemen (Windows, Linux, macOS)**, **0 native afhankelijkheden**, en kan **50+ vector‑primitieven** per seconde renderen op een typische server. De bibliotheek is pure Java, zodat je hem in elke Java 8+ toepassing kunt integreren zonder extra native bibliotheken.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. Een functionele Java‑ontwikkelomgeving (JDK 8 of later).  
2. De Aspose.Page for Java‑bibliotheek toegevoegd aan je project. Je kunt deze **[van de Aspose.Page for Java release‑pagina](https://releases.aspose.com/page/java/)** downloaden.  

## Pakketten importeren
Importeer in je Java‑bronbestand de klassen die nodig zijn voor het tekenen en opslaan van PostScript‑inhoud.

Het `java.awt`‑pakket levert de basisgrafiektype­s zoals `Color`, `Ellipse2D` en `BasicStroke`. Het `com.aspose.page`‑pakket biedt de `PsDocument`‑klasse die PostScript‑output schrijft.

- **`Color`** – vertegenwoordigt een sRGB‑kleur die wordt gebruikt voor schilderen.  
- **`Ellipse2D`** – beschrijft een ellipsvorm gedefinieerd door een begrenzende rechthoek.  
- **`BasicStroke`** – specificeert lijndikte, stippelpatroon en eindkapstijl voor het tekenen van omtrekken.  
- **`PsDocument`** – vertegenwoordigt een PostScript‑document en biedt methoden om grafieken te tekenen en pagina's te beheren.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hoe verfkleur instellen voor een ellips
De eerste stap is het document vertellen welke kleur moet worden gebruikt voor de volgende tekenbewerking. De `setPaint`‑methode stelt een effen kleur in die wordt toegepast op een vulling of een lijn, afhankelijk van de daaropvolgende aanroep.

### Stap 1: Het PostScript‑document instellen
Maak een output‑stream, configureer de paginagrootte en instantiateer een `PsDocument`.

`PsDocument` is de kernklasse die een PostScript‑bestand in het geheugen vertegenwoordigt. Alle teken‑commando's worden via dit object geleid, en het beheert paginalay-out, resource‑beheer en de uiteindelijke bestandsgeneratie.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Stap 2: Ellips vullen – gebruik set paint color
Om **een ellips te vullen**, moet je eerst `setPaint` aanroepen met de gewenste vulkleur, en vervolgens `fill` aanroepen met een `Ellipse2D`‑instantie.

`setPaint` stelt de huidige tekenkleur in die wordt gebruikt voor daaropvolgende vul‑ of lijnbewerkingen.  
`Ellipse2D` definieert de geometrische grenzen van de ellips; de constructor neemt de X‑Y‑coördinaten van de linkerbovenhoek plus breedte en hoogte.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Stap 3: Ellipsomtrek tekenen en lijndikte instellen
Na het vullen kun je de verf naar een andere kleur wijzigen, een `BasicStroke` definiëren om de lijndikte te regelen, en de ellipsomtrek tekenen.

`BasicStroke` specificeert lijndikte, stippelpatroon en eindkapstijl voor het tekenen van omtrekken. Door de `width`‑eigenschap aan te passen, bepaal je hoe dik de ellipsrand verschijnt.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Stap 4: Het document sluiten en opslaan
Rond de pagina af en schrijf het PostScript‑bestand naar schijf.

Het aanroepen van `document.close()` spoelt alle wachtende teken‑commando's weg en geeft resources vrij. Het resulterende `.ps`‑bestand kan worden geopend met elke PostScript‑viewer of worden geconverteerd naar PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Je hebt nu een PostScript‑bestand dat twee ellipsen bevat — één gevuld met oranje en een andere met een rode omtrek. Voel je vrij om te experimenteren met verschillende coördinaten, maten en kleuren om aan je ontwerpbehoeften te voldoen.

## Veelvoorkomende valkuilen en probleemoplossing
- **Onjuist bestandspad** – Zorg ervoor dat `dataDir` eindigt met een scheidingsteken (`/` of `\\`) dat geschikt is voor je OS.  
- **Ontbrekende licentie** – Zonder een geldige licentie draait de bibliotheek in evaluatiemodus en kan watermerken toevoegen.  
- **Kleur niet toegepast** – Vergeet niet `document.setPaint(...)` *vóór* elke `fill`‑ of `draw`‑aanroep te zetten; de verfinstelling blijft niet automatisch behouden tussen afzonderlijke bewerkingen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos te integreren met andere Java‑bibliotheken.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Verkrijg een tijdelijke licentie **[van de Aspose tijdelijke‑licentiepagina](https://purchase.aspose.com/temporary-license/)** voor testdoeleinden.

**Q: Is Aspose.Page geschikt voor commerciële projecten?**  
A: Absoluut! Bezoek **[de Aspose aankooppagina](https://purchase.aspose.com/buy)** om licentie‑opties voor commercieel gebruik te bekijken.

**Q: Waar kan ik hulp zoeken of discussies over Aspose.Page‑gerelateerde vragen voeren?**  
A: Word lid van de community op het **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** voor discussies en ondersteuning.

**Q: Zijn er gratis bronnen om meer te leren over Aspose.Page for Java?**  
A: Maak gebruik van de **[Aspose gratis proefpagina](https://releases.aspose.com/)** en bekijk voorbeelden in de documentatie.

## Conclusie
Aspose.Page for Java maakt het eenvoudig om **verfkleur in te stellen**, **een ellips te vullen**, en **de omtrek van een ellips te tekenen** — of je nu een eenvoudige gevulde vorm of een complexe getekende grafiek nodig hebt. Met de bovenstaande stappen kun je snel professionele vectorafbeeldingen toevoegen aan elk afdrukbaar document. Voor een diepere verkenning — zoals het combineren van meerdere vormen, het toepassen van verlopen, of het converteren naar PDF — raadpleeg de officiële **[Aspose.Page Java‑documentatie](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Gerelateerde tutorials

- [Hoe een rechthoek tekenen in Java PostScript met Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Hoe Unicode‑tekst toevoegen in Java PostScript met Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Radiale verloop maken in PostScript met Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
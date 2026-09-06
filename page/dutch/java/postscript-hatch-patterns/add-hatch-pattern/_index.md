---
date: 2026-08-18
description: Leer hoe je een hatch pattern toevoegt aan Java PostScript‑bestanden
  met Aspose.Page Java. Deze step‑by‑step gids toont de volledige code en tips.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Hatch pattern toevoegen in Java PostScript
og_description: Leer hoe je een hatch pattern toevoegt in Java PostScript met Aspose.Page.
  Volg deze step‑by‑step tutorial om snel hatch‑gevulde graphics te maken.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Hoe een hatch pattern toe te voegen in Java PostScript – Aspose.Page guide
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Hoe een hatch pattern toe te voegen in Java PostScript
url: /nl/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een hatch-patroon toe te voegen in Java PostScript

## Introductie
Als je werkt met **Aspose.Page Java** en je afvraagt **hoe je een hatch-patroon** aan je PostScript-uitvoer kunt toevoegen, dan zijn hatch-patronen een snelle en flexibele oplossing. In deze tutorial lopen we **hoe je hatch**-ontwerpen aan een PostScript-document kunt toevoegen, leggen we uit waarom ze nuttig zijn, en geven we je een compleet, kant‑klaar code‑voorbeeld. Aan het einde kun je visueel aantrekkelijke, met hatch gevulde vormen en tekst maken met slechts een paar regels Java.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.Page for Java (de “aspose page java” SDK).  
- **Welk visueel effect voegen we toe?** Hatch-patronen (bijv. diagonale lijnen, kruispatroon).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Hoeveel regels code?** Ongeveer 70 regels, opgesplitst in duidelijke stappen.  
- **Kan ik dezelfde aanpak gebruiken voor PDF's?** Ja—Aspose.Page ondersteunt meerdere uitvoerformaten, waaronder PDF.

## Wat is een hatch-patroon?
Een hatch-patroon is een vector‑gebaseerde vulling bestaande uit herhaalde lijnen of vormen die een textuureffect creëren. Omdat het wiskundig gedefinieerd is, schaalt het patroon zonder kwaliteitsverlies, waardoor het ideaal is voor hoge‑resolutie afdrukken en monochrome uitvoer.

## Waarom hatch-patronen gebruiken met Aspose.Page Java?
Aspose.Page ondersteunt **meer dan 10 uitvoerformaten** (inclusief PostScript, PDF, EPS, SVG en XPS) en kan hatch-vullingen renderen in documenten tot **500 pagina's** zonder het volledige bestand in het geheugen te laden. Dit betekent dat je snelle prestaties, een lage geheugengebruik en consistente visuele resultaten krijgt over alle ondersteunde formaten.

## Hoe hatch-patroon toe te voegen – overzicht
Hatch-patronen zijn vector‑gebaseerde texturen die bij elke resolutie helder renderen en goed werken op monochrome printers. Met Aspose.Page Java kun je deze patronen toepassen op vormen, paden en zelfs tekst zonder low‑level PostScript‑commando's te gebruiken.

## Vereisten
- **Java-ontwikkelomgeving** – JDK 8 of hoger en een IDE naar keuze.  
- **Aspose.Page for Java bibliotheek** – Download de nieuwste JAR van de officiële **Aspose.Page for Java downloadpagina** [**hier**](https://releases.aspose.com/page/java/).  
- Je kunt ook andere Aspose-releases bekijken [**hier**](https://releases.aspose.com/).  
- **Schrijftoegang** tot een map waar het gegenereerde PostScript‑bestand wordt opgeslagen.

## Pakketten importeren
De onderstaande imports omvatten standaard Java AWT‑klassen voor grafische primitieve elementen zoals kleuren, lijnen en geometrische vormen, evenals Aspose.Page‑klassen die het documentmodel, hatch‑stijldefinities en opslaan‑opties bieden die nodig zijn om een PostScript‑bestand te genereren.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Wat is de `Document`-klasse?
De `Document`-klasse is het top‑level object van Aspose.Page dat een enkel PostScript‑bestand in het geheugen vertegenwoordigt. Alle tekenbewerkingen worden via dit object uitgevoerd.

## Hoe de uitvoerstroom in te stellen?
Om de uitvoer te schrijven, maak je een `FileOutputStream` aan die naar het gewenste bestandspad wijst; deze stream behandelt low‑level byte‑schrijven. `PsSaveOptions` configureert hoe het document wordt opgeslagen, inclusief paginagrootte en compressie. Instantieer vervolgens een `Document` met een `PsSaveOptions`‑object dat paginagrootte, compressie en andere PostScript‑specifieke instellingen opgeeft.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Hoe de grafische toestand op te slaan en de oorsprong te verplaatsen?
Het opslaan van de grafische toestand legt de huidige transformatie‑matrix, het clip‑gebied en teken‑attributen vast, zodat je later kunt terugkeren. Na het opslaan roep je `translate(x, y)` aan op het grafische object om de oorsprong te verplaatsen naar een handige locatie voor het tekenen van het raster van hatch‑vierkanten.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Hoe een herbruikbaar vierkant voor elk patroon te maken?
`Rectangle2D` vertegenwoordigt een rechthoekige vorm gedefinieerd door positie en grootte. Door één instantie te maken die overeenkomt met de celafmetingen, kun je deze hergebruiken voor elk hatch‑gevuld vierkant, waardoor objectallocatie wordt verminderd en de tekenslus efficiënt blijft.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Hoe een pen in te stellen voor de omtrek van het patroon‑vierkant?
`BasicStroke` beschrijft de dikte van de omtrek, het streep‑patroon en de eindkappen voor vectorvormen. Het gebruik van een 2‑punt `BasicStroke` biedt een duidelijke rand rond elk hatch‑gevuld vak, waardoor de vulling visueel gescheiden wordt van aangrenzende vierkanten.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Hoe door hatch-patronen te itereren?
`HatchStyle` is een enumeratie die alle vooraf gedefinieerde hatch-patronen opsomt, zoals diagonale, kruis‑ en gestippelde stijlen. Door over `HatchStyle.values()` te itereren kun je elk patroon achtereenvolgens toepassen, de rechthoek vullen met een `HatchBrush` en vervolgens de omtrek tekenen.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Hoe de grafische toestand herstellen na het tekenen?
Het aanroepen van `restore()` op het grafische object zet de transformatie‑matrix en tekeninstellingen terug naar de eerder opgeslagen toestand, waardoor cumulatieve translaties of schalingen geen invloed hebben op volgende tekenbewerkingen. Dit zorgt ervoor dat latere inhoud start vanuit het oorspronkelijke coördinatensysteem en standaard‑attributen gebruikt.  
```java
document.writeGraphicsRestore();
```

## Hoe tekst te vullen met een hatch-patroon?
`TextFragment` vertegenwoordigt een stuk tekst dat onafhankelijk kan worden gepositioneerd en gestyled. Door een `HatchBrush` met een gekozen `HatchStyle` toe te wijzen aan de vulling van het fragment, worden de tekens gerenderd met de hatch‑textuur in plaats van een effen kleur.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Hoe tekst omranden met een andere hatch-stijl?
`HatchBrush` kan ook worden gebruikt voor stroken. Om een omtrek te tekenen, stel je de stroke van het fragment in op een `HatchBrush` met een andere `HatchStyle` (bijv. 70 % hatch) en vergroot je de lijndikte via `setStrokeWidth`. Hierdoor wordt de rand van de tekst weergegeven met zijn eigen hatch‑patroon, terwijl de gevulde binnenkant behouden blijft.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Hoe het document te sluiten en op te slaan?
`document.save()` schrijft het in‑memory document naar de opgegeven uitvoerstroom. Na het voltooien van alle teken‑commando's roep je deze methode aan en sluit je vervolgens de `FileOutputStream` om systeembronnen vrij te geven en ervoor te zorgen dat het bestand correct naar de schijf wordt weggeschreven.  
```java
document.closePage();
document.save();
```

Volg deze stappen, en je krijgt een PostScript‑bestand dat een volledige set hatch‑patronen toont die zowel op vormen als tekst zijn toegepast — allemaal aangedreven door **aspose page java**.

## Veelvoorkomende valkuilen & tips
- **Bestandspad‑fouten** – Zorg ervoor dat `dataDir` eindigt met de juiste scheidingsteken (`/` of `\`).  
- **Niet‑ondersteunde kleuren** – Sommige oudere PostScript‑interpreters kunnen bepaalde kleurenschema's niet verwerken; houd je aan basis‑RGB voor maximale compatibiliteit.  
- **Licentie‑waarschuwingen** – Het uitvoeren van het voorbeeld zonder een geldige licentie zal een watermerk in de uitvoer plaatsen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page Java gebruiken met andere Java‑frameworks?**  
A: Ja, de bibliotheek is framework‑agnostisch en werkt met Spring, Jakarta EE, Android (beperkt) en gewone Java SE.

**Q: Is er een proefversie beschikbaar voor Aspose.Page Java?**  
A: Absoluut. Download een gratis 30‑daagse proefversie [**Aspose proefdownloadpagina**](https://releases.aspose.com/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor ontwikkeling?**  
A: Vraag een tijdelijke licentie aan [**pagina voor tijdelijke licentieaanvraag**](https://purchase.aspose.com/temporary-license/). Het verwijdert evaluatiewatermerken.

**Q: Waar kan ik meer tutorials en community‑ondersteuning vinden?**  
A: Bezoek het officiële forum [**Aspose.Page voor Java forum**](https://forum.aspose.com/c/page/39) voor extra voorbeelden en Q&A.

**Q: Is er uitgebreide documentatie voor alle klassen en methoden?**  
A: Ja, de volledige API‑referentie is beschikbaar [**Aspose.Page Java API‑referentie**](https://reference.aspose.com/page/java/).

**Q: Kan ik hetzelfde hatch-patroon renderen naar PDF in plaats van PostScript?**  
A: Absoluut. Verander de `PsSaveOptions` naar `PdfSaveOptions` (of het equivalent) en de rest van de code blijft ongewijzigd.

**Q: Wat moet ik doen als het gegenereerde bestand leeg is?**  
A: Controleer of de uitvoerstroom naar een schrijfbare directory wijst en dat `document.save()` wordt aangeroepen na alle tekenbewerkingen.

---

**Laatst bijgewerkt:** 2026-08-18  
**Getest met:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Textuurpatroon maken in PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Hoe een verloop toe te voegen: Diagonaal verloop in Java PostScript met Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Hoe PostScript te converteren naar PDF met Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
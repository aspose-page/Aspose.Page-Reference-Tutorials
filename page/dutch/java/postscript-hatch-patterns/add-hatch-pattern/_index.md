---
date: 2025-12-08
description: Leer hoe u hatchpatronen kunt toevoegen aan Java‑PostScript‑documenten
  met Aspose.Page Java. Deze stapsgewijze gids laat u zien hoe u hatchpatroon‑graphics
  efficiënt kunt toevoegen.
language: nl
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Hatchpatroon toevoegen in Java PostScript'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hatch-patroon toevoegen in Java PostScript

## Introductie
Als je werkt met **Aspose.Page Java** en je wilt je PostScript‑output verrijken met getexturede graphics, dan zijn hatch‑patronen een snelle en flexibele oplossing. In deze tutorial lopen we stap voor stap door **hoe je hatch‑ontwerpen** toevoegt aan een PostScript‑document, leggen we uit waarom ze nuttig zijn, en geven we je een compleet, kant‑klaar code‑voorbeeld. Aan het einde kun je visueel aantrekkelijke hatch‑gevulde vormen en tekst maken met slechts een paar regels Java.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.Page voor Java (de “aspose page java” SDK).  
- **Welk visueel effect voegen we toe?** Hatch‑patronen (bijv. diagonale lijnen, kruis‑hatch).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Hoeveel regels code?** Ongeveer 70 regels, verdeeld over duidelijke stappen.  
- **Kan ik dezelfde aanpak gebruiken voor PDF's?** Ja—Aspose.Page ondersteunt meerdere uitvoerformaten, inclusief PDF.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

- **Java-ontwikkelomgeving** – JDK 8 of hoger en een IDE naar keuze.  
- **Aspose.Page voor Java bibliotheek** – Download de nieuwste JAR van de officiële site [here](https://releases.aspose.com/page/java/).  
- **Schrijftoegang** tot een map waarin het gegenereerde PostScript‑bestand wordt opgeslagen.

## Pakketten importeren
Eerst importeer je de benodigde klassen in je project. Deze imports geven je toegang tot teken‑primitieven, kleurafhandeling en de Aspose.Page API.

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

## Stap 1: Initialiseer parameters
Maak de output‑stream, configureer de paginagrootte (A4) en definieer een paar lay‑outvariabelen die later worden hergebruikt bij het tekenen van elk hatch‑gevuld vierkant.

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

## Stap 2: Grafische status opslaan en vertalen
Het opslaan van de grafische status stelt ons in staat later terug te keren naar het oorspronkelijke coördinatensysteem, terwijl `translate` de oorsprong verplaatst naar een handig startpunt.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Stap 3: Vierkant maken voor elk patroon
Definieer een herbruikbare rechthoek die elk hatch‑gevuld vakje zal vertegenwoordigen.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Stap 4: Pen instellen voor patroonvierkantcontour
Een `BasicStroke` van 2 points geeft een scherpe omtrek rond elk vierkant.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Stap 5: Door Hatch-patronen itereren
Loop door elke waarde in de `HatchStyle`‑enum, vul elk vierkant met de overeenkomstige textuur en teken vervolgens de omtrek. Dit is de kern van **het toevoegen van hatch‑patronen**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Stap 6: Grafische status herstellen
Keer terug naar het oorspronkelijke coördinatensysteem nadat we het raster van vierkanten hebben getekend.

```java
document.writeGraphicsRestore();
```

## Stap 7: Tekst vullen met Hatch-patroon
Hier demonstreren we hoe je tekst schildert met een hatch‑textuur. Het voorbeeld vult het woord “ABC” met een diagonaal‑kruispatroon.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Stap 8: Tekst omlijnen met Hatch-patroon
Nu omlijnen we dezelfde tekst, maar dit keer met een 70 % hatch‑stijl en een dikkere pen.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Stap 9: Document sluiten en opslaan
Rond de pagina af, schrijf het bestand naar schijf en maak bronnen vrij.

```java
document.closePage();
document.save();
```

Volg deze stappen, en je hebt een PostScript‑bestand dat een volledige set hatch‑patronen toont, toegepast op zowel vormen als tekst—alles aangedreven door **aspose page java**.

## Waarom Hatch-patronen gebruiken met Aspose.Page Java?
- **Visueel onderscheid** – Hatch‑vullingen werken zelfs wanneer printers beperkt zijn tot monochrome output.  
- **Prestaties** – Texturen worden on‑the‑fly gegenereerd, zodat je grote afbeeldingsbestanden vermijdt.  
- **Cross‑formatondersteuning** – Dezelfde code kan PDF, EPS of SVG targeten met minimale aanpassingen.

## Veelvoorkomende valkuilen & tips
- **Bestandspad‑fouten** – Zorg ervoor dat `dataDir` eindigt met het juiste scheidingsteken (`/` of `\`).  
- **Niet‑ondersteunde kleuren** – Sommige oudere PostScript‑interpreters kunnen bepaalde kleurenschema's niet verwerken; houd je aan basis‑RGB voor maximale compatibiliteit.  
- **Licentie‑waarschuwingen** – Het uitvoeren van het voorbeeld zonder geldige licentie voegt een watermerk toe aan de output.

## Conclusie
Het integreren van hatch‑patronen kan de leesbaarheid en esthetiek van technische tekeningen, kaarten of elke door Java gegenereerde grafiek aanzienlijk verbeteren. Met **Aspose.Page Java** krijg je een beknopte API die de low‑level PostScript‑commando's abstraheert, zodat je je kunt concentreren op design in plaats van bestandsformaat‑details.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page Java gebruiken met andere Java‑frameworks?**  
A: Ja, de bibliotheek is framework‑agnostisch en werkt met Spring, Jakarta EE, Android (beperkt) en gewone Java SE.

**Q: Is er een proefversie beschikbaar voor Aspose.Page Java?**  
A: Absoluut. Download een gratis 30‑daagse proefversie [here](https://releases.aspose.com/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor ontwikkeling?**  
A: Vraag een tijdelijke licentie [here](https://purchase.aspose.com/temporary-license/) aan. Deze verwijdert evaluatiewatermerken.

**Q: Waar vind ik meer tutorials en community‑ondersteuning?**  
A: Bezoek het officiële forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) voor extra voorbeelden en Q&A.

**Q: Is er uitgebreide documentatie voor alle klassen en methoden?**  
A: Ja, de volledige API‑referentie is beschikbaar [here](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose
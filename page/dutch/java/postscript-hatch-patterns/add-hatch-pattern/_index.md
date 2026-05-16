---
date: 2026-02-15
description: Leer hoe je een arceringspatroon toevoegt aan Java‑PostScript‑bestanden
  met Aspose.Page Java. Deze stapsgewijze gids toont de volledige code en tips.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Hoe een hatchpatroon toe te voegen in Java PostScript met Aspose.Page
url: /nl/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Hatch-patroon toe te voegen in Java PostScript

## Introduction
Als je werkt met **Aspose.Page Java** en je afvraagt **hoe je een hatch pattern** aan je PostScript‑output kunt toevoegen, dan zijn hatch‑patronen een snelle en flexibele oplossing. In deze tutorial lopen we stap voor stap door **hoe je hatch**‑ontwerpen aan een PostScript‑document kunt toevoegen, leggen we uit waarom ze nuttig zijn, en geven we je een compleet, kant‑en‑klaar code‑voorbeeld. Aan het einde kun je visueel aantrekkelijke, met hatch gevulde vormen en tekst maken met slechts een paar regels Java.

## Quick Answers
- **Welke bibliotheek heb ik nodig?** Aspose.Page for Java (de “aspose page java” SDK).  
- **Welk visueel effect voegen we toe?** Hatch‑patronen (bijv. diagonale lijnen, kruispatroon).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Hoeveel regels code?** Ongeveer 70 regels, verdeeld over duidelijke stappen.  
- **Kan ik dezelfde aanpak gebruiken voor PDF’s?** Ja—Aspose.Page ondersteunt meerdere outputformaten, inclusief PDF.

## How to Add Hatch Pattern – Overview
Hatch‑patronen zijn vector‑gebaseerde texturen die op elke resolutie scherp renderen en goed werken op monochrome printers. Met Aspose.Page Java kun je deze patronen toepassen op vormen, paden en zelfs tekst zonder low‑level PostScript‑commando’s te gebruiken.

## Prerequisites
Voordat je begint, zorg dat je het volgende hebt:

- **Java Development Environment** – JDK 8 of hoger en een IDE naar keuze.  
- **Aspose.Page for Java library** – Download de nieuwste JAR van de officiële site [here](https://releases.aspose.com/page/java/).  
- **Write access** tot een map waar het gegenereerde PostScript‑bestand wordt opgeslagen.

## Import Packages
Eerst haal je de benodigde klassen in je project. Deze imports geven je toegang tot teken‑primitieven, kleurafhandeling en de Aspose.Page API.

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

## Step 1: Set Up Initial Parameters
Maak de output‑stream aan, configureer de paginagrootte (A4) en definieer een paar lay‑outvariabelen die later hergebruikt worden bij het tekenen van elk hatch‑gevuld vierkant.

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

## Step 2: Save Graphics State and Translate
Het opslaan van de grafische status stelt ons in staat later terug te keren naar het oorspronkelijke coördinatensysteem, terwijl `translate` de oorsprong naar een handig startpunt verplaatst.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
Definieer een herbruikbare rechthoek die elk hatch‑gevuld vakje zal vertegenwoordigen.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
Een `BasicStroke` van 2 points geeft een scherpe omtrek rond elk vierkant.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
Loop door elke waarde in de `HatchStyle`‑enum, vul elk vierkant met de bijbehorende textuur en teken vervolgens de omtrek. Dit is de kern van de functionaliteit voor **het toevoegen van een hatch pattern**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
Herstel het oorspronkelijke coördinatensysteem nadat we het raster van vierkanten hebben getekend.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
Hier laten we zien hoe je tekst kunt schilderen met een hatch‑textuur. Het voorbeeld vult het woord “ABC” met een diagonaal‑kruispatroon.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
Nu omlijnen we dezelfde tekst, maar dit keer met een 70 % hatch‑stijl en een dikkere lijn.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
Rond de pagina af, schrijf het bestand naar schijf en maak de resources vrij.

```java
document.closePage();
document.save();
```

Volg deze stappen, en je hebt een PostScript‑bestand dat een volledige set hatch‑patronen toont die zowel op vormen als op tekst zijn toegepast — allemaal aangedreven door **aspose page java**.

## Why Use Hatch Patterns with Aspose.Page Java?
- **Visual distinction** – Hatch‑vullingen werken zelfs wanneer printers beperkt zijn tot monochrome output.  
- **Performance** – Texturen worden on‑the‑fly gegenereerd, zodat je grote afbeeldingsbestanden vermijdt.  
- **Cross‑format support** – Dezelfde code kan PDF, EPS of SVG targeten met minimale aanpassingen.

## Common Pitfalls & Tips
- **File path errors** – Zorg ervoor dat `dataDir` eindigt met het juiste scheidingsteken (`/` of `\`).  
- **Unsupported colors** – Sommige oudere PostScript‑interpreters kunnen bepaalde kleurenschema's niet verwerken; houd je aan basis‑RGB voor maximale compatibiliteit.  
- **License warnings** – Het uitvoeren van het voorbeeld zonder een geldige licentie zal een watermerk in de output plaatsen.

## Conclusion
Het incorporeren van hatch‑patronen kan de leesbaarheid en esthetiek van technische tekeningen, kaarten of elke door Java gegenereerde grafiek dramatisch verbeteren. Met **Aspose.Page Java** krijg je een beknopte API die de low‑level PostScript‑commando’s abstraheert, zodat je je kunt concentreren op ontwerp in plaats van bestandsformaat‑details. Nu weet je **hoe je een hatch pattern** aan je PostScript‑documenten kunt toevoegen—experimenteer met verschillende `HatchStyle`‑waarden om precies de look te creëren die je nodig hebt.

## Frequently Asked Questions

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

**Q: Kan ik hetzelfde hatch‑patroon renderen naar PDF in plaats van PostScript?**  
A: Absoluut. Verander de `PsSaveOptions` naar `PdfSaveOptions` (of het equivalent) en de rest van de code blijft ongewijzigd.

**Q: Wat moet ik doen als het gegenereerde bestand leeg is?**  
A: Controleer of de output‑stream naar een schrijfbare directory wijst en of `document.save()` wordt aangeroepen na alle teken‑operaties.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
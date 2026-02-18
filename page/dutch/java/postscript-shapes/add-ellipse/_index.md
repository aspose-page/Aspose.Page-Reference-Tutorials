---
date: 2026-02-18
description: Leer hoe u de verfkleur instelt en een PostScript-ellips maakt in Java
  met Aspose.Page. Deze gids laat zien hoe u een ellips in Java vult, de omtrek van
  de ellips tekent en de lijndikte instelt.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Stel de verfkleur in om een PostScript-ellips te tekenen in Java
url: /nl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel verf kleur in om PostScript-ellips te tekenen in Java

## Introductie
Als je **verf kleur moet instellen** tijdens het tekenen van vectorafbeeldingen, geeft de Aspose.Page for Java bibliotheek je volledige controle over elke lijn en vulling. In deze tutorial ontdek je hoe je **verf kleur instelt**, **ellipse vult in Java**, en **de omtrek van een ellipse tekent** met een eenvoudige, stap‑voor‑stap aanpak. Aan het einde kun je hoogwaardige PostScript‑ellipsen toevoegen aan facturen, rapporten of elk afdrukbaar document.

## Snelle antwoorden
- **Welke bibliotheek is het beste voor het tekenen van PostScript‑graphics in Java?** Aspose.Page for Java.  
- **Kan ik een ellipse vullen met een effen kleur?** Ja – gebruik `document.setPaint(Color.YOUR_COLOR)` vóór `fill`.  
- **Hoe teken ik alleen de omtrek van een ellipse?** Stel de verf en de lijn in, en roep vervolgens `document.draw(...)` aan.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist; een tijdelijke licentie is beschikbaar voor testen.  
- **Welke Java‑versie wordt ondersteund?** Elke Java 8+ runtime werkt met de huidige Aspose.Page‑release.

## Wat is een PostScript‑ellipse?
Een PostScript‑ellipse is een vectorvorm die wordt gedefinieerd door een begrenzende rechthoek. In tegenstelling tot rasterafbeeldingen schaalt hij zonder kwaliteitsverlies, waardoor hij ideaal is voor hoge‑resolutie afdrukken en PDF‑conversie.

## Waarom Aspose.Page gebruiken om een PostScript‑ellipse te maken?
- **Volledige controle** over tekenprimitieven (lijnen, curven, ellipsen).  
- **Cross‑platform** – werkt op Windows, Linux en macOS.  
- **Geen externe afhankelijkheden** – pure Java‑API, geen native code.  
- **Eenvoudige integratie** met bestaande Java‑applicaties en build‑tools.

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. Een functionele Java‑ontwikkelomgeving (JDK 8 of hoger).  
2. De Aspose.Page for Java bibliotheek aan je project toegevoegd. Je kunt deze **[hier](https://releases.aspose.com/page/java/)** downloaden.  

## Importeer pakketten
Importeer in je Java‑bronbestand de klassen die nodig zijn voor het tekenen en opslaan van PostScript‑inhoud.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hoe verf kleur instellen voor een ellipse
Het instellen van de verf kleur is de eerste stap vóór elke vullings‑ of lijnoperatie. De `setPaint`‑methode bepaalt de kleur die wordt gebruikt voor de volgende tekenopdracht.

### Stap 1: Het PostScript‑document opzetten
Maak een output‑stream, configureer de paginagrootte en instantieer een `PsDocument`.

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

### Stap 2: Hoe een ellipse vullen – gebruik set paint color
Om een **ellipse te vullen**, moet je eerst `setPaint` aanroepen met de gewenste vulkleur, en vervolgens `fill` aanroepen met een `Ellipse2D`‑instantie.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Stap 3: De omtrek van de ellipse tekenen en de lijndikte instellen
Na het vullen kun je de verf naar een andere kleur wijzigen, een `BasicStroke` definiëren om de lijndikte te regelen, en de omtrek van de ellipse tekenen.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Stap 4: Het document sluiten en opslaan
Rond de pagina af en schrijf het PostScript‑bestand naar schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Je hebt nu een PostScript‑bestand dat twee ellipsen bevat — één gevuld met oranje en een andere met een rode omtrek. Voel je vrij om te experimenteren met verschillende coördinaten, afmetingen en kleuren om aan je ontwerpbehoeften te voldoen.

## Veelvoorkomende valkuilen en probleemoplossing
- **Onjuist bestandspad** – Zorg ervoor dat `dataDir` eindigt met een scheidingsteken (`/` of `\\`) dat geschikt is voor je OS.  
- **Ontbrekende licentie** – Zonder een geldige licentie draait de bibliotheek in evaluatiemodus en kan watermerken toevoegen.  
- **Kleur niet toegepast** – Vergeet niet `document.setPaint(...)` *vóór* elke `fill`‑ of `draw`‑aanroep te zetten; de verfinstelling blijft niet automatisch behouden tussen afzonderlijke bewerkingen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos te integreren met andere Java‑bibliotheken.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java krijgen?**  
A: Verkrijg een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)** voor testdoeleinden.

**Q: Is Aspose.Page geschikt voor commerciële projecten?**  
A: Absoluut! Bezoek **[hier](https://purchase.aspose.com/buy)** om licentie‑opties voor commercieel gebruik te bekijken.

**Q: Waar kan ik hulp zoeken of vragen over Aspose.Page bespreken?**  
A: Word lid van de community op het **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** voor discussies en ondersteuning.

**Q: Zijn er gratis bronnen om meer te leren over Aspose.Page for Java?**  
A: Maak gebruik van de **[gratis proefversie](https://releases.aspose.com/)** en bekijk voorbeelden in de documentatie.

## Conclusie
Aspose.Page for Java maakt het eenvoudig om **verf kleur in te stellen**, **ellipse te vullen**, en **de omtrek van een ellipse te tekenen** — of je nu een eenvoudige gevulde vorm of een complexe getekende grafiek nodig hebt. Met de bovenstaande stappen kun je snel professionele vectorafbeeldingen toevoegen aan elk afdrukbaar document. Voor een diepere verkenning — zoals het combineren van meerdere vormen, het toepassen van verlopen, of het converteren naar PDF — raadpleeg de officiële **[documentatie](https://reference.aspose.com/page/java/)**.

---

**Laatst bijgewerkt:** 2026-02-18  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
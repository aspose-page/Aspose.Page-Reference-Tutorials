---
date: 2025-12-11
description: Leer hoe u een PostScript‑ellips maakt in Java met Aspose.Page. Deze
  stapsgewijze handleiding laat u zien hoe u een ellips met kleur vult en een ellips
  tekent met Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Hoe maak je een PostScript-ellips in Java met Aspose.Page
url: /nl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een PostScript-ellips in Java met Aspose.Page

## Introductie
Het programmatisch maken van een **PostScript-ellips** geeft je fijnmazige controle over vectorafbeeldingen in rapporten, facturen of elk afdrukbaar document. In deze tutorial leer je hoe je **PostScript-ellips**-vormen maakt met de Aspose.Page for Java-bibliotheek, een ellips vult met kleur, en een ellipscontour tekent. Aan het einde kun je aangepaste grafische elementen direct in je PostScript-uitvoer insluiten.

## Snelle antwoorden
- **Welke bibliotheek is het beste voor het tekenen van PostScript‑graphics in Java?** Aspose.Page for Java.  
- **Kan ik een ellips vullen met een effen kleur?** Ja – gebruik `document.setPaint(Color.YOUR_COLOR)` vóór `fill`.  
- **Hoe teken ik alleen de omtrek van een ellips?** Stel de paint en stroke in, en roep vervolgens `document.draw(...)` aan.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist; een tijdelijke licentie is beschikbaar voor testen.  
- **Welke Java‑versie wordt ondersteund?** Elke Java 8+ runtime werkt met de huidige Aspose.Page-release.

## Wat is een PostScript-ellips?
Een PostScript-ellips is een vectorvorm die wordt gedefinieerd door een omvattende rechthoek. In tegenstelling tot rasterafbeeldingen schaalt hij zonder kwaliteitsverlies, waardoor hij ideaal is voor hoge‑resolutie‑afdrukken en PDF‑conversie.

## Waarom Aspose.Page gebruiken om een PostScript-ellips te maken?
- **Volledige controle** over tekenprimitieven (lijnen, curven, ellipsen).  
- **Cross‑platform** – werkt op Windows, Linux en macOS.  
- **Geen externe afhankelijkheden** – pure Java‑API, geen native code.  
- **Eenvoudige integratie** met bestaande Java‑applicaties en build‑tools.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. Een functionele Java‑ontwikkelomgeving (JDK 8 of later).  
2. De Aspose.Page for Java‑bibliotheek toegevoegd aan je project. Je kunt deze downloaden **[hier](https://releases.aspose.com/page/java/)**.  

## Importeer pakketten
In je Java‑bronbestand importeer je de klassen die nodig zijn voor het tekenen en opslaan van PostScript‑inhoud.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stapsgewijze handleiding

### Stap 1: Het PostScript‑document instellen
Maak een output‑stream, configureer de paginagrootte en instantiate een `PsDocument`.

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

### Stap 2: Ellips vullen met kleur
Stel de paint in op de gewenste vulkleur en roep `fill` aan met een `Ellipse2D`‑instantie.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Stap 3: Ellips omranden met stroke
Schakel de paint over naar de streepkleur, definieer een `BasicStroke` voor de lijndikte, en teken de ellipscontour.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Stap 4: Document sluiten en opslaan
Rond de pagina af en schrijf het PostScript‑bestand naar de schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Je hebt nu een PostScript‑bestand dat twee ellipsen bevat – één gevuld met oranje en een andere omrand met rood. Voel je vrij om te experimenteren met verschillende coördinaten, groottes en kleuren om aan je ontwerpbehoeften te voldoen.

## Veelvoorkomende valkuilen en probleemoplossing
- **Onjuist bestandspad** – Zorg ervoor dat `dataDir` eindigt met een scheidingsteken (`/` of `\\`) dat geschikt is voor je OS.  
- **Ontbrekende licentie** – Zonder een geldige licentie draait de bibliotheek in evaluatiemodus en kan watermerken toevoegen.  
- **Kleur niet toegepast** – Vergeet niet `document.setPaint(...)` *voor* elke `fill`‑ of `draw`‑aanroep in te stellen; de paint‑instelling blijft niet automatisch behouden tussen afzonderlijke bewerkingen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos te integreren met andere Java‑bibliotheken.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java krijgen?**  
A: Verkrijg een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)** voor testdoeleinden.

**Q: Is Aspose.Page geschikt voor commerciële projecten?**  
A: Absoluut! Bezoek **[hier](https://purchase.aspose.com/buy)** om licentie‑opties voor commercieel gebruik te verkennen.

**Q: Waar kan ik hulp zoeken of discussiëren over Aspose.Page‑gerelateerde vragen?**  
A: Word lid van de community op het **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** voor discussies en ondersteuning.

**Q: Zijn er gratis bronnen om meer te leren over Aspose.Page for Java?**  
A: Maak gebruik van de **[free trial](https://releases.aspose.com/)** en verken voorbeelden in de documentatie.

## Conclusie
Aspose.Page for Java maakt het eenvoudig om **PostScript-ellips**‑grafieken te maken, of je nu een eenvoudige gevulde vorm of een complexe omrande contour nodig hebt. Met de bovenstaande stappen kun je snel professionele vectorafbeeldingen toevoegen aan elk afdrukbaar document. Voor diepere verkenning – zoals het combineren van meerdere vormen, het toepassen van verlopen, of het converteren naar PDF – raadpleeg de officiële **[documentatie](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-11  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose
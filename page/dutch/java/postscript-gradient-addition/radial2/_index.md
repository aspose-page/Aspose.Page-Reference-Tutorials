---
date: 2026-09-09
description: Leer hoe je een gradient maakt in Java PostScript en een gradient toevoegt
  aan een shape met Aspose.Page. Volg deze step‑by‑step guide met code en tips.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient met Aspose.Page
og_description: Leer hoe je een gradient maakt in Java PostScript en een gradient
  toevoegt aan een shape met Aspose.Page. Volg deze step‑by‑step guide met code en
  tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Hoe maak je een gradient in Java PostScript met radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Hoe maak je een gradient in Java PostScript met radial fill
url: /nl/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een verloop in Java PostScript met radiale vulling

## Inleiding
In deze tutorial leer je **hoe je een verloop** grafieken te maken in een PostScript-document met Java en Aspose.Page. We lopen elke stap door — van projectopzet tot het renderen van een cirkel gevuld met een vloeiend radiaal verloop — zodat je **verloop aan vorm** objecten direct kunt toevoegen en de visuele kwaliteit van je Java-toepassingen kunt verhogen.

## Snelle antwoorden
- **Wat maakt deze tutorial?** Een PostScript‑bestand (`.ps`) met een cirkel gevuld met een radiaal verloop.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (latest version).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een werkend voorbeeld.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik; een gratis proefversie werkt voor ontwikkeling.  
- **Kan ik de code hergebruiken voor PDF of SVG?** Ja—Aspose.Page ondersteunt meerdere uitvoerformaten met minimale wijzigingen.  

## Hoe vorm te vullen met verloop in PostScript
Je kunt een vorm vullen met een radiaal verloop in PostScript door een `PsDocument` te maken, een `RadialGradientPaint` te definiëren, deze toe te passen op de doelvorm, en uiteindelijk het document op te slaan. Deze beknopte workflow stelt je in staat professionele vectorafbeeldingen te produceren zonder rasterafbeeldingen, en dezelfde code kan worden hergebruikt voor PDF- of SVG-uitvoer. Het proces is eenvoudig en werkt consistent over alle ondersteunde formaten.

## Wat is een radiaal verloop?
Een radiaal verloop verplaatst kleuren van een centraal punt naar buiten, waardoor een vloeiende, ronde overgang ontstaat. Het is ideaal voor highlights, knopachtergronden, of elke visuele die een natuurlijk “glow” effect nodig heeft. Door de kleurstops en radius te variëren, kun je verlichting, diepte en materiaaleigenschappen simuleren in pure vectorvorm.

## Waarom Aspose.Page gebruiken voor radiale verlopen?
Aspose.Page stelt je in staat apparaat‑onafhankelijke vectorafbeeldingen te genereren met één Java‑API. Het ondersteunt meer dan 50 invoer‑ en uitvoerformaten — waaronder PostScript, PDF en SVG — terwijl het kleuraccuratesse en anti‑aliasing behoudt voor hoge‑resolutie‑output. De bibliotheek biedt ook gemakkelijk te gebruiken verloopklassen, waardoor complexe visuele effecten eenvoudig te implementeren zijn.

## Voorvereisten
Before we dive in, make sure you have:

- Basiskennis van Java-programmeren.  
- JDK 8 of nieuwer geïnstalleerd op je machine.  
- Aspose.Page for Java bibliotheek (download van de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Importeer pakketten
Eerst importeer je de klassen die we nodig hebben. Deze omvatten standaard AWT‑grafiektype en de Aspose.Page‑API.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stap 1: map voor document instellen
Definieer de map waar het gegenereerde PostScript‑bestand wordt opgeslagen. Vervang de placeholder door een daadwerkelijk pad op je systeem.

```java
String dataDir = "Your Document Directory";
```

## Stap 2: uitvoerstroom maken
FileOutputStream schrijft ruwe bytes naar een bestand, waardoor binaire data kan worden opgeslagen. Het openen van een stream gericht op een `.ps`‑bestand laat Aspose.Page de gegenereerde PostScript‑data rechtstreeks naar de schijf streamen.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Stap 3: opslaanopties maken
PsSaveOptions configureert hoe een PostScript‑bestand wordt opgeslagen, inclusief paginagrootte en compressie. Je kunt deze instellingen aanpassen, maar de standaardwaarden zijn geschikt voor dit voorbeeld.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Stap 4: ps‑document maken
PsDocument vertegenwoordigt een PostScript‑document in het geheugen en biedt methoden om pagina's en grafieken toe te voegen.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 5: een cirkel maken
`Ellipse2D.Float` beschrijft een ellipsvorm; wanneer breedte = hoogte wordt het een perfecte cirkel. Dit object dient als canvas voor onze verloopvulling.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Hoe een cirkel te tekenen met verloop
Om een cirkel te tekenen met een radiaal verloop, laad je een `RadialGradientPaint` in de grafische context en vul je vervolgens de eerder gedefinieerde ellips. Deze enkele bewerking schildert de vorm met een vloeiende kleurverandering van het centrum naar buiten, waardoor een visueel aantrekkelijk effect ontstaat.

## Stap 6: verloopkleuren definiëren
Bereid twee arrays voor: één voor de kleuren die in het verloop verschijnen en een andere voor de overeenkomstige fractionele posities (0 = centrum, 1 = rand).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Stap 7: AffineTransform maken
AffineTransform is een matrix die grafische objecten kan vertalen, roteren, schalen of scheefmaken. Hier schaalt en vertaalt het het verloop zodat het precies binnen de cirkel past.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Stap 8: radiale verloopverf maken
RadialGradientPaint maakt een radiaal kleurverloop op basis van een centraal punt, radius en kleurstops.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Stap 9: verf instellen en cirkel vullen
Pas de verloopverf toe op het document en vul de eerder gedefinieerde cirkel. Dit is de kern van ons **radial gradient example** en toont hoe je **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Stap 10: pagina sluiten en document opslaan
Rond de pagina af, schrijf de inhoud naar de schijf en sluit de stream. Je PostScript‑bestand is nu klaar om te bekijken met elke PS‑viewer.

```java
document.closePage();
document.save();
```

Gefeliciteerd! Je hebt met succes een radiaal verloop voorbeeld gemaakt in Java PostScript met behulp van Aspose.Page. Je hebt nu een herbruikbaar patroon voor **fill shape with gradient** dat kan worden aangepast aan andere vormen en uitvoerformaten.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **FileNotFoundException** bij het openen van de uitvoerstroom | Controleer of `dataDir` naar een bestaande map wijst en dat je schrijfrechten hebt. |
| Verloop ziet er vlak uit of ontbreekt | Zorg ervoor dat de `fractions`‑array overeenkomt met de lengte van de `colors`‑array en dat de `AffineTransform` correct schaalt. |
| Kleuren lijken omgekeerd | Wissel de volgorde van kleuren in de `colors`‑array of pas de coördinaten van het `focus`‑punt aan. |

## Veelgestelde vragen

**Q: Waar kan ik de documentatie voor Aspose.Page for Java vinden?**  
A: De volledige API‑referentie is beschikbaar in de [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik Aspose.Page voor Java downloaden?**  
A: Download de nieuwste JAR van de [releases page](https://releases.aspose.com/page/java/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja—download een proefversie van de [Aspose free trial download page](https://releases.aspose.com/).

**Q: Kan ik een tijdelijke licentie voor testen verkrijgen?**  
A: Absoluut, vraag er een aan via de [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik community‑ondersteuning krijgen?**  
A: Doe mee aan de discussie op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusie
In deze gids hebben we een volledig **radial gradient example** gebouwd voor een PostScript‑document met Aspose.Page voor Java. Door de stappen te volgen heb je nu een herbruikbaar patroon voor **fill shape with gradient**, dat je kunt aanpassen aan PDF, SVG of elk ander formaat dat door Aspose.Page wordt ondersteund. Experimenteer met verschillende kleuren, radii en vormen om je Java‑grafiekprojecten te verrijken.

---

**Laatst bijgewerkt:** 2026-09-09  
**Getest met:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Create Texture Pattern in PostScript with Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
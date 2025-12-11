---
date: 2025-12-08
description: Leer hoe je een radiale gradient‑voorbeeld maakt in Java PostScript met
  Aspose.Page. Stapsgewijze gids met volledige code en foutopsporing.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Voorbeeld van radiale gradiënt: Java PostScript met Aspose.Page'
url: /nl/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radiale gradient voorbeeld: Java PostScript met Aspose.Page

## Inleiding
In deze tutorial bouw je een **radial gradient example** voor een PostScript‑document met Aspose.Page voor Java. We lopen elke stap door—van het opzetten van het project tot het renderen van een cirkel gevuld met een vloeiende radiale gradient—zodat je direct opvallende graphics aan je Java‑applicaties kunt toevoegen.

## Snelle antwoorden
- **Wat maakt deze tutorial?** Een PostScript‑bestand (`.ps`) met een cirkel gevuld met een radiale gradient.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (latest version).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een werkend voorbeeld.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik; een gratis proefversie werkt voor ontwikkeling.  
- **Kan ik de code hergebruiken voor PDF of SVG?** Ja—Aspose.Page ondersteunt meerdere uitvoerformaten met minimale wijzigingen.

## Wat is een radiale gradient?
Een radiale gradient laat kleuren van een centraal punt naar buiten overgaan, waardoor een vloeiende, ronde menging ontstaat. Het is ideaal voor highlights, knopachtergronden, of elke visuele die een natuurlijk “glow”‑effect nodig heeft.

## Waarom Aspose.Page gebruiken voor radiale gradients?
- **Apparaatonafhankelijke rendering** – werkt hetzelfde op PostScript, PDF, SVG en meer.  
- **Volledige Java‑integratie** – geen native code, alleen gewone Java‑API’s.  
- **Uitvoer van hoge kwaliteit** – ondersteunt anti‑aliasing en kleur‑ruimtekontrole.

## Vereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- JDK 8 of nieuwer geïnstalleerd op je machine.  
- Aspose.Page for Java bibliotheek (download van de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Importeer pakketten
Importeer eerst de klassen die we nodig hebben. Deze omvatten standaard AWT‑grafiektype en de Aspose.Page‑API.

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

## Stap 1: Documentmap instellen
Definieer de map waarin het gegenereerde PostScript‑bestand wordt opgeslagen. Vervang de placeholder door een echt pad op jouw systeem.

```java
String dataDir = "Your Document Directory";
```

## Stap 2: Output‑stream maken
Open een `FileOutputStream` die naar het doel‑`.ps`‑bestand wijst. Deze stream levert de binaire data die door Aspose.Page wordt gegenereerd.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Stap 3: Opslagopties maken
Instantieer `PsSaveOptions`. Je kunt paginagrootte, compressie, enz. aanpassen, maar de standaardinstellingen zijn prima voor dit voorbeeld.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Stap 4: PS‑document maken
Maak het `PsDocument`‑object aan, waarbij je de output‑stream en opslagopties doorgeeft. De `false`‑vlag vertelt Aspose.Page om geen pagina automatisch te openen (we doen het handmatig).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 5: Een cirkel maken
We tekenen een cirkel met `Ellipse2D.Float`. De parameters zijn `(x, y, width, height)`. Door breedte = hoogte in te stellen ontstaat een perfecte cirkel.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Stap 6: Gradientkleuren definiëren
Bereid twee arrays voor: één voor de kleuren die in de gradient verschijnen en een andere voor de overeenkomstige fractionele posities (0 = centrum, 1 = rand).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Stap 7: AffineTransform maken
De `AffineTransform` schaalt en verschuift de gradient zodat deze in onze cirkel past. De matrix `(scaleX, 0, 0, scaleY, translateX, translateY)` doet het werk.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Stap 8: Radial Gradient Paint maken
Nu bouwen we het `RadialGradientPaint`‑object. Het neemt het middelpunt, de radius, het focuspunt, de kleurfractionen, de kleurenarray, de cyclismethode, de kleurruimte en de transform die we zojuist hebben gedefinieerd.

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

## Stap 9: Paint instellen en cirkel vullen
Pas de gradient‑paint toe op het document en vul de eerder gedefinieerde cirkel. Dit is de kern van ons **radial gradient example**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Stap 10: Pagina sluiten en document opslaan
Rond de pagina af, schrijf de inhoud naar schijf en sluit de stream. Je PostScript‑bestand is nu klaar om te bekijken met elke PS‑viewer.

```java
document.closePage();
document.save();
```

Gefeliciteerd! Je hebt met succes een radial gradient example gemaakt in Java PostScript met Aspose.Page.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **FileNotFoundException** bij het openen van de output‑stream | Controleer of `dataDir` naar een bestaande map wijst en dat je schrijfrechten hebt. |
| Gradient ziet er vlak uit of ontbreekt | Zorg ervoor dat de `fractions`‑array overeenkomt met de lengte van de `colors`‑array en dat de `AffineTransform` correct schaalt. |
| Kleuren lijken omgekeerd | Verwissel de volgorde van kleuren in de `colors`‑array of pas de coördinaten van het `focus`‑punt aan. |

## Veelgestelde vragen

**V: Waar kan ik de documentatie voor Aspose.Page voor Java vinden?**  
A: De volledige API‑referentie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**V: Hoe kan ik Aspose.Page voor Java downloaden?**  
A: Download de nieuwste JAR van de [releases page](https://releases.aspose.com/page/java/).

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja—download een proefversie [hier](https://releases.aspose.com/).

**V: Kan ik een tijdelijke licentie voor testen verkrijgen?**  
A: Zeker, vraag er een aan via de [temporary license page](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik community‑ondersteuning krijgen?**  
A: Doe mee aan de discussie op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusie
In deze gids hebben we een volledige **radial gradient example** gebouwd voor een PostScript‑document met Aspose.Page voor Java. Door de stappen te volgen heb je nu een herbruikbaar patroon voor het maken van geavanceerde gradients, die je kunt aanpassen voor PDF, SVG of andere ondersteunde formaten. Experimenteer met verschillende kleuren, radiussen en vormen om je Java‑grafiekprojecten te verrijken.

---

**Laatst bijgewerkt:** 2025-12-08  
**Getest met:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
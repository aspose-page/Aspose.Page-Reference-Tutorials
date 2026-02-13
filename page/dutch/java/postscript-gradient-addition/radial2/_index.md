---
date: 2026-02-13
description: Leer hoe je een vorm vult met een verloop en een cirkel tekent met een
  verloop in Java PostScript met behulp van Aspose.Page. Stapsgewijze gids met code
  en tips.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Vorm vullen met kleurverloop: Java PostScript radiaal voorbeeld'
url: /nl/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vorm vullen met gradient: Java PostScript Radiale Voorbeeld

## Introductie
In deze tutorial leer je hoe je **vorm kunt vullen met gradient** door een radiale gradient‑voorbeeld te bouwen voor een PostScript‑document met Aspose.Page voor Java. We lopen elke stap door—van het opzetten van het project tot het renderen van een cirkel gevuld met een vloeiende radiale gradient—zodat je direct opvallende grafische elementen aan je Java‑applicaties kunt toevoegen.

## Snelle antwoorden
- **Wat maakt deze tutorial?** Een PostScript‑bestand (`.ps`) met een cirkel gevuld met een radiale gradient.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (latest version).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een werkend voorbeeld.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik; een gratis proefversie werkt voor ontwikkeling.  
- **Kan ik de code hergebruiken voor PDF of SVG?** Ja—Aspose.Page ondersteunt meerdere uitvoerformaten met minimale aanpassingen.

## Hoe vorm te vullen met gradient in PostScript
Voordat we in de code duiken, laten we verduidelijken waarom “vorm vullen met gradient” belangrijk is. Het gebruik van gradients geeft je grafische elementen een professionele, driedimensionale uitstraling zonder rasterafbeeldingen. Met Aspose.Page kun je dezelfde gradientlogica toepassen op elke vectorvorm—cirkels, rechthoeken of aangepaste paden—over alle ondersteunde uitvoerformaten (PostScript, PDF, SVG).

## Wat is een radiale gradient?
Een radiale gradient laat kleuren van een centraal punt naar buiten overgaan, waardoor een vloeiende, ronde menging ontstaat. Het is ideaal voor highlights, knopachtergronden of elke visuele weergave die een natuurlijk “gloei‑effect” nodig heeft.

## Waarom Aspose.Page gebruiken voor radiale gradients?
- **Apparaatonafhankelijke rendering** – werkt hetzelfde op PostScript, PDF, SVG en meer.  
- **Volledige Java‑integratie** – geen native code, alleen gewone Java‑API’s.  
- **Hoogwaardige output** – ondersteunt anti‑aliasing en kleur‑ruimte‑controle.

## Voorwaarden
Voordat we erin duiken, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- JDK 8 of nieuwer geïnstalleerd op je machine.  
- Aspose.Page for Java bibliotheek (download van de [Aspose.Page Java documentatie](https://reference.aspose.com/page/java/)).  

## Pakketten importeren
Importeer eerst de klassen die we nodig hebben. Deze omvatten standaard AWT‑grafiektype­s en de Aspose.Page‑API.

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
Definieer de map waarin het gegenereerde PostScript‑bestand wordt opgeslagen. Vervang de tijdelijke aanduiding door een daadwerkelijk pad op jouw systeem.

```java
String dataDir = "Your Document Directory";
```

## Stap 2: Output‑stream maken
Open een `FileOutputStream` die naar het doel‑`.ps`‑bestand wijst. Deze stream levert de binaire gegevens die door Aspose.Page worden gegenereerd.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Stap 3: Opslagopties maken
Instantieer `PsSaveOptions`. Je kunt paginagrootte, compressie, enz. aanpassen, maar de standaardinstellingen zijn voldoende voor dit voorbeeld.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Stap 4: PS‑document maken
Maak het `PsDocument`‑object aan, waarbij je de output‑stream en opslagopties doorgeeft. De `false`‑vlag vertelt Aspose.Page geen pagina automatisch te openen (we doen het handmatig).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 5: Een cirkel maken
We tekenen een cirkel met `Ellipse2D.Float`. De parameters zijn `(x, y, breedte, hoogte)`. Door breedte = hoogte in te stellen, ontstaat een perfecte cirkel.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Hoe een cirkel met gradient tekenen
Nu we een vorm hebben, is de volgende stap om **een cirkel met gradient te tekenen**. Door een `RadialGradientPaint` op de cirkel toe te passen, zal de vuloperatie automatisch de door ons gedefinieerde gradient gebruiken.

## Stap 6: Gradient‑kleuren definiëren
Bereid twee arrays voor: één voor de kleuren die in de gradient verschijnen en een andere voor de bijbehorende fractionele posities (0 = centrum, 1 = rand).

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
Nu bouwen we het `RadialGradientPaint`‑object. Het neemt het middelpunt, de straal, het focuspunt, de kleurfracties, de kleurenarray, de cyclismethode, de kleur‑ruimte en de transformatie die we zojuist hebben gedefinieerd.

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
Pas de gradient‑paint toe op het document en vul de eerder gedefinieerde cirkel. Dit is de kern van ons **radiale gradient‑voorbeeld** en laat zien hoe je **een vorm kunt vullen met gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Stap 10: Pagina sluiten en document opslaan
Rond de pagina af, schrijf de inhoud naar schijf en sluit de stream. Je PostScript‑bestand is nu klaar om bekeken te worden met elke PS‑viewer.

```java
document.closePage();
document.save();
```

Gefeliciteerd! Je hebt met succes een radiale gradient‑voorbeeld gemaakt in Java PostScript met Aspose.Page. Je hebt nu een herbruikbaar patroon voor **vorm vullen met gradient** dat kan worden aangepast aan andere vormen en uitvoerformaten.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **FileNotFoundException** bij het openen van de output‑stream | Controleer of `dataDir` naar een bestaande map wijst en of je schrijfrechten hebt. |
| Gradient ziet er vlak uit of ontbreekt | Zorg ervoor dat de `fractions`‑array dezelfde lengte heeft als de `colors`‑array en dat de `AffineTransform` correct schaalt. |
| Kleuren lijken omgekeerd | Wissel de volgorde van kleuren in de `colors`‑array of pas de coördinaten van het `focus`‑punt aan. |

## Veelgestelde vragen

**V: Waar kan ik de documentatie voor Aspose.Page voor Java vinden?**  
A: De volledige API‑referentie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**V: Hoe kan ik Aspose.Page voor Java downloaden?**  
A: Haal de nieuwste JAR van de [releases‑pagina](https://releases.aspose.com/page/java/).

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja—download een proefversie [hier](https://releases.aspose.com/).

**V: Kan ik een tijdelijke licentie voor testen verkrijgen?**  
A: Zeker, vraag er een aan via de [pagina voor tijdelijke licenties](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik community‑ondersteuning krijgen?**  
A: Doe mee aan de discussie op het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39).

## Conclusie
In deze gids hebben we een volledig **radiale gradient‑voorbeeld** gebouwd voor een PostScript‑document met Aspose.Page voor Java. Door de stappen te volgen heb je nu een herbruikbaar patroon voor **vorm vullen met gradient**, dat je kunt aanpassen aan PDF, SVG of elk ander formaat dat door Aspose.Page wordt ondersteund. Experimenteer met verschillende kleuren, stralen en vormen om je Java‑grafiekprojecten te verrijken.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
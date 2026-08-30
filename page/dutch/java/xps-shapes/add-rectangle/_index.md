---
date: 2026-04-24
description: Leer hoe je de kleur van een rechthoek instelt en een rechthoek toevoegt
  in Java XPS met Aspose.Page. Deze gids behandelt het toevoegen van een rechthoek
  in Java en het wijzigen van de rechthoeklijn.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Rechthoek toevoegen in Java XPS
second_title: Aspose.Page Java API
title: Stel rechthoekkleur in en voeg rechthoek toe in Java XPS
url: /nl/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel rechthoekkleur in en voeg een rechthoek toe in Java XPS

## Inleiding
In deze gids leer je hoe je **rechthoekkleur instelt** en **een rechthoek toevoegt** in Java XPS met behulp van de Aspose.Page‑bibliotheek. Of je nu eenvoudige vormen voor een rapport wilt tekenen of complexe vectorafbeeldingen wilt maken, het beheersen van rechthoekstyling geeft je precieze controle over je XPS‑documenten.  

## Quick Answers
- **Which library is required?** Aspose.Page for Java  
- **Can I change the rectangle stroke?** Yes, using `setStroke` and `setStrokeThickness`  
- **Is a CMYK color profile supported?** Absolutely – you can load ICC profiles as shown  
- **Do I need a license for production?** Yes, a commercial license is required for non‑evaluation use  
- **How long does implementation take?** Typically under 10 minutes for a basic rectangle

## What is **set rectangle color**?
Het instellen van de kleur van een rechthoek betekent dat je de vul‑ of lijnkleur definieert waarmee de vorm wordt gerenderd in het uiteindelijke XPS‑document. Met Aspose.Page kun je RGB, CMYK of zelfs aangepaste ICC‑kleurprofielen gebruiken om exacte kleuraanpassing te bereiken.

## Why use Aspose.Page to **add rectangle java** and **change rectangle stroke**?
- **Volledig uitgeruste API** – ondersteunt zowel effen kleuren als verlopen.  
- **Cross‑platform** – werkt op elke Java‑runtime zonder native afhankelijkheden.  
- **Rijke geometrie‑ondersteuning** – maak complexe paden, pas transformaties toe en beheer de lijndikte eenvoudig.  

## Vereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page‑bibliotheek geïnstalleerd. Zo niet, download deze van de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Een werkende Java‑ontwikkelomgeving (IDE, JDK, enz.).  

## Pakketten importeren
Om te beginnen, importeer je de benodigde pakketten in je Java‑project. Zorg ervoor dat de Aspose.Page‑bibliotheek correct aan je classpath is toegevoegd. Hier is een basisvoorbeeld:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nu gaan we het voorbeeld opsplitsen in meerdere stappen om **een rechthoek toe te voegen** en **de kleur ervan in te stellen** in Java XPS.

## Stap 1: Stel de documentdirectory in
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Vervang `"Your Document Directory"` door het absolute pad waar je XPS‑bestanden wilt lezen/schrijven.

## Stap 2: Maak een nieuw XPS‑document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Deze regel initialiseert een nieuw XPS‑document dat onze vormen zal bevatten.

## Stap 3: Voeg een CMYK solide gekleurde omrande rechthoek toe
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Deze stap voegt een **omrande rechthoek** toe met een CMYK‑solide kleur. De `setStroke`‑methode definieert de kleur van de rechthoekrand, terwijl `setStrokeThickness` de lijndikte regelt — perfect voor **het wijzigen van de rechthoeklijn**.

### Pro tip:
Als je een RGB‑kleur verkiest, vervang dan de `createColor`‑aanroep door `doc.createColor(0, 0, 255)` voor een effen blauwe vulling.

## Stap 4: Sla het resulterende XPS‑document op
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Tot slot wordt het XPS‑document naar schijf weggeschreven. Het bestand `AddRectangle_out.xps` bevat nu een rechthoek waarvan je de kleur en lijn hebt gedefinieerd.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Rechthoek niet zichtbaar** | Onjuiste padgeometrie of lijndikte ingesteld op 0 | Controleer de padstring (`"M 20,10 L 220,10 220,100 20,100 Z"`) en zorg dat `setStrokeThickness` groter is dan 0. |
| **Verkeerde kleur** | Een ICC‑profiel gebruiken dat niet overeenkomt met de beoogde kleurenruimte | Gebruik `doc.createColor(r, g, b)` voor RGB of controleer het ICC‑bestandspad opnieuw. |
| **Bestand niet opgeslagen** | `dataDir` wijst naar een niet‑bestaande map of heeft geen schrijfrechten | Maak de map van tevoren aan of kies een schrijfbare locatie. |

## Veelgestelde vragen

**Q:** *Kan ik meerdere rechthoeken toevoegen in één XPS‑document?*  
A: Ja. Herhaal eenvoudig de stappen voor het maken van geometrie en styling voor elke gewenste rechthoek.

**Q:** *Hoe kan ik de vulkleur van de rechthoek wijzigen in plaats van de lijn?*  
A: Gebruik `path.setFill(...)` met een effen kleurkwast, vergelijkbaar met hoe `setStroke` wordt gebruikt.

**Q:** *Is Aspose.Page geschikt voor complexe XPS‑documentmanipulaties?*  
A: Zeker. De bibliotheek ondersteunt geavanceerde functies zoals verlopen, transformaties en ingebedde lettertypen.

**Q:** *Waar kan ik extra voorbeelden en community‑ondersteuning vinden?*  
A: Bekijk het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor meer codevoorbeelden en hulp van de gemeenschap.

**Q:** *Kan ik Aspose.Page uitproberen voordat ik het koop?*  
A: Ja, je kunt een [gratis proefversie](https://releases.aspose.com/) verkennen om de mogelijkheden van de API te evalueren.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
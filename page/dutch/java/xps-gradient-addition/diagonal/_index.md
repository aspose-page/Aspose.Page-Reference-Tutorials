---
date: 2026-05-25
description: Leer hoe u een gradient toevoegt aan XPS‑documenten in Java met Aspose.Page.
  Deze stap‑voor‑stap‑gids laat zien hoe u een diagonale gradient toevoegt, linear
  gradient brushes toepast en professionele XPS‑bestanden maakt.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Diagonale gradient toevoegen in Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Hoe een gradient toe te voegen: Diagonale gradient in Java XPS'
url: /nl/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een verloop toe te voegen: Diagonaal verloop in Java XPS

## Introductie
In moderne Java-ontwikkeling geeft het beheersen van **how to add gradient** voor XPS-documenten uw rapporten een gepolijste, opvallende uitstraling. Deze tutorial leidt u door het maken van een XPS‑bestand vanaf nul, het toevoegen van een diagonaal verloop, en het opslaan van het resultaat — allemaal met Aspose.Page voor Java. U begrijpt waarom verlopen belangrijk zijn, ziet de exacte API‑aanroepen, en krijgt praktische tips om veelvoorkomende valkuilen te vermijden.

## Snelle antwoorden
- **Wat is de primaire bibliotheek?** Aspose.Page for Java  
- **Welke methode voegt het verloop toe?** `createLinearGradientBrush` met gradient stops  
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisdiagonaal verloop  
- **Kan ik dit gebruiken met andere Java‑frameworks?** Ja, de API is framework‑agnostisch  

## Wat is een diagonaal verloop in een XPS‑document?
Een diagonaal verloop is een soepele kleurverandering die loopt van de ene hoek van een vorm naar de tegenoverliggende hoek, waardoor een scheef visueel effect ontstaat. In XPS wordt dit effect gedefinieerd door een lineaire gradient‑kwast die geordende gradient‑stops bevat die kleuren en relatieve posities langs de diagonale lijn specificeren.

## Waarom een diagonaal verloop toevoegen met Aspose.Page?
Aspose.Page levert **100 % render‑fidelity** voor verlopen in meer dan 20 XPS‑viewers, en ondersteunt **30+ XPS‑functies** zoals tekst, afbeeldingen en vectorvormen. De API abstraheert de complexe XPS‑markup, zodat u zich kunt concentreren op ontwerp terwijl gegarandeerd wordt dat hetzelfde bestand er identiek uitziet op Windows-, macOS- en Linux‑platformen.

## Vereisten
- Basiskennis van Java‑programmeren.  
- JDK geïnstalleerd op uw machine.  
- Aspose.Page for Java‑bibliotheek – download deze **[hier](https://releases.aspose.com/page/java/)**.  
- Een IDE zoals IntelliJ IDEA of Eclipse.

## Pakketten importeren
Begin met het importeren van de klassen die u nodig heeft. Deze imports geven u toegang tot geometrie, verloopverwerking en het maken van XPS‑documenten.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Stap 1: Stel uw project in
Maak een nieuw Java‑project aan in uw favoriete IDE en voeg de Aspose.Page‑JAR‑bestanden toe aan het build‑pad van het project.

## Stap 2: Definieer documentmap
Geef aan waar het gegenereerde XPS‑bestand moet worden opgeslagen.

```java
String dataDir = "Your Document Directory";
```

## Stap 3: Maak XPS‑document
`XpsDocument` is het kernobject dat een XPS‑bestand in het geheugen vertegenwoordigt. Een instantie ervan geeft u een canvas om pagina's, vormen en kwasten toe te voegen.

```java
XpsDocument doc = new XpsDocument();
```

## Stap 4: Voeg diagonaal verlooppad toe
Maak een rechthoekig pad dat het verloop ontvangt. De padgeometrie gebruikt een eenvoudige move‑line‑close‑opdracht.  
XpsPath definieert een vectorvorm in het XPS‑document, zoals een rechthoek of aangepaste geometrie.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Stap 5: Definieer lineaire gradient‑stops
Stel de kleuren en hun posities in. Elke stop definieert een punt in het verloop waar een specifieke kleur verschijnt.  
XpsGradientStop vertegenwoordigt een enkele kleurstop in een verloop, met een kleur en de bijbehorende offset.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Stap 6: Pas lineair verloop toe op pad
`XpsLinearGradientBrush` is het kwasttype van Aspose.Page voor lineaire kleurverlopen. Het neemt twee punten die de richting van het verloop definiëren en een collectie gradient‑stops die de kleuren langs die lijn bepalen.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Stap 7: Sla het document op
Sla het XPS‑bestand op schijf op. Het bestand zal de rechthoek bevatten die is gevuld met het door u gedefinieerde diagonaal verloop.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Hoe voeg ik een verloop toe in Java XPS?
Laad het XpsDocument, maak een `XpsLinearGradientBrush` met startpunt `(0,0)` en eindpunt `(width,height)`, voeg gradient‑stops toe, wijs de kwast toe aan de `Fill`‑eigenschap van een vorm, en roep ten slotte `save` aan. Deze beknopte stroom stelt u in staat een diagonaal verloop in te sluiten met slechts een handvol API‑aanroepen, waardoor uw code schoon en onderhoudbaar blijft.

## Veelvoorkomende valkuilen & tips
- **Gradient‑richting** – zorg ervoor dat de start‑ en eindpunten van de kwast de gewenste diagonaal weergeven; verwisselen keert het verloop om.  
- **Kleurprecisie** – Aspose gebruikt ARGB; voeg het alfacanalen toe als u transparantie nodig heeft.  
- **Bestandspad** – gebruik altijd een absoluut pad of controleer of het relatieve pad naar een bestaande, schrijfbare map wijst.

## Aanvullende FAQ

**Q: Hoe voeg ik **how to add gradient** toe aan een bestaande XPS‑vorm?**  
A: Maak een `XpsLinearGradientBrush`, definieer gradient‑stops, en wijs deze toe aan de `Fill`‑eigenschap van de vorm zoals weergegeven in Stap 6.

**Q: Wat doet **apply linear gradient** eigenlijk achter de schermen?**  
A: Het genereert een kwastdefinitie in het XPS‑pakket die verwijst naar de start‑/eindpunten en een collectie gradient‑stops, die de viewer weergeeft als een soepele kleurverandering.

**Q: Is er een snelle manier om **how to use aspose** te gebruiken voor andere XPS‑functies?**  
A: Ja, de Aspose.Page‑API bevat methoden voor het toevoegen van afbeeldingen, tekst en aangepaste vormen — verken eenvoudig de `XpsDocument`‑klasse voor extra hulpmiddelen.

**Q: Kan ik **add gradient path** toepassen op niet‑rechthoekige vormen?**  
A: Absoluut. Definieer elke geometrie met `createPathGeometry` en stel vervolgens de `Fill` in op een gradient‑kwast.

**Q: Heeft het verloop een significante invloed op de bestandsgrootte?**  
A: Alleen marginaal; gradient‑definities zijn lichte XML‑items binnen het XPS‑pakket.

---

**Laatst bijgewerkt:** 2026-05-25  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Aspose Page XPS Gradient Toevoeging](/page/java/xps-gradient-addition/)
- [Java XPS Tekst Toevoeging - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [Hoe afbeelding toe te voegen aan Java XPS-documenten – Een eenvoudige gids met Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
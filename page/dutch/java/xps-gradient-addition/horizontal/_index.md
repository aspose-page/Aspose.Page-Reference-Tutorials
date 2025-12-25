---
date: 2025-12-25
description: Leer hoe u een verloop aan XPS-documenten in Java kunt toevoegen met
  Aspose.Page en hoe u verloopstops kunt aanpassen voor verbluffende horizontale effecten.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Hoe een verloop toe te voegen – horizontaal verloop in Java XPS
url: /nl/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Gradient toe te voegen – Horizontale Gradient in Java XPS

## Inleiding
Welkom bij deze stapsgewijze handleiding over **hoe je een gradient** toevoegt aan een XPS‑document met Java. In deze tutorial leer je hoe je een horizontale gradient maakt, waarom dit belangrijk is voor visuele afwerking, en hoe je **gradient‑stops kunt aanpassen** voor precieze kleuraansturing. Aspose.Page voor Java maakt het werken met XPS‑documenten (XML Paper Specification) eenvoudig, zodat je je kunt concentreren op ontwerp in plaats van op low‑level bestandsafhandeling.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page voor Java  
- **Welke Java‑versie werkt?** Elke Java 8+ runtime  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie  
- **Kan ik de richting van de gradient wijzigen?** Ja – pas gewoon de start‑/eindpunten van de lineaire brush aan  
- **Is het mogelijk om meerdere gradients toe te voegen?** Absoluut – herhaal de stappen voor padcreatie met verschillende brushes  

## Wat is een horizontale gradient in XPS?
Een horizontale gradient is een vloeiende overgang van kleuren van links naar rechts over een vorm. In XPS wordt dit weergegeven door een lineaire gradient‑brush die interpoleert tussen gedefinieerde **gradient‑stops**. Dit visuele effect wordt vaak gebruikt voor banners, knoppen en achtergrondvullingen.

## Waarom Aspose.Page voor Java gebruiken?
- **Volledige XPS‑ondersteuning** – maken, bewerken en renderen zonder tools van derden.  
- **Eenvoudige API** – high‑level objecten zoals `XpsDocument`, `XpsPath` en `XpsGradientBrush` verbergen de XML‑complexiteit.  
- **Prestaties** – geoptimaliseerd voor grote documenten en batchverwerking.  

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

1. **Java‑ontwikkelomgeving** – Installeer de nieuwste JDK vanaf [java.com](https://www.java.com).  
2. **Aspose.Page voor Java‑bibliotheek** – Download de JAR van de [Aspose.Page voor Java‑documentatie](https://reference.aspose.com/page/java/).  

## Importpakketten
Begin met het importeren van de benodigde klassen. Deze imports geven je toegang tot documentcreatie, gradient‑verwerking en basisgeometrie.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Stap 1: Initialiseert het XPS‑document
Maak een nieuw `XpsDocument`‑object aan en geef de map op waar je het resultaat wilt opslaan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Stap 2: Maak een horizontale gradient
Definieer een lijst met **gradient‑stops** die de kleur en positie van elk overgangspunt bepalen. Het voorbeeld hieronder bouwt een levendige regenboog‑achtige gradient.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Hoe gradient‑stops aan te passen
- **Kleur** – Gebruik `doc.createColor(alpha, red, green, blue)` om een willekeurige ARGB‑waarde in te stellen.  
- **Positie** – Het tweede argument (`float` tussen `0` en `1`) bepaalt waar de stop langs de gradient‑lijn verschijnt. Pas deze waarden aan om kleuren naar links of rechts te verschuiven.

## Stap 3: Voeg pad met gradient toe
Maak een rechthoekig pad, pas indien nodig een transformatie toe, en vul het met de lineaire gradient‑brush. De brush gebruikt twee punten (`(10,0)` tot `(228,0)`) om een horizontaal effect te produceren.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro‑tip:** Het hergebruiken van dezelfde `stops`‑lijst voor meerdere paden kan de prestaties verbeteren, maar vergeet niet `clear()` aan te roepen voordat je nieuwe stops toevoegt.

## Stap 4: Sla het document op
Schrijf het XPS‑bestand naar schijf. Je kunt het nu openen met elke XPS‑viewer om de horizontale gradient in actie te zien.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Veelvoorkomende problemen & oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|----------|-----------|
| Gradient appears solid | No gradient stops added or brush not set | Ensure `path.setFill(...)` uses a `LinearGradientBrush` and that stops are added via `getGradientStops().addAll(stops)`. |
| Colors look muted | Incorrect alpha value (first parameter) | Use `255` for fully opaque colors unless transparency is desired. |
| Path size is off | Transform matrix values are wrong | Adjust the matrix parameters (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Veelgestelde vragen

**Q: Kan ik meerdere gradients in één XPS‑document toepassen?**  
A: Ja, je kunt meerdere paden toevoegen, elk met zijn eigen gradient‑brush, om complexe gelaagde ontwerpen te maken.

**Q: Is Aspose.Page compatibel met de nieuwste Java‑versies?**  
A: Aspose.Page voor Java wordt regelmatig bijgewerkt en werkt met Java 8 en nieuwere releases.

**Q: Zijn er andere gradient‑typen beschikbaar in Aspose.Page?**  
A: Naast lineaire gradients ondersteunt Aspose.Page ook radiale gradients voor cirkelvormige kleurovergangen.

**Q: Kan ik de kleuren en posities van gradient‑stops aanpassen?**  
A: Absoluut! Je hebt volledige controle over elke stop’s ARGB‑kleur en de relatieve positie (bereik 0‑1).

**Q: Is er een community‑forum voor Aspose.Page waar ik hulp kan zoeken?**  
A: Ja, je kunt het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) bezoeken om contact te leggen met de community en ondersteuning te krijgen.

---

**Laatst bijgewerkt:** 2025-12-25  
**Getest met:** Aspose.Page voor Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-25
description: Leer hoe je een verticale gradient kunt toevoegen in Java XPS met Aspose.Page.
  Volg deze stapsgewijze gids om de visuele aantrekkingskracht van je document te
  verbeteren.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Hoe een verticale gradiënt toe te voegen in Java XPS
url: /nl/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een verticale gradient toe te voegen in Java XPS

## Introductie
In deze tutorial ontdek je **hoe je een verticale gradient** kunt toevoegen aan XPS-documenten bij het werken met Java. Het toepassen van een verticale gradient kan de visuele impact van je rapporten, facturen of andere afdrukbare inhoud dramatisch verbeteren. We lopen elke stap door, van het opzetten van het project tot het opslaan van het uiteindelijke XPS‑bestand, met behulp van de krachtige Aspose.Page for Java‑bibliotheek.

## Snelle antwoorden
- **Wat doet een verticale gradient?** Het creëert een vloeiende kleurverloop van boven naar beneden van een vorm.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (downloadbaar van de officiële site).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Is dit compatibel met Java 8+?** Ja, de API ondersteunt Java 8 en latere versies.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten zodra de omgeving is opgezet.

## Voorvereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- Een werkende Java‑ontwikkelomgeving (JDK 8 of nieuwer).  
- Aspose.Page for Java library. You can download it from [here](https://releases.aspose.com/page/java/).  
- Een basisbegrip van Java‑programmeervoorconcepten.  

## Pakketten importeren
Begin met het importeren van de benodigde pakketten voor je Java‑project. Zorg ervoor dat de Aspose.Page for Java‑bibliotheek aan de classpath van je project is toegevoegd.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Stap 1: Document initialiseren
Begin met het aanmaken van een nieuw XPS‑document. Dit object zal alle tekenelementen bevatten die je later toevoegt.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Stap 2: Een pad maken met een verticale gradient
Definieer vervolgens een rechthoekig pad en pas een verticale lineaire gradient toe. De gradient‑stops bepalen de kleuren en hun posities langs de verticale as.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Stap 3: Document opslaan
Schrijf tenslotte het XPS‑bestand naar schijf. Het resulterende bestand zal de rechthoek bevatten die is gevuld met de verticale gradient die je hebt gedefinieerd.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Gefeliciteerd! Je hebt met succes geleerd **hoe je een verticale gradient** kunt toevoegen aan een Java XPS‑document met behulp van Aspose.Page.

## Waarom een verticale gradient gebruiken?
- **Verbeterde esthetiek:** Gradients voegen diepte en een moderne uitstraling toe aan statische vormen.  
- **Merkconsistentie:** Pas bedrijfs‑kleuren soepel aan over pagina’s.  
- **Eenvoudige aanpassing:** Verander kleuren of stop‑posities zonder grafische ontwerpen opnieuw te maken.

## Veelvoorkomende problemen & probleemoplossing
- **Gradient niet zichtbaar:** Controleer of de start‑ en eindpunten van de `LinearGradientBrush` correct zijn ingesteld voor een verticale oriëntatie.  
- **Bestand niet opgeslagen:** Zorg ervoor dat `dataDir` naar een schrijfbare map wijst en dat je toestemming hebt om bestanden te schrijven.  
- **Bibliotheek niet gevonden:** Controleer dubbel of de Aspose.Page JAR is opgenomen in het build‑pad van je project.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken in commerciële projecten?**  
A: Ja, Aspose.Page for Java is beschikbaar voor commercieel gebruik. Je kunt het aanschaffen via [here](https://purchase.aspose.com/buy).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie krijgen via [here](https://releases.aspose.com/).

**Q: Waar kan ik de documentatie voor Aspose.Page for Java vinden?**  
A: De documentatie is beschikbaar via [here](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Verkrijg een tijdelijke licentie via [here](https://purchase.aspose.com/temporary-license/).

**Q: Hulp nodig of vragen?**  
A: Bezoek het Aspose.Page‑community [forum](https://forum.aspose.com/c/page/39).

---

**Laatst bijgewerkt:** 2025-12-25  
**Getest met:** Aspose.Page for Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
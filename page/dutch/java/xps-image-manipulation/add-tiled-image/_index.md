---
date: 2025-12-28
description: Leer hoe u een XPS‑document maakt in Java met Aspose.Page en moeiteloos
  een getegelde afbeelding toevoegt met deze stapsgewijze handleiding.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Hoe een XPS-document met een getegelde afbeelding in Java te maken
url: /nl/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak XPS-document en voeg een getegelde afbeelding toe in Java

## Inleiding
In moderne Java-ontwikkeling is het vermogen om **XPS-documenten** programmatisch te maken een waardevolle vaardigheid, vooral wanneer je ze wilt verrijken met grafische elementen zoals getegelde afbeeldingen. Aspose.Page for Java maakt dit proces eenvoudig, zodat je je kunt concentreren op het visuele ontwerp in plaats van op low‑level bestandsafhandeling. In deze tutorial leer je precies hoe je een XPS-document maakt, **een getegelde afbeelding toevoegt**, en het resultaat opslaat, alles met duidelijke, stap‑voor‑stap codevoorbeelden.

## Snelle antwoorden
- **Wat doet Aspose.Page?** Het biedt een high‑level API om XPS-documenten in Java te genereren en te manipuleren.  
- **Kan ik een afbeelding tegelen?** Ja – gebruik `XpsImageBrush` met `XpsTileMode.Tile`.  
- **Heb ik een licentie nodig?** Een tijdelijke of commerciële licentie is vereist voor productiegebruik.  
- **Welke Java‑versie wordt ondersteund?** Elke JDK 8+ is compatibel.  
- **Hoe lang duurt de implementatie?** Ongeveer 10–15 minuten voor een basis getegelde‑afbeeldingsscenario.

## Wat is “XPS-document maken”?
Een XPS (XML Paper Specification)-bestand is een vaste‑indeling documentformaat dat vergelijkbaar is met PDF. Het programmatisch maken van een XPS-document stelt je in staat om afdrukbare, apparaat‑onafhankelijke bestanden direct vanuit Java‑code te genereren.

## Waarom een getegelde afbeelding toevoegen?
Het tegelen van een afbeelding herhaalt de grafiek over een gedefinieerd gebied, wat perfect is voor achtergronden, watermerken of patroonvullingen. Met `XpsTileMode.Tile` van Aspose.Page kun je dit bereiken met slechts een paar regels code.

## Voorvereisten
1. **Java Development Kit (JDK)** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Page for Java** – download van de [website](https://releases.aspose.com/page/java/).  
3. **Een beschrijfbare map** – waar het gegenereerde XPS‑bestand wordt opgeslagen.

## Importeer pakketten
Importeer in je Java‑project de benodigde klassen:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Stapsgewijze gids

### Stap 1: Stel je project in
Voeg de Aspose.Page JAR‑bestanden toe aan de classpath van je project en controleer of de import‑verklaringen zonder fouten compileren.

### Stap 2: Maak XPS-document
Instantieer een nieuw `XpsDocument`‑object. Dit is de kerncontainer die alle pagina's, paden en bronnen zal bevatten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Stap 3: Definieer het pad van de getegelde afbeelding
Plaats de afbeelding die je wilt tegelen (bijv. `R08LN_NN.jpg`) in de map die wordt aangeduid door `dataDir`. De afbeelding wordt gebruikt als penseelpatroon.

### Stap 4: Voeg getegelde afbeelding toe
Maak een rechthoekig pad en vul dit met een `XpsImageBrush`. Door de tile‑modus in te stellen op `Tile`, wordt de afbeelding over de rechthoek herhaald.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Stap 5: Sla het document op
Sla het XPS‑bestand op schijf op. Het uitvoerbestand zal de getegelde afbeelding bevatten die je zojuist hebt gedefinieerd.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Herhaal deze stappen telkens wanneer je **een getegelde afbeelding wilt toevoegen** aan andere pagina's of vormen binnen hetzelfde XPS‑document.

## Veelvoorkomende problemen en oplossingen
| Issue | Solution |
|-------|----------|
| Afbeelding wordt niet weergegeven | Controleer of het bestandspad (`dataDir + "R08LN_NN.jpg"`) correct is en de afbeelding toegankelijk is. |
| Tegelpatroon lijkt uitgerekt | Pas de bron- en bestemmingswaarden van `Rectangle2D` aan om de tegelgrootte te regelen. |
| Doorzichtigheid heeft geen effect | Zorg ervoor dat de doorzichtigheid van de penseel **na** de configuratie van de tegelmodus is ingesteld. |

## Veelgestelde vragen

### Is Aspose.Page compatibel met alle Java‑versies?
Aspose.Page is ontworpen om te werken met verschillende Java‑versies. Controleer de compatibiliteit door de documentatie [hier](https://reference.aspose.com/page/java/) te raadplegen.

### Kan ik Aspose.Page gebruiken voor commerciële projecten?
Ja, Aspose.Page biedt commerciële licenties. Koop ze [hier](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar?
Ja, verken de functies van Aspose.Page met een gratis proefversie [hier](https://releases.aspose.com/).

### Waar kan ik community‑ondersteuning en discussies vinden?
Doe mee met de Aspose.Page‑community op het [forum](https://forum.aspose.com/c/page/39).

### Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?
Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2025-12-28  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

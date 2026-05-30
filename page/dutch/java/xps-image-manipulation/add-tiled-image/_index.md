---
date: 2026-05-30
description: Leer hoe u een XPS-document in Java maakt met Aspose.Page en moeiteloos
  een getegelde afbeelding toevoegt met deze stapsgewijze handleiding. Hoe XPS-bestanden
  snel te maken.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Getegelde afbeelding toevoegen in Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hoe een XPS-document te maken met een getegelde afbeelding in Java
url: /nl/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een XPS-document met een getegelde afbeelding in Java maken

## Introductie
Het programmatisch maken van XPS-documenten is een essentiële vaardigheid voor Java‑ontwikkelaars die afdrukbare, apparaat‑onafhankelijke output nodig hebben. **Hoe XPS**‑bestanden efficiënt te maken wordt beantwoord door Aspose.Page for Java, dat de low‑level XML Paper Specification‑details abstraheert en je laat focussen op visueel ontwerp. In deze gids zie je precies hoe je een XPS-document maakt, een getegelde afbeelding toevoegt als achtergrond of patroon, en het resultaat opslaat — alles met beknopte, productie‑klare code.

## Snelle antwoorden
- **Wat doet Aspose.Page?** Het biedt een high‑level API om XPS‑documenten te genereren en te manipuleren in Java.  
- **Kan ik een afbeelding tegelen?** Ja – gebruik `XpsImageBrush` met `XpsTileMode.Tile`.  
- **Heb ik een licentie nodig?** Een tijdelijke of commerciële licentie is vereist voor productiegebruik.  
- **Welke Java‑versie wordt ondersteund?** Elke JDK 8+ is compatibel.  
- **Hoe lang duurt de implementatie?** Ongeveer 10–15 minuten voor een basis getegelde‑afbeeldingsscenario.

## Wat betekent “XPS-document maken”?
`XpsDocument` is het top‑level object van Aspose.Page dat een enkel XPS‑bestand in het geheugen vertegenwoordigt. Het omvat pagina’s, resources en metadata, waardoor je het document programmatisch kunt opbouwen. Een XPS‑document maken betekent deze klasse instantieren, visuele elementen toevoegen en uiteindelijk `save` aanroepen om het vaste‑layout‑bestand naar schijf te schrijven. Deze aanpak elimineert handmatige XML‑verwerking en garandeert naleving van de XML Paper Specification.

## Waarom een getegelde afbeelding toevoegen?
Tegelen herhaalt een grafisch element over een gedefinieerd gebied, wat ideaal is voor achtergronden, watermerken of patroonvullingen. Met `XpsTileMode.Tile` wordt de afbeelding automatisch herhaald zonder handmatige duplicatie, waardoor ontwikkeltijd wordt bespaard en consistente weergave op elk apparaat wordt gegarandeerd. Getegelde afbeeldingen houden de bestandsgrootte bovendien laag omdat dezelfde bitmap‑resource wordt hergebruikt in plaats van meerdere keren in te sluiten.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Page for Java** – download van de [website](https://releases.aspose.com/page/java/).  
3. **Een beschrijfbare map** – waar het gegenereerde XPS‑bestand wordt opgeslagen.

## Pakketten importeren
Importeer in je Java‑project de benodigde klassen:

`XpsDocument` is het hoofdobject dat een XPS‑bestand vertegenwoordigt.  
`XpsImageBrush` schildert vormen met een afbeeldingsbron.  
`XpsTileMode` specificeert hoe een afbeelding wordt getegeld.  
`Rectangle2D` beschrijft een rechthoekig gebied voor positionering.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Stapsgewijze handleiding

### Stap 1: Stel uw project in
Voeg de Aspose.Page‑JAR‑bestanden toe aan de classpath van uw project en controleer of de import‑verklaringen zonder fouten compileren.

### Stap 2: Maak XPS-document
`XpsDocument` is de kerncontainer die pagina’s, paden en resources bevat. Instantieer het met de gewenste paginagrootte en begin vervolgens grafische elementen toe te voegen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Stap 3: Definieer het pad van de getegelde afbeelding
Plaats de afbeelding die je wilt tegelen (bijv. `R08LN_NN.jpg`) in de map die wordt aangeduid door `dataDir`. De afbeelding wordt gebruikt als brush‑patroon.

### Stap 4: Voeg getegelde afbeelding toe
Maak een rechthoekig pad en vul dit met een `XpsImageBrush`. Door de tegelmodus op `Tile` in te stellen, wordt de afbeelding over het rechthoekgebied herhaald. Pas de bron‑ en bestemmingsrechthoeken aan om de tegelgrootte en -positie te regelen.

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
Schrijf het XPS‑bestand naar schijf. Het uitvoerbestand bevat de getegelde afbeelding die je zojuist hebt gedefinieerd en kan worden geopend met elke XPS‑viewer.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Herhaal deze stappen telkens wanneer je een **getegelde afbeelding** wilt toevoegen aan andere pagina’s of vormen binnen hetzelfde XPS‑document.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| Afbeelding wordt niet weergegeven | Controleer of het bestandspad (`dataDir + "R08LN_NN.jpg"`) correct is en de afbeelding toegankelijk is. |
| Tegelpatroon lijkt uitgerekt | Pas de bron- en bestemmingswaarden van `Rectangle2D` aan om de tegelgrootte te regelen. |
| Doorzichtigheid heeft geen effect | Zorg ervoor dat de doorzichtigheid van de brush **na** de tegelmodusconfiguratie wordt ingesteld. |

## Veelgestelde vragen

**Q:** Is Aspose.Page compatibel met alle Java‑versies?  
**A:** Aspose.Page ondersteunt Java 8 tot en met Java 21; de volledige compatibiliteitsmatrix vind je [hier](https://reference.aspose.com/page/java/).

**Q:** Kan ik Aspose.Page gebruiken voor commerciële projecten?  
**A:** Ja, een commerciële licentie is vereist voor productiegebruik. Aankoopopties staan vermeld [hier](https://purchase.aspose.com/buy).

**Q:** Is er een gratis proefversie beschikbaar?  
**A:** Een volledig functionele gratis proefversie kan worden gedownload vanaf de Aspose‑releasespagina [hier](https://releases.aspose.com/).

**Q:** Waar kan ik community‑ondersteuning krijgen?  
**A:** Word lid van het Aspose.Page‑communityforum op [forum](https://forum.aspose.com/c/page/39) om vragen te stellen en voorbeelden te delen.

**Q:** Hoe verkrijg ik een tijdelijke licentie voor evaluatie?  
**A:** Tijdelijke licenties worden op verzoek verstrekt via het Aspose‑portaal [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie
Je beschikt nu over een complete, productie‑klare workflow voor **hoe XPS**‑documenten met getegelde afbeeldingen te maken met Aspose.Page for Java. Door gebruik te maken van `XpsImageBrush` en `XpsTileMode.Tile` kun je rijke, herhaalbare graphics genereren zonder de bestandsgrootte op te blazen. Experimenteer met verschillende tegelgroottes, doorzichtigheidsniveaus en vormen om geavanceerde documentlay-outs te bouwen. Voor de volgende stap kun je vectorvormen of tekstoverlays toevoegen om je XPS‑bestanden verder te verrijken.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe afbeelding toevoegen aan Java XPS-documenten – Een eenvoudige gids met Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java – Pagina's toevoegen aan XPS‑tutorial](/page/java/xps-page-manipulation/add-page/)
- [XPS naar PDF converteren in Java met Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
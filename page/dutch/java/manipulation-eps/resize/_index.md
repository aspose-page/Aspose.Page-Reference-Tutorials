---
date: 2025-12-02
description: Leer hoe u EPS‑bestanden in Java moeiteloos kunt aanpassen met Aspose.Page.
  Deze stap‑voor‑stap gids laat zien hoe u EPS kunt schalen met punten, inches, millimeters
  of percentages.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hoe EPS-bestanden te verkleinen in Java met Aspose.Page
url: /nl/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe EPS-bestanden te schalen in Java met Aspose.Page

## Inleiding
Als je op zoek bent naar een betrouwbare manier **om EPS**‑bestanden programmatisch te schalen, ben je hier aan het juiste adres. In deze tutorial lopen we stap voor stap door het schalen van EPS‑afbeeldingen in Java met de Aspose.Page‑bibliotheek. Of je nu de grootte wilt verdubbelen, wilt verkleinen tot een specifieke maat, of met percentages wilt werken, de onderstaande stappen geven je volledige controle over de uitvoerafmetingen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java  
- **Kan ik schalen met points, inches of millimeters?** Ja – de API ondersteunt alle drie de eenheden plus percentages.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.  
- **Is de code thread‑safe?** Elke `PsDocument`‑instantie is geïsoleerd, zodat je bestanden parallel kunt verwerken.

## Voorvereisten
Voordat we in de code duiken, zorg dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page for Java‑bibliotheek. Je kunt deze **[hier](https://releases.aspose.com/page/java/)** downloaden.  
- Een basisbegrip van Java‑programmeren.  

## Import pakketten
Voeg in je Java‑project de benodigde imports toe zodat je kunt werken met Aspose.Page‑objecten en standaard I/O‑streams.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hoe EPS te schalen met points
Hieronder vind je een volledig, stap‑voor‑stap voorbeeld dat de grootte van een EPS‑bestand verdubbelt met points als meeteenheid.

### Stap 1: De invoer‑stream instellen
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Stap 2: Het `PsDocument`‑object initialiseren
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Stap 3: De huidige grootte van de EPS‑afbeelding ophalen
```java
Dimension oldSize = doc.extractEpsSize();
```

### Stap 4: Een uitvoer‑stream voor het geschaalde bestand maken
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Stap 5: Het EPS schalen en opslaan met points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hoe EPS te schalen met inches
Hetzelfde vijf‑stappenpatroon geldt; vervang gewoon `Units.Points` door `Units.Inches` en pas de schaalfactor naar behoefte aan.

## Hoe EPS te schalen met millimeters
Volg opnieuw dezelfde stappen, maar verwissel de eenheid naar `Units.Millimeters`. Handig wanneer je metrische afmetingen nodig hebt voor print‑workflows.

## Hoe EPS te schalen met percentages
Voor schaalvergroting op basis van percentages behoud je de eenheid `Units.Percent`. Vermenigvuldig de oorspronkelijke breedte en hoogte met het gewenste percentage (bijv. `0.5` voor een reductie van 50 %).

## Veelvoorkomende valkuilen & tips
- **Altijd streams sluiten** – In productiecodel, wikkel streams in try‑with‑resources om bestandsvergrendelingen te voorkomen.  
- **Aspectratio behouden** – Vermenigvuldig zowel breedte als hoogte met dezelfde factor, tenzij je opzettelijk vervorming wilt.  
- **Controleer DPI** – Schalen verandert de DPI niet; als je een andere DPI nodig hebt, pas die apart aan na het schalen.

## Conclusie
Je weet nu **hoe EPS**‑bestanden te schalen in Java met Aspose.Page, of je nu points, inches, millimeters of percentages verkiest. Deze flexibiliteit stelt je in staat EPS‑manipulatie te integreren in geautomatiseerde pipelines, desktop‑hulpmiddelen of server‑side services.

## Veelgestelde vragen

**Q: Kan ik deze bibliotheek voor andere afbeeldingsformaten gebruiken?**  
A: Nee, Aspose.Page is gespecialiseerd in PostScript‑ en EPS‑bestanden alleen.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt de gratis proefversie **[hier](https://releases.aspose.com/)** verkennen.

**Q: Waar vind ik extra hulp en discussies?**  
A: Bezoek het **[Aspose.Page‑forum](https://forum.aspose.com/c/page/39)** voor community‑ondersteuning.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen?**  
A: Je kunt een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)** krijgen.

**Q: Zijn er voorbeeldprojecten beschikbaar?**  
A: Ja, bekijk de documentatie **[hier](https://reference.aspose.com/page/java/)**.

---

**Laatst bijgewerkt:** 2025-12-02  
**Getest met:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
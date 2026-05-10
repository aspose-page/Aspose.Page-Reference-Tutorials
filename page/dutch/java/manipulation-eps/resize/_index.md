---
date: 2026-02-07
description: Leer hoe u EPS‑bestanden in Java kunt verkleinen en de afmetingen van
  EPS kunt wijzigen met Aspose.Page. Deze stapsgewijze handleiding laat zien hoe u
  EPS kunt verkleinen met punten, inches, millimeters of percentages.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hoe EPS‑bestanden te verkleinen in Java met Aspose.Page
url: /nl/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe EPS-bestanden te schalen in Java met Aspose.Page

## Introductie
Als je op zoek bent naar een betrouwbare manier **hoe EPS-bestanden te schalen** via code, ben je hier aan het juiste adres. In deze tutorial lopen we stap voor stap door het schalen van EPS-afbeeldingen in Java met behulp van de Aspose.Page‑bibliotheek. Of je nu de grootte wilt verdubbelen, wilt verkleinen tot een specifieke maat, of met percentages wilt werken, de onderstaande stappen geven je volledige controle over de uitvoerafmetingen. Het begrijpen van **hoe EPS te schalen** is essentieel wanneer je graphics moet aanpassen voor verschillende afdrukindelingen of schermresoluties.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page voor Java  
- **Kan ik schalen met points, inches of millimeters?** Ja – de API ondersteunt alle drie eenheden plus percentages.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.  
- **Is de code thread‑safe?** Elke `PsDocument`‑instantie is geïsoleerd, dus je kunt bestanden parallel verwerken.  

## Wat is EPS en waarom schalen?
Encapsulated PostScript (EPS) is een populair vectorgrafisch formaat dat wordt gebruikt in publicatie en drukwerk. Soms wordt het oorspronkelijke EPS‑bestand aangemaakt in een grootte die niet overeenkomt met je gewenste output – bijvoorbeeld, een logo ontworpen op 72 pts moet mogelijk 144 pts zijn voor een grotere brochure. Het kennen van **hoe EPS te schalen** stelt je in staat de vectorkwaliteit te behouden terwijl je de afmetingen aanpast aan elke workflow.

## Waarom Aspose.Page gebruiken voor het schalen van EPS?
- **Volledige controle over eenheden** – points, inches, millimeters of percentages.  
- **Geen externe afhankelijkheden** – pure Java‑API, geen native libraries.  
- **Hoge prestaties** – geschikt voor batchverwerking op servers.  
- **Behoudt vectorfidelity** – de output blijft schaalbaar zonder rasterisatie.

## Voorvereisten
Voordat we in de code duiken, zorg dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Page voor Java bibliotheek. Je kunt deze **[hier](https://releases.aspose.com/page/java/)** downloaden.  
- Een basisbegrip van Java‑programmeren.  

## Import pakketten
Voeg in je Java‑project de benodigde imports toe zodat je met Aspose.Page‑objecten en standaard I/O‑streams kunt werken.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hoe EPS‑dimensies te wijzigen met verschillende eenheden
De bibliotheek laat je **eps-dimensies wijzigen** door simpelweg de juiste `Units`‑enum te selecteren. Hieronder doorlopen we hetzelfde vijf‑stappenpatroon voor points, inches, millimeters en percentages. Het enige wat verandert is de eenheid die je doorgeeft aan `resizeEps`.

## Hoe EPS te schalen met points
Hieronder vind je een compleet, stap‑voor‑stap voorbeeld dat de grootte van een EPS‑bestand verdubbelt met points als meeteenheid.

### Stap 1: De invoerstroom instellen
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

### Stap 4: Een uitvoerstroom maken voor het geschaalde bestand
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Stap 5: Schalen en opslaan van de EPS met points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hoe EPS te schalen met inches
Hetzelfde vijf‑stappenpatroon geldt; vervang gewoon `Units.Points` door `Units.Inches` en pas de schaalfactor aan naar de gewenste inch‑waarde.

## Hoe EPS te schalen met millimeters
Volg opnieuw dezelfde stappen, maar wissel de eenheid naar `Units.Millimeters`. Handig wanneer je metrische afmetingen nodig hebt voor druk‑workflows.

## Hoe EPS te schalen met percentages
Voor schaalvergroting op basis van percentages, houd je de eenheid `Units.Percent` aan. Vermenigvuldig de oorspronkelijke breedte en hoogte met het gewenste percentage (bijv. `0.5` voor een reductie van 50 %).

## Veelvoorkomende valkuilen & tips
- **Altijd streams sluiten** – In productiecodel, wikkel streams in try‑with‑resources om bestandsvergrendelingen te voorkomen.  
- **Behouden van aspect ratio** – Vermenigvuldig zowel breedte als hoogte met dezelfde factor tenzij je bewust vervorming wilt.  
- **Controleer DPI** – Schalen verandert de DPI niet; als je een andere DPI nodig hebt, pas die apart aan na het schalen.  
- **Thread‑veiligheid** – Maak een nieuwe `PsDocument` per thread; het delen van dezelfde instantie kan onverwachte resultaten opleveren.  

## Veelgestelde vragen

**Q: Kan ik deze bibliotheek voor andere afbeeldingsformaten gebruiken?**  
A: Nee, Aspose.Page is gespecialiseerd in PostScript‑ en EPS‑bestanden alleen.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?**  
A: Ja, je kunt de gratis proefversie verkennen **[hier](https://releases.aspose.com/)**.

**Q: Waar vind ik extra hulp en discussies?**  
A: Bezoek het **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** voor community‑ondersteuning.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen?**  
A: Je kunt een tijdelijke licentie krijgen **[hier](https://purchase.aspose.com/temporary-license/)**.

**Q: Zijn er voorbeeldprojecten beschikbaar?**  
A: Ja, bekijk de documentatie **[hier](https://reference.aspose.com/page/java/)**.

---

**Laatst bijgewerkt:** 2026-02-07  
**Getest met:** Aspose.Page voor Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
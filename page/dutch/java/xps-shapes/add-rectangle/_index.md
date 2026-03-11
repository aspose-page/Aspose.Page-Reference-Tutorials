---
date: 2025-12-30
description: Leer hoe u een XPS‑document in Java maakt door rechthoeken toe te voegen
  met Aspose.Page. Volg deze stapsgewijze gids voor naadloze XPS‑documentmanipulatie.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: XPS-document maken in Java – Rechthoek toevoegen met Aspose.Page
url: /nl/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document Java – Add Rectangle

## Introductie
In deze uitgebreide tutorial maak je **XPS document Java**‑bestanden en leer je rechthoeken toe te voegen met de Aspose.Page‑bibliotheek. Of je nu rapporten, facturen of aangepaste grafische elementen maakt, het beheersen van het maken van rechthoeken geeft je precieze controle over de XPS‑lay-out. We lopen elke stap door, leggen uit waarom elke regel code nodig is en laten zien hoe je kleuren en lijnen kunt aanpassen voor een professioneel resultaat.

## Snelle antwoorden
- **Welke bibliotheek wordt aanbevolen?** Aspose.Page for Java  
- **Hoe lang duurt de implementatie?** Ongeveer 10 minuten voor een eenvoudige rechthoek  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie  
- **Welke Java‑versie wordt ondersteund?** Java 8 en later  
- **Kan ik meerdere vormen toevoegen?** Ja – herhaal de stappen voor elke vorm

## Vereisten
Zorg ervoor dat je het volgende hebt:

- Basiskennis van de programmeertaal Java.  
- Aspose.Page‑bibliotheek geïnstalleerd. Zo niet, download deze via de [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Een werkende Java‑ontwikkelomgeving (IDE, JDK en Maven/Gradle indien gewenst).

## Import Packages
Om te beginnen importeer je de benodigde pakketten in je Java‑project. Zorg ervoor dat de Aspose.Page‑bibliotheek correct aan je classpath is toegevoegd. Hieronder een basisvoorbeeld:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Laten we nu het voorbeeld opsplitsen in meerdere stappen om een rechthoek toe te voegen in Java XPS.

## Stap 1: Stel de documentdirectory in
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het pad naar de map waarin je de XPS‑bestanden wilt opslaan.

## Stap 2: Maak een nieuw XPS‑document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Deze regel **maakt** een nieuw XPS‑document dat je later kunt vullen met vormen, tekst of afbeeldingen.

## Stap 3: Voeg een CMYK‑solide kleur‑gestrekte rechthoek toe
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Deze stap voegt een gestrekte rechthoek toe met een CMYK‑solide kleur. Je kunt de geometrie‑string (`"M 20,10 L 220,10 220,100 20,100 Z"`) wijzigen om grootte of positie aan te passen, en de kleurwaarden in `createColor` aanpassen aan je ontwerp.

## Stap 4: Sla het resulterende XPS‑document op
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Sla tenslotte het gewijzigde XPS‑document met de toegevoegde rechthoek op in de eerder opgegeven map.

## Veelvoorkomende gebruikssituaties
- **Rapportkoppen** – Gebruik rechthoeken als achtergrondblokken voor titels.  
- **Factuurtabellen** – Markeer cellen of secties met gekleurde randen.  
- **Aangepaste grafieken** – Combineer meerdere rechthoeken om complexe vormen te creëren.

## Tips voor probleemoplossing
- **Bestand niet gevonden‑fout:** Controleer of `dataDir` naar een bestaande map wijst en of het ICC‑profiel (`uswebuncoated.icc`) aanwezig is.  
- **Onjuiste kleuren:** Zorg ervoor dat het ICC‑profiel overeenkomt met de kleurmodus die je wilt gebruiken (CMYK vs. RGB).  
- **Onverwachte afmetingen:** Pas de geometrie‑string aan zodat deze de juiste coördinaten weergeeft.

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je **XPS document Java**‑bestanden maakt en rechthoeken toevoegt met Aspose.Page. Deze basis stelt je in staat om rijkere XPS‑documenten te bouwen, grafische elementen aan te passen en vormen te integreren in grotere workflows.

## Veelgestelde vragen
### Kan ik meerdere rechthoeken in één XPS‑document toevoegen?
Ja, je kunt zoveel rechthoeken toevoegen als nodig door de stappen uit de tutorial te herhalen.

### Hoe kan ik de kleur van de rechthoek wijzigen?
Pas de kleurwaarden in de `createColor`‑methode aan om de gewenste kleur te verkrijgen.

### Is Aspose.Page geschikt voor complexe XPS‑documentmanipulaties?
Absoluut! Aspose.Page biedt een robuuste set functies voor diverse XPS‑documenttaken.

### Waar vind ik extra voorbeelden en ondersteuning?
Bekijk het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor meer voorbeelden en vraag hulp aan de community.

### Kan ik Aspose.Page eerst uitproberen voordat ik koop?
Ja, je kunt een [free trial](https://releases.aspose.com/) verkennen om de mogelijkheden van Aspose.Page te ervaren.

## Frequently Asked Questions

**Q: Werkt deze aanpak met Java 11 of nieuwer?**  
A: Ja, de Aspose.Page‑bibliotheek is compatibel met Java 8 en later, inclusief Java 11, 17 en hoger.

**Q: Kan ik afbeeldingen in het rechthoek‑gebied plaatsen?**  
A: Je kunt een `XpsImage`‑element toevoegen en dit positioneren boven of binnen de rechthoek met dezelfde geometrie‑coördinaten.

**Q: Hoe stel ik een vulkleur in plaats van alleen een lijn in?**  
A: Roep `path.setFill(...)` aan met een solide kleur‑brush gemaakt via `doc.createSolidColorBrush(...)`.

**Q: Is het mogelijk de rechthoek te roteren?**  
A: Pas een transformatie‑matrix toe op het pad met `path.setTransform(...)` om rotatie of schaling te bereiken.

**Q: Welke licentie is vereist voor productiegebruik?**  
A: Een commerciële Aspose.Page‑licentie is vereist voor implementatie; de gratis proefversie is beperkt tot evaluatie en ontwikkeling.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---
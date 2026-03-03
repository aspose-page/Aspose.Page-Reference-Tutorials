---
date: 2025-12-17
description: Leer hoe je Unicode‑tekst kunt toevoegen in Java PostScript met Aspose.Page
  – een stapsgewijze handleiding om Unicode‑strings moeiteloos toe te voegen.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Hoe Unicode-tekst toe te voegen in Java PostScript met Aspose.Page
url: /nl/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Unicode-tekst toe te voegen in Java PostScript met Aspose.Page

## Inleiding
Als je je afvraagt **hoe Unicode**‑tekens toe te voegen aan een Java‑gebaseerde PostScript (of XPS) workflow, ben je op de juiste plek. In deze tutorial lopen we stap voor stap door de exacte handelingen die nodig zijn om Unicode‑strings in te sluiten met behulp van de Aspose.Page‑bibliotheek voor Java. Aan het einde van de gids kun je elke taalspecifieke tekst—Arabisch, Chinees, emoji’s, wat je maar wilt—direct in je PostScript‑output invoegen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java  
- **Kan ik rechts‑naar‑links scripts toevoegen?** Ja, stel het Bidi‑niveau in zoals in de code getoond  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie  
- **Welke IDE werkt het beste?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Is de code platform‑onafhankelijk?** Absoluut—voer het uit op Windows, macOS of Linux

## Wat betekent “hoe Unicode toe te voegen” in de context van PostScript?
Unicode toevoegen betekent tekens invoegen die worden gerepresenteerd door code‑punten buiten het basis‑ASCII‑bereik. Aspose.Page abstraheert de low‑level‑encodering, zodat je je kunt concentreren op de tekstinhoud en de visuele plaatsing.

## Waarom Aspose.Page gebruiken voor Unicode‑tekst?
- **Volledige Unicode‑ondersteuning** – Handelt complexe scripts, ligaturen en rechts‑naar‑links talen af.  
- **Geen externe afhankelijkheden** – Je hoeft geen lettertype‑bestanden handmatig te beheren; de API werkt met systeembrede lettertypen.  
- **Eenvoudige API** – Een paar methode‑aanroepen zijn voldoende om meertalige tekst te renderen.

## Voorvereisten
Zorg er voordat we beginnen voor dat je de volgende zaken klaar hebt staan:

1. **Java Development Kit (JDK)** – Elke recente versie (8 of nieuwer).  
2. **Aspose.Page for Java** – Download en installeer de bibliotheek via de [download‑link](https://releases.aspose.com/page/java/).  
3. **IDE naar keuze** – IntelliJ IDEA, Eclipse, of een andere Java‑IDE die je verkiest.

## Importeer pakketten
Voeg de benodigde Aspose.Page‑klassen toe aan je Java‑bronbestand:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Stap 1: Stel uw project in
Maak een nieuw Java‑project, voeg de Aspose.Page‑JAR toe aan het build‑pad van het project, en maak een map aan waar het gegenereerde XPS‑bestand wordt opgeslagen. Deze map wordt later aangeduid als `dataDir`.

## Stap 2: Initialiseer XPS‑document
Maak een leeg XPS‑document aan dat de inhoud zal bevatten:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Stap 3: Voeg Unicode‑tekst toe
Nu voegen we daadwerkelijk de Unicode‑string toe. Het voorbeeld hieronder schrijft de omgekeerde zin “AVAJ rof SPX.esopsA”, die alleen ASCII‑tekens bevat, maar je kunt dit vervangen door elke Unicode‑tekst (bijv. Arabisch “مرحبا” of Chinees “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** Om rechts‑naar‑links talen correct te renderen, stel `glyphs.setBidiLevel(1);` in. Voor links‑naar‑rechts scripts kun je deze regel weglaten.

## Stap 4: Sla het document op
Schrijf het XPS‑bestand naar schijf:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Na het uitvoeren van het programma, open het gegenereerde `AddEncodingText_out.xps` met een willekeurige XPS‑viewer om de Unicode‑tekst te zien op de opgegeven coördinaten.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Tekst verschijnt als vierkanten | Lettertype niet gevonden of ondersteunt de tekens niet | Gebruik een lettertype dat de benodigde glyphs bevat (bijv. “Arial Unicode MS”) |
| Rechts‑naar‑links tekst wordt links‑naar‑rechts weergegeven | Bidi‑niveau niet ingesteld | Roep `glyphs.setBidiLevel(1);` aan |
| Bestand niet opgeslagen | `dataDir` pad ongeldig of ontbrekende schrijfrechten | Zorg ervoor dat de map bestaat en de applicatie schrijfrechten heeft |

## Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
Aspose.Page is voornamelijk ontworpen voor Java, maar Aspose biedt bibliotheken voor verschillende programmeertalen.

### Is er een gratis proefversie beschikbaar?
Ja, je kunt een gratis proefversie van Aspose.Page [hier](https://releases.aspose.com/) verkrijgen.

### Waar kan ik ondersteuning en discussies over Aspose.Page vinden?
Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor ondersteuning en discussies.

### Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?
Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

### Wat zijn de beschikbare lettertype‑stijlen in Aspose.Page?
Aspose.Page ondersteunt lettertype‑stijlen zoals Regular, Bold, Italic en BoldItalic.

## Conclusie
Je hebt nu **hoe Unicode**‑tekst toe te voegen aan een Java PostScript (XPS)‑document onder de knie met Aspose.Page. Deze mogelijkheid opent de deur naar meertalige rapportage, internationaal gefactureerde documenten en elke situatie waarin niet‑ASCII‑tekens vereist zijn. Voel je vrij om extra functies te verkennen, zoals tekstrotatie, knip‑paden of het insluiten van aangepaste lettertypen—details zijn beschikbaar in de officiële [documentatie](https://reference.aspose.com/page/java/).

---

**Laatst bijgewerkt:** 2025-12-17  
**Getest met:** Aspose.Page for Java 23latest at time of writing)  
**Auteur:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

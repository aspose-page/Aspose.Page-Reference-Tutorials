---
date: 2025-12-21
description: Leer hoe je Aspose.Page XMP in EPS‑documenten kunt wijzigen met Java.
  Verbeter metadata snel met Aspose.Page voor Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page xmp wijzigen – Waarden in XMP wijzigen met Java
url: /nl/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Waarden in XMP wijzigen met Java

## Inleiding
Als je **aspose.page modify xmp** gegevens in een EPS‑bestand moet wijzigen, ben je hier op de juiste plek. In deze tutorial lopen we stap voor stap door de exacte stappen die nodig zijn om XMP‑waarden (Extensible Metadata Platform) te lezen, bij te werken en op te slaan met de Aspose.Page‑bibliotheek voor Java. Aan het einde kun je de documentmetadata—zoals maker, titel en wijzigingsdatum—afstemmen op de eisen van je project.

## Snelle antwoorden
- **Wat doet “aspose.page modify xmp”?** Het stelt je in staat XMP‑metadata in EPS‑bestanden te lezen en te schrijven via de Aspose.Page Java‑API.  
- **Welke bibliotheekversie is vereist?** Elke recente Aspose.Page for Java‑release (de API is stabiel over versies).  
- **Heb ik eenentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik meerdere XMP‑velden tegelijk wijzigen?** Ja—roep `put` aan voor elk veld voordat je het document opslaat.  
- **Is tijdzone‑afhandeling nodig?** Het instellen van de standaardtijdzone (bijv. UTC) zorgt voor consistente datumwaarden.

## Wat is XMP en waarom wijzigen?
XMP (Extensible Metadata Platform) is een gestandaardiseerde manier om rijke metadata direct in bestanden zoals EPS, PDF en afbeeldingen te embedden. Het bijwerken van XMP stelt je in staat te bepalen hoe documenten worden geïndexeerd, weergegeven en doorzocht—cruciaal voor branding, compliance en workflow‑automatisering.

## Waarom Aspose.Page voor Java gebruiken?
- **Volledig uitgeruste API** – geen externe tools nodig; alles wordt in‑process afgehandeld.  
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.  
- **Geen native afhankelijkheden** – pure Java‑implementatie vereenvoudigt de uitrol.  
- **Robuuste ondersteuning** – verwerkt zowel bestaande XMP‑blokken als maakt nieuwe aan vanuit PS‑commentaren wanneer deze ontbreken.

## Voorvereisten
Voordat we aan deze tutorial beginnen, zorg dat je de volgende zaken gereed hebt:
1. **Java‑ontwikkelomgeving** – een JDK (8 of hoger) en een IDE of build‑tool naar keuze.  
2. **Aspose.Page for Java‑bibliotheek** – download en installeer de Aspose.Page for Java‑bibliotheek. Je kunt het benodigde pakket [hier](https://releases.aspose.com/page/java/) vinden.

## Pakketten importeren
Begin met het importeren van de vereiste pakketten in je Java‑project. Deze pakketten zijn essentieel voor interactie met en manipulatie van EPS‑documenten.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Stap 1: XMP‑metadata ophalen
Haal de XMP‑metadata op uit het EPS‑document. Als het EPS‑bestand geen XMP‑metadata bevat, wordt er een nieuwe aangemaakt met waarden uit PS‑metadata‑commentaren zoals %%Creator, %%CreateDate en %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 2: “ModifyDate”‑waarde wijzigen
Wijzig de “ModifyDate”‑waarde in de XMP‑metadata zodat deze de gewenste datum weergeeft.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Stap 3: “Creator”‑waarde wijzigen
Werk de “Creator”‑waarde in de XMP‑metadata bij om de maker van het document te specificeren.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Stap 4: “Title”‑waarde wijzigen
Pas de “Title”‑waarde in de XMP‑metadata aan om een passende titel voor het document in te stellen.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Stap 5: Document opslaan met gewijzigde XMP‑metadata
Sla het document op met de bijgewerkte XMP‑metadata naar een nieuw EPS‑bestand.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Veelvoorkomende problemen en oplossingen
- **Ontbrekend XMP‑blok** – de API maakt automatisch een aan vanuit PS‑commentaren, maar je kunt ook handmatig `XmpMetadata` instantiëren indien nodig.  
- **Tijdzone‑verschillen** – stel altijd `TimeZone.setDefault` in vóór het aanmaken van het `Date`‑object om onverwachte verschuivingen te voorkomen.  
- **Bestands‑toegangs fouten** – zorg ervoor dat de invoer‑ en uitvoer‑paden correct zijn en dat je applicatie lees‑/schrijfrechten heeft.

## Veelgestelde vragen

**Q: Hoe kan ik tijdzone‑overwegingen afhandelen bij het wijzigen van XMP‑waarden?**  
A: Gebruik `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` om consistentie in tijdzone‑instellingen te waarborgen.

**Q: Kan ik meerdere XMP‑waarden in één bewerking wijzigen?**  
A: Ja, door de `put`‑methode voor elke gewenste waarde te gebruiken, kun je meerdere XMP‑waarden gelijktijdig aanpassen.

**Q: Waar kan ik extra documentatie vinden voor Aspose.Page for Java?**  
A: Bekijk de uitgebreide documentatie [hier](https://reference.aspose.com/page/java/).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page for Java?**  
A: Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

**Q: Heeft het wijzigen van XMP invloed op de visuele inhoud van de EPS?**  
A: Nee. XMP‑wijzigingen betreffen alleen metadata en wijzigen de grafische elementen van het EPS‑bestand niet.

**Q: Kan ik programmatically de bijgewerkte waarden teruglezen om de wijziging te verifiëren?**  
A: Absoluut—roep simpelweg `xmp.get("dc:creator")` (of de relevante sleutel) aan na het opslaan en vóór het sluiten van het document.

## Conclusie
Gefeliciteerd! Je hebt met succes het proces doorlopen om **aspose.page modify xmp** waarden in EPS‑documenten te wijzigen met Aspose.Page voor Java. Deze tutorial heeft je uitgerust met de kennis om metadata aan te passen, zodat je documenten naadloos aansluiten op je specifieke eisen.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

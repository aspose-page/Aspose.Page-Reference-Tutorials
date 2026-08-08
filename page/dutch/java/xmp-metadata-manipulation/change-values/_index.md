---
date: 2026-05-25
description: Leer hoe je xmp in EPS-documenten kunt wijzigen met Java en Aspose.Page.
  Werk metadata snel en betrouwbaar bij.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Waarden in XMP wijzigen met Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hoe xmp te wijzigen met Aspose.Page – Waarden in XMP wijzigen met Java
url: /nl/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Waarden wijzigen in XMP met Java

## Inleiding
Als je **hoe je xmp kunt wijzigen** in een EPS‑bestand met Java zoekt, ben je op de juiste plek. Deze tutorial leidt je stap voor stap door – het lezen van het bestaande XMP‑blok, het bijwerken van velden zoals maker, titel en wijzigingsdatum, en tenslotte het opslaan van de wijzigingen terug naar het EPS‑document. Aan het einde heb je een herbruikbare code‑snippet die in elke geautomatiseerde workflow past, zodat je bestanden de juiste metadata bevatten voor branding, compliance of zoekmachine‑indexering.

## Snelle antwoorden
- **Wat doet “aspose.page modify xmp”?** Het laat je XMP‑metadata lezen en schrijven in EPS‑bestanden via de Aspose.Page Java‑API.  
- **Welke bibliotheekversie is vereist?** Elke recente Aspose.Page for Java‑release (de API is stabiel over versies).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik meerdere XMP‑velden tegelijk wijzigen?** Ja—roep `put` aan voor elk veld voordat je het document opslaat.  
- **Is tijdzone‑afhandeling nodig?** Het instellen van de standaardtijdzone (bijv. UTC) zorgt voor consistente datumwaarden.

## Wat is XMP en waarom wijzigen?
XMP (Extensible Metadata Platform) is een gestandaardiseerd, XML‑gebaseerd formaat voor het embedden van rijke metadata direct in bestanden zoals EPS, PDF en afbeeldingen. Het bijwerken van XMP stelt je in staat te bepalen hoe documenten worden geïndexeerd, weergegeven en doorzocht—cruciaal voor merkconsistentie, wettelijke naleving en geautomatiseerde content‑pijplijnen.

## Waarom Aspose.Page voor Java gebruiken?
Aspose.Page biedt een **volledig uitgeruste, pure‑Java API** die de noodzaak voor externe tools of native bibliotheken elimineert. Het ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan EPS‑bestanden tot **500 MB** verwerken zonder het volledige document in het geheugen te laden, waardoor snelle, geheugen‑efficiënte metadata‑manipulatie op elk OS dat Java draait mogelijk is.

## Vereisten
Voordat we aan deze tutorial beginnen, zorg dat je de volgende zaken gereed hebt:
1. **Java-ontwikkelomgeving** – Een JDK (8 of hoger) en een IDE of build‑tool naar keuze.  
2. **Aspose.Page for Java‑bibliotheek** – Download en installeer de Aspose.Page for Java‑bibliotheek. Je kunt het benodigde pakket [hier](https://releases.aspose.com/page/java/) vinden.

## Importeer pakketten
Begin met het importeren van de benodigde pakketten in je Java‑project. Deze pakketten zijn essentieel voor het interactief werken met en manipuleren van EPS‑documenten.

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

## Hoe XMP in EPS wijzigen met Java?
`Document` is de Aspose.Page‑klasse die een EPS‑bestand vertegenwoordigt en toegang biedt tot de inhoud en metadata. `XmpMetadata` vertegenwoordigt het XMP‑blok dat aan het document is gekoppeld en maakt lezen en schrijven van metadata‑velden mogelijk. `put` voegt een metadata‑item toe of werkt het bij in het XmpMetadata‑object. `save` schrijft het gewijzigde document, inclusief eventuele bijgewerkte XMP‑metadata, naar een bestand.

Laad het EPS‑bestand met `new Document("input.eps")`, haal het `XmpMetadata`‑object op, werk de gewenste sleutels bij met `put`, en roep tenslotte `save` aan om de wijzigingen naar een nieuw bestand te schrijven. Deze beknopte flow behandelt ontbrekende XMP‑blokken automatisch, maakt er een aan vanuit PostScript‑commentaren wanneer nodig, en zorgt voor tijdzone‑consistente datums.

## Stap 1: XMP-metadata ophalen
De `XmpMetadata`‑klasse vertegenwoordigt het XMP‑blok dat aan een EPS‑document is gekoppeld. Wanneer je `document.getXmpMetadata()` aanroept, retourneert de API het bestaande blok of bouwt een nieuw blok op uit PS‑commentaren zoals `%%Creator`, `%%CreateDate` en `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 2: “ModifyDate”-waarde wijzigen
Werk de `"ModifyDate"`‑invoer bij om de nieuwe wijzigings‑timestamp weer te geven. Gebruik `java.util.Date` gecombineerd met `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` om te garanderen dat de opgeslagen waarde tijdzone‑onafhankelijk is.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Stap 3: “Creator”-waarde wijzigen
De `"Creator"`‑sleutel slaat de naam op van de applicatie of persoon die het EPS‑bestand heeft gegenereerd. Roep `xmp.put("dc:creator", "Your Company Name")` aan om de bestaande waarde te vervangen door een aangepaste identifier.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Stap 4: “Title”-waarde wijzigen
Het `"Title"`‑veld wordt door veel asset‑managementsystemen weergegeven. Door het in te stellen via `xmp.put("dc:title", "New Document Title")` zorg je ervoor dat het document correct verschijnt in catalogi en zoekresultaten.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Stap 5: Document opslaan met gewijzigde XMP-metadata
Na alle aanpassingen roep je `document.save("output.eps")` aan. De bibliotheek schrijft het bijgewerkte XMP‑blok terug in de EPS‑stroom terwijl de oorspronkelijke grafische inhoud ongewijzigd blijft.

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
- **Missing XMP block** – De API maakt automatisch een blok aan vanuit PS‑commentaren, maar je kunt ook handmatig een `XmpMetadata`‑instantie maken indien nodig.  
- **Timezone mismatches** – Stel altijd `TimeZone.setDefault` in vóór het aanmaken van het `Date`‑object om onverwachte verschuivingen te voorkomen.  
- **File access errors** – Zorg dat de invoer‑ en uitvoer‑paden correct zijn en dat je applicatie lees‑/schrijfrechten heeft.

## Veelgestelde vragen

**Q: Hoe kan ik tijdzone‑overwegingen afhandelen bij het wijzigen van XMP‑waarden?**  
A: Gebruik `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` om consistentie in tijdzone‑instellingen te waarborgen.

**Q: Kan ik meerdere XMP‑waarden in één bewerking wijzigen?**  
A: Ja, door de `put`‑methode voor elke gewenste waarde te gebruiken, kun je meerdere XMP‑waarden gelijktijdig aanpassen.

**Q: Waar vind ik aanvullende documentatie voor Aspose.Page for Java?**  
A: Verken de uitgebreide documentatie [hier](https://reference.aspose.com/page/java/).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

**Q: Heeft het wijzigen van XMP invloed op de visuele inhoud van de EPS?**  
A: Nee. XMP‑wijzigingen betreffen alleen metadata en wijzigen de grafische elementen van het EPS‑bestand niet.

**Q: Kan ik programmatisch de bijgewerkte waarden teruglezen om de wijziging te verifiëren?**  
A: Absoluut—roep simpelweg `xmp.get("dc:creator")` (of de relevante sleutel) aan na het opslaan en vóór het sluiten van het document.

## Conclusie
Gefeliciteerd! Je hebt **hoe je xmp‑waarden** in EPS‑documenten kunt wijzigen met Aspose.Page voor Java onder de knie. Door nauwkeurige maker‑, titel‑ en wijzigings‑datum‑metadata in te sluiten, zorg je ervoor dat je assets doorzoekbaar, compliant en afgestemd op je branding‑standaarden zijn. Integreer dit patroon gerust in batch‑verwerkings‑pijplijnen, CI/CD‑stappen of elke geautomatiseerde document‑generatie‑workflow.

---

**Laatst bijgewerkt:** 2026-05-25  
**Getest met:** Aspose.Page for Java (latest release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Aspose Page Java‑tutorial – XMP-metadata toevoegen aan EPS‑bestanden](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Hoe XMP-metadata lezen met Java – Aspose.Page‑gids](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java – Array‑items wijzigen in XMP met Java](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
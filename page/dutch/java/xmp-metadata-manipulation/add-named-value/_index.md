---
date: 2026-09-19
description: Leer hoe je XMP named values kunt toevoegen aan EPS-bestanden met Aspose.Page
  for Java – een stap‑voor‑stap gids met codevoorbeelden.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Named Value toevoegen in XMP met Java
og_description: Hoe XMP named values toe te voegen aan EPS-bestanden met Aspose.Page
  for Java. Volg deze beknopte gids om binnen enkele minuten custom metadata in te
  voegen.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Hoe XMP named value toe te voegen aan EPS-bestanden met Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Hoe XMP named value toe te voegen aan EPS-bestanden met Java
url: /nl/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg benoemde waarde toe aan XMP-metadata met Java

## Introductie
In moderne Java-ontwikkeling is het leren **hoe XMP**-metadata toe te voegen aan EPS-bestanden essentieel voor het behouden van de herkomst van documenten en het verbeteren van de doorzoekbaarheid. Met **Aspose.Page for Java** kun je moeiteloos aangepaste benoemde waarden in het XMP-pakket injecteren. Deze tutorial leidt je stap voor stap door de exacte stappen — compleet met codefragmenten — zodat je vandaag nog XMP-metadata aan je EPS-documenten kunt toevoegen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java (Aspose)  
- **Welk bestandstype is het doel?** EPS-bestanden met XMP-metadata  
- **Primaire gebruikssituatie?** Aangepaste benoemde waarden toevoegen (bijv. paginagroottebeperkingen) aan XMP  
- **Voorvereisten?** JDK 8+ en de Aspose.Page for Java-bibliotheek  
- **Typische implementatietijd?** 5–10 minuten zodra de bibliotheek is ingesteld  

## Wat is asp?
Aspose is de afkorting voor Aspose, een suite van API's die ontwikkelaars in staat stelt om een breed scala aan documentformaten te maken, bewerken, converteren en renderen zonder externe software te vereisen. De Aspose.Page for Java-component richt zich specifiek op PostScript- en EPS-verwerking, en biedt programmatische toegang tot paginainhoud, grafische elementen en metadata zoals XMP.

## Waarom benoemde waarden toevoegen aan XMP-metadata?
Benoemde waarden laten je willekeurige sleutel‑waardeparen direct in het XMP-pakket opslaan, waardoor ze onmiddellijk leesbaar zijn voor downstream‑tools. Dit verbetert de zoekmachinevriendelijkheid, maakt workflow‑automatisering mogelijk en voldoet aan nalevingsvereisten door regelgevende informatie in te sluiten zonder de visuele inhoud te wijzigen.

## Waarom dit belangrijk is
Het toevoegen van benoemde waarden aan XMP stelt je in staat willekeurige sleutel‑waardeparen op te slaan die gelezen kunnen worden zonder het volledige EPS‑bestand te parseren. Deze mogelijkheid is vooral waardevol in geautomatiseerde publicatie‑pijplijnen, digitale asset‑managementsystemen en compliance‑gedreven workflows waar metadata downstream‑acties aanstuurt.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- **Java Development Kit (JDK):** Een recente JDK (8 of hoger) geïnstalleerd op je machine.  
- **Aspose.Page for Java Library:** Download deze van de officiële [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Voeg de JAR toe aan de classpath van je project.  
- **Een EPS‑bestand** dat al XMP‑metadata bevat of automatisch zal worden gegenereerd.

## Pakketten importeren
Begin met het importeren van de benodigde Java‑pakketten. Deze imports geven je toegang tot bestandsstreams, het EPS‑documentmodel en XMP‑verwerkingsklassen.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Hoe XMP‑benoemde waarde toe te voegen aan EPS‑bestanden met Java
Om een benoemde waarde toe te voegen, laad je het EPS‑bestand met een `FileInputStream`, haal je het `XmpMetadata`‑object op of maak je het aan, voeg je de gewenste `NamedValue` toe aan de juiste namespace, en schrijf je vervolgens het gewijzigde document terug met een `FileOutputStream`. Aspose.Page behandelt automatisch de creatie van het XMP‑pakket indien ontbrekend, zodat de nieuwe metadata correct wordt ingebed.

### Stap 1: Initialiseer invoer‑EPS‑bestandstream
**FileInputStream** is een Java I/O‑klasse die ruwe bytes uit een bestand leest. Laad het bron‑EPS‑bestand in een `FileInputStream`. Deze stream levert het document aan de API van Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro tip:** Houd de `dataDir`‑variabele configureerbaar zodat dezelfde code in verschillende omgevingen werkt.

### Stap 2: Verkrijg XMP‑metadata
**XmpMetadata** vertegenwoordigt het XMP‑pakket dat aan een EPS‑document is gekoppeld. Haal het bestaande XMP‑pakket op; als het EPS‑bestand er geen heeft, maakt Aspose een nieuw XMP‑object aan, gevuld vanuit de PS‑commentaren.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Stap 3: Voeg benoemde waarde toe
**NamedValue** is een sleutel‑waarde‑paar dat wordt opgeslagen binnen de XMP‑metadata‑namespace. Voeg een aangepaste benoemde waarde toe aan de XMP‑structuur. In dit voorbeeld voegen we een nieuwe sleutel toe onder de `xmpTPg:MaxPageSize`‑namespace.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Waarom dit belangrijk is:** Benoemde waarden laten je willekeurige sleutel‑waardeparen opslaan die downstream‑applicaties kunnen lezen zonder het volledige document te parseren.

### Stap 4: Initialiseer uitvoer‑EPS‑bestandstream
**FileOutputStream** is een Java I/O‑klasse die ruwe bytes naar een bestand schrijft. Bereid een `FileOutputStream` voor waar de gewijzigde EPS wordt opgeslagen.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Stap 5: Document opslaan
De `save`‑methode slaat de wijzigingen op. Het schrijft het bijgewerkte XMP‑pakket terug naar het EPS‑bestand, waardoor de nieuwe benoemde waarde onderdeel wordt van de metadata van het document.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Stap 6: Sluit invoer‑EPS‑stream
Het sluiten van de oorspronkelijke bestandshandle voorkomt resource‑lekken en zorgt ervoor dat het bestand niet vergrendeld blijft voor volgende bewerkingen.

```java
psStream.close();
```

Door deze zes stappen te volgen, heb je met succes **een benoemde waarde toegevoegd aan XMP‑metadata** met **Aspose.Page for Java**.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `NullPointerException` op `xmp` | EPS‑bestand heeft geen XMP en Aspose kon er geen genereren | Zorg ervoor dat het EPS ten minste één PS‑commentaar bevat of maak handmatig een nieuw `XmpMetadata`‑object aan. |
| Uitvoerbestand is leeg | Uitvoerstroom niet geflusht/gesloten | Controleer of `outPsStream.close()` wordt aangeroepen in een `finally`‑blok (zoals getoond). |
| Duplicaat‑sleutel fout | Dezelfde benoemde waarde twee keer toegevoegd | Controleer of de sleutel al bestaat met `xmp.containsNamedValue(...)` voordat je toevoegt. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos samen te werken met andere Java‑bibliotheken, waardoor flexibiliteit in je ontwikkelomgeving wordt geboden.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie van Aspose.Page for Java krijgen op de [Aspose releases page](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page for Java?**  
A: Bezoek de [temporary license page](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor Aspose.Page for Java te verkrijgen.

**Q: Waar kan ik meer tutorials en voorbeelden vinden voor Aspose.Page for Java?**  
A: Bekijk de [documentation](https://reference.aspose.com/page/java/) voor uitgebreide tutorials en voorbeelden.

**Q: Is Aspose.Page for Java geschikt voor grootschalige projecten?**  
A: Absoluut, Aspose.Page for Java is ontworpen om grootschalige projecten efficiënt te verwerken, met robuuste mogelijkheden voor documentmanipulatie.

## Conclusie
In deze gids hebben we laten zien hoe **Aspose.Page for Java** het eenvoudig maakt om **benoemde waarden toe te voegen aan XMP‑metadata** binnen EPS‑bestanden. Met de bovenstaande stappen kun je je documenten verrijken met aangepaste metadata, de doorzoekbaarheid verbeteren en slimmere downstream‑verwerking mogelijk maken.

---

**Last Updated:** 2026-09-19  
**Getest met:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe XMP-namespace toe te voegen aan EPS-bestanden met Aspose.Page – Java Tutorial](/page/java/xmp-metadata-manipulation/add-namespace/)
- [XMP-metadata toevoegen aan EPS-bestanden met Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [XMP lezen met Aspose.Page – Java-gids](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
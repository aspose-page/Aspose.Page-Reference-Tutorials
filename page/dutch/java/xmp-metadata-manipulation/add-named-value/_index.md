---
date: 2026-05-05
description: Leer hoe u XMP‑naamwaarden aan EPS‑bestanden kunt toevoegen met Aspose.Page
  voor Java – een stapsgewijze handleiding met codevoorbeelden.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Genamde waarde toevoegen in XMP met Java
second_title: Aspose.Page Java API
title: Hoe een XMP‑naamwaarde toe te voegen aan EPS‑bestanden met Java
url: /nl/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een benoemde waarde toe aan XMP-metadata met Java

## Introductie
In moderne Java-ontwikkeling is het leren **hoe XMP**-metadata toe te voegen aan EPS-bestanden essentieel voor het behouden van de documentherkomst en het verbeteren van de doorzoekbaarheid. Met **asp** (Aspose.Page for Java) kun je moeiteloos aangepaste benoemde waarden in het XMP-pakket injecteren. Deze tutorial leidt je stap voor stap door de exacte procedures — compleet met codefragmenten — zodat je vandaag nog XMP-metadata aan je EPS-documenten kunt toevoegen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java (asp)  
- **Welk bestandstype is het doel?** EPS-bestanden met XMP-metadata  
- **Primaire gebruikssituatie?** Aangepaste benoemde waarden toevoegen (bijv. paginagroottebeperkingen) aan XMP  
- **Voorvereisten?** JDK 8+ en de Aspose.Page for Java-bibliotheek  
- **Typische implementatietijd?** 5–10 minuten zodra de bibliotheek is ingesteld  

## Wat is asp?
*asp* is de afkorting voor **Aspose**, een familie van .NET- en Java-API's die documentverwerking vereenvoudigen. De Aspose.Page for Java-component stelt je in staat PostScript- en EPS-bestanden te maken, bewerken en converteren, terwijl je volledige programmatische toegang krijgt tot hun metadata, inclusief XMP.

## Waarom benoemde waarden toevoegen aan XMP-metadata?
- **Zoekmachinevriendelijkheid:** Aangepaste tags verbeteren de vindbaarheid.  
- **Workflow-automatisering:** Downstream-tools kunnen je aangepaste waarden lezen om beslissingen te nemen.  
- **Naleving:** Regelgevende informatie direct in het documentpakket opnemen.  

## Waarom dit belangrijk is
Het toevoegen van benoemde waarden aan XMP stelt je in staat willekeurige sleutel‑waardeparen op te slaan die gelezen kunnen worden zonder het hele EPS-bestand te parseren. Deze mogelijkheid is vooral waardevol in geautomatiseerde publicatie‑pijplijnen, digitale asset‑managementsystemen en compliance‑gedreven workflows waar metadata downstream‑acties aanstuurt.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- **Java Development Kit (JDK):** Een recente JDK (8 of hoger) geïnstalleerd **op je machine**.  
- **Aspose.Page for Java Library:** Download deze van de officiële [download link](https://releases.aspose.com/page/java/). Voeg de JAR **toe aan je** project‑classpath.  
- **Een EPS‑bestand** dat al **XMP-metadata** bevat of **automatisch** zal genereren.

## Pakketten importeren
Begin met het importeren van de benodigde Java‑pakketten. Deze imports geven je toegang tot bestandsstromen, het EPS‑documentmodel en XMP‑verwerkingsklassen.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Hoe XMP-benoemde waarde toevoegen in EPS-bestanden met Java
Hieronder vind je een beknopte, genummerde walkthrough die precies laat zien **hoe XMP**‑benoemde waarden aan een EPS‑document toe te voegen.

### Stap 1: Input EPS-bestandsstroom initialiseren
Laad het bron‑EPS‑bestand in een `FileInputStream`. Deze stroom levert het document aan de API van Aspose.

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

### Stap 2: XMP-metadata verkrijgen
Haal het bestaande XMP‑pakket op. Als het EPS‑bestand er geen heeft, maakt Aspose een nieuw XMP‑object aan, gevuld vanuit de PS‑commentaren.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Stap 3: Benoemde waarde toevoegen
Voeg een aangepaste benoemde waarde toe aan de XMP‑structuur. In dit voorbeeld voegen we een nieuwe sleutel toe onder de `xmpTPg:MaxPageSize`‑namespace.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Waarom dit belangrijk is:** Benoemde waarden laten je willekeurige sleutel‑waardeparen opslaan die downstream‑applicaties kunnen lezen zonder het volledige document te parseren.

### Stap 4: Output EPS-bestandsstroom initialiseren
Bereid een `FileOutputStream` voor waarin de gewijzigde EPS wordt opgeslagen.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Stap 5: Document opslaan
Sla de wijzigingen op. De `save`‑aanroep schrijft het bijgewerkte XMP‑pakket terug naar het EPS‑bestand.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Stap 6: Input EPS-stroom sluiten
Vrijgeven van de oorspronkelijke bestandshandle om resource‑lekken te voorkomen.

```java
psStream.close();
```

Door deze zes stappen te volgen, heb je met succes **een benoemde waarde toegevoegd aan XMP-metadata** met **asp** (Aspose.Page for Java).

## Veelvoorkomende problemen & oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `NullPointerException` on `xmp` | EPS‑bestand heeft geen XMP en Aspose kon er geen genereren | Zorg ervoor dat het EPS‑bestand minstens één PS‑commentaar bevat of maak handmatig een nieuw `XmpMetadata`‑object aan. |
| Output file is empty | Output stream not flushed/closed | Controleer of `outPsStream.close()` wordt aangeroepen in een `finally`‑blok (zoals getoond). |
| Duplicate key error | Same named value added twice | Controleer of de sleutel al bestaat met `xmp.containsNamedValue(...)` voordat je toevoegt. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java is ontworpen om naadloos samen te werken met andere Java‑bibliotheken, waardoor je flexibiliteit krijgt in je ontwikkelomgeving.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie van Aspose.Page for Java [hier](https://releases.aspose.com/) verkrijgen.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Bezoek [deze link](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor Aspose.Page for Java te verkrijgen.

**Q: Waar kan ik meer tutorials en voorbeelden vinden voor Aspose.Page for Java?**  
A: Bekijk de [documentatie](https://reference.aspose.com/page/java/) voor uitgebreide tutorials en voorbeelden.

**Q: Is Aspose.Page for Java geschikt voor grootschalige projecten?**  
A: Absoluut, Aspose.Page for Java is ontworpen om grootschalige projecten efficiënt te verwerken, met robuuste mogelijkheden voor documentmanipulatie.

## Conclusie
In deze gids hebben we laten zien hoe **asp** (Aspose.Page for Java) het eenvoudig maakt om **benoemde waarden toe te voegen aan XMP-metadata** binnen EPS‑bestanden. Met de bovenstaande stappen kun je je documenten verrijken met aangepaste metadata, de doorzoekbaarheid verbeteren en slimmere downstream‑verwerking mogelijk maken.

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
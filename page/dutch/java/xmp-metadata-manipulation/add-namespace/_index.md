---
date: 2026-03-08
description: Leer hoe u XMP-namespace toevoegt aan EPS‑bestanden met Aspose.Page voor
  Java – een stapsgewijze tutorial over het toevoegen van XMP en XMP-namespace, Java‑gids.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Hoe XMP-namespace toe te voegen aan EPS-bestanden met Aspose.Page – Java-tutorial
url: /nl/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe XMP-namespace toevoegen aan EPS-bestanden met Aspose.Page – Java Tutorial

Als u de metadata van EPS‑bestanden moet wijzigen of verrijken, laat deze **how to add xmp** tutorial u precies zien hoe u een XMP‑namespace kunt toevoegen met Java en Aspose.Page. Aan het einde van de gids heeft u een herbruikbaar patroon voor het injecteren van aangepaste metadata in elk EPS‑document.

## Snelle antwoorden
- **Wat is het primaire doel?** Voeg een aangepaste XMP-namespace en eigenschap toe aan een EPS‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java.  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoeveel code‑wijzigingen zijn nodig?** Slechts vijf korte code‑fragmenten—één voor elke stap.  
- **Kan ik dit patroon hergebruiken voor andere namespaces?** Ja, wijzig gewoon de prefix en URI in de `registerNamespaceURI`‑aanroep.

## Wat is een XMP-namespace?

Een XMP (Extensible Metadata Platform) namespace is een unieke identifier die gerelateerde metadata‑eigenschappen groepeert onder een gemeenschappelijke URI. Het registreren van een namespace stelt u in staat aangepaste gegevens—zoals propriëtaire tags—op te slaan zonder conflicten met bestaande standaarden.

## Waarom Aspose.Page gebruiken voor XMP-manipulatie?

- **Volledige controle** over EPS‑ en PDF‑metadata zonder Adobe‑tools.  
- **Automatische creatie** van XMP‑blokken wanneer deze ontbreken, gebaseerd op PS‑commentaren.  
- **Cross‑platform Java‑ondersteuning**, waardoor het eenvoudig is om te integreren in bestaande pipelines.

## Prerequisites

- Aspose.Page for Java: Zorg ervoor dat u de bibliotheek geïnstalleerd heeft. U kunt deze downloaden [hier](https://releases.aspose.com/page/java/).  
- Java Development Environment: Installeer een Java‑omgeving op uw systeem.  
- Documentbestand: Zorg voor een EPS‑bestand met XMP‑metadata. Als het geen XMP‑metadata bevat, maakt de bibliotheek er een aan op basis van PS‑metadata‑commentaren.

## Pakketten importeren

To start, import the necessary packages into your Java project:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Stap 1: XMP-metadata ophalen

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### Waarom dit belangrijk is
Het ophalen van het `XmpMetadata`‑object geeft u een live referentie naar de metadata van het document, waardoor u deze kunt lezen, wijzigen of uitbreiden vóór het opslaan.

## Stap 2: Nieuwe namespace registreren *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Uitleg
De `registerNamespaceURI`‑methode koppelt een korte prefix (`tmp`) aan een volledige URI. Deze stap is essentieel voor de volgende bewerking omdat XMP‑eigenschappen moeten worden gekwalificeerd met een geregistreerde namespace.

## Stap 3: Nieuwe eigenschap toevoegen

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### Wat gebeurt er?
Hier maken we een aangepaste eigenschap genaamd `tmp:newKey` en wijzen we de waarde "NewValue" toe. U kunt de sleutel en waarde vervangen door iets dat past bij uw bedrijfslogica.

## Stap 4: Document opslaan

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Tip
Omhul altijd de `save`‑aanroep in een `try/finally`‑blok (of gebruik try‑with‑resources) om te garanderen dat de output‑stream wordt gesloten, zelfs als er een uitzondering optreedt.

## Stap 5: Streams sluiten

```java
// Close input EPS stream
psStream.close();
```

### Best practice
Het sluiten van de input‑stream geeft de bestands‑handle direct vrij, waardoor bestands‑lockproblemen op Windows‑systemen worden voorkomen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Geen XMP‑blok verschijnt na het opslaan | Originele EPS bevatte geen XMP en commentaren waren onvoldoende | Zorg ervoor dat de EPS standaard PS‑commentaren (`%%Creator`, `%%Title`, etc.) bevat of maak handmatig een leeg `XmpMetadata`‑object aan voordat u een namespace registreert. |
| `registerNamespaceURI` geeft een uitzondering | Prefix al in gebruik | Kies een unieke prefix of controleer bestaande namespaces via `xmp.getRegisteredNamespaces()`. |
| Opgeslagen bestand is beschadigd | Output‑stream niet geflusht | Gebruik `try‑with‑resources` of roep expliciet `outPsStream.flush()` aan vóór het sluiten. |

## Conclusie

Door deze **how to add xmp** tutorial te volgen, heeft u nu een herhaalbare methode om aangepaste namespaces en eigenschappen toe te voegen aan EPS‑bestanden met Aspose.Page for Java. Deze mogelijkheid opent de deur naar rijkere metadata‑strategieën—of u nu workflow‑identifiers, propriëtaire tags of integratie‑gegevens voor downstream‑systemen embedt.

## Veelgestelde vragen

### Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?
Aspose.Page ondersteunt voornamelijk Java, maar er zijn versies beschikbaar voor andere talen zoals .NET.

### Is er een gratis proefversie beschikbaar?
Ja, u kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/).

### Waar kan ik uitgebreide documentatie vinden?
Raadpleeg de documentatie [hier](https://reference.aspose.com/page/java/).

### Hoe kan ik een tijdelijke licentie verkrijgen?
U kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### Zijn er community‑forums voor Aspose.Page?
Ja, u kunt deelnemen aan de community op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**Laatst bijgewerkt:** 2026-03-08  
**Getest met:** Aspose.Page for Java 24.10 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
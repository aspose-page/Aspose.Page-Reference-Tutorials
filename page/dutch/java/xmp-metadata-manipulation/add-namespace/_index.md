---
date: 2025-12-20
description: Leer hoe u XMP-namespace toevoegt in EPS-bestanden met Aspose.Page voor
  Java in deze uitgebreide aspose.page XMP-tutorial.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page XMP-tutorial – Namespace toevoegen in XMP met Java
url: /nl/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutorial – Namespace toevoegen in XMP met Java

## Inleiding

Als je de metadata van EPS‑bestanden moet wijzigen of verrijken, laat de **aspose.page xmp tutorial** je precies zien **hoe je een XMP‑namespace toevoegt** met Java. In deze gids lopen we elke stap door – beginnend met het laden van een EPS‑document, het registreren van een aangepaste namespace, het invoegen van een nieuwe eigenschap en tenslotte het opslaan van het bijgewerkte bestand. Aan het einde heb je een duidelijk, herbruikbaar patroon voor het werken met XMP‑metadata in elk Aspose.Page‑geactiveerd Java‑project.

## Snelle antwoorden
- **Wat is het primaire doel?** Een aangepaste XMP‑namespace en eigenschap toevoegen aan een EPS‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java.  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoeveel code‑wijzigingen zijn nodig?** Slechts vijf korte code‑fragmenten – één voor elke stap.  
- **Kan ik dit patroon hergebruiken voor andere namespaces?** Ja, wijzig gewoon het prefix en de URI in de `registerNamespaceURI`‑aanroep.

## Wat is een XMP‑namespace?

Een XMP (Extensible Metadata Platform)‑namespace is een unieke identifier die gerelateerde metadata‑eigenschappen groepeert onder een gemeenschappelijke URI. Het registreren van een namespace stelt je in staat om aangepaste gegevens – zoals propriëtaire tags – op te slaan zonder conflicten met bestaande standaarden.

## Waarom Aspose.Page gebruiken voor XMP‑manipulatie?

- **Volledige controle** over EPS‑ en PDF‑metadata zonder Adobe‑tools.  
- **Automatische creatie** van XMP‑blokken wanneer deze ontbreken, gebaseerd op PS‑commentaren.  
- **Cross‑platform Java‑ondersteuning**, waardoor integratie in bestaande pipelines eenvoudig is.

## Voorvereisten

- Aspose.Page for Java: Zorg dat je de bibliotheek geïnstalleerd hebt. Je kunt deze downloaden [hier](https://releases.aspose.com/page/java/).  
- Java‑ontwikkelomgeving: Stel een Java‑omgeving in op je systeem.  
- Documentbestand: Heb een EPS‑bestand met XMP‑metadata. Als het geen XMP‑metadata bevat, maakt de bibliotheek er één aan op basis van PS‑metadata‑commentaren.

## Pakketten importeren

Om te beginnen, importeer de benodigde pakketten in je Java‑project:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Stap 1: XMP‑metadata ophalen

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
Het ophalen van het `XmpMetadata`‑object geeft je een live‑handle naar de metadata van het document, zodat je deze kunt lezen, wijzigen of uitbreiden vóór het opslaan.

## Stap 2: Nieuwe namespace registreren *(hoe een xmp‑namespace toe te voegen)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Uitleg
De `registerNamespaceURI`‑methode koppelt een kort prefix (`tmp`) aan een volledige URI. Deze stap is essentieel voor de volgende bewerking omdat XMP‑eigenschappen moeten worden gekwalificeerd met een geregistreerde namespace.

## Stap 3: Nieuwe eigenschap toevoegen

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### Wat gebeurt er?
Hier maken we een aangepaste eigenschap `tmp:newKey` aan en wijzen we de waarde `"NewValue"` toe. Je kunt de sleutel en waarde vervangen door wat dan ook dat past bij je bedrijfslogica.

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
Omring de `save`‑aanroep altijd met een `try/finally`‑blok (of gebruik try‑with‑resources) om te garanderen dat de output‑stream wordt gesloten, zelfs als er een uitzondering optreedt.

## Stap 5: Streams sluiten

```java
// Close input EPS stream
psStream.close();
```

### Best practice
Het sluiten van de input‑stream maakt de bestands­handle direct vrij, waardoor bestands‑lock‑problemen op Windows‑systemen worden voorkomen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Er verschijnt geen XMP‑blok na het opslaan | Originele EPS bevatte geen XMP en commentaren waren onvoldoende | Zorg dat de EPS standaard PS‑commentaren bevat (`%%Creator`, `%%Title`, etc.) of maak handmatig een leeg `XmpMetadata`‑object aan vóór het registreren van een namespace. |
| `registerNamespaceURI` geeft een uitzondering | Prefix al in gebruik | Kies een uniek prefix of controleer bestaande namespaces via `xmp.getRegisteredNamespaces()`. |
| Opgeslagen bestand is corrupt | Output‑stream niet geflusht | Gebruik `try‑with‑resources` of roep expliciet `outPsStream.flush()` aan vóór het sluiten. |

## Conclusie

Door deze **aspose.page xmp tutorial** te volgen, heb je nu een herhaalbare methode om aangepaste namespaces en eigenschappen toe te voegen aan EPS‑bestanden met Aspose.Page for Java. Deze mogelijkheid opent de deur naar rijkere metadata‑strategieën – of je nu workflow‑identifiers, propriëtaire tags of integratiedata voor downstream‑systemen wilt embedden.

## Veelgestelde vragen

### Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?
Aspose.Page ondersteunt voornamelijk Java, maar er zijn versies beschikbaar voor andere talen zoals .NET.

### Is er een gratis proefversie beschikbaar?
Ja, je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/).

### Waar vind ik uitgebreide documentatie?
Raadpleeg de documentatie [hier](https://reference.aspose.com/page/java/).

### Hoe kan ik een tijdelijke licentie verkrijgen?
Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### Zijn er community‑forums voor Aspose.Page?
Ja, je kunt deelnemen aan de community op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.Page for Java 23.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
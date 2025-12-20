---
date: 2025-12-20
description: Leer hoe u XMP‑metadata in EPS‑bestanden maakt met Aspose.Page voor Java.
  Stapsgewijze handleiding om eenvoudig XMP‑eigenschappen programmatisch toe te voegen.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Hoe maak je xmp-metadata eps met Java
url: /nl/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg eenvoudige eigenschappen toe in XMP met Java

## Introductie
In moderne documentworkflows geeft de mogelijkheid om **XMP‑metadata EPS**‑bestanden programmatisch te maken je volledige controle over hoe je graphics worden beschreven, doorzocht en gearchiveerd. Met Aspose.Page voor Java kun je XMP‑pakketten in EPS‑documenten lezen, wijzigen en schrijven zonder de Java‑omgeving te verlaten. In deze tutorial lopen we stap voor stap door hoe je eenvoudige XMP‑eigenschappen aan een EPS‑bestand toevoegt, zodat je je graphics snel en betrouwbaar kunt verrijken met aangepaste metadata.

## Snelle antwoorden
- **Wat betekent “create xmp metadata eps”?** Een XMP‑pakket (XML‑gebaseerde metadata) toevoegen aan een EPS‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Page voor Java (downloadbaar vanaf de Aspose‑site).  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoeveel regels code?** Minder dan 30 regels Java plus een paar import‑verklaringen.  
- **Kan ik andere gegevenstypen toevoegen?** Ja – datums, gehele getallen, doubles, strings en zelfs arrays worden ondersteund.

## Wat is create xmp metadata eps?
XMP (Extensible Metadata Platform) is een standaard voor het insluiten van rijke metadata in bestanden. Wanneer je **XMP‑metadata EPS** maakt, embed je een XML‑pakket in een EPS‑ (Encapsulated PostScript) document, waardoor downstream‑applicaties auteur, aanmaakdatum, aangepaste tags en meer kunnen lezen.

## Waarom XMP‑metadata toevoegen aan EPS‑bestanden?
- **Zoekbaarheid:** Maakt automatische indexering door DAM‑systemen mogelijk.  
- **Naleving:** Slaat juridische of licentie‑informatie direct in het bestand op.  
- **Automatisering:** Laat downstream‑pijplijnen beslissingen nemen op basis van ingebedde data.  
- **Portabiliteit:** De metadata reist mee met de EPS, waardoor consistentie over platformen heen wordt gegarandeerd.

## Voorvereisten
Zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page voor Java‑bibliotheek geïnstalleerd. Je kunt het **[hier](https://releases.aspose.com/page/java/)** downloaden.  
- Een voorbeeld‑EPS‑bestand met metadata. Als je er geen hebt, kun je het meegeleverde **`xmp3.eps`**‑bestand gebruiken.

## Importpakketten
Importeer eerst de klassen die je nodig hebt. De imports blijven exact hetzelfde als in het originele voorbeeld:

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

## Stap 1: Laad het EPS‑document en haal XMP‑metadata op
We openen het EPS‑bestand, maken een `PsDocument`‑instantie aan en halen (of maken) het XMP‑pakket op.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 2: Voeg een datum‑eigenschap toe
Een datum toevoegen is zo simpel als een `Date`‑object maken en deze in de XMP‑map plaatsen.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Stap 3: Voeg een integer‑eigenschap toe
Je kunt numerieke identifiers of versienummers opslaan met een integer‑waarde.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Stap 4: Voeg een double‑eigenschap toe
Floating‑point getallen zijn handig voor metingen of beoordelingen.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Stap 5: Voeg een string‑eigenschap toe
Aangepaste teksttags (bijv. projectcodes) worden opgeslagen als strings.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Stap 6: Sla het bijgewerkte EPS‑bestand op
Nadat alle eigenschappen zijn toegevoegd, schrijf je het document terug naar de schijf.

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

## Stap 7: Ruim bronnen op
Sluit altijd de invoerstroom om lekken van bestands‑handles te voorkomen.

```java
// Close input EPS stream
psStream.close();
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Null XMP‑metadata** | Het EPS‑bestand bevatte geen XMP‑pakket en de bibliotheek kon geen PS‑commentaren afleiden. | Zorg ervoor dat de bron‑EPS minstens één PS‑commentaar bevat (bijv. `%%Creator`). De bibliotheek genereert automatisch een minimaal XMP‑pakket. |
| **Tijdzone‑mismatch** | Datums verschijnen verschoven wanneer ze in een andere applicatie worden geopend. | Stel `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` in vóór het aanmaken van het `Date`‑object, zoals getoond in Stap 2. |
| **Licentie‑exception** | Runtime gooit `LicenseException`. | Pas een geldige Aspose.Page‑licentie toe vóór het gebruik van de API, of werk in proefmodus voor evaluatie. |

## Conclusie
Door deze stappen te volgen weet je nu hoe je **XMP‑metadata EPS**‑bestanden maakt met Aspose.Page voor Java. Het toevoegen van eenvoudige eigenschappen zoals datums, integers, doubles en strings is eenvoudig, en de resulterende EPS‑bestanden bevatten rijke, doorzoekbare metadata die elke downstream‑workflow ten goede komt.

## Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
Aspose.Page ondersteunt voornamelijk Java, maar er zijn versies beschikbaar voor andere talen zoals .NET.

### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, je kunt de functies van Aspose.Page verkennen door een gratis proefversie te verkrijgen **[hier](https://releases.aspose.com/)**.

### Waar vind ik gedetailleerde documentatie voor Aspose.Page voor Java?
De documentatie is beschikbaar **[hier](https://reference.aspose.com/page/java/)**.

### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor Java?
Een tijdelijke licentie kan worden verkregen **[hier](https://purchase.aspose.com/temporary-license/)**.

### Waar kan ik Aspose.Page voor Java kopen?
Je kunt het product aanschaffen **[hier](https://purchase.aspose.com/buy)**.

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.Page voor Java 24.11 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
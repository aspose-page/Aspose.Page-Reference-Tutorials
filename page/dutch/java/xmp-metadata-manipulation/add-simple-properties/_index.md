---
date: 2026-05-20
description: Leer hoe je XMP-metadata aan EPS-bestanden kunt toevoegen met Aspose.Page
  for Java. Stapsgewijze handleiding om eenvoudige XMP-eigenschappen programmatisch
  in te sluiten.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Eenvoudige eigenschappen in XMP toevoegen met Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP-metadata toevoegen aan EPS-bestanden met Java
url: /nl/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP-metadata toevoegen aan EPS-bestanden met Java

## Inleiding
In moderne grafische pipelines biedt de mogelijkheid om **XMP-metadata toe te voegen** aan EPS-bestanden via code volledige controle over hoe uw illustraties worden beschreven, doorzocht en gearchiveerd. Met Aspose.Page for Java kunt u XMP‑pakketten in EPS‑documenten lezen, wijzigen en schrijven zonder de Java‑omgeving te verlaten. In deze tutorial leiden we u stap voor stap door het toevoegen van eenvoudige XMP‑eigenschappen aan een EPS‑bestand, zodat u uw graphics snel en betrouwbaar kunt verrijken met aangepaste metadata.

## Snelle antwoorden
- **Wat betekent “add XMP metadata to EPS”?** Het insluiten van een XMP‑pakket (XML‑gebaseerde metadata) in een EPS‑bestand.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (downloadbaar vanaf de Aspose‑site).  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoeveel regels code?** Minder dan 30 regels Java plus een paar import‑verklaringen.  
- **Kan ik andere gegevenstypen toevoegen?** Ja – datums, gehele getallen, doubles, strings en zelfs arrays worden ondersteund.

## Hoe XMP-metadata toevoegen aan EPS-bestanden met Java?
Laad het EPS‑bestand met `new PsDocument("input.eps")`, haal het XMP‑pakket op of maak er een aan, voeg de gewenste eigenschappen toe en sla vervolgens het document op schijf – alles in minder dan tien regels Java‑code. Deze aanpak stelt u in staat doorzoekbare, aan standaarden conforme metadata in te sluiten zonder handmatige bewerking van de EPS‑bron.

## Wat is XMP-metadata in EPS?
XMP-metadata in EPS is een XML‑pakket dat zich binnen het EPS‑bestand bevindt en informatie opslaat zoals auteur, aanmaakdatum en aangepaste tags. Het insluiten van dit pakket stelt downstream‑tools in staat de gegevens te lezen en erop te reageren zonder aparte side‑car‑bestanden.

## Waarom XMP-metadata toevoegen aan EPS-bestanden?
Het insluiten van XMP-metadata maakt EPS‑assets direct doorzoekbaar, zorgt voor naleving door licentie‑informatie in het bestand op te slaan, stelt geautomatiseerde pipelines in staat beslissingen te nemen op basis van ingesloten tags, en garandeert dat de metadata met de afbeelding meereist over alle platforms. Aspose.Page kan bestanden tot 500 MB verwerken zonder het volledige document in het geheugen te laden, wat snelle prestaties levert voor grootschalige workloads.

## Vereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:

- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. U kunt deze **[hier](https://releases.aspose.com/page/java/)** downloaden.  
- Een voorbeeld‑EPS‑bestand met metadata. Als u er geen heeft, kunt u gerust het meegeleverde **`xmp3.eps`**‑bestand gebruiken.

## Pakketten importeren
Eerst importeert u de klassen die u nodig heeft. De import‑verklaringen blijven precies hetzelfde als in het originele voorbeeld:

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
De `PsDocument`‑klasse vertegenwoordigt een EPS‑bestand en biedt methoden om toegang te krijgen tot de inhoud en metadata.  
Het `XmpMetadata`‑object bevat het XMP‑pakket dat aan het document is gekoppeld.

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
De `Date`‑klasse vertegenwoordigt een specifiek moment in de tijd, met millisecondenprecisie.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Stap 3: Voeg een integer‑eigenschap toe
De `Integer`‑klasse verpakt een primitieve `int`‑waarde als een object.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Stap 4: Voeg een double‑eigenschap toe
De `Double`‑klasse verpakt een primitieve `double`‑waarde als een object.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Stap 5: Voeg een string‑eigenschap toe
De `String`‑klasse vertegenwoordigt een reeks tekens.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Stap 6: Sla het bijgewerkte EPS‑bestand op
De `save`‑methode schrijft het gewijzigde document terug naar schijf, waarbij de EPS‑structuur behouden blijft.

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
Sluit altijd streams om lekken van bestands‑handles te voorkomen en zorg ervoor dat alle buffers worden leeggemaakt.

```java
// Close input EPS stream
psStream.close();
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Null XMP-metadata** | Het EPS‑bestand had geen XMP‑pakket en de bibliotheek kon geen PS‑commentaren afleiden. | Zorg ervoor dat het bron‑EPS minstens één PS‑commentaar bevat (bijv. `%%Creator`). De bibliotheek zal automatisch een minimaal XMP‑pakket genereren. |
| **Tijdzone‑mismatch** | Datums lijken verschoven wanneer geopend in een andere applicatie. | Stel `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` in voordat het `Date`‑object wordt aangemaakt, zoals getoond in Stap 2. |
| **Licentie‑exceptie** | Runtime gooit `LicenseException`. | Pas een geldige Aspose.Page‑licentie toe voordat u de API gebruikt, of voer uit in proefmodus voor evaluatie. |

## Veelgestelde vragen
**Q:** Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?  
**A:** Aspose.Page ondersteunt voornamelijk Java, maar equivalente bibliotheken zijn beschikbaar voor .NET, C++ en Python.

**Q:** Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?  
**A:** Ja, u kunt de functies van Aspose.Page verkennen door een gratis proefversie te verkrijgen **[hier](https://releases.aspose.com/)**.

**Q:** Waar kan ik gedetailleerde documentatie vinden voor Aspose.Page for Java?  
**A:** De documentatie is beschikbaar **[hier](https://reference.aspose.com/page/java/)**.

**Q:** Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page for Java?  
**A:** Een tijdelijke licentie kan worden verkregen **[hier](https://purchase.aspose.com/temporary-license/)**.

**Q:** Waar kan ik Aspose.Page for Java kopen?  
**A:** U kunt het product aanschaffen **[hier](https://purchase.aspose.com/buy)**.

---

**Laatst bijgewerkt:** 2026-05-20  
**Getest met:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe XMP-metadata lezen met Java – Aspose.Page-gids](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp-tutorial – Namespace toevoegen in XMP met Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Array‑items toevoegen in XMP-metadata met Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
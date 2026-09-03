---
date: 2026-05-25
description: Leer hoe je XMP kunt lezen met Aspose.Page in Java. Deze stapsgewijze
  gids laat zien hoe je XMP-metadata, makerinformatie, tijdstempels, miniaturen en
  meer kunt extraheren.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Hoe XMP-metadata lezen met Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP lezen met Aspose.Page – Java-gids
url: /nl/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadata ophalen van XMP met Java

## Hoe XMP lezen met Aspose.Page (Java)?

Laad het EPS‑bestand met `new Document("file.eps")` — de `Document`‑klasse vertegenwoordigt een geladen bestand. Roep `getXmpMetadata()` aan, die het XMP‑pakket extraheert, en query vervolgens het geretourneerde `XmpMetadata`‑object — een map‑achtige interface voor XMP‑eigenschappen — om de benodigde sleutels op te halen. Dit is alles wat nodig is om XMP te lezen met Aspose.Page. De API abstraheert de low‑level parsing, zodat je in slechts twee regels code een kant‑klaar map van eigenschappen krijgt.

Welkom bij onze stapsgewijze tutorial die laat zien **hoe XMP**‑metadata te lezen met Java en de Aspose.Page‑bibliotheek. XMP (Extensible Metadata Platform) is een breed geaccepteerde standaard voor het insluiten van rijke metadata in documenten. Aan het einde van deze gids kun je XMP van documentformaten lezen, makerinformatie, tijdstempels, miniaturen en meer ophalen — waardoor je slimmere document‑analyseoplossingen kunt bouwen.

## Snelle antwoorden
- **Wat betekent “read XMP”?** Het betekent het programmatisch extraheren van het XMP‑pakket dat metadata opslaat binnen een bestand.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (download vanaf de officiële pagina [here](https://releases.aspose.com/page/java/)).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik XMP lezen van andere formaten?** Ja – Aspose.Page extraheert XMP uit EPS, PDF, JPEG, PNG en meer dan 20 andere formaten.

## Vereisten
Before diving into the code, make sure you have:

- **Java Development Kit (JDK)** – Java 8+ geïnstalleerd en geconfigureerd op uw machine.  
- **Aspose.Page for Java** – Download de bibliotheek van de officiële site [here](https://releases.aspose.com/page/java/).  
- Een EPS‑bestand dat XMP‑metadata bevat (bijv. `xmp1.eps`).  

## Pakketten importeren
De `XmpMetadata`‑klasse bevindt zich in de `com.aspose.page.xmp`‑namespace, terwijl de `Document`‑klasse in `com.aspose.page` zit. Importeer beide zodat u met het EPS‑bestand en de metadata kunt werken.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Stap 1: Input EPS‑bestandstream initialiseren
Begin met het instellen van het pad naar uw documentmap en het initialiseren van de input‑EPS‑bestandstream.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Stap 2: XMP‑metadata ophalen
`XmpMetadata` is het object van Aspose.Page dat het uit een document geëxtraheerde XMP‑pakket bevat. Haal het op met `document.getXmpMetadata()`. Als het bestand geen XMP bevat, genereert de API een minimaal pakket op basis van bestaande PostScript‑commentaren.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 3: CreatorTool‑informatie extraheren
De `CreatorTool`‑sleutel bevindt zich onder de `xmp`‑namespace en registreert de applicatie die het bestand heeft gegenereerd. Controleer of deze aanwezig is en druk de waarde af.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Stap 4: CreateDate‑informatie extraheren
`CreateDate` slaat de tijdstempel op wanneer het document oorspronkelijk is aangemaakt. Gebruik hetzelfde `containsKey`/`get`‑patroon om het te lezen.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Stap 5: Thumbnail‑breedte ophalen
Als miniaturen bestaan, bevat de `xmp:Thumbnails`‑array een of meer items. Elk item bevat `width`, `height` en binaire data. Het voorbeeld haalt de breedte van de eerste miniatuur op.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Stap 6: Formaat‑informatie extraheren
De `format`‑sleutel geeft het oorspronkelijke bestandsformaat weer (bijv. “application/postscript”). Dit is handig wanneer u bron‑typen moet loggen of valideren.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Stap 7: DocumentID ophalen
`DocumentID` is een unieke identifier die door de maker‑applicatie wordt toegewezen. Het kan worden gebruikt voor deduplicatie in grote asset‑bibliotheken.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Waarom dit belangrijk is
Aspose.Page kan XMP lezen uit **20+** bestandsformaten en verwerkt documenten tot **500 MB** zonder het volledige bestand in het geheugen te laden, waardoor u snelle, low‑overhead toegang tot essentiële metadata krijgt. Deze mogelijkheid is cruciaal voor batch‑verwerkingspijplijnen, digitale asset‑managementsystemen en elke oplossing die afhankelijk is van doorzoekbare, machinaal leesbare documenteigenschappen.

## Veelvoorkomende valkuilen & tips
- **Missing XMP:** Sommige EPS‑bestanden bevatten mogelijk geen XMP. De `getXmpMetadata()`‑aanroep genereert een minimale set op basis van bestaande PS‑commentaren, maar u krijgt geen volledige metadata tenzij deze is ingebed.  
- **Thumbnail‑arrays:** De `xmp:Thumbnails`‑sleutel kan meerdere items bevatten. Het voorbeeld haalt alleen de eerste op; doorloop de array als u alle miniaturen nodig heeft.  
- **Namespace‑bewustzijn:** XMP‑sleutels gebruiken namespaces (bijv. `xmp:`, `dc:`). Zorg ervoor dat u de exacte sleutelnaam gebruikt; anders zal `containsKey` false retourneren.  

## Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
Ja, Aspose.Page ondersteunt Java, .NET en verschillende andere talen. Zie de volledige lijst in de [documentation](https://reference.aspose.com/page/java/).

### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, u kunt de gratis proefversie [here](https://releases.aspose.com/).

### Waar kan ik ondersteuning vinden voor Aspose.Page voor Java?
Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑hulp en officiële ondersteuning.

### Hoe verkrijg ik een tijdelijke licentie voor Aspose.Page voor Java?
U kunt een tijdelijke licentie krijgen [here](https://purchase.aspose.com/temporary-license/).

### Zijn er extra bronnen voor Aspose.Page voor Java?
Bekijk de volledige [documentation](https://reference.aspose.com/page/java/) en download de bibliotheek [here](https://releases.aspose.com/page/java/).

## Aanvullende FAQ
**Q: Werkt deze aanpak met PDF‑bestanden die XMP bevatten?**  
A: Ja, Aspose.Page kan XMP lezen uit PDF, EPS en verschillende beeldformaten.

**Q: Kan ik XMP‑metadata wijzigen na het lezen?**  
A: Absoluut. Het `XmpMetadata`‑object is mutabel; u kunt sleutels toevoegen, bijwerken of verwijderen en vervolgens het document opslaan.

**Q: Is er een manier om alle miniatuur‑afbeeldingen te extraheren, niet alleen de afmetingen?**  
A: U kunt de binaire data ophalen uit de `xmpGImg:data`‑eigenschap van elk miniatuur‑item en deze naar een bestand schrijven.

## Conclusie
U hebt nu beheerst **hoe XMP**‑metadata te lezen met Java en Aspose.Page. Door deze stappen te volgen kunt u maker‑tools, tijdstempels, miniaturen, formaat‑informatie en document‑ID's extraheren — waardoor u volledig inzicht krijgt in de ingebedde metadata van uw EPS‑bestanden. Voel u vrij om te experimenteren met extra XMP‑namespaces om nog rijkere gegevens voor uw toepassingen te verkrijgen.

---

**Laatst bijgewerkt:** 2026-05-25  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Aspose Page Java Tutorial – XMP‑metadata toevoegen aan EPS‑bestanden](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Namespace toevoegen in XMP met Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Naamwaarde wijzigen in XMP met Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
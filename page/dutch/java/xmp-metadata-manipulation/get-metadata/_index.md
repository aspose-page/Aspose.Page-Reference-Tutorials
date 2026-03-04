---
date: 2025-12-21
description: Leer hoe u XMP-metadata kunt lezen met Java en Aspose.Page. Deze stapsgewijze
  handleiding laat u zien hoe u XMP van documentformaten kunt lezen en belangrijke
  eigenschappen kunt extraheren.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hoe XMP-metadata te lezen met Java – Aspose.Page-gids
url: /nl/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadata ophalen uit XMP met Java

## Hoe XMP-metadata lezen met Java

Welkom bij onze stapsgewijze tutorial die laat zien **hoe XMP te lezen** metadata met Java en de Aspose.Page bibliotheek. XMP (Extensible Metadata Platform) is een breed geaccepteerde standaard voor het insluiten van rijke metadata in documenten. Aan het einde van deze gids kun je XMP van documentformaten lezen, makerinformatie, tijdstempels, miniaturen en meer ophalen — waardoor je slimmere document‑analyseoplossingen kunt bouwen.

## Snelle antwoorden
- **Wat betekent “hoe XMP te lezen”?** Het verwijst naar het programmatisch extraheren van XMP-metadata uit bestanden.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (beschikbaar op de Aspose downloadpagina).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Kan ik XMP lezen uit andere formaten?** Ja, Aspose.Page kan EPS, PDF en verschillende afbeeldingsformaten die XMP bevatten verwerken.

## Voorvereisten
Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

- **Java Development Kit (JDK)** – Java 8+ geïnstalleerd en geconfigureerd op je machine.  
- **Aspose.Page for Java** – Download de bibliotheek van de officiële site [here](https://releases.aspose.com/page/java/).  
- Een EPS‑bestand dat XMP-metadata bevat (bijv. `xmp1.eps`).  

## Importeer pakketten
Importeer in je Java‑project de benodigde pakketten:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Stap 1: Initialiseer invoer‑EPS‑bestandstroom
Begin met het instellen van het pad naar je documentmap en het initialiseren van de invoer‑EPS‑bestandstroom.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Stap 2: Haal XMP‑metadata op
Haal XMP‑metadata op uit het EPS‑bestand. Als het bestand geen XMP‑metadata bevat, wordt er een nieuwe aangemaakt met waarden uit PS‑metadata‑commentaren.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 3: Haal CreatorTool‑informatie op
Controleer en print de "CreatorTool"‑waarde uit de XMP‑metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Stap 4: Haal CreateDate‑informatie op
Controleer en print de "CreateDate"‑waarde uit de XMP‑metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Stap 5: Haal thumbnail‑breedte op
Als er miniaturen bestaan, haal dan de breedte van de eerste miniatuur op en print deze.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Stap 6: Haal formaat‑informatie op
Controleer en print de "format"‑waarde uit de XMP‑metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Stap 7: Haal DocumentID op
Controleer en print de "DocumentID"‑waarde uit de XMP‑metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Waarom dit belangrijk is
Het lezen van XMP‑metadata stelt je in staat om programmatisch de oorsprong, aanmaakdatum en andere essentiële attributen van een document te ontdekken zonder het in een viewer te openen. Dit is vooral nuttig voor batchverwerking, content‑managementsystemen en digitale‑asset‑pijplijnen waar metadata de indexering en zoekfunctionaliteit aandrijft.

## Veelvoorkomende valkuilen & tips
- **Ontbrekende XMP:** Sommige EPS‑bestanden bevatten mogelijk geen XMP. De `getXmpMetadata()`‑aanroep zal een minimale set synthetiseren op basis van bestaande PS‑commentaren, maar je krijgt geen volledige metadata tenzij deze is ingebed.  
- **Thumbnail‑arrays:** De sleutel `xmp:Thumbnails` kan meerdere items bevatten. Het voorbeeld haalt alleen de eerste op; doorloop de array als je alle miniaturen nodig hebt.  
- **Namespace‑bewustzijn:** XMP‑sleutels gebruiken namespaces (bijv. `xmp:`, `dc:`). Zorg ervoor dat je de exacte sleutelnaam gebruikt; anders retourneert `containsKey` false.

## Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
Ja, Aspose.Page ondersteunt meerdere talen, waaronder Java, .NET en meer. Bekijk de [documentation](https://reference.aspose.com/page/java/) voor details.

### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

### Waar kan ik ondersteuning vinden voor Aspose.Page voor Java?
Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

### Hoe verkrijg ik een tijdelijke licentie voor Aspose.Page voor Java?
Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

### Zijn er extra bronnen voor Aspose.Page voor Java?
Bekijk de volledige [documentation](https://reference.aspose.com/page/java/) en download de bibliotheek [hier](https://releases.aspose.com/page/java/).

## Aanvullende FAQ
**V: Werkt deze aanpak met PDF‑bestanden die XMP bevatten?**  
A: Ja, Aspose.Page kan XMP lezen uit PDF, EPS en verschillende afbeeldingsformaten.

**V: Kan ik XMP‑metadata wijzigen na het lezen?**  
A: Absoluut. Het `XmpMetadata`‑object is mutabel; je kunt sleutels toevoegen, bijwerken of verwijderen en vervolgens het document opslaan.

**V: Is er een manier om alle thumbnail‑afbeeldingen te extraheren, niet alleen de afmetingen?**  
A: Je kunt de binaire gegevens ophalen uit de `xmpGImg:data`‑eigenschap van elk thumbnail‑item en deze naar een bestand schrijven.

## Conclusie
Je hebt nu **hoe XMP te lezen** metadata onder de knie met Java en Aspose.Page. Door deze stappen te volgen kun je maker‑tools, tijdstempels, miniaturen, formaat‑informatie en document‑ID’s extraheren — waardoor je volledig inzicht krijgt in de ingebedde metadata van je EPS‑bestanden. Voel je vrij om te experimenteren met extra XMP‑namespaces om nog rijkere gegevens voor je toepassingen op te halen.

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

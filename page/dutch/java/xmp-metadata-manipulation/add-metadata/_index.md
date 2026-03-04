---
date: 2025-12-20
description: Leer hoe u XMP-metadata aan EPS‑bestanden kunt toevoegen met de Aspose
  Page Java‑tutorial. Volg deze stapsgewijze gids om uw documentbeheer te verbeteren.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java‑tutorial – XMP‑metadata toevoegen aan EPS‑bestanden
url: /nl/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metagegevens toevoegen in XMP met Java

## Introductie
In deze **aspose page java tutorial** leer je hoe je de metagegevens van je document kunt verbeteren door XMP‑informatie toe te voegen met Java. Deze stap‑voor‑stap gids leidt je door het lezen van een bestaand EPS‑bestand, het extraheren van de XMP‑metagegevens, en het opslaan van de wijzigingen terug naar de schijf met de Aspose.Page for Java‑bibliotheek. Aan het einde van de tutorial heb je een solide, herbruikbaar patroon voor het werken met XMP in elke EPS‑workflow.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik XMP toevoegen aan elk EPS‑bestand?** Ja – de API maakt een nieuw XMP‑blok aan als er nog geen bestaat.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 en later.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een basis‑metagegevensupdate.

## Overzicht van de Aspose Page Java‑tutorial
Deze tutorial toont de kernstappen die je nodig hebt om XMP‑metagegevens in EPS‑bestanden te manipuleren. Het begrijpen van deze stappen helpt je om metagegevensverwerking te integreren in grotere document‑verwerkingspijplijnen, de doorzoekbaarheid te verbeteren en te voldoen aan industriestandaarden voor digitaal asset‑beheer.

## Voorvereisten
Voordat we aan de tutorial beginnen, zorg dat je de volgende zaken hebt:
- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. Je kunt deze downloaden [hier](https://releases.aspose.com/page/java/).  
- Een EPS‑bestand dat je wilt wijzigen.

## Pakketten importeren
Importeer eerst de benodigde pakketten in je Java‑programma:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Stap 1: XMP‑metagegevens ophalen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Vervang `"Your Document Directory"` door het daadwerkelijke pad waar je documenten zijn opgeslagen.

## Stap 2: Waarde van CreatorTool ophalen
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Stap 3: Waarde van CreateDate ophalen
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Stap 4: Waarde van Title ophalen
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Stap 5: Waarde van Format ophalen
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Stap 6: Waarde van Creator ophalen
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Stap 7: Waarde van MetadataDate ophalen
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Stap 8: Document opslaan met nieuwe XMP‑metagegevens
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Vergeet tenslotte niet om de invoer‑EPS‑stream te sluiten:

```java
// Close input EPS stream
psStream.close();
```

Nu heb je met succes metagegevens toegevoegd aan je EPS‑bestand met Aspose.Page for Java!

## Conclusie
In deze **aspose page java tutorial** hebben we onderzocht hoe je XMP‑metagegevens kunt toevoegen aan een EPS‑bestand met de Aspose.Page for Java‑bibliotheek. Deze krachtige API stelt je in staat om document‑metagegevens programmatisch te manipuleren, waardoor je assets georganiseerd en doorzoekbaar houdt.

## Veelgestelde vragen

**Q: Is Aspose.Page for Java gratis te gebruiken?**  
A: Aspose.Page for Java is een commercieel product. Je kunt de functies verkennen via een gratis proefversie [hier](https://releases.aspose.com/).

**Q: Waar kan ik de documentatie voor Aspose.Page for Java vinden?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Welke bestandsformaten ondersteunt Aspose.Page for Java?**  
A: Aspose.Page for Java ondersteunt verschillende formaten, waaronder EPS, PDF en XPS.

**Q: Kan ik Aspose.Page for Java kopen?**  
A: Ja, je kunt Aspose.Page for Java aanschaffen [hier](https://purchase.aspose.com/buy).

**Q: Hoe ga ik om met grote EPS‑bestanden bij het toevoegen van metagegevens?**  
A: Verwerk het bestand in een streaming‑manier (zoals getoond) om het geheugenverbruik laag te houden, en sluit streams direct.

**Q: Kan ik bestaande XMP‑velden wijzigen in plaats van ze alleen te lezen?**  
A: Absoluut – je kunt `xmp.put(key, value)` gebruiken om bestaande waarden bij te werken of nieuwe toe te voegen voordat je opslaat.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-08
description: Leer hoe u XMP‑metadata aan EPS‑bestanden kunt toevoegen met de Aspose Page Java‑tutorial.
  Volg deze stapsgewijze gids om uw documentbeheer te verbeteren.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java Tutorial – XMP-metadata toevoegen aan EPS‑bestanden
url: /nl/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

Conclusion" => "Conclusie"

"In this **aspose page java tutorial**, we explored..." etc.

"Frequently Asked Questions" => "Veelgestelde vragen"

Then each Q and A.

"Last Updated:" etc.

"Tested With:" etc.

"Author:" etc.

All other shortcodes remain.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadata toevoegen in XMP met Java

## Inleiding
In deze **aspose page java tutorial** leert u hoe u de metadata van uw document kunt verbeteren door XMP‑informatie toe te voegen met Java. Deze stapsgewijze gids leidt u door het lezen van een bestaand EPS‑bestand, het extraheren van de XMP‑metadata en het opslaan van de wijzigingen op schijf met de Aspose.Page for Java‑bibliotheek. Aan het einde van de tutorial heeft u een solide, herbruikbaar patroon voor het werken met XMP in elke EPS‑workflow.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik XMP toevoegen aan elk EPS‑bestand?** Ja – de API maakt een nieuw XMP‑blok aan als er nog geen bestaat.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 en later.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een eenvoudige metadata‑update.

## Wat is Aspose Page Java?
Aspose.Page for Java (vaak aangeduid als **aspose page java**) is een hoog‑presterende API waarmee ontwikkelaars PostScript‑ en EPS‑bestanden kunnen maken, bewerken en converteren zonder Adobe‑software. Het biedt ook volledige toegang tot XMP‑metadata, zodat u doorzoekbare informatie direct in uw grafische bestanden kunt insluiten.

## Waarom XMP‑metadata toevoegen aan EPS‑bestanden?
Het insluiten van XMP‑metadata verbetert asset‑beheer, doorzoekbaarheid en naleving van industriestandaarden zoals IPTC en Dublin Core. Wanneer u velden zoals maker, titel of aanmaakdatum toevoegt, kunnen downstream‑systemen (DAM‑systemen, zoekmachines of print‑workflows) uw EPS‑assets automatisch indexeren en organiseren.

## Overzicht van de Aspose Page Java‑tutorial
Deze tutorial toont de kernstappen die nodig zijn om XMP‑metadata in EPS‑bestanden te manipuleren. Het begrijpen van deze stappen helpt u bij het integreren van metadata‑verwerking in grotere document‑verwerkingspijplijnen, verbetert de doorzoekbaarheid en voldoet aan industriestandaarden voor digitaal asset‑beheer.

## Vereisten
Voordat we aan de tutorial beginnen, zorg ervoor dat u de volgende zaken hebt:
- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. U kunt deze downloaden [hier](https://releases.aspose.com/page/java/).  
- Een EPS‑bestand dat u wilt aanpassen.

## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java‑programma:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Stap 1: XMP‑metadata ophalen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Vervang `"Your Document Directory"` door het daadwerkelijke pad waar uw documenten zijn opgeslagen.

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

## Stap 8: Document opslaan met nieuwe XMP‑metadata
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

Vergeet tenslotte niet om de invoer‑EPS‑stroom te sluiten:

```java
// Close input EPS stream
psStream.close();
```

Nu hebt u met succes metadata toegevoegd aan uw EPS‑bestand met Aspose.Page for Java!

## Veelvoorkomende problemen en oplossingen
- **Ontbrekend XMP‑blok** – De API maakt er automatisch één aan, maar zorg ervoor dat het EPS‑bestand niet corrupt is.  
- **Niet‑ondersteunde tekens** – XMP‑waarden moeten UTF‑8 zijn; vermijd niet‑standaard symbolen in metadata‑velden.  
- **Grote EPS‑bestanden** – Verwerk het bestand met streams (zoals getoond) om het geheugenverbruik laag te houden, en sluit streams altijd in een `finally`‑blok.

## Conclusie
In deze **aspose page java tutorial** hebben we onderzocht hoe u XMP‑metadata kunt toevoegen aan een EPS‑bestand met de Aspose.Page for Java‑bibliotheek. Deze krachtige API stelt u in staat om documentmetadata programmatisch te manipuleren, waardoor u assets georganiseerd en doorzoekbaar houdt.

## Veelgestelde vragen

**Q: Is Aspose.Page for Java gratis te gebruiken?**  
A: Aspose.Page for Java is een commercieel product. U kunt de functies verkennen via een gratis proefversie [hier](https://releases.aspose.com/).

**Q: Waar kan ik de documentatie voor Aspose.Page for Java vinden?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: U kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Welke bestandsformaten ondersteunt Aspose.Page for Java?**  
A: Aspose.Page for Java ondersteunt verschillende formaten, waaronder EPS, PDF en XPS.

**Q: Kan ik Aspose.Page for Java aanschaffen?**  
A: Ja, u kunt Aspose.Page for Java aanschaffen [hier](https://purchase.aspose.com/buy).

**Q: Hoe ga ik om met grote EPS‑bestanden bij het toevoegen van metadata?**  
A: Verwerk het bestand in een streaming‑modus (zoals getoond) om het geheugenverbruik laag te houden, en sluit streams direct.

**Q: Kan ik bestaande XMP‑velden wijzigen in plaats van alleen lezen?**  
A: Absoluut – u kunt `xmp.put(key, value)` gebruiken om entries bij te werken of nieuwe toe te voegen vóór het opslaan.

---

**Laatst bijgewerkt:** 2026-03-08  
**Getest met:** Aspose.Page for Java 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
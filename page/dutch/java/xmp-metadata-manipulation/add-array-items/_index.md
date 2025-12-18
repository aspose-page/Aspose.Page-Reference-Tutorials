---
date: 2025-12-18
description: Leer hoe u metadata kunt toevoegen door array‑items in de XMP‑metadata
  van EPS‑bestanden in te voegen met Aspose.Page voor Java. Volg onze stapsgewijze
  handleiding.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hoe metadata toe te voegen – Array‑items toevoegen in XMP (Java)
url: /nl/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Array-items toevoegen in XMP-metadata met Java

## Hoe metadata toe te voegen
Welkom bij onze stapsgewijze handleiding over **hoe metadata toe te voegen** aan EPS‑bestanden met Aspose.Page for Java. In deze tutorial laten we je zien hoe je array‑items toevoegt aan XMP‑metadata — een veelvoorkomende behoefte wanneer je documentinformatie zoals titels of makers wilt verrijken. Aan het einde begrijp je waarom XMP waardevol is, hoe je het programmatisch kunt manipuleren en hoe je het bijgewerkte EPS‑bestand opslaat.

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Page for Java  
- **Op welk bestandsformaat is het gericht?** EPS (Encapsulated PostScript)  
- **Kan ik meerdere titels toevoegen?** Ja, gebruik `xmp.addArrayItem("dc:title", ...)` herhaaldelijk  
- **Heb ik een licentie nodig voor productie?** Ja, een geldige Aspose.Page‑licentie is vereist  
- **Is de code compatibel met Java 8+?** Absoluut, hij werkt met alle moderne Java‑versies  

## Vereisten
Voordat we aan de tutorial beginnen, zorg dat je de volgende zaken hebt:
- Aspose.Page for Java‑bibliotheek geïnstalleerd.  
- Basiskennis van Java‑programmeren.  
- Een geldig EPS‑bestand met bestaande XMP‑metadata of PS‑metadata‑commentaren.

## Pakketten importeren
Om te beginnen moet je de benodigde pakketten importeren voor het werken met Aspose.Page. Voeg de volgende regels toe aan het begin van je Java‑bestand:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Stap 1: XMP‑metadata ophalen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
In deze stap halen we de bestaande XMP‑metadata op uit het EPS‑bestand. Als het EPS‑bestand nog geen XMP‑metadata bevat, genereert Aspose.Page een nieuwe en vult deze met waarden uit PS‑metadata‑commentaren.

## Stap 2: Array‑item “dc:title” toevoegen
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nu voegen we een nieuw array‑item toe aan de **dc:title**‑eigenschap in de XMP‑metadata. Vervang `"NewTitle"` door de gewenste titel.

## Stap 3: Array‑item “dc:creator” toevoegen
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Op dezelfde manier voegen we een nieuw array‑item toe aan de **dc:creator**‑eigenschap in de XMP‑metadata. Vervang `"NewCreator"` door de gewenste makerinformatie.

## Stap 4: Output‑EPS‑bestandstream initialiseren
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Bereid de output‑EPS‑bestandstream voor waar het gewijzigde document met bijgewerkte XMP‑metadata wordt opgeslagen.

## Stap 5: Document opslaan met gewijzigde XMP‑metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Sla het document met de bijgewerkte XMP‑metadata op in het output‑EPS‑bestand.

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd **hoe metadata toe te voegen** door array‑items in XMP‑metadata in te voegen met Aspose.Page for Java. Deze krachtige bibliotheek vereenvoudigt het manipuleren van EPS‑bestanden en biedt uitgebreide functionaliteit voor documentverwerking.

## Veelgestelde vragen

### Kan ik Aspose.Page for Java gebruiken met andere documentformaten?
Ja, Aspose.Page ondersteunt verschillende documentformaten, waaronder EPS, PDF en XPS.

### Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?
Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) vinden.

### Waar vind ik de documentatie voor Aspose.Page for Java?
De documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

### Hoe kan ik Aspose.Page for Java aanschaffen?
Je kunt het product [hier](https://purchase.aspose.com/buy) kopen.

### Zijn tijdelijke licenties beschikbaar voor Aspose.Page for Java?
Ja, je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

## Aanvullende veelgestelde vragen

**Q: Kan ik meer dan één array‑item toevoegen aan dezelfde eigenschap?**  
A: Zeker. Roep `xmp.addArrayItem` meerdere keren aan voor dezelfde eigenschap om een lijst met waarden op te bouwen.

**Q: Werkt deze aanpak met bestaande XMP‑schemas anders dan Dublin Core?**  
A: Ja, je kunt array‑items toevoegen aan elke XMP‑eigenschap zolang de namespace correct wordt gerefereerd.

**Q: Hoe kan ik verifiëren of de metadata correct is toegevoegd?**  
A: Open het resulterende EPS‑bestand in een viewer die XMP ondersteunt (bijv. Adobe Bridge) of extraheer de metadata programmatisch met behulp van `XmpMetadata`‑methoden.

---

**Laatst bijgewerkt:** 2025-12-18  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
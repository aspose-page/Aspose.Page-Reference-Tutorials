---
date: 2026-05-15
description: Leer hoe u XMP-metadata kunt bewerken en hoe u XMP-waarden in EPS‑bestanden
  kunt wijzigen met Aspose.Page for Java – een duidelijke stapsgewijze handleiding.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Named Value wijzigen in XMP met Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: hoe XMP bewerken – Named Value wijzigen in XMP met Java
url: /nl/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# hoe xmp bewerken – Naamwaarde wijzigen in XMP met Java

In moderne documentworkflows maakt **Aspose.Page for Java** het eenvoudig om XMP‑metadata in EPS‑bestanden te lezen, te bewerken en te schrijven. **Deze tutorial laat zien hoe je XMP** metadata in EPS‑documenten kunt bewerken met de Aspose.Page API, zodat je documentinformatie nauwkeurig, doorzoekbaar en conform de industrienormen blijft. Of je nu paginagrootte, auteursinformatie of aangepaste tags bijwerkt, de onderstaande stappen begeleiden je door het proces in Java.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Een benoemde XMP‑waarde wijzigen in een EPS‑bestand met Aspose.Page for Java.  
- **Welke bibliotheekversie is vereist?** Elke recente Aspose.Page for Java‑release (de API is al enkele jaren stabiel).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productie; een gratis proefversie werkt voor testen.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een ontwikkelaar die bekend is met Java I/O.  
- **Kan ik dit gebruiken met andere bestandsformaten?** De XMP API is ook beschikbaar voor PDF, SVG en andere formaten die door Aspose.Page worden ondersteund.

## Wat is XMP‑metadata?
XMP (Extensible Metadata Platform) is een gestandaardiseerd XML‑gebaseerd formaat voor het insluiten van rijke metadata—zoals maker, titel en aangepaste eigenschappen—direct in bestanden. In EPS‑documenten bevindt XMP zich naast traditionele PostScript‑commentaren, waardoor toepassingen metadata kunnen lezen en wijzigen zonder de visuele inhoud te wijzigen.

## Waarom Aspose.Page for Java gebruiken om XMP te bewerken?
Aspose.Page biedt **volledige controle over meer dan 150 XMP‑schema‑eigenschappen** en werkt consistent over EPS-, PDF- en SVG-formaten. Het verwerkt bestanden tot **500 MB** zonder het volledige document in het geheugen te laden, en het bevat ingebouwde validatie die garandeert dat de resulterende EPS aan de normen voldoet. Er zijn geen externe XML‑parsers of native bibliotheken nodig.

## Introductie
Aspose.Page for Java is een robuuste bibliotheek die het manipuleren en verwerken van EPS‑bestanden vergemakkelijkt. Als het gaat om het omgaan met XMP‑metadata in deze bestanden, biedt Aspose.Page ontwikkelaars een uitgebreide set functies. In deze tutorial richten we ons op het wijzigen van een benoemde waarde in XMP, en bieden we een duidelijke en beknopte gids voor ontwikkelaars die hun documentverwerkingsmogelijkheden willen uitbreiden.

## Vereisten
Voordat je aan de tutorial begint, zorg ervoor dat je de volgende vereisten hebt:
1. **Java-ontwikkelomgeving** – Een JDK (8 of hoger) en een IDE of build‑tool (Maven/Gradle).  
2. **Aspose.Page for Java‑bibliotheek** – Download en integreer de Aspose.Page for Java‑bibliotheek in je project. Je kunt de bibliotheek en gedetailleerde documentatie [hier](https://reference.aspose.com/page/java/) vinden.  
3. **Voorbeeld‑EPS‑bestand** – Zorg voor een voorbeeld‑EPS‑bestand om mee te experimenteren. Als je er geen hebt, gebruik dan het meegeleverde voorbeeldbestand genaamd **"xmp4.eps."**

## Pakketten importeren
De `import`‑verklaringen brengen de essentiële Aspose.Page‑klassen in scope.

De `PsDocument`‑klasse is het kernobject van Aspose.Page dat een EPS‑document in het geheugen vertegenwoordigt.  
De `XmpMetadata`‑klasse biedt toegang tot het XMP‑pakket dat in het EPS‑bestand is ingebed.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Hoe XMP‑metadata bewerken?
Laad het EPS‑bestand, haal het XMP‑pakket op, wijzig de gewenste eigenschap en sla het document op—alles in een paar eenvoudige regels. Deze aanpak werkt voor elke benoemde XMP‑waarde, of het nu een standaard Dublin Core‑veld is of een aangepaste namespace die je hebt gedefinieerd.

## Stap 1: Input‑EPS‑bestandstream initialiseren
`FileInputStream` opent een alleen‑lezen‑stream naar het bron‑EPS‑bestand, waardoor Aspose.Page het document kan inlezen zonder het bestandssysteem te vergrendelen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Stap 2: PsDocument initialiseren
`PsDocument` is het primaire object dat de EPS‑inhoud omvat en toegang biedt tot de metadata, pagina's en bronnen.

```java
PsDocument document = new PsDocument(psStream);
```

## Stap 3: XMP‑metadata ophalen
`XmpMetadata` vertegenwoordigt het XMP‑pakket in het EPS‑bestand en biedt methoden om individuele eigenschappen te lezen, te wijzigen of te verwijderen.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Stap 4: Nieuwe waarde instellen in XMP
`setProperty` stelt de waarde van een opgegeven XMP‑eigenschap in het metadata‑pakket in.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Stap 5: Output‑EPS‑bestandstream initialiseren
`FileOutputStream` maakt een schrijfbare stream aan voor het opslaan van het gewijzigde EPS‑bestand.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Stap 6: Document opslaan met gewijzigde XMP‑metadata
`save` schrijft het in‑memory PsDocument, inclusief bijgewerkte XMP, naar de output‑stream.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Stap 7: Input‑EPS‑stream sluiten
`close` geeft de bestands‑handle vrij en maakt de bronnen vrij die aan de input‑stream zijn gekoppeld.

```java
// Close input EPS stream
psStream.close();
```

## Veelvoorkomende problemen en oplossingen
- **FileNotFoundException** – Controleer of `dataDir` naar de juiste map wijst en of `xmp4.eps` bestaat.  
- **LicenseException** – Als je licentiefouten ziet, zorg er dan voor dat een geldig Aspose.Page‑licentiebestand is geladen voordat je `PsDocument` maakt.  
- **Metadata Not Updated** – Open na het opslaan de resulterende EPS in een metadata‑viewer (bijv. Adobe Bridge) om te bevestigen dat de nieuwe waarde verschijnt.

## Veelgestelde vragen
**Q: Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?**  
A: Aspose.Page ondersteunt voornamelijk Java, maar Aspose biedt equivalente bibliotheken voor .NET, C++ en Python die vergelijkbare XMP‑manipulatiemogelijkheden bieden.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie van Aspose.Page for Java [hier](https://releases.aspose.com/) verkennen.

**Q: Waar kan ik extra ondersteuning en discussies over Aspose.Page for Java vinden?**  
A: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning en discussies.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

**Q: Waar kan ik Aspose.Page for Java kopen?**  
A: Om Aspose.Page for Java te kopen, bezoek de [aankooppagina](https://purchase.aspose.com/buy).

---

**Laatst bijgewerkt:** 2026-05-15  
**Getest met:** Aspose.Page for Java (latest release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe XMP‑metadata lezen met Java – Aspose.Page-gids](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java‑tutorial – XMP‑metadata toevoegen aan EPS‑bestanden](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Waarden wijzigen in XMP met Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
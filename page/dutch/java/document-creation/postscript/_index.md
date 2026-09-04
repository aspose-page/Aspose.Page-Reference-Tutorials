---
date: 2026-06-20
description: Leer hoe u A4-paginaformaat instelt, PostScript-bestanden maakt in Java
  en aangepaste lettertypen toevoegt met Aspose.Page. Probeer vandaag nog de gratis
  proefversie!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Document aanmaken in Java met PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hoe A4-paginaformaat instellen en PostScript maken in Java met Aspose.Page
url: /nl/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe A4-paginaformaat instellen en PostScript maken in Java met Aspose.Page

## Inleiding
Als je **a4-paginaformaat moet instellen** bij het genereren van PostScript‑bestanden vanuit Java, biedt Aspose.Page een snelle, betrouwbare API die de low‑level details verbergt. In deze tutorial lopen we het volledige proces door—het maken van een PostScript‑document, het configureren van de A4‑pagina‑afmetingen, en **aangepaste lettertypen toevoegen** wanneer nodig. Aan het einde heb je een kant‑klaar code‑fragment dat je in elk Java‑project kunt gebruiken.

## Snelle antwoorden
- **Welke bibliotheek maakt PostScript in Java?** Aspose.Page for Java.  
- **Welke paginagrootte richt deze gids zich op?** A4 (210 mm × 297 mm).  
- **Kan ik mijn eigen lettertypen insluiten?** Ja – stel de extra lettertype‑map in de opslaan‑opties in.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Welke Java‑versies worden ondersteund?** Java 8 en later.

## Hoe a4-paginaformaat instellen en postscript maken in Java
Laad de Aspose.Page‑bibliotheek, configureer `PsSaveOptions` met de A4‑constanten, en schrijf het document naar een bestand – alles in minder dan tien regels code. Deze directe aanpak garandeert de juiste paginadimensies en stelt je in staat aangepaste lettertypen toe te voegen zonder extra configuratie.

## Wat is de PostScript A4-grootte?
PostScript A4-grootte is de ISO 216‑standaard (210 mm × 297 mm) weergegeven in de PostScript‑paginabeschrijvingstaal. Het definieert het afdrukbare gebied dat printers en viewers interpreteren, waardoor een consistente lay-out over platforms heen wordt gegarandeerd. Omdat PostScript paginainhoud beschrijft op een apparaat‑onafhankelijke manier, zorgt het gebruik van de A4‑grootte ervoor dat het document er overal hetzelfde uitziet op elke A4‑capabele printer of viewer wereldwijd.

## Waarom Aspose.Page gebruiken om het PostScript-paginaformaat in te stellen?
Aspose.Page ondersteunt **30+ PostScript‑operatoren** en kan bestanden tot **500 MB** genereren zonder het volledige document in het geheugen te laden. Dit geeft je precieze controle over paginadimensies terwijl grote workloads efficiënt worden afgehandeld. De bibliotheek abstraheert bovendien complexe PostScript‑syntaxis, beheert automatisch bronnen en biedt high‑performance streaming, waardoor het ideaal is voor zowel eenvoudige één‑pagina‑flyers als complexe meer‑pagina‑rapporten.

## Hoe aangepaste lettertypen toevoegen in Java
Het insluiten van je eigen lettertypen zorgt ervoor dat het gegenereerde document er exact uitziet zoals ontworpen op elke printer of viewer, en Aspose.Page ontdekt automatisch lettertypen die in de opgegeven map staan. Door een extra lettertype‑map te registreren, kun je elk TrueType‑ of OpenType‑lettertype gebruiken, fallback‑substituties vermijden en merkconsistentie behouden over alle uitvoerapparaten.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

- Een goede kennis van Java‑programmeren.  
- Aspose.Page for Java geïnstalleerd. Je kunt het downloaden [hier](https://releases.aspose.com/page/java/).  
- Een map genaamd `necessary_fonts` (of een andere naam naar keuze) die de aangepaste lettertypen bevat die je wilt insluiten.

## Pakketten importeren
Importeer in je Java‑project de benodigde Aspose.Page‑klassen:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Laten we nu het voorbeeld opsplitsen in duidelijke, genummerde stappen.

### Stap 1: Documentmap instellen
De constante `OUTPUT_DIR` vertelt de bibliotheek waar het gegenereerde bestand moet worden weggeschreven.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Stap 2: Lettertype‑map definiëren
`FONTS_FOLDER` wijst naar de directory die je aangepaste TrueType‑ of OpenType‑lettertypen bevat.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Stap 3: Output‑stream maken voor PostScript‑document
`FileOutputStream` opent een stream die de uiteindelijke PostScript A4‑output zal ontvangen.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Stap 4: Opslagopties maken met A4-grootte
`PsSaveOptions` laat je de doelpaginagrootte specificeren.  
**Definitie:** `PsPageSize` is een enumeratie die standaard paginagrootte‑constanten bevat zoals A4, Letter en Legal.  
Het instellen van `options.setPageSize(PsPageSize.A4)` configureert het document voor standaard A4‑dimensies.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Stap 5: Paginamarges instellen en aangepaste lettertype‑map toevoegen
`options.setMargins(0, 0, 0, 0)` verwijdert alle marges voor een full‑bleed pagina, en `options.setAdditionalFontsFolder(FONTS_FOLDER)` registreert je aangepaste lettertypen.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Stap 6: Een meer‑pagina‑ of enkel‑pagina‑PS‑document maken
`PsDocument document = new PsDocument(outputStream, options)` maakt het document. `PsDocument` vertegenwoordigt een PostScript‑document dat één of meerdere pagina's kan bevatten. Stel `multiPaged` in op `true` voor een meer‑pagina‑output.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Stap 7: Huidige pagina sluiten en document opslaan
Het aanroepen van `document.close()` finaliseert het bestand en schrijft de **PostScript A4-grootte** output naar schijf.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Veelvoorkomende problemen & tips
- **Lettertype verschijnt niet?** Controleer of het lettertype‑bestand een ondersteund TrueType‑ of OpenType‑formaat is en of `FONTS_FOLDER` eindigt op een slash (`/`).  
- **Marges blijven zichtbaar?** Roep `options.setMargins(...)` **voordat** je de `PsDocument` instantiate.  
- **Meer‑pagina‑output is leeg?** Vergeet niet `document.newPage()` aan te roepen voor elke extra pagina die je nodig hebt.

## Veelgestelde vragen

**V: Kan ik aangepaste lettertypen gebruiken in mijn PostScript‑document?**  
A: Ja, stel de extra lettertype‑map in de opslaan‑opties in (zie Stap 5) en Aspose.Page zal de lettertypen automatisch insluiten.

**V: Is er een proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

**V: Hoe krijg ik toegang tot de volledige API‑referentie?**  
A: Raadpleeg de documentatie [hier](https://reference.aspose.com/page/java/).

**V: Waar kan ik een licentie kopen voor Aspose.Page for Java?**  
A: Je kunt een licentie aanschaffen [hier](https://purchase.aspose.com/buy).

**V: Waar kan ik de community om hulp vragen?**  
A: Bezoek het Aspose.Page‑forum [forum](https://forum.aspose.com/c/page/39).

**V: Kan ik multi‑page PostScript‑bestanden genereren?**  
A: Absoluut—stel `multiPaged` in op `true` in Stap 6 en roep `document.newPage()` aan voor elke extra pagina.

## Conclusie
Door deze stappen te volgen weet je nu **hoe a4-paginaformaat in te stellen** en **PostScript**‑bestanden te maken in Java met Aspose.Page, terwijl je ook **aangepaste lettertypen in Java kunt toevoegen** en paginagrootte‑opties kunt beheren. Aspose.Page doet het zware werk, zodat jij je kunt concentreren op de inhoud van je documenten.

---

**Laatst bijgewerkt:** 2026-06-20  
**Getest met:** Aspose.Page for Java 24.11  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Page Java‑tutorial – aangepaste paginagrootte instellen tijdens het toevoegen van pagina's in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Hoe tekst toevoegen in PostScript met Aspose.Page voor Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java‑tutorial - PostScript naar PDF converteren](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```
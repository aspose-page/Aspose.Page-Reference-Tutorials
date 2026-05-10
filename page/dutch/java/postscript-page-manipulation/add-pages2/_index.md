---
date: 2026-02-18
description: Leer hoe u een aangepaste paginagrootte instelt en pagina's toevoegt
  aan Java PostScript‑documenten met Aspose.Page. Volg onze stap‑voor‑stap‑gids voor
  naadloze documentmanipulatie.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java Tutorial – stel aangepaste paginagrootte in bij het toevoegen
  van pagina’s in PostScript
url: /nl/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – aangepaste paginagrootte instellen bij het toevoegen van pagina's in PostScript

## Introductie
In moderne Java‑toepassingen is het **instellen van een aangepaste paginagrootte** voor PostScript‑output vaak vereist—of u nu facturen, tickets of aangepaste graphics genereert. In deze tutorial leert u hoe u **een aangepaste paginagrootte** voor elke pagina kunt **instellen**, meerdere pagina's kunt toevoegen en uiteindelijk een **PostScript‑bestand kunt genereren** dat precies aan uw lay-outbehoeften voldoet. We lopen de code stap‑voor‑stap door zodat u de techniek snel in uw eigen projecten kunt toepassen.

## Snelle antwoorden
- **Kan ik verschillende paginagroottes voor elke pagina instellen?** Ja, u kunt pagina's openen met aangepaste afmetingen via `document.openPage(width, height)`.  
- **Heb ik een licentie nodig voor productiegebruik?** Een geldige Aspose.Page‑licentie is vereist voor niet‑evaluatie‑implementaties.  
- **Welke Java‑versies worden ondersteund?** De bibliotheek werkt met Java 8 en hoger.  
- **Is de API thread‑safe?** Document‑instanties zijn niet thread‑safe; maak een aparte `PsDocument` per thread.  
- **Hoe groot kan een PostScript‑bestand zijn?** Aspose.Page verwerkt multi‑megabyte bestanden efficiënt; het geheugenverbruik schaalt met de inhoud, niet met het aantal pagina's.  
- **Kan ik de overload met breedte/hoogte gebruiken?** Absoluut—`openPage(double width, double height)` laat u elke afmeting in points opgeven.  

## Vereisten
- Een basisbegrip van Java‑programmeren.  
- Aspose.Page for Java toegevoegd aan uw project (Maven/Gradle of handmatige JAR).  
- Een Java‑ontwikkelomgeving (IDE, JDK 8+).  

## Pakketten importeren
Om te beginnen, importeer de benodigde klassen uit de Aspose.Page‑bibliotheek.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stap 1: Maak een meerpagina‑PostScript‑document
Maak eerst een nieuw `PsDocument` geconfigureerd voor meerdere pagina's. Dit stelt de output‑stream in en vertelt de bibliotheek dat we met een meerpagina‑bestand gaan werken.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Stap 2: Voeg inhoud toe aan de eerste pagina
Met het document klaar, kunt u alle gewenste inhoud aan de eerste pagina toevoegen. Wanneer u klaar bent, sluit u de pagina om de inhoud te vergrendelen.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Hoe een aangepaste paginagrootte in te stellen
Als de standaard paginagrootte niet geschikt is, kunt u **een aangepaste paginagrootte** instellen bij het openen van een nieuwe pagina. Dit is handig voor bonnen, etiketten of elke niet‑standaard lay-out.

## Stap 3: Voeg een tweede pagina toe met een andere grootte
Hieronder openen we een tweede pagina en geven expliciet een aangepaste breedte en hoogte (in points) op. Dit toont hoe u een aangepaste paginagrootte voor individuele pagina's kunt instellen, waardoor u **verschillende paginagroottes** binnen hetzelfde document kunt gebruiken.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Stap 4: Sla het document op
Sla tenslotte de wijzigingen op door het document te bewaren. Alle pagina's—incl. die met aangepaste groottes—worden naar het uitvoerbestand geschreven.

```java
// Save the document
document.save();
```

Door deze stappen te volgen, kunt u naadloos pagina's toevoegen en **een aangepaste paginagrootte** instellen in een Java‑PostScript‑document met Aspose.Page, waardoor u volledige controle krijgt over de lay-out van elke pagina.

## Waarom Aspose.Page gebruiken om een aangepaste paginagrootte in te stellen?
- **Precisie:** Dimensies worden gedefinieerd in points, zodat u exacte controle heeft over paginabreedte en -hoogte.  
- **Flexibiliteit:** Meng en combineer **verschillende paginagroottes** in één PostScript‑bestand.  
- **Prestaties:** De bibliotheek streamt inhoud direct naar het uitvoerbestand, waardoor het geschikt is voor grootschalige **PostScript‑bestanden genereren** scenario's.  
- **Rijke API:** Ondersteunt het tekenen van graphics, het insluiten van afbeeldingen en het toevoegen van tekst—alles terwijl de door u ingestelde aangepaste afmetingen gerespecteerd worden.  

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Paginadimensies lijken verwisseld** | Onthoud dat `openPage(width, height)` eerst de breedte en daarna de hoogte verwacht (beide in points). |
| **Inhoud loopt over de pagina heen** | Gebruik het `PsGraphics`‑coördinatensysteem om elementen binnen de aangepaste grenzen te positioneren, of schaal uw tekening. |
| **Out‑of‑memory‑fouten bij enorme documenten** | Schakel streaming in door direct naar een `FileOutputStream` te schrijven zoals getoond, en vermijd het in één keer laden van grote afbeeldingen in het geheugen. |

## Veelgestelde vragen
### Kan ik pagina's met verschillende groottes toevoegen in één PostScript‑document?
Ja, zoals in deze tutorial getoond, kunt u pagina's met variërende groottes toevoegen in een meerpagina‑PostScript‑document.  

### Zijn er beperkingen op het aantal pagina's dat ik kan toevoegen?
Aspose.Page ondersteunt het toevoegen van praktisch onbeperkt aantal pagina's aan een document.  

### Kan ik aangepaste inhoud, zoals afbeeldingen of graphics, aan de pagina's toevoegen?
Absoluut! Aspose.Page stelt u in staat een breed scala aan inhoud toe te voegen, waaronder tekst, afbeeldingen en andere grafische elementen.  

### Is Aspose.Page geschikt voor het verwerken van grote documenten?
Ja, Aspose.Page is ontworpen om zowel kleine als grote documenten efficiënt te verwerken.  

### Waar vind ik extra bronnen en ondersteuning voor Aspose.Page?
Bekijk de [Aspose.Page documentation](https://reference.aspose.com/page/java/), of bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.  

**Aanvullende Q&A**

**Q:** *Welke afbeeldingsformaten worden ondersteund bij het tekenen op een PostScript‑pagina?*  
**A:** U kunt PNG-, JPEG-, BMP- en GIF‑afbeeldingen direct insluiten via de teken‑API.  

**Q:** *Hoe wijzig ik de standaard DPI voor het document?*  
**A:** Stel `PsSaveOptions.setResolution(int dpi)` in vóór het aanmaken van de `PsDocument`.  

**Q:** *Kan ik een PostScript‑bestand versleutelen met een wachtwoord?*  
**A:** PostScript zelf ondersteunt geen versleuteling, maar u kunt de output in een PDF wikkelen en daar beveiligingsinstellingen toepassen indien nodig.  

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-05
description: Leer hoe u dc:title‑array‑items kunt toevoegen aan de XMP‑metadata van
  EPS‑bestanden met Aspose.Page voor Java. Volg deze stapsgewijze handleiding voor
  snelle resultaten.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hoe dc:title-arrayitems toe te voegen in XMP-metadata met Java
url: /nl/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Array-items toevoegen in XMP-metadata met Java

## Introductie
In deze tutorial ontdek je **hoe je dc:title** (en andere array-items) kunt toevoegen aan XMP-metadata in een EPS‑bestand met Aspose.Page for Java. Het bijwerken van XMP-metadata is nuttig wanneer je doorzoekbare informatie—zoals titels, makers of trefwoorden—direct in je grafische bestanden wilt embedden. We lopen elke stap door, leggen uit waarom elke regel belangrijk is, en laten je zien hoe je de wijzigingen kunt verifiëren.

## Snelle antwoorden
- **Wat betekent “dc:title”?** Het is de Dublin Core‑titel eigenschap opgeslagen als een XMP‑array.  
- **Waarom XMP-metadata wijzigen?** Het maakt beter asset‑beheer, doorzoekbaarheid en naleving van standaarden mogelijk.  
- **Heb ik een bestaand XMP‑blok nodig?** Nee—Aspose.Page genereert er een vanuit PS‑commentaren als het ontbreekt.  
- **Welke bibliotheekversie is vereist?** Elke recente Aspose.Page for Java‑release (getest met de nieuwste 2026‑build).  
- **Kan ik andere array‑eigenschappen toevoegen?** Ja—gebruik dezelfde `addArrayItem`‑methode voor eigenschappen zoals `dc:creator`.

## Voorwaarden
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Aspose.Page for Java‑bibliotheek geïnstalleerd (voeg de JAR toe aan het classpath van je project).  
- Basis Java‑ontwikkelervaring (JDK 8+ aanbevolen).  
- Een EPS‑bestand dat al XMP‑metadata bevat of ten minste PS‑metadata‑commentaren (bijv. `%%Title`, `%%Creator`).  

## Pakketten importeren
Om te beginnen, importeer je de klassen die nodig zijn voor het lezen, manipuleren en opslaan van EPS‑bestanden:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Stap 1: Laad het EPS‑document en haal XMP‑metadata op
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Hier openen we het EPS‑bestand en vragen we Aspose.Page om het XMP‑blok. Als het bestand geen XMP heeft, maakt de bibliotheek er automatisch één aan met behulp van bestaande PS‑commentaren, zodat je altijd een metadata‑container hebt om mee te werken.

## Stap 2: Voeg een nieuw **dc:title**‑array‑item toe  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Deze regel toont **hoe je dc:title** kunt toevoegen. Vervang `"NewTitle"` door de daadwerkelijke titel die je wilt embedden. De methode voegt de waarde toe aan de bestaande titel‑array, waarbij eerdere titels behouden blijven.

## Stap 3: Voeg een nieuw **dc:creator**‑array‑item toe  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Op dezelfde manier kun je de `dc:creator`‑eigenschap verrijken. Meerdere makers kunnen worden opgeslagen; elke aanroep voegt een nieuw item toe.

## Stap 4: Bereid de output‑stream voor  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Wij maken een stream voor het gewijzigde EPS‑bestand. Het gebruik van een andere bestandsnaam (`xmp3_changed.eps`) houdt het originele bestand ongewijzigd.

## Stap 5: Sla het document op met bijgewerkte XMP‑metadata  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

De `save`‑aanroep schrijft de EPS‑gegevens samen met het bijgewerkte XMP‑blok. Het `finally`‑blok zorgt ervoor dat de bestands‑handle wordt vrijgegeven, zelfs als er een uitzondering optreedt.

## Waarom dit belangrijk is
Het embedden van nauwkeurige `dc:title`‑ en `dc:creator`‑waarden verbetert:

- **Doorzoekbaarheid** in digitale asset‑management (DAM) systemen.  
- **Naleving** van publicatiestandaarden die metadata vereisen.  
- **Samenwerking**, omdat teamleden snel de inhoud van een bestand kunnen identificeren zonder het EPS‑bestand te openen.

## Veelvoorkomende valkuilen & tips
- **Valkuil:** Bestaande array‑items per ongeluk overschrijven.  
  **Tip:** Gebruik `xmp.getArrayItems("dc:title")` om de huidige waarden te inspecteren voordat je nieuwe toevoegt.  
- **Valkuil:** Vergeten streams te sluiten, wat leidt tot bestandsvergrendelingen.  
  **Tip:** Omring I/O altijd met try‑with‑resources of een `finally`‑blok zoals getoond.  
- **Tip:** Je kunt meerdere `addArrayItem`‑aanroepen ketenen om meerdere titels of makers in één keer toe te voegen.

## Veelgestelde vragen

### Kan ik Aspose.Page for Java gebruiken met andere documentformaten?
Ja, Aspose.Page ondersteunt verschillende documentformaten, waaronder EPS, PDF en XPS.

### Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?
Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

### Waar kan ik de documentatie voor Aspose.Page for Java vinden?
De documentatie is beschikbaar [hier](https://reference.aspose.com/page/java/).

### Hoe kan ik Aspose.Page for Java aanschaffen?
Je kunt het product [hier](https://purchase.aspose.com/buy) kopen.

### Zijn tijdelijke licenties beschikbaar voor Aspose.Page for Java?
Ja, je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
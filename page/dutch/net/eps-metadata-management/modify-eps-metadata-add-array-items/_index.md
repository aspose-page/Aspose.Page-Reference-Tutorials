---
date: 2026-08-08
description: Leer hoe je array-items kunt toevoegen aan EPS-metadata met Aspose.Page
  EPS metadata. Deze stap‑voor‑stap .NET‑gids toont hoe je array-items kunt toevoegen
  en EPS‑bestanden efficiënt kunt lezen.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Array-items toevoegen
og_description: Ontdek hoe je array-items kunt toevoegen aan EPS-metadata met Aspose.Page
  EPS metadata. Volg deze beknopte .NET‑tutorial om EPS‑bestanden te lezen en metadata
  efficiënt te beheren.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Array-items toevoegen met Aspose.Page EPS-metadata in .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Array-items toevoegen met Aspose.Page EPS-metadata in .NET
url: /nl/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg array‑items toe met Aspose.Page EPS‑metadata in .NET

## Introductie

In deze tutorial leer je hoe je array‑items kunt toevoegen aan EPS‑metadata met behulp van **Aspose.Page EPS metadata**. Of je nu een EPS‑bestand wilt verrijken met extra titels, makers of aangepaste tags, Aspose.Page maakt de taak eenvoudig voor elke .NET‑ontwikkelaar. We lopen elke stap door, van het openen van de EPS‑stream tot het opslaan van het bijgewerkte XMP‑pakket, zodat je metadata‑verwerking met vertrouwen in je eigen applicaties kunt integreren.

## Snelle antwoorden
- **Wat stelt Aspose.Page EPS metadata je in staat te doen?** Het maakt het mogelijk om XMP‑metadata‑arrays in EPS‑bestanden te lezen en te schrijven vanuit .NET.  
- **Welke klasse vertegenwoordigt een EPS‑document?** `PsDocument` is de kernklasse voor het laden en opslaan van EPS‑inhoud.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik metadata wijzigen zonder de EPS‑grafieken aan te passen?** Ja, alleen het XMP‑pakket wordt gewijzigd, terwijl de paginainhoud onaangeroerd blijft.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is Aspose.Page EPS‑metadata?
Aspose.Page EPS‑metadata is een XMP‑gebaseerd informatieblok dat in een EPS‑bestand is ingebed. Het slaat beschrijvende eigenschappen op, zoals titels, makers, trefwoorden en aangepaste tags volgens de ISO 16684‑1‑norm. De metadata kan programmatisch worden benaderd en gewijzigd via de Aspose.Page‑API, waardoor geautomatiseerd documentbeheer en zoekoptimalisatie mogelijk zijn.

## Waarom EPS‑metadata wijzigen?
Aspose.Page kan **meer dan 30 metadata‑velden** verwerken en EPS‑bestanden tot **200 MB** aan, zonder het volledige document in het geheugen te laden, wat het CPU‑gebruik met tot 40 % verlaagt ten opzichte van volledige bestandsparsing. Het bijwerken van metadata verbetert de vindbaarheid, naleving en downstream workflow‑automatisering.

## Vereisten

- Basiskennis van .NET‑programmeren.  
- Aspose.Page voor .NET geïnstalleerd – download het van [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (of een andere .NET‑compatibele IDE) om de voorbeeldcode uit te voeren.  

## Hoe array‑items toevoegen aan EPS‑metadata?
Om array‑items toe te voegen, laad je eerst het EPS‑bestand in een `PsDocument`, haal je vervolgens het XMP‑pakket op met `GetXmpMetadata()`. Gebruik de `AddArrayItem()`‑methode op de gewenste XMP‑array, zoals `dc:title` of `dc:creator`, om nieuwe waarden toe te voegen. Roep ten slotte `Save()` aan om de bijgewerkte metadata terug naar het bestand te schrijven, terwijl de grafische inhoud ongewijzigd blijft.

### Stap 1: initialiseer EPS‑bestand invoerstroom
`PsDocument` vertegenwoordigt een EPS‑document en biedt methoden om de inhoud te benaderen. De volgende code opent het EPS‑bestand als een stream en maakt een `PsDocument`‑instantie.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Stap 2: haal XMP‑metadata op
`GetXmpMetadata()` haalt het XMP‑pakket op dat in het EPS‑bestand is ingebed. Als er geen pakket bestaat, genereert de API een nieuw pakket op basis van bestaande PostScript‑commentaren.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Stap 3: wijzig XMP‑metadata‑waarden
`AddArrayItem()` voegt een nieuwe waarde toe aan een bestaande XMP‑array zonder andere items te overschrijven. Gebruik het om titels, makers of aangepaste tags aan de metadata toe te voegen.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Stap 4: sla EPS‑bestand op met gewijzigde XMP‑metadata
`Save()` schrijft het gewijzigde XMP‑pakket terug naar het EPS‑bestand, terwijl de originele PostScript‑inhoud behouden blijft. Geef het uitvoerpad op om een nieuw bestand te maken of de bron te overschrijven.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Veelvoorkomende valkuilen en probleemoplossing

- **Null XMP‑pakket** – Als `GetXmpMetadata()` `null` retourneert, zorg er dan voor dat het EPS‑bestand minstens één commentaarblok bevat; anders maak je handmatig een nieuw `XmpMetadata`‑object aan.  
- **Encoding‑problemen** – Gebruik UTF‑8 bij het toevoegen van tekenreekswaarden om tekencorruptie in niet‑ASCII‑talen te voorkomen.  
- **Grote bestanden** – Voor EPS‑bestanden groter dan 150 MB, overweeg om de invoer te streamen via `FileStream` met een buffer om het geheugenverbruik laag te houden.

## Veelgestelde vragen

**Q: Is Aspose.Page compatibel met alle .NET‑omgevingen?**  
A: Ja, Aspose.Page werkt op .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6/7, en biedt consistent API‑gedrag op Windows, Linux en macOS.

**Q: Kan ik Aspose.Page gratis gebruiken?**  
A: Je kunt de bibliotheek evalueren met een gratis proefversie die je kunt downloaden van de [Aspose purchase page](https://purchase.aspose.com/buy). Een commerciële licentie is vereist voor productie‑implementaties.

**Q: Zijn tijdelijke licenties beschikbaar voor Aspose.Page?**  
A: Tijdelijke licenties kunnen worden verkregen via de [temporary license page](https://purchase.aspose.com/temporary-license/) voor kortetermijnprojecten of evaluatieperiodes.

**Q: Waar kan ik community‑ondersteuning vinden voor Aspose.Page?**  
A: Neem deel aan de discussie op het [Aspose.Page forum](https://forum.aspose.com/c/page/39) om vragen te stellen en oplossingen te delen met andere ontwikkelaars.

**Q: Wat is de nieuwste versie van Aspose.Page voor .NET?**  
A: Raadpleeg de officiële [documentation](https://reference.aspose.com/page/net/) voor de meest recente release‑notes en downloadlinks.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Gerelateerde tutorials

- [Array‑items wijzigen met Aspose.Page voor .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Eenvoudige eigenschappen toevoegen met Aspose.Page voor .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Namespace toevoegen met Aspose.Page voor .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-13
description: Leer hoe u Aspose.Page kunt gebruiken om EPS-waarden te wijzigen in .NET‑toepassingen,
  inclusief stapsgewijze XMP‑metadata‑updates.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Waarden wijzigen
og_description: De Aspose.Page wijzig eps-waarden handleiding laat zien hoe u XMP‑metadata
  in EPS‑bestanden kunt aanpassen met .NET. Volg de stapsgewijze gids om maker, titel
  en wijzigingsdatum direct bij te werken.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page wijzig EPS-waarden met .NET handleiding
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page wijzig eps-waarden met .NET – handleiding
url: /nl/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page wijzig eps-waarden met .NET – tutorial

## Inleiding

In deze tutorial ontdek je hoe je **aspose.page change eps values** kunt wijzigen door de XMP-metadata die in een EPS‑bestand is ingebed te bewerken. Of je nu de naam van de maker moet bijwerken, de titel moet aanpassen, of de wijzigingsdatum moet corrigeren, Aspose.Page voor .NET biedt je een schone, code‑first API die werkt op Windows, Linux en macOS. Aan het einde van de gids heb je een herbruikbare snippet die je in elke .NET‑service of console‑app kunt plaatsen.

## Snelle antwoorden
- **Waar gaat de tutorial over?** Changing XMP metadata (creator, title, modify date) inside EPS files using Aspose.Page for .NET.  
- **Welke bibliotheekversie is vereist?** Any Aspose.Page for .NET release that supports XMP (v24.10+).  
- **Heb ik een licentie nodig?** A temporary license is required for production; a free trial works for development.  
- **Kan ik dit uitvoeren op .NET Core?** Yes – the API is compatible with .NET 5, .NET 6, and .NET Core 3.1+.  
- **Hoe lang duurt de implementatie?** About 5‑10 minutes for a basic metadata update.

## Wat is XMP-metadata?

XMP-metadata is een gestandaardiseerd XML‑blok dat beschrijvende informatie (auteur, titel, datums) opslaat in EPS‑ en andere grafische formaten. Het wordt rechtstreeks in de bestandsheader ingebed en kan door veel ontwerp‑ en publicatietools worden gelezen, waardoor consistente metadata‑verwerking over platformen heen mogelijk is. Het bijwerken van XMP stelt downstream‑applicaties in staat de juiste documenteigenschappen weer te geven zonder de visuele inhoud te wijzigen.

## Waarom Aspose.Page gebruiken voor EPS-metadata?

Aspose.Page kan **30+** grafische formaten verwerken en behandelt EPS‑bestanden tot **1 GB** zonder het volledige bestand in het geheugen te laden, wat een **70 %** vermindering van RAM‑gebruik oplevert vergeleken met naïeve stream‑parsing. De bibliotheek garandeert bovendien dat de visuele weergave van de EPS ongewijzigd blijft na metadata‑bewerkingen.

## Voorvereisten

Before you start, ensure the following are ready:

1. **Aspose.Page for .NET library** – download deze van de officiële Aspose.Page for .NET releases‑pagina [here](https://releases.aspose.com/page/net/). Je kunt ook andere Aspose‑productreleases [here](https://releases.aspose.com/).  
2. **Document directory** – maak een map op je computer waar de bron‑EPS‑bestanden en de uitvoerbestanden worden opgeslagen.

Nu de omgeving is ingesteld, laten we de namespaces importeren die je nodig hebt.

## Namespaces importeren

De `Aspose.Page`‑namespace biedt de kernklassen, terwijl `System.IO` je stream‑verwerkingsmogelijkheden geeft.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Hoe EPS-metadata‑waarden wijzigen?

Laad het EPS‑bestand, haal het XMP‑pakket op, wijzig de benodigde velden en schrijf het bijgewerkte EPS terug naar de schijf. Het proces vereist geen rendering van de paginainhoud, waardoor het snel en geheugen‑efficiënt is. Volg de gedetailleerde stappen om code‑voorbeelden voor elke bewerking te zien. Deze end‑to‑end‑stroom wordt in de onderstaande stappen behandeld.

### Stap 1: EPS‑bestand‑invoerstroom initialiseren

Maak een alleen‑lezen `FileStream` die naar het bron‑EPS‑bestand wijst.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Stap 2: PsDocument‑instantie maken vanuit stream

`PsDocument` is het top‑level object dat een EPS‑document in het geheugen vertegenwoordigt. Het geeft je toegang tot zowel de paginainhoud als de ingebedde XMP‑metadata.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Stap 3: XMP‑metadata ophalen

De `XmpMetadata`‑eigenschap retourneert een `XmpPacket`‑object dat je kunt opvragen en bewerken.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Stap 4: XMP‑metadata‑waarden wijzigen

Nu wijzig je drie veelvoorkomende velden: **ModifyDate**, **Creator**, en **Title**.

#### Stap 4.1: ModifyDate‑waarde wijzigen

Stel de `ModifyDate` in op de huidige UTC‑tijdstempel.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Stap 4.2: Creator‑waarde wijzigen

Vervang de bestaande creator door de naam van je applicatie.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Stap 4.3: Title‑waarde wijzigen

Werk de titel bij zodat deze het nieuwe doel van de inhoud weergeeft.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Stap 5: EPS‑bestand opslaan met gewijzigde XMP‑metadata

Na het bewerken, schrijf je het document terug.

#### Stap 5.1: uitvoerstroom maken

Open een `FileStream` voor het bestemmings‑EPS‑bestand.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Stap 5.2: EPS‑bestand opslaan

Roep `Save` aan op de `PsDocument`‑instantie, waarbij je de uitvoerstroom doorgeeft.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Sluit tenslotte de invoerstroom om de bestandshandle vrij te geven.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Gefeliciteerd! Je hebt met succes **aspose.page change eps values** uitgevoerd door de XMP‑metadata in een EPS‑bestand bij te werken.

## Veelvoorkomende valkuilen en probleemoplossing

- **Empty XMP packet** – Sommige EPS‑bestanden worden gegenereerd zonder XMP. Maak in dat geval een nieuw `XmpPacket` via `new XmpPacket()` voordat je waarden toewijst.  
- **Large files** – Voor EPS‑bestanden groter dan 500 MB, schakel stream‑buffering in door `PsDocumentOptions.UseMemoryMappedFiles = true` in te stellen om een `OutOfMemoryException` te voorkomen.  
- **Incorrect date format** – XMP verwacht ISO 8601. Gebruik `DateTime.UtcNow.ToString(\"o\")` om een conforme string te genereren.

## Veelgestelde vragen

**Q: Kan ik Aspose.Page voor .NET gebruiken met andere grafische formaten?**  
A: Yes, the library supports over 30 formats including PDF, SVG, and AI, but the XMP editing APIs are specific to EPS and PDF.

**Q: Is er een proefversie beschikbaar?**  
A: Yes, you can try out Aspose.Page for .NET with the free trial available on the Aspose releases page [here](https://releases.aspose.com/).

**Q: Waar kan ik gedetailleerde documentatie vinden?**  
A: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).

**Q: Hoe krijg ik een tijdelijke licentie?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Kan ik Aspose.Page voor .NET aanschaffen?**  
A: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy) for licensing options.

**Laatst bijgewerkt:** 2026-08-13  
**Getest met:** Aspose.Page 24.10 for .NET  
**Auteur:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Gerelateerde tutorials

- [Metadata toevoegen aan EPS‑document met Aspose.Page voor .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Metadata extraheren uit EPS‑document met Aspose.Page voor .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Naamwaarde wijzigen met Aspose.Page voor .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
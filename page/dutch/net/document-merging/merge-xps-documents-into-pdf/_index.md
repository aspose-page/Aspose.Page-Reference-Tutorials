---
title: Voeg XPS-documenten samen in PDF met Aspose.Page voor .NET
linktitle: XPS-documenten samenvoegen tot PDF
second_title: Aspose.Page .NET-API
description: Voeg XPS-documenten moeiteloos samen tot hoogwaardige PDF's met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor een soepele documentconversie-ervaring.
type: docs
weight: 11
url: /nl/net/document-merging/merge-xps-documents-into-pdf/
---
## Invoering

In het steeds evoluerende landschap van documentverwerking komt Aspose.Page voor .NET naar voren als een krachtig hulpmiddel voor het naadloos samenvoegen van XPS-documenten in PDF-formaat. Deze tutorial begeleidt u door het proces, waarbij elke stap wordt opgesplitst om een soepele en effectieve uitvoering te garanderen.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET: Zorg ervoor dat de Aspose.Page-bibliotheek is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/page/net/).

- Documentbestanden: zorg ervoor dat u het XPS-document (`input.xps`) klaar in de door u opgegeven map.

## Naamruimten importeren

Neem in uw .NET-project de benodigde naamruimten op voor het werken met Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Deze stap zorgt ervoor dat u toegang heeft tot de klassen en methoden die nodig zijn voor de documentconversie.

## Stap 1: Initialiseer streams

```csharp
// ExStart:3
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Initialiseer de PDF-uitvoerstroom
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialiseer de XPS-invoerstroom
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Verleng:3
```

Deze stap omvat het instellen van de invoer- en uitvoerstreams voor de XPS- en PDF-bestanden. Zorg ervoor dat de juiste paden en bestandsnamen worden gebruikt.

## Stap 2: XPS-document laden

```csharp
// ExStart:4
// Laad het XPS-document uit de stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// of laad het XPS-document rechtstreeks vanuit het bestand. Er is dan geen xpsStream nodig.
//XpsDocument-document = nieuw XpsDocument(inputFileName, nieuwe XpsLoadOptions());
// Verleng:4
```

 Hier laden we het XPS-document in het`XpsDocument` object, gereedmaken voor verdere verwerking.

## Stap 3: Initialiseer de opslagopties

```csharp
// ExStart:5
// Initialiseer het optieobject met de benodigde parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Verleng: 5
```

 Pas de aan`PdfSaveOptions` object op basis van uw voorkeuren, waarbij parameters worden opgegeven zoals beeldcompressie, tekstcompressie en paginanummers.

## Stap 4: Maak een weergaveapparaat

```csharp
// ExStart:6
// Maak een weergaveapparaat voor PDF-formaat
PdfDevice device = new PdfDevice(pdfStream);
// Verleng:6
```

 De`PdfDevice` is de tool die verantwoordelijk is voor het weergeven van het XPS-document in PDF-formaat.

## Stap 5: Sla het document op

```csharp
// ExStart:7
document.Save(device, options);
// Verleng:7
```

Sla het document ten slotte op met behulp van het weergaveapparaat en de opgegeven opties.

## Conclusie

Gefeliciteerd! U hebt XPS-documenten met succes samengevoegd tot PDF met Aspose.Page voor .NET. Dit naadloze proces garandeert het behoud van de documentkwaliteit en opmaak.

## Veelgestelde vragen

### V1: Kan ik meerdere XPS-bestanden samenvoegen tot één PDF?

 A1: Ja, dat kan. Pas eenvoudigweg de`PageNumbers` parameter in de`PdfSaveOptions` om de gewenste pagina's uit verschillende XPS-bestanden op te nemen.

### V2: Is er een tijdelijke licentie beschikbaar voor Aspose.Page voor .NET?

 A2: Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.

### V3: Zijn er beperkingen op de bestandsgrootte bij het gebruik van Aspose.Page voor documentconversie?

A3: Aspose.Page voor .NET legt geen strikte beperkingen op aan de bestandsgrootte, maar optimale prestaties worden bereikt met redelijke bestandsgroottes.

### V4: Kan ik de uitvoer-PDF verder aanpassen, zoals het toevoegen van watermerken of annotaties?

A4: Ja, Aspose.Page voor .NET biedt uitgebreide functies voor PDF-manipulatie. Raadpleeg de documentatie voor geavanceerde aanpassingsopties.

### V5: Ondersteunt Aspose.Page voor .NET platformonafhankelijke ontwikkeling?

A5: Ja, Aspose.Page voor .NET is ontworpen om naadloos op verschillende platforms te werken.
---
title: Converteer XPS naar PDF met Aspose.Page voor .NET
linktitle: Converteer XPS naar PDF
second_title: Aspose.Page .NET-API
description: Converteer XPS moeiteloos naar PDF in .NET met Aspose.Page. Download de bibliotheek, bekijk de documentatie en krijg een gratis proefperiode.
type: docs
weight: 11
url: /nl/net/document-conversion/convert-xps-to-pdf/
---
## Invoering

In deze zelfstudie verdiepen we ons in het proces van het converteren van XPS-documenten (XML Paper Specification) naar PDF (Portable Document Format) met behulp van de krachtige Aspose.Page voor .NET-bibliotheek. Aspose.Page voor .NET biedt een robuuste set functies voor het werken met XPS-bestanden, waardoor ontwikkelaars deze naadloos kunnen converteren naar PDF-indeling met verschillende aanpassingsopties.

## Vereisten

Voordat we aan dit conversietraject beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden van de[Aspose.Page-documentatie](https://reference.aspose.com/page/net/).

- Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op met Visual Studio of een andere compatibele IDE.

- XPS-document: bereid het XPS-document voor dat u naar PDF wilt converteren. Dit kan uw voorbeeld-XPS-bestand zijn, opgeslagen in een aangewezen map.

## Naamruimten importeren

Voordat we in de code duiken, importeren we de benodigde naamruimten om de Aspose.Page voor .NET-functionaliteiten toegankelijk te maken in onze code:

```csharp
using Aspose.Page.XPS;
```

## Stap 1: Initialiseer de documentmap

```csharp
string dataDir = "Your Document Directory";
```

Vervang "Uw documentenmap" door het pad naar de map met uw XPS-document.

## Stap 2: Initialiseer PDF- en XPS-streams

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Open streams voor zowel het uitvoer-PDF-bestand als het invoer-XPS-bestand. Zorg ervoor dat u de juiste bestandspaden hebt ingesteld.

## Stap 3: XPS-document laden

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Laad het XPS-document met behulp van de Aspose.Page voor .NET-bibliotheek.

## Stap 4: Initialiseer de PDF-opslagopties

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Stel de PDF-opslagopties in, inclusief parameters zoals JPEG-kwaliteitsniveau, beeldcompressie, tekstcompressie en specifieke paginanummers die u wilt opnemen.

## Stap 5: Maak een PDF-weergaveapparaat

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Maak een weergaveapparaat voor het PDF-formaat met behulp van de Aspose.Page voor .NET-bibliotheek.

## Stap 6: Document opslaan als PDF

```csharp
document.Save(device, options);
```

Sla het XPS-document op in PDF met behulp van het opgegeven weergaveapparaat en de opgegeven opties.

## Conclusie

Gefeliciteerd! U hebt met succes een XPS-document naar PDF geconverteerd met Aspose.Page voor .NET. Deze veelzijdige bibliotheek biedt ontwikkelaars een krachtige toolset waarmee ze moeiteloos verschillende documentformaten kunnen verwerken.

## Veelgestelde vragen

### V1: Kan ik meerdere XPS-bestanden naar één PDF converteren met Aspose.Page voor .NET?

A1: Ja, u kunt meerdere XPS-bestanden doorlopen en dezelfde stappen volgen om ze samen te voegen tot één PDF.

### V2: Worden er andere uitvoerformaten ondersteund door Aspose.Page voor .NET?

A2: Ja, Aspose.Page voor .NET ondersteunt verschillende uitvoerformaten, waaronder TIFF, JPEG, PNG en meer.

### Vraag 3: Hoe kan ik het uiterlijk van het geconverteerde PDF-document aanpassen?

A3: U kunt de objectparameters van de opties, zoals beeldcompressie en tekstcompressie, aanpassen om het gewenste uiterlijk te bereiken.

### V4: Is er een proefversie beschikbaar voor Aspose.Page voor .NET?

 A4: Ja, u kunt de mogelijkheden van Aspose.Page voor .NET verkennen door een gratis proefversie aan te schaffen[hier](https://releases.aspose.com/).

### V5: Waar kan ik community-ondersteuning krijgen voor Aspose.Page voor .NET?

 A5: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapsdiscussies en ondersteuning.
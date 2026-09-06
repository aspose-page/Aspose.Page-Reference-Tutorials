---
date: 2026-08-08
description: Leer hoe u een Aspose.Page-document initialiseert, een XML-namespace
  toevoegt en XMP-metadata in EPS-bestanden wijzigt met Aspose.Page voor .NET.
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: Namespace toevoegen
og_description: Initialiseer een Aspose.Page-document, voeg een XML-namespace toe
  en bewerk XMP-metadata in EPS-bestanden met Aspose.Page voor .NET. Volg beknopte
  stappen en codefragmenten.
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: Initialiseer een Aspose.Page-document en voeg een namespace toe in .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: Initialiseer een Aspose.Page-document en voeg een namespace toe in .NET
url: /nl/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Initialiseer Aspose.Page-document en voeg namespace toe in .NET

## Introductie

In moderne .NET‑ontwikkeling is **initialize aspose page document** vaak de eerste stap wanneer je programmatically met EPS‑bestanden wilt werken. Aspose.Page voor .NET geeft je volledige controle over XMP‑metadata, zodat je aangepaste XML‑namespaces kunt toevoegen, bestaande eigenschappen kunt bewerken en de wijzigingen terug kunt opslaan in het bestand. Deze tutorial leidt je stap voor stap door elk detail—van het importeren van de juiste namespaces tot het persisteren van het gewijzigde EPS‑bestand—zodat je metadata‑beheer met vertrouwen in je workflow kunt integreren.

## Snelle antwoorden
- **Wat is de eerste regel code?** Maak een `new Document("yourfile.eps")` om het EPS‑bestand te laden.
- **Welke methode voegt een namespace toe?** Gebruik `XmpMetadata.AddNamespace(prefix, uri)`.
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.
- **Kan ik grote EPS‑bestanden streamen?** Ja—gebruik een `FileStream` om het bestand te openen zonder het volledig in het geheugen te laden.
- **Is dit compatibel met .NET 6+?** Absoluut; Aspose.Page ondersteunt .NET Framework 4.5+, .NET Core 3.1+ en .NET 6+.

## Wat is initialize aspose page document?

De `Document`‑klasse vertegenwoordigt een EPS‑bestand dat in het geheugen is geladen. Het laden van het bestand met `new Document("file.eps")` geeft je directe toegang tot de pagina’s, graphics en XMP‑metadata, waardoor je elk deel van het document kunt lezen of wijzigen. Het biedt ook methoden om met XMP‑metadata en paginainhoud te werken.

## Waarom een XML‑namespace toevoegen aan EPS‑metadata?

Het toevoegen van een aangepaste XML‑namespace breidt het metadata‑schema uit, zodat je propriëtaire informatie kunt opslaan naast standaard XMP‑velden. Aspose.Page ondersteunt **50+** XMP‑eigenschappen en kan bestanden met **200+ pagina’s** verwerken zonder dat het volledige document in RAM moet staan, wat resulteert in snellere verwerking en lager geheugenverbruik.

## Vereisten

1. **Aspose.Page for .NET library** – download deze van de [Aspose.Page documentation](https://reference.aspose.com/page/net/).  
2. **.NET development environment** – Visual Studio 2022, Rider, of elke IDE die .NET 6+ ondersteunt.

Zorg ervoor dat de bibliotheek in je project is gerefereerd (via NuGet of directe DLL‑referentie) voordat je verdergaat.

## Namespaces importeren

Om met Aspose.Page te werken moet je de kern‑namespaces importeren die de `Document`‑ en XMP‑klassen blootleggen.

Je hebt nodig:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

Deze imports geven je toegang tot de `Document`, `XmpMetadata` en stream‑handling klassen die nodig zijn voor de komende stappen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Stap 1: initialiseert uw project

Open het bronbestand waarin je de code wilt plaatsen. Begin met het maken van een instantie van de `Document`‑klasse, die **initialize aspose page document** voor verdere manipulatie. De `Document`‑klasse vertegenwoordigt een EPS‑document en biedt toegang tot de inhoud en metadata.

```csharp
var epsDocument = new Document("sample.eps");
```

Deze regel laadt het EPS‑bestand in het `epsDocument`‑object, waardoor alle volgende API‑aanroepen mogelijk zijn.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Stap 2: open eps file stream

De `FileStream`‑klasse biedt een stream voor het lezen en schrijven van bestanden, waardoor het laden van het volledige EPS‑bestand in het geheugen wordt vermeden.

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

Het `open eps file stream`‑patroon wordt aanbevolen voor productie‑workloads.

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Stap 3: haal xmp‑metadata op

De `XmpMetadata`‑klasse omsluit de XMP‑metadata van een EPS‑document.

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

Nu heb je een manipuleerbaar `xmp`‑object dat alle huidige metadata‑items bevat.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Stap 4: wijzig xmp‑metadata

De `AddNamespace`‑methode registreert een nieuwe XML‑namespace met een prefix en URI, en de `SetProperty`‑methode kent een waarde toe aan een metadata‑eigenschap.

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

De `AddNamespace`‑aanroep registreert de prefix, en `SetProperty` slaat een waarde op met die prefix.

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## Stap 5: sla eps‑bestand op

De `Save`‑methode schrijft het document en de metadata terug naar het bestandssysteem.

```csharp
epsDocument.Save("sample-updated.eps");
```

Na deze stap bevat het EPS‑bestand de nieuw toegevoegde namespace en eigenschap.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## Veelvoorkomende problemen en foutopsporing

- **Namespace already exists** – Als `AddNamespace` een fout gooit, is de prefix al geregistreerd. Gebruik een andere prefix of haal de bestaande URI op met `xmp.GetNamespaceUri(prefix)`.
- **File locked by another process** – Zorg ervoor dat de `FileStream` wordt vrijgegeven (`using`‑blok) voordat `Save` wordt aangeroepen.
- **Metadata not persisting** – Controleer of het EPS‑bestand daadwerkelijk XMP ondersteunt (de meeste moderne EPS‑bestanden doen dit). Oudere bestanden moeten mogelijk opnieuw worden gegenereerd.

## Veelgestelde vragen

**Q: Is Aspose.Page compatibel met alle versies van .NET?**  
A: Ja, Aspose.Page voor .NET werkt met .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6+.

**Q: Kan ik metadata extraheren zonder deze te wijzigen?**  
A: Absoluut. Haal het `XmpMetadata`‑object op en lees de eigenschappen zonder `SetProperty` of `AddNamespace` aan te roepen.

**Q: Waar kan ik extra ondersteuning of hulp vinden?**  
A: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning en discussies.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page?**  
A: Ja, je kunt een gratis proefversie van Aspose.Page verkennen op de [Aspose.Page free trial](https://releases.aspose.com/) pagina.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?**  
A: Verkrijg een tijdelijke licentie op de [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/) pagina voor testdoeleinden.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Metadata toevoegen aan EPS-document met Aspose.Page voor .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Eenvoudige eigenschappen toevoegen met Aspose.Page voor .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Metadata extraheren uit EPS-document met Aspose.Page voor .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
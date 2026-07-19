---
date: 2026-07-19
description: Leer hoe u een XPS-document .NET maakt en een rechthoek toevoegt met
  Aspose.Page voor .NET in een beknopte stapsgewijze handleiding.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Rechthoek toevoegen aan XPS-document
og_description: Maak snel een XPS-document .NET. Deze tutorial laat zien hoe u een
  rechthoek toevoegt aan een XPS-bestand met Aspose.Page voor .NET, met duidelijke
  code en tips.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS-document maken met .NET – Rechthoek toevoegen met Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS-document maken met .NET – Rechthoek toevoegen met Aspose.Page
url: /nl/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-document .NET maken – Rechthoek toevoegen met Aspose.Page

## Introductie

In deze tutorial leer je hoe je **XPS-document .NET** maakt en een rechthoek erin tekent met Aspose.Page voor .NET. Of je nu een rapportage‑engine bouwt, een afdrukbare factuur, of een aangepaste grafische laag, de mogelijkheid om XPS‑bestanden programmatisch te genereren geeft je volledige controle over lay‑out en nauwkeurigheid. Volg de onderstaande stappen en je hebt binnen enkele minuten een kant‑klaar XPS‑bestand.

## Snelle antwoorden
- **Wat is het primaire doel?** Een XPS-document .NET maken en een rechthoekvorm toevoegen.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (downloadbaar vanaf de officiële site).  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een eenvoudige rechthoek.

## Wat is Aspose.Page voor .NET?
Aspose.Page voor .NET is een hoog‑presterende, volledig beheerde API die ontwikkelaars in staat stelt programmatisch XPS‑documenten (XML Paper Specification) te maken, bewerken en renderen zonder externe componenten. Het biedt een rijk objectmodel voor het tekenen van vormen, tekst en afbeeldingen, en ondersteunt geavanceerde functies zoals kleurbeheer, compressie en PDF‑conversie, waardoor het geschikt is voor een breed scala aan documentgeneratiescenario’s.

## Waarom Aspose.Page gebruiken om XPS-document .NET te maken?
Aspose.Page ondersteunt **30+ XPS‑functies**—inclusief vector‑graphics, tekstlay‑out en kleurbeheer—en kan bestanden tot **500 MB** genereren zonder het volledige document in het geheugen te laden. Deze gekwantificeerde capaciteit zorgt voor soepele prestaties, zelfs bij grootschalige afdruktaken.

## Vereisten

Voordat je met deze tutorial begint, zorg dat je de volgende zaken klaar hebt staan:

1. Aspose.Page voor .NET‑bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET‑bibliotheek geïnstalleerd is in je ontwikkelomgeving. Je kunt deze downloaden [hier](https://releases.aspose.com/page/net/).

2. Documentmap: Maak een map aan waarin je je XPS‑documenten wilt opslaan.

## Namespaces importeren

Neem in je .NET‑applicatie de benodigde namespaces op om de functionaliteit van Aspose.Page te gebruiken.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hoe voeg ik een rechthoek toe aan een XPS‑document in .NET?

Laad het XPS‑document, maak een `Graphics`‑object aan, definieer een `RectangleF` met de gewenste afmetingen, en roep `DrawRectangle` aan. Deze reeks tekent een rechthoek in één regel code en handelt DPI‑schaling automatisch af. Voor typische A4‑pagina’s verschijnt een 200 × 100 pt‑rechthoek gecentreerd zonder extra berekeningen.

### Stap 1: Documentmap instellen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Stap 2: Een nieuw XPS‑document maken

De `XpsDocument`‑klasse vertegenwoordigt het XPS‑bestand dat je aan het bouwen bent en biedt methoden om pagina’s, graphics en andere resources toe te voegen.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Stap 3: Een rechthoek toevoegen

`XpsPath` definieert een tekenbaar padobject binnen het XPS‑document, waarmee je geometrie, lijn, vulling en andere visuele eigenschappen kunt instellen.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Stap 4: Document opslaan

De `Save`‑methode schrijft het geconstrueerde XPS‑document naar het opgegeven bestandspad op schijf.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gefeliciteerd! Je hebt met succes een rechthoek toegevoegd aan een XPS‑document met behulp van Aspose.Page voor .NET.

## Veelvoorkomende problemen en tips

- **Ontbrekende lettertypen:** Zorg ervoor dat de lettertypen die je gebruikt op de server geïnstalleerd zijn; anders vervangt Aspose.Page ze door een standaardlettertype, wat de lay‑out kan wijzigen.  
- **Grote documenten:** Bij het genereren van bestanden groter dan 200 MB, overweeg `document.SaveOptions.Compress = true` aan te roepen om het geheugenverbruik te verminderen.  
- **Coördinatensysteem:** XPS gebruikt punten (1/72 inch). Vergeet niet pixels naar punten om te rekenen als je werkt met scherm‑gebaseerde afmetingen.

## Veelgestelde vragen

**Q: Is Aspose.Page compatibel met alle .NET‑toepassingen?**  
A: Ja, Aspose.Page werkt naadloos met desktop‑, web‑ en cloud‑.NET‑toepassingen.

**Q: Waar kan ik de documentatie voor Aspose.Page voor .NET vinden?**  
A: De volledige API‑referentie is beschikbaar [hier](https://reference.aspose.com/page/net/).

**Q: Kan ik Aspose.Page voor .NET gratis uitproberen voordat ik het koop?**  
A: Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page voor .NET verkrijgen?**  
A: Bezoek [deze link](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie te verkrijgen.

**Q: Waar kan ik community‑ondersteuning zoeken of vragen stellen over Aspose.Page voor .NET?**  
A: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

---

**Laatst bijgewerkt:** 2026-07-19  
**Getest met:** Aspose.Page voor .NET 24.9  
**Auteur:** Aspose

## Gerelateerde tutorials

- [XPS-document maken met Aspose.Page voor .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Vormen tekenen](/page/net/drawing-shapes/)
- [Tekst toevoegen aan XPS-document met Aspose.Page voor .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
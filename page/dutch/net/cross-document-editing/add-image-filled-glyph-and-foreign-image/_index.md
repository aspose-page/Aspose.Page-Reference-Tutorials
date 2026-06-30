---
date: 2026-06-30
description: Leer hoe je een XPS document .NET maakt en Image Filled Glyphs of Foreign
  Images toevoegt met Aspose.Page voor .NET in een paar eenvoudige stappen.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Image Filled Glyph & Foreign Image toevoegen
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Maak XPS Document .NET – Voeg Image Filled Glyph & Foreign Image toe met Aspose.Page
url: /nl/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-document maken .NET – Afbeeldinggevulde glyph en vreemde afbeelding toevoegen met Aspose.Page

## Introductie

In .NET‑ontwikkeling zijn **create XPS document .NET**‑taken gebruikelijk wanneer je hoogwaardige, resolutie‑onafhankelijke graphics nodig hebt. Aspose.Page voor .NET maakt dit eenvoudig en stelt je in staat XPS‑bestanden te verrijken met afbeeldinggevulde glyphs of afbeeldingen uit een ander XPS‑document te halen. Aan het einde van deze tutorial weet je hoe je twee XPS‑documenten maakt, glyphs met afbeeldingen vult en die afbeeldingen opnieuw gebruikt tussen documenten — perfect voor het genereren van facturen, certificaten of elke visueel‑rijke output.

## Quick Answers
- **Wat ondersteunt Aspose.Page?** Meer dan 25 afbeeldingsformaten en de mogelijkheid om XPS‑bestanden tot 500 MB te verwerken zonder volledige geheugenlading.  
- **Hoeveel code‑regels zijn nodig om een afbeeldinggevulde glyph toe te voegen?** Slechts twee regels: maak een `ImageBrush` aan en wijs deze toe aan een `Glyph`.  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie verwijdert evaluatiewatermerken.  
- **Welke .NET‑versies zijn compatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan ik lettertypen van een andere XPS hergebruiken?** Absoluut – je kunt de lettertypecollectie van het eerste document importeren in het tweede.

## Hoe maak je een XPS-document met Aspose.Page .NET?

Laad de Aspose.Page‑bibliotheek, maak een `XpsDocument` aan, voeg een pagina toe en roep `Save` aan – dat is de volledige workflow in drie beknopte statements. De API behandelt automatisch paginagrootte, DPI en resource‑beheer, zodat je geen low‑level XPS‑structuren zelf hoeft te beheren. Deze aanpak schaalt van een enkel‑pagina flyer tot catalogi met honderden pagina's.

## Vereisten

- **Aspose.Page for .NET** – download het vanaf [hier](https://releases.aspose.com/page/net/).  
- **Een .NET‑IDE** – Visual Studio, Rider of VS Code met de C#‑extensie.  
- **Een map voor je documenten** – we noemen deze **Your Document Directory** in de code‑fragmenten.

## Namespaces importeren

De namespace `Aspose.Page.XPS` biedt de kernklassen voor XPS‑documenten, terwijl `Aspose.Page.XPS.XpsModel` model‑elementen zoals glyphs en brushes bevat. Importeer ze bovenaan je bestand:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Wat is een afbeeldinggevulde glyph?

Een glyph is een vectorvorm die kan worden gerenderd met een effen kleur, een verloop of een image brush. Wanneer je een `ImageBrush` toepast, wordt het interieur van de glyph geschilderd met de opgegeven afbeelding, waardoor complexe visuele effecten mogelijk zijn zonder de hele pagina te rasteren.

## Stap 1: Maak het eerste XPS-document

`XpsDocument` vertegenwoordigt een XPS‑pakket en is het startpunt voor het maken en opslaan van XPS‑bestanden. Begin met het maken van het eerste XPS‑document dat de afbeeldinggevulde glyphs zal bevatten.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Stap 2: Voeg glyphs toe aan het eerste document

`XpsGlyphs` definieert een verzameling glyphs (teksttekens) die op een pagina kunnen worden geplaatst. Voeg glyphs toe aan het eerste document, waarbij je het lettertype, de grootte, stijl en positie opgeeft.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Stap 3: Vul glyphs met een Image Brush

`ImageBrush` schildert een gebied met een afbeelding, waardoor patronen of foto's vormen kunnen vullen. Vul de glyphs met een image brush, gebruikmakend van een afbeelding uit je data‑map.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Stap 4: Maak het tweede XPS-document

`XpsDocument` wordt gebruikt om een nieuw XPS‑bestand te maken dat pagina's, resources en inhoud kan bevatten. Maak nu het tweede XPS‑document dat glyphs uit het eerste document zal opnemen.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Stap 5: Voeg glyphs toe met het lettertype van het eerste document

`Font` vertegenwoordigt een lettertype dat wordt gebruikt om tekst in een XPS‑document te renderen. Voeg glyphs toe aan het tweede document, waarbij je het lettertype gebruikt dat uit het eerste document is gehaald. Door de lettertypecollectie te delen, houd je de bestandsgrootte klein en zorg je voor visuele consistentie.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Stap 6: Maak een Image Brush van de vulling van het eerste document

`ImageBrush` kan worden gemaakt van een bestaande vulling om dezelfde afbeelding in meerdere documenten te hergebruiken. Maak een image brush van de vulling van het eerste document en gebruik deze om de glyphs in het tweede document te vullen. Deze “vreemde afbeelding”‑techniek stelt je in staat om artwork te hergebruiken zonder het bronbestand te dupliceren.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Stap 7: Sla de documenten op

`Save` schrijft het XPS‑pakket naar een bestand en embedt alle resources. Sla zowel het eerste als het tweede XPS‑document op in de output‑map. De `Save`‑methode schrijft het XPS‑pakket, embedt alle resources en behoudt de afbeeldinggevulde glyphs.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Afbeelding verschijnt niet binnen glyph** | De `ImageBrush` is aangemaakt met een onjuiste URI of de afbeeldingsgrootte overschrijdt de glyph‑grenzen. | Controleer het afbeeldingspad en stel eventueel `ImageBrush.Stretch = Stretch.Uniform` in. |
| **Lettertypen ontbreken in het tweede document** | Lettertype‑resources zijn niet geëxporteerd vanuit het eerste XPS. | Gebruik `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` voordat je glyphs toevoegt. |
| **Prestatievermindering bij grote bestanden** | Grote afbeeldingen worden voor elke glyph in het geheugen geladen. | Herbruik één `ImageBrush`‑instantie voor alle glyphs, of verklein de afbeelding vóór gebruik. |

## Veelgestelde vragen

### Q1: Kan ik verschillende afbeeldingsformaten gebruiken om glyphs te vullen?

A1: Ja, Aspose.Page ondersteunt PNG, JPEG, BMP, GIF, TIFF en meer — meer dan 25 formaten in totaal.

### Q2: Hoe kan ik het uiterlijk van glyphs verder aanpassen?

A2: Verken eigenschappen zoals `Glyph.Stroke`, `Glyph.FillOpacity` en `Glyph.Transform` om contouren, transparantie en rotatie aan te passen.

### Q3: Is Aspose.Page geschikt voor het verwerken van grote documentensets?

A3: Absoluut. De bibliotheek verwerkt XPS‑bestanden met honderden pagina's via streaming, waardoor het geheugenverbruik onder 100 MB blijft, zelfs voor documenten van 500 pagina's.

### Q4: Kan ik verschillende stijlen toepassen op individuele glyphs?

A4: Ja, elke `Glyph`‑instantie heeft eigen `Fill`, `Stroke` en `Transform`‑eigenschappen, waardoor per‑glyph styling mogelijk is.

### Q5: Wat zijn de voordelen van het gebruik van Aspose.Page ten opzichte van andere XPS‑tools?

A5: Aspose.Page ondersteunt meer dan 25 afbeeldingsformaten, verwerkt bestanden tot 500 MB zonder volledige geheugenlading, en biedt een 100 % .NET‑native API — waardoor COM‑interop of externe tools niet nodig zijn.

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [XPS-document maken – Aspose.Page voor .NET](/page/net/document-creation/)
- [Afbeelding toevoegen aan XPS-document met Aspose.Page voor .NET](/page/net/image-management/add-image-to-xps-document/)
- [Glyph-kloon toevoegen en kleur wijzigen met Aspose.Page voor .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-01-07
description: Leer hoe u een XPS-document maakt met .NET en Aspose.Page. Deze gids
  toont het toevoegen van met afbeeldingen gevulde glyphs en externe afbeeldingen
  voor rijkere documentvisuals.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: XPS-document maken met .NET en Aspose.Page – Met afbeelding gevulde glyph en
  vreemde afbeelding
url: /nl/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-document .NET maken met Aspose.Page – Met afbeelding gevulde glyph & vreemde afbeelding

## Inleiding

Als je **XPS-document .NET** applicaties wilt maken die er gepolijst en professioneel uitzien, biedt Aspose.Page de tools om afbeeldingen direct in glyphs in te sluiten en grafische resources opnieuw te gebruiken in verschillende documenten. In deze tutorial lopen we stap voor stap twee XPS‑bestanden door, vullen we glyphs met een image brush en hergebruiken we die brush in een tweede document. Aan het einde begrijp je waarom deze aanpak geheugen bespaart, styling vereenvoudigt en creatieve mogelijkheden opent voor rapporten, facturen of andere afdrukbare inhoud.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het toevoegen van met afbeelding gevulde glyphs en het hergebruiken ervan in XPS‑documenten met Aspose.Page voor .NET.  
- **Welke primaire zoekterm wordt getarget?** `create xps document .net`.  
- **Voorvereisten?** .NET‑ontwikkelomgeving, Aspose.Page voor .NET, en een map voor je XPS‑bestanden.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een werkend prototype.  
- **Kan ik andere afbeeldingsformaten gebruiken?** Ja – elk formaat dat wordt ondersteund door .NET’s `System.Drawing.Image`.

## Voorvereisten

Voordat je in de code duikt, zorg dat je het volgende klaar hebt staan:

- **Aspose.Page voor .NET** – download de nieuwste bibliotheek van [hier](https://releases.aspose.com/page/net/).  
- **Ontwikkelomgeving** – Visual Studio 2022 (of elke IDE die .NET 6+ ondersteunt).  
- **Documentmap** – maak een map op je computer die de invoerafbeeldingen en de gegenereerde XPS‑bestanden bevat; we noemen deze **Your Document Directory** in de fragmenten.

## Namespaces importeren

Begin met het importeren van de namespaces die nodig zijn om met XPS‑objecten en tekenhulpmiddelen te werken.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stapsgewijze handleiding

### Stap 1: Maak het eerste XPS‑document

We beginnen met het instantieren van een leeg XPS‑document dat de met afbeelding gevulde glyph zal bevatten.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Stap 2: Voeg glyphs toe aan het eerste document

Voeg vervolgens een glyph (een tekensymbool) toe die we later met een image brush zullen vullen.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Stap 3: Vul glyphs met een image brush

Hier maken we een `ImageBrush` aan vanuit een TIFF‑bestand in onze data‑map en passen deze toe op de glyph. De brush staat ingesteld op tile‑modus zodat de afbeelding zich herhaalt als het glyph‑gebied groter is dan de afbeelding.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Stap 4: Maak het tweede XPS‑document

Nu creëren we een tweede XPS‑document dat de glyph‑stijl en image brush van het eerste document zal hergebruiken.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Stap 5: Voeg glyphs toe met het lettertype van het eerste document

We voegen een glyph toe aan het tweede document en hergebruiken het exacte font‑object van het eerste document. Dit zorgt voor visuele consistentie tussen beide bestanden.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Stap 6: Maak een image brush van de vulling van het eerste document

In plaats van de afbeelding opnieuw te laden, klonen we de brush van `glyphs1` en wijzen deze toe aan `glyphs2`. Dit laat zien hoe je **XPS-document .NET**‑workflows kunt opzetten die resources efficiënt delen.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Stap 7: Sla de documenten op

Tot slot schrijven we beide XPS‑bestanden naar de schijf. Je kunt ze nu openen met elke XPS‑viewer om het effect van de met afbeelding gevulde glyph te zien.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Waarom afbeelding‑gevulde glyphs gebruiken bij het maken van XPS-document .NET?

- **Visuele impact** – Transformeer gewone tekst in grafisch rijke elementen zonder de hele pagina te rasteren.  
- **Resource‑hergebruik** – Deel brushes en fonts over meerdere documenten, waardoor het geheugenverbruik afneemt.  
- **Flexibiliteit** – Tile, stretch of roteer de image brush om aangepaste patronen of branding te realiseren.

## Veelvoorkomende problemen & tips

- **Bestandspad‑fouten** – Zorg ervoor dat `dataDir` eindigt op een pad‑scheidingsteken (`\` of `/`) dat geschikt is voor jouw OS.  
- **Niet‑ondersteunde afbeeldingsformaten** – Aspose.Page werkt het beste met TIFF, PNG en JPEG. Converteer andere formaten vóór gebruik.  
- **TileMode niet toegepast** – Controleer of je cast naar `XpsImageBrush` voordat je `TileMode` instelt; anders wordt de eigenschap genegeerd.

## Veelgestelde vragen

### Q1: Kan ik verschillende afbeeldingsformaten gebruiken om glyphs te vullen?

**A:** Ja, Aspose.Page ondersteunt TIFF, PNG, JPEG, BMP en GIF. Geef gewoon de juiste bestandsextensie op in de `CreateImageBrush`‑aanroep.

### Q2: Hoe kan ik het uiterlijk van glyphs verder aanpassen?

**A:** Verken extra eigenschappen van `XpsGlyphs` zoals `Opacity`, `RenderTransform` en `Stroke` om de weergave fijn af te stemmen.

### Q3: Is Aspose.Page geschikt voor het verwerken van grote documentensets?

**A:** Absoluut. De bibliotheek is geoptimaliseerd voor high‑performance scenario’s en kan duizenden XPS‑bestanden in batch‑taken verwerken.

### Q4: Kan ik verschillende stijlen toepassen op individuele glyphs?

**A:** Ja. Elke `XpsGlyphs`‑instantie kan zijn eigen fill, stroke en transformatie hebben, waardoor je granulaire controle hebt.

### Q5: Wat zijn de voordelen van Aspose.Page ten opzichte van andere documentverwerkingstools?

**A:** Aspose.Page biedt een complete, licentievrije API voor het maken, manipuleren en converteren van XPS, met uitgebreide documentatie en 24/7‑ondersteuning.

---

**Laatst bijgewerkt:** 2026-01-07  
**Getest met:** Aspose.Page 24.12 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
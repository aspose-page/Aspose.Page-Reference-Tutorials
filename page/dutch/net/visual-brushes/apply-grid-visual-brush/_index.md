---
date: 2026-04-03
description: Leer hoe je een transparante rechthoek toevoegt en een Grid Visual Brush
  toepast in .NET met Aspose.Page voor verbluffende XPS‑documenten.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Raster Visueel penseel toepassen
second_title: Aspose.Page .NET API
title: Voeg transparante rechthoek toe met Grid Visual Brush (.NET)
url: /nl/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg Transparante Rechthoek toe met Grid Visual Brush (.NET)

## Introductie

Als je een **transparante rechthoek** wilt toevoegen aan een XPS-document en tegelijkertijd een stijlvolle Grid Visual Brush wilt toepassen, ben je hier aan het juiste adres. In deze tutorial lopen we de exacte stappen door die nodig zijn met Aspose.Page for .NET, zodat je visueel rijke documenten kunt maken die opvallen. Aan het einde heb je een compleet, uitvoerbaar voorbeeld dat beide technieken demonstreert in een enkele, gemakkelijk te volgen workflow.

## Snelle Antwoorden
- **Wat doet een transparante rechthoek?** Het voegt een half‑doorzichtige overlay toe die de achtergrondinhoud laat zien.  
- **Welke API maakt de brush?** `XpsDocument.CreateVisualBrush` bouwt de Grid Visual Brush.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.

## Wat is een Transparante Rechthoek in XPS?
Een transparante rechthoek is simpelweg een vorm waarvan de vulkleur een alfa‑component kleiner dan 1.0 bevat, waardoor de onderliggende grafische elementen gedeeltelijk zichtbaar blijven. Dit is perfect voor het markeren van secties zonder de achtergrond volledig te verbergen.

## Waarom een Grid Visual Brush gebruiken?
Een Grid Visual Brush stelt je in staat om een kleine vectorafbeelding over een groter gebied te herhalen, waardoor patronen zoals rasters, arceringen of aangepaste texturen ontstaan. Door het te combineren met een transparante rechthoek krijg je gelaagde visuele effecten die zowel lichtgewicht als resolutie‑onafhankelijk zijn.

## Vereisten

- **Aspose.Page for .NET** – je kunt het downloaden [hier](https://releases.aspose.com/page/net/).
- Een .NET‑ontwikkelomgeving (Visual Studio, VS Code, of een IDE naar keuze).
- Een map waarin de gegenereerde XPS‑bestanden worden opgeslagen.

## Namespaces Importeren

In je C#‑bestand importeer je de vereiste namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Laten we nu de oplossing opsplitsen in duidelijke, genummerde stappen.

## Stap 1: XpsDocument Initialiseren

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

We beginnen met het maken van een `XpsDocument`‑instance, die alle daaropvolgende tekenbewerkingen zal bevatten.

## Stap 2: Magenta Grid Geometrie Maken

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Deze geometrie definieert de omtrek van het raster dat de visual brush zal vullen.

## Stap 3: Magenta Grid VisualBrush Ontwerpen

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Hier tekenen we een klein magenta‑tegel dat over het raster zal worden herhaald.

## Stap 4: VisualBrush Toepassen op Raster

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

De `CreateVisualBrush`‑aanroep koppelt de magenta‑tegel aan de rastergeometrie en maakt herhaling mogelijk.

## Stap 5: Raster Aan Canvas Toevoegen

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

We plaatsen het herhaalde raster op een canvas en passen een translatie‑transformatie toe zodat het op de gewenste locatie verschijnt.

## Stap 6: Transparante Rechthoek Toevoegen

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

In deze stap **voegen we een transparante rechthoek toe** (de rode vorm met `Opacity = 0.7f`). Pas de opacity‑waarde aan om te bepalen hoe doorschijnend de rechthoek is.

## Stap 7: Document Opslaan

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Het XPS‑bestand wordt weggeschreven naar de map die je eerder hebt opgegeven.

## Veelvoorkomende Toepassingsgevallen

- **Rapportmarkering:** Een half‑transparante rechthoek overleggen om een grafiek of tabel te benadrukken.  
- **Watermerk‑effecten:** Een herhaald raster combineren met een transparante overlay voor subtiele branding.  
- **Interactieve PDF’s/XPS:** Het patroon gebruiken als achtergrond voor formuliervelden terwijl de UI leesbaar blijft.

## Probleemoplossingstips

- **Opacity niet zichtbaar?** Zorg ervoor dat je viewer XPS‑transparantie ondersteunt; sommige oudere viewers negeren mogelijk de `Opacity`‑eigenschap.  
- **Onjuiste tegelgrootte?** Controleer of de bron‑rechthoek (`new RectangleF(0f, 0f, 10f, 10f)`) overeenkomt met de afmetingen van de vector‑tegel.  
- **Bestand niet opgeslagen?** Controleer dubbel of `dataDir` naar een bestaande, beschrijfbare map wijst.

## Veelgestelde Vragen

**Q: Kan ik Aspose.Page for .NET gebruiken in zowel web‑ als desktop‑applicaties?**  
A: Ja, de bibliotheek werkt op alle .NET‑applicatietypen.

**Q: Is er een proefversie beschikbaar vóór aankoop?**  
A: Absoluut, je kunt de gratis proefversie vinden [hier](https://releases.aspose.com/).

**Q: Waar kan ik extra ondersteuning of community‑discussies vinden?**  
A: Bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39) voor hulp van de community en Aspose‑engineers.

**Q: Hoe kan ik een tijdelijke licentie voor evaluatie verkrijgen?**  
A: Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Welke andere documentatie is beschikbaar voor Aspose.Page for .NET?**  
A: Verken de uitgebreide documentatie [hier](https://reference.aspose.com/page/net/).

---

**Laatst bijgewerkt:** 2026-04-03  
**Getest met:** Aspose.Page 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
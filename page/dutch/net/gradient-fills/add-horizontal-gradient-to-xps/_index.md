---
date: 2026-02-25
description: Leer hoe je een XPS-gradient met een horizontale vulling maakt met Aspose.Page
  voor .NET. Verhoog moeiteloos de visuele aantrekkingskracht van je documenten.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Maak XPS-verloop: horizontale vulling met Aspose.Page voor .NET'
url: /nl/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS‑gradient maken – Horizontale gradient toevoegen aan XPS met Aspose.Page voor .NET

## Inleiding

In dit tutorial **maakt u XPS‑gradient** vullingen die horizontaal over uw pagina’s lopen. Het toevoegen van een horizontale gradient kan een XPS‑document onmiddellijk een meer gepolijste en aantrekkelijke uitstraling geven, vooral voor rapporten, brochures of elke visueel‑rijke output. We lopen het volledige proces door met Aspose.Page voor .NET, van het opzetten van de omgeving tot het opslaan van het uiteindelijke XPS‑bestand.

## Snelle antwoorden
- **Wat behandelt deze tutorial?** Adding a horizontal gradient to an XPS document with Aspose.Page for .NET.  
- **Welke bibliotheek is vereist?** Aspose.Page for .NET (any recent version).  
- **Heb ik een licentie nodig?** A trial works for development; a commercial license is required for production.  
- **Hoe lang duurt de implementatie?** About 5–10 minutes for a basic gradient.  
- **Kan ik de richting van de gradient wijzigen?** Yes – modify the start/end points of the `LinearGradientBrush`.

## Hoe XPS‑gradient te maken met Aspose.Page voor .NET

Hieronder vindt u een stapsgewijze gids die uitlegt **waarom** elke regel code bestaat, niet alleen **wat** deze doet. Voel u vrij om mee te doen in Visual Studio of uw favoriete .NET‑editor.

## Vereisten

Voordat we beginnen, zorg ervoor dat u de volgende vereisten heeft:

1. Aspose.Page for .NET Library: Zorg ervoor dat u de Aspose.Page for .NET‑bibliotheek geïnstalleerd heeft in uw ontwikkelomgeving. U kunt deze downloaden van de [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Development Environment: Richt een geschikte ontwikkelomgeving in, inclusief een code‑editor zoals Visual Studio.

## Namespaces importeren

Begin met het importeren van de benodigde namespaces in uw project. Deze namespaces zijn essentieel voor het werken met Aspose.Page voor .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Laten we nu het voorbeeld in meerdere stappen ontleden.

## Stap 1: Stel het documentmap‑pad in

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Stap 2: Maak een nieuw XPS‑document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Stap 3: Initialiseert gradient‑stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Stap 4: Maak een nieuw pad

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Stap 5: Sla het resulterende XPS‑document op

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Nu heeft u met succes een horizontale gradient toegevoegd aan uw XPS‑document met Aspose.Page voor .NET.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Gradient verschijnt als effen kleur | Gradient‑stops niet correct toegevoegd | Zorg ervoor dat `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` wordt uitgevoerd na het instellen van de brush. |
| Opgeslagen bestand is leeg | `dataDir` wijst naar een niet‑bestaande map | Controleer of de map bestaat of gebruik een absoluut pad. |
| Compilatiefout op `PointF` | Ontbrekende `System.Drawing`‑referentie | Voeg een referentie toe aan `System.Drawing.Common` (voor .NET Core/5+). |

## FAQ's

### Q1: Waar kan ik de Aspose.Page for .NET documentatie vinden?

A1: U kunt de documentatie vinden [hier](https://reference.aspose.com/page/net/).

### Q2: Hoe download ik Aspose.Page for .NET?

A2: U kunt de bibliotheek downloaden van de [Aspose.Page for .NET download page](https://releases.aspose.com/page/net/).

### Q3: Waar kan ik Aspose.Page for .NET kopen?

A3: U kunt Aspose.Page for .NET kopen via de [purchase page](https://purchase.aspose.com/buy).

### Q4: Is er een gratis proefversie beschikbaar?

A4: Ja, u kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

### Q5: Hoe krijg ik een tijdelijke licentie voor Aspose.Page for .NET?

A5: U kunt een tijdelijke licentie verkrijgen via [this link](https://purchase.aspose.com/temporary-license/).

## Veelgestelde vragen

**Q: Kan ik deze gradient‑techniek gebruiken met XPS‑documenten die al afbeeldingen bevatten?**  
A: Absoluut. De gradient wordt toegepast op een pad‑laag, zodat bestaande afbeeldingen onaangeroerd blijven.

**Q: Is het mogelijk om in plaats daarvan een verticale gradient te maken?**  
A: Ja. Verander de start‑ en eindpunten van de `LinearGradientBrush` zodat ze verschillende Y‑coördinaten hebben terwijl X constant blijft.

**Q: Ondersteunt Aspose.Page .NET Core?**  
A: De bibliotheek is volledig compatibel met .NET Core, .NET 5 en latere versies.

**Q: Hoe kan ik dezelfde gradient hergebruiken op meerdere pagina's?**  
A: Maak de `XpsLinearGradientBrush` één keer, sla deze op in een variabele en wijs hem toe aan paden op elke pagina.

## Conclusie

Het verbeteren van uw XPS‑documenten met gradients verhoogt niet alleen de visuele aantrekkingskracht, maar levert ook een meer boeiende gebruikerservaring op. Met Aspose.Page voor .NET kunt u **XPS‑gradient** vullingen snel en betrouwbaar **creëren**, waardoor uw rapporten, brochures of e‑books een professionele afwerking krijgen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose
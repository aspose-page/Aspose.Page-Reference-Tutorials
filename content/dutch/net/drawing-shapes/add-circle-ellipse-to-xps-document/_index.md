---
title: Voeg Circle Ellipse toe aan XPS-document met Aspose.Page voor .NET
linktitle: Cirkel-ellips toevoegen aan XPS-document
second_title: Aspose.Page .NET-API
description: Verbeter XPS-documenten met levendige radiale verlopen met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor verbluffende visuele effecten.
type: docs
weight: 11
url: /nl/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Invoering

Het creëren van visueel aantrekkelijke XPS-documenten is een veel voorkomende vereiste in verschillende toepassingen. Aspose.Page voor .NET biedt een krachtige reeks functies om XPS-documenten efficiënt te manipuleren. In deze zelfstudie concentreren we ons op het toevoegen van een cirkel-ellips aan een XPS-document met behulp van Aspose.Page voor .NET. Volg de onderstaande stappen om uw XPS-documenten te verfraaien met levendige radiale verlopen.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/page/net/).
- Een ontwikkelomgeving, bij voorkeur Visual Studio of een andere .NET-ontwikkeltool.
- Basiskennis van programmeren in C#.

## Naamruimten importeren

Neem om te beginnen de benodigde naamruimten op in uw C#-code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen:

## Stap 1: Stel het document in

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```

Hier initialiseren we een nieuw XPS-document met Aspose.Page voor .NET.

## Stap 2: Definieer de radiale verloopellips

```csharp
// Radiale gradiënt gestreken ellips linksonder
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Deze stap omvat het definiëren van een radiale gradiëntellips met verschillende kleurstops.

## Stap 3: Stel het Radiaal Verlooppenseel in

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Hier stellen we de lijn van de ellips in op een radiale gradiëntborstel, waardoor deze van de nodige parameters wordt voorzien.

## Stap 4: Pas de lijndikte aan

```csharp
path.StrokeThickness = 12f;
```

Deze stap omvat het aanpassen van de dikte van de streek voor een betere visualisatie.

## Stap 5: Sla het resulterende XPS-document op

```csharp
// Sla het resulterende XPS-document op
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Verlengen: 1
```

Sla ten slotte het gewijzigde XPS-document op de gewenste locatie op.

## Conclusie

Gefeliciteerd! U hebt met succes een cirkel-ellips met radiale verlopen aan uw XPS-document toegevoegd met Aspose.Page voor .NET. Experimenteer met verschillende parameters en kleuren om de gewenste visuele effecten in uw documenten te bereiken.

## Veelgestelde vragen

### V1: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?

A1: Aspose.Page voor .NET houdt zich specifiek bezig met manipulatie van XPS-documenten. Voor andere indelingen kunt u overwegen gerelateerde Aspose-bibliotheken te gebruiken.

### Vraag 2: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?

 A2: Ja, u kunt een tijdelijke testlicentie verkrijgen door te bezoeken[deze link](https://purchase.aspose.com/temporary-license/).

### Vraag 3: Waar kan ik aanvullende hulp en discussies vinden?

 A3: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapsondersteuning en discussies.

### Vraag 4: Zijn er voorbeelddocumenten beschikbaar ter referentie?

 A4: Ontdek de[documentatie](https://reference.aspose.com/page/net/) voor uitgebreide voorbeelden en richtlijnen.

### V5: Kan ik Aspose.Page voor .NET kopen?

 A5: Ja, u kunt de bibliotheek kopen[hier](https://purchase.aspose.com/buy).
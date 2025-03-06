---
title: Voeg een verticaal verloop toe aan XPS met Aspose.Page voor .NET
linktitle: Voeg verticaal verloop toe aan XPS
second_title: Aspose.Page .NET-API
description: Leer hoe u XPS-documenten kunt verbeteren met verticale verlopen met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 15
url: /nl/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een verticaal verloop toe aan XPS met Aspose.Page voor .NET

## Invoering

Welkom bij deze stapsgewijze zelfstudie over hoe u een verticaal verloop aan een XPS-document kunt toevoegen met Aspose.Page voor .NET. Aspose.Page is een krachtige API waarmee u kunt werken met XPS-bestanden (XML Paper Specification) in uw .NET-toepassingen. In deze zelfstudie begeleiden we u bij het maken van een nieuw XPS-document, het toevoegen van een verticaal verloop aan een pad en het opslaan van het resultaat.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/page/net/).

- Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op met uw favoriete IDE, zoals Visual Studio.

Laten we nu aan de slag gaan met het toevoegen van een verticaal verloop aan een XPS-document met behulp van Aspose.Page voor .NET.

## Naamruimten importeren

Neem in uw .NET-toepassing de benodigde naamruimten op om toegang te krijgen tot Aspose.Page-klassen en -methoden.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Stap 1: Stel uw documentenmap in

Voordat u begint, stelt u het pad in naar uw documentmap waar u het resulterende XPS-document wilt opslaan.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// Verleng:3
```

## Stap 2: Maak een nieuw XPS-document

Initialiseer een nieuw XPS-document met de volgende code:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// Verleng:4
```

## Stap 3: Definieer verloopstops

Maak een lijst met verloopstops, waarbij u voor elke stop de kleur en positie opgeeft. In dit voorbeeld definiëren we een verticaal verloop met vijf stops.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Verleng: 5
```

## Stap 4: Maak een pad met verloop

Definieer een pad door de geometrie ervan op te geven en er een lineair verlooppenseel op toe te passen.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Verleng:6
```

## Stap 5: Sla het resulterende XPS-document op

Sla het gewijzigde XPS-document op in de door u opgegeven map.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Verleng:7
```

Gefeliciteerd! U hebt met succes een verticaal verloop aan een XPS-document toegevoegd met Aspose.Page voor .NET.

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u Aspose.Page voor .NET kunt gebruiken om XPS-documenten met verticale verlopen te verbeteren. Aspose.Page vereenvoudigt complexe taken en biedt ontwikkelaars een naadloze manier om XPS-bestanden in hun .NET-applicaties te manipuleren.

## Veelgestelde vragen

### V1: Is Aspose.Page compatibel met Visual Studio 2019?

A1: Ja, Aspose.Page is compatibel met Visual Studio 2019. Zorg ervoor dat u de juiste versie van de bibliotheek hebt geïnstalleerd.

### V2: Kan ik Aspose.Page gebruiken voor commerciële projecten?

 A2: Ja, Aspose.Page kan worden gebruikt voor commerciële projecten. Bezoek[hier](https://purchase.aspose.com/buy) om licentiemogelijkheden te verkennen.

### Vraag 3: Is er een gratis proefversie beschikbaar?

 A3: Ja, u kunt Aspose.Page gratis uitproberen[hier](https://releases.aspose.com/).

### V4: Waar kan ik Aspose.Page-documentatie vinden?

 A4: De documentatie is beschikbaar[hier](https://reference.aspose.com/page/net/).

### Vraag 5: Hoe kan ik ondersteuning krijgen of vragen stellen?

 A5: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapssteun.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

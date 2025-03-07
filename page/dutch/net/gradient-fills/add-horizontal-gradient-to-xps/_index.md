---
title: Voeg horizontaal verloop toe aan XPS met Aspose.Page voor .NET
linktitle: Voeg horizontaal verloop toe aan XPS
second_title: Aspose.Page .NET-API
description: Leer hoe u verbluffende horizontale verlopen aan uw XPS-documenten kunt toevoegen met Aspose.Page voor .NET. Verhoog moeiteloos de visuele aantrekkingskracht.
weight: 13
url: /nl/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg horizontaal verloop toe aan XPS met Aspose.Page voor .NET

## Invoering

In deze zelfstudie onderzoeken we hoe u XPS-documenten kunt verbeteren door een horizontaal verloop toe te voegen met Aspose.Page voor .NET. Aspose.Page voor .NET is een krachtige bibliotheek die een naadloze verwerking van XPS-documenten (XML Paper Specification) in .NET-toepassingen biedt. Het toevoegen van kleurverlopen kan uw documenten een visuele aantrekkingskracht geven, en deze handleiding begeleidt u stap voor stap door het proces.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1.  Aspose.Page voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden van de[Aspose.Page voor .NET-documentatie](https://reference.aspose.com/page/net/).

2. Ontwikkelomgeving: Zet een geschikte ontwikkelomgeving op, inclusief een code-editor zoals Visual Studio.

## Naamruimten importeren

Begin met het importeren van de benodigde naamruimten in uw project. Deze naamruimten zijn essentieel voor het werken met Aspose.Page voor .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen.

## Stap 1: Stel het documentmappad in

```csharp
// ExStart:3
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Verleng:3
```

## Stap 2: Maak een nieuw XPS-document

```csharp
// ExStart:4
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
// Verleng:4
```

## Stap 3: Initialiseer verloopstops

```csharp
// ExStart:5
// Initialiseer de lijst met XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Verleng: 5
```

## Stap 4: Maak een nieuw pad

```csharp
// ExStart:6
//Creëer een nieuw pad door geometrie in afkorting te definiëren
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Verleng:6
```

## Stap 5: Sla het resulterende XPS-document op

```csharp
// ExStart:7
// Sla het resulterende XPS-document op
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Verleng:7
```

Nu hebt u met succes een horizontaal verloop aan uw XPS-document toegevoegd met Aspose.Page voor .NET.

## Conclusie

Het verbeteren van uw XPS-documenten met kleurverlopen verbetert niet alleen hun visuele aantrekkingskracht, maar zorgt ook voor een boeiendere gebruikerservaring. Aspose.Page voor .NET vereenvoudigt dit proces, waardoor u moeiteloos professionele resultaten kunt behalen.

## Veelgestelde vragen

### V1: Waar kan ik de Aspose.Page voor .NET-documentatie vinden?

 A1: U kunt de documentatie vinden[hier](https://reference.aspose.com/page/net/).

### V2: Hoe download ik Aspose.Page voor .NET?

 A2: U kunt de bibliotheek downloaden van de[Aspose.Page voor .NET-downloadpagina](https://releases.aspose.com/page/net/).

### V3: Waar kan ik Aspose.Page voor .NET kopen?

 A3: U kunt Aspose.Page voor .NET kopen bij de[aankooppagina](https://purchase.aspose.com/buy).

### Vraag 4: Is er een gratis proefversie beschikbaar?

 A4: Ja, u kunt een gratis proefperiode krijgen van[hier](https://releases.aspose.com/).

### V5: Hoe krijg ik een tijdelijke licentie voor Aspose.Page voor .NET?

 A5: U kunt een tijdelijke licentie verkrijgen via[deze link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

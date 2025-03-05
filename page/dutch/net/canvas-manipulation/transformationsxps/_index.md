---
title: Transformaties XPS met Aspose.Page voor .NET
linktitle: Transformaties XPS
second_title: Aspose.Page .NET-API
description: Transformeer XPS-documenten moeiteloos met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor naadloze transformaties.
type: docs
weight: 13
url: /nl/net/canvas-manipulation/transformationsxps/
---
## Invoering

Welkom in de wereld van Aspose.Page voor .NET, een krachtige bibliotheek waarmee u moeiteloos verschillende transformaties op XPS-documenten kunt uitvoeren. In deze zelfstudie duiken we in het proces van het transformeren van XPS-documenten met Aspose.Page voor .NET. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze gids begeleidt u bij elke stap, zodat u de concepten gemakkelijk begrijpt.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

-  Aspose.Page voor .NET Library: Download en installeer de bibliotheek van[Aspose.Page voor .NET-documentatie](https://reference.aspose.com/page/net/).

- Ontwikkelomgeving: Zet een compatibele ontwikkelomgeving op, zoals Visual Studio of een andere .NET-ontwikkeltool.

- Uw documentenmap: Vervang de tijdelijke aanduiding in de code door het daadwerkelijke pad naar uw documentmap.

Laten we nu naar de tutorial gaan!

## Naamruimten importeren

Zorg er eerst voor dat u de benodigde naamruimten importeert om de Aspose.Page voor .NET-functionaliteiten beschikbaar te maken in uw code. Voeg de volgende naamruimten toe aan het begin van uw script:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stap 1: Maak een nieuw XPS-document

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";

// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```

## Stap 2: Maak een hoofdcanvas

```csharp
// Maak een hoofdcanvas, gemeenschappelijk voor alle pagina-elementen
XpsCanvas canvas1 = doc.AddCanvas();

// Maak linker- en bovenverschuivingen in het hoofdcanvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Stap 3: Maak een rechthoekige padgeometrie

```csharp
// Creëer een rechthoekige padgeometrie
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Stap 4: Voeg een vulling toe voor rechthoeken

```csharp
// Maak een vulling voor rechthoeken
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Stap 5: Voeg een nieuw canvas toe zonder transformaties

```csharp
// Voeg een nieuw canvas toe zonder enige transformatie aan het hoofdcanvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Maak een rechthoek in dit canvas en vul het
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Stap 6: Voeg een nieuw canvas toe met vertaaltransformatie

```csharp
// Voeg een nieuw canvas toe met vertaaltransformatie naar het hoofdcanvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Vertaal dit canvas om een nieuwe rechthoek onder de vorige rechthoek te plaatsen
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Vertaal dit canvas naar de rechterkant van de pagina
canvas3.RenderTransform.Translate(500, 0);

// Maak een rechthoek in dit canvas en vul het
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Stap 7: Voeg een nieuw canvas toe met transformatie op dubbele schaal

```csharp
//Voeg een nieuw canvas met dubbele schaaltransformatie toe aan het hoofdcanvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Vertaal dit canvas om een nieuwe rechthoek onder de vorige rechthoek te plaatsen
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Schaal dit canvas
canvas4.RenderTransform.Scale(2, 2);

// Maak een rechthoek in dit canvas en vul het
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Stap 8: Voeg een nieuw canvas toe met rotatie rond een punttransformatie

```csharp
// Voeg een nieuw canvas toe met rotatie rond een punttransformatie aan het hoofdcanvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Vertaal dit canvas om een nieuwe rechthoek onder de vorige rechthoek te plaatsen
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Draai dit canvas rond een punt op 45 graden
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Maak een rechthoek in dit canvas en vul het
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Stap 9: Bewaar het resulterende XPS-document

```csharp
// Sla het resulterende XPS-document op
doc.Save(dataDir + "output1.xps");
// Verlengen: 1
```

## Conclusie

Gefeliciteerd! U hebt met succes een XPS-document getransformeerd met Aspose.Page voor .NET. Deze gids omvatte essentiële stappen, van het opstellen van randvoorwaarden tot het uitvoeren van verschillende transformaties. Experimenteer met deze technieken en ontgrendel het volledige potentieel van Aspose.Page voor .NET in uw projecten.

## Veelgestelde vragen

### Vraag 1: Is Aspose.Page voor .NET compatibel met alle .NET-ontwikkelomgevingen?

A1: Ja, Aspose.Page voor .NET is ontworpen om naadloos samen te werken met verschillende .NET-ontwikkelomgevingen, waaronder Visual Studio.

### V2: Waar kan ik aanvullende voorbeelden en documentatie vinden voor Aspose.Page voor .NET?

 A2: Bezoek de[Aspose.Page voor .NET-documentatie](https://reference.aspose.com/page/net/) voor uitgebreide documentatie en voorbeelden.

### V3: Kan ik Aspose.Page voor .NET uitproberen voordat ik een aankoop doe?

 A3: Ja, u kunt een gratis proefversie verkennen door naar te gaan[Gratis proefversie van Aspose.Page](https://releases.aspose.com/).

### V4: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor .NET?

 A4: Vraag een tijdelijke licentie aan door te bezoeken[Tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

### V5: Waar kan ik Aspose.Page voor .NET kopen?

 A5: Koop Aspose.Page voor .NET op[Aspose.Pagina Kopen](https://purchase.aspose.com/buy).
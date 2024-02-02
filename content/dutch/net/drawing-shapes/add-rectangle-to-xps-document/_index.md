---
title: Voeg een rechthoek toe aan een XPS-document met Aspose.Page voor .NET
linktitle: Rechthoek toevoegen aan XPS-document
second_title: Aspose.Page .NET-API
description: Verbeter het maken van documenten met Aspose.Page voor .NET. Leer hoe u rechthoeken aan XPS-documenten toevoegt in deze stapsgewijze zelfstudie.
type: docs
weight: 13
url: /nl/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Invoering

Aspose.Page voor .NET is een krachtige bibliotheek die een verscheidenheid aan functies biedt voor het werken met XPS-documenten (XML Paper Specification) in .NET-toepassingen. In deze zelfstudie concentreren we ons op het toevoegen van een rechthoek aan een XPS-document met Aspose.Page voor .NET. Volg deze stapsgewijze handleiding om uw proces voor het maken van documenten te verbeteren.

## Vereisten

Voordat u met deze zelfstudie begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Page voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/page/net/).

2. Documentmap: Stel een map in waarin u uw XPS-documenten wilt opslaan.

## Naamruimten importeren

Neem in uw .NET-toepassing de benodigde naamruimten op om de Aspose.Page-functionaliteiten te gebruiken.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stap 1: Stel de documentmap in

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

## Stap 3: voeg een rechthoek toe

```csharp
// ExStart:5
// CMYK (blauw) effen gekleurde rechthoek linksonder
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Verleng: 5
```

## Stap 4: Sla het document op

```csharp
// ExStart:6
// Sla het resulterende XPS-document op
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Verleng:6
```

Gefeliciteerd! U hebt met succes een rechthoek aan een XPS-document toegevoegd met Aspose.Page voor .NET.

## Conclusie

Aspose.Page voor .NET vereenvoudigt documentmanipulatietaken, waardoor ontwikkelaars moeiteloos XPS-documenten kunnen maken en wijzigen. Deze stapsgewijze handleiding laat zien hoe u een rechthoek aan uw XPS-document kunt toevoegen, zodat u een solide basis krijgt voor verdere verkenning.

## Veelgestelde vragen

### Vraag 1: Is Aspose.Page compatibel met alle .NET-applicaties?

A1: Ja, Aspose.Page is ontworpen om naadloos samen te werken met alle .NET-applicaties.

### V2: Waar kan ik de documentatie voor Aspose.Page voor .NET vinden?

 A2: De documentatie is beschikbaar[hier](https://reference.aspose.com/page/net/).

### V3: Kan ik Aspose.Page voor .NET gratis uitproberen voordat ik een aankoop doe?

 A3: Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### V4: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor .NET?

 A4: Bezoek[deze link](https://purchase.aspose.com/temporary-license/) om een tijdelijke vergunning te verkrijgen.

### V5: Waar kan ik community-ondersteuning zoeken of vragen stellen met betrekking tot Aspose.Page voor .NET?

 A5: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapssteun.
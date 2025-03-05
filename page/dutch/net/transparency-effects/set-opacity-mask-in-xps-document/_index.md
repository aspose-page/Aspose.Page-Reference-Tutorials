---
title: Stel het dekkingsmasker in het XPS-document in met Aspose.Page voor .NET
linktitle: Stel het dekkingsmasker in in het XPS-document
second_title: Aspose.Page .NET-API
description: Leer dekkingsmaskers instellen in XPS-documenten met Aspose.Page voor .NET. Verbeter de esthetiek van documenten moeiteloos.
type: docs
weight: 12
url: /nl/net/transparency-effects/set-opacity-mask-in-xps-document/
---
## Invoering

Dekkingsmaskers zijn essentieel als u visueel aantrekkelijke documenten met verschillende transparantieniveaus wilt maken. Aspose.Page voor .NET vereenvoudigt dit proces en biedt ontwikkelaars een uitgebreide set tools om XPS-documenten te verbeteren. In deze zelfstudie bekijken we stapsgewijze hoe u een dekkingsmasker instelt.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET: Zorg ervoor dat de bibliotheek is geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van de[website](https://releases.aspose.com/page/net/).

- Documentmap: stel een map in om uw XPS-documenten op te slaan.

## Naamruimten importeren

Begin in uw .NET-project met het importeren van de benodigde naamruimten:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Stap 1: Maak een nieuw XPS-document

```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```

Begin met het maken van een nieuw XPS-document met Aspose.Page voor .NET.

## Stap 2: Canvas toevoegen aan XpsDocument-instantie

```csharp
// Canvas toevoegen aan XpsDocument-instantie
XpsCanvas canvas = doc.AddCanvas();
```

Voeg nu een canvas toe aan het XPS-document. Het canvas zal dienen als container voor verschillende grafische elementen.

## Stap 3: Rechthoek toevoegen met dekkingsmasker

```csharp
// Rechthoek met dekking gemaskeerd door ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 Voeg een rechthoek toe aan het canvas en stel de dekking in met behulp van de`OpacityMask`eigendom. In dit voorbeeld gebruiken we een afbeelding als dekkingsmasker.

## Stap 4: Bewaar het resulterende XPS-document

```csharp
// Sla het resulterende XPS-document op
doc.Save(dataDir + "OpacityMask_out.xps");
```

Sla ten slotte het gewijzigde XPS-document op met het dekkingsmasker toegepast.

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u dekkingsmaskers kunt instellen in XPS-documenten met behulp van Aspose.Page voor .NET. Deze functie opent een wereld aan creatieve mogelijkheden voor het ontwerpen van geavanceerde en visueel aantrekkelijke documenten.

## Veelgestelde vragen

### Vraag 1: Kan ik dekkingsmaskers toepassen op andere vormen dan rechthoeken?

A1: Ja, met Aspose.Page voor .NET kunt u dekkingsmaskers toepassen op verschillende vormen, waaronder cirkels, polygonen en aangepaste paden.

### Vraag 2: Is het dekkingsmasker beperkt tot afbeeldingen?

A2: Nee, hoewel in deze zelfstudie een afbeelding als dekkingsmasker werd gebruikt, kunt u effen kleuren, verlopen of zelfs patronen gebruiken.

### Vraag 3: Zijn er geavanceerde opties voor het verfijnen van de dekkingsniveaus?

A3: Absoluut, Aspose.Page voor .NET biedt gedetailleerde controle over de dekkingsinstellingen, waardoor u nauwkeurige transparantie-effecten kunt bereiken.

### V4: Kan ik meerdere dekkingsmaskers op één element toepassen?

A4: Ja, u kunt meerdere dekkingsmaskers over elkaar heen leggen om ingewikkelde transparantie-effecten te creëren.

### V5: Is Aspose.Page compatibel met andere documentformaten?

A5: Aspose.Page richt zich primair op XPS-documenten, maar Aspose biedt een reeks producten voor het verwerken van verschillende formaten.
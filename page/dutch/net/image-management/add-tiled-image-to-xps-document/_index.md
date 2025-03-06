---
title: Voeg een betegelde afbeelding toe aan een XPS-document met Aspose.Page voor .NET
linktitle: Voeg naast elkaar geplaatste afbeelding toe aan XPS-document
second_title: Aspose.Page .NET-API
description: Ontdek hoe u moeiteloos tegelafbeeldingen aan XPS-documenten kunt toevoegen met Aspose.Page voor .NET. Verbeter de visuele aantrekkingskracht en creëer verbluffende documenten.
weight: 12
url: /nl/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een betegelde afbeelding toe aan een XPS-document met Aspose.Page voor .NET

## Invoering

Wilt u uw XPS-documenten verbeteren door visueel aantrekkelijke naast elkaar geplaatste afbeeldingen toe te voegen? Aspose.Page voor .NET stelt ontwikkelaars in staat dit naadloos te bereiken. In deze stapsgewijze handleiding leiden we u door het proces van het toevoegen van een tegelafbeelding aan een XPS-document met behulp van Aspose.Page voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET: Zorg ervoor dat de Aspose.Page-bibliotheek is geïnstalleerd. U kunt gedetailleerde documentatie vinden en de bibliotheek downloaden[hier](https://reference.aspose.com/page/net/).
- Ontwikkelomgeving: Stel de .NET-ontwikkelomgeving van uw voorkeur in, zoals Visual Studio.

## Naamruimten importeren

Importeer om te beginnen de benodigde naamruimten in uw project. Dit zorgt ervoor dat u toegang heeft tot de klassen en methoden die nodig zijn om met Aspose.Page te werken. Voeg de volgende naamruimten toe aan het begin van uw code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen.

## Stap 1: Definieer de documentmap

```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
```

Zorg ervoor dat u "Uw documentenmap" vervangt door het daadwerkelijke pad waar u uw XPS-document wilt opslaan.

## Stap 2: Maak een nieuw XPS-document

```csharp
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```

 Instantieer een nieuw XPS-document met behulp van de`XpsDocument` klas.

## Stap 3: Voeg een betegelde afbeelding toe

```csharp
// Tegel afbeelding
// Met ImageBrush gevulde rechthoek rechts bovenaan
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Met deze stap wordt een naast elkaar geplaatste afbeelding toegevoegd aan het XPS-document. Pas de coördinaten en het afbeeldingsbestandspad aan volgens uw vereisten.

## Stap 4: Sla het resulterende XPS-document op

```csharp
// Sla het resulterende XPS-document op
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Sla het gewijzigde XPS-document op in de opgegeven map.

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u een tegelafbeelding aan een XPS-document kunt toevoegen met behulp van Aspose.Page voor .NET. Met deze eenvoudige maar krachtige functie kunt u de visuele aantrekkingskracht van uw documenten moeiteloos verbeteren.

## Veelgestelde vragen

### Vraag 1: Is Aspose.Page compatibel met alle .NET-ontwikkelomgevingen?

A1: Ja, Aspose.Page is ontworpen om naadloos samen te werken met verschillende .NET-ontwikkelomgevingen, waaronder Visual Studio.

### Vraag 2: Kan ik de dekking van de naast elkaar geplaatste afbeelding aanpassen?

A2: Zeker, zoals aangetoond in het voorbeeld, kunt u de dekking van de gevulde rechthoek instellen met behulp van de`Opacity` eigendom.

### V3: Zijn er andere tegelmodi beschikbaar in Aspose.Page voor .NET?

 A3: Ja, Aspose.Page biedt verschillende tegelmodi. In deze tutorial hebben we gebruikt`XpsTileMode.Tile`, maar u kunt andere opties verkennen in de documentatie.

### V4: Hoe ga ik om met tijdelijke licenties voor Aspose.Page?

 A4: Raadpleeg de[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) pagina op de Aspose-website voor begeleiding bij het verkrijgen en implementeren van tijdelijke licenties.

### V5: Waar kan ik hulp zoeken of contact maken met de Aspose.Page-gemeenschap?

 A5: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) om met de gemeenschap in contact te komen, vragen te stellen en oplossingen te vinden.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

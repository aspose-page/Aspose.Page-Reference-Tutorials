---
date: 2026-01-05
description: Leer hoe u XPS‑documenten moeiteloos kunt transformeren met Aspose.Page
  voor .NET. Volg onze stapsgewijze handleiding voor naadloze transformaties.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Hoe XPS te transformeren met Aspose.Page voor .NET
url: /nl/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe XPS transformeren met Aspose.Page voor .NET

## Introductie

Welkom in de wereld van Aspose.Page voor .NET, een krachtige bibliotheek die u in staat stelt om moeiteloos verschillende transformaties op XPS‑documenten uit te voeren. **In deze tutorial ontdekt u hoe u XPS‑documenten kunt transformeren met Aspose.Page voor .NET**, of u nu een ervaren ontwikkelaar bent of net begint. We lopen elke stap door, leggen de reden achter elke transformatie uit en geven praktische tips die u in echte projecten kunt toepassen.

## Snelle antwoorden
- **Wat kunt u bereiken?** Maak, verplaats, schaal en roteer XPS‑canvas‑elementen programmatisch.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (nieuwste versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Ondersteunde platformen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor de basis‑transformaties die hier worden getoond.

## Wat betekent “how to transform xps”?
De uitdrukking *how to transform xps* verwijst naar het programmatisch wijzigen van de lay‑out, grootte en oriëntatie van elementen binnen een XPS‑document (XML Paper Specification). Met Aspose.Page kunt u matrix‑gebaseerde transformaties toepassen op canvassen, waardoor u fijne controle krijgt over positionering, schalen en roteren zonder handmatig de XPS‑XML te bewerken.

## Waarom Aspose.Page gebruiken voor XPS‑transformaties?
- **Volledige .NET‑integratie** – werkt naadloos met Visual Studio, Rider en andere IDE’s.  
- **Geen externe afhankelijkheden** – de API behandelt alle low‑level XPS‑details voor u.  
- **Rijke transformatiesupport** – verplaatsen, schalen, roteren en meerdere transformaties combineren in één oproep.  
- **Prestaties‑geoptimaliseerd** – geschikt voor het genereren van rapporten, facturen of andere afdrukbare graphics on‑the‑fly.

## Voorvereisten

Voordat we beginnen, zorg dat u het volgende heeft:

- **Aspose.Page voor .NET‑bibliotheek** – download en installeer deze via de officiële documentatie: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Ontwikkelomgeving** – Visual Studio, Visual Studio Code of een andere .NET‑compatibele IDE.  
- **Documentmap** – een map op uw computer waar u XPS‑bestanden leest en schrijft. Vervang de tijdelijke aanduiding in de code door het daadwerkelijke pad.

Nu alles klaar is, duiken we in de code.

## Namespaces importeren

Importeer eerst de namespaces die de Aspose.Page‑klassen blootleggen die u nodig heeft:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hoe XPS transformeren – Stapsgewijze gids

### Stap 1: Een nieuw XPS‑document maken

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Uitleg*: We definiëren eerst de map die onze bron‑ en uitvoerbestanden bevat, en maken vervolgens een lege `XpsDocument`. Dit object wordt het canvas voor alle volgende transformaties.

### Stap 2: Een hoofd‑canvas maken

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Waarom dit belangrijk is*: Het hoofd‑canvas fungeert als container voor alle andere canvassen. Door een kleine offset toe te passen zorgen we ervoor dat de inhoud niet wordt afgesneden aan de paginarand.

### Stap 3: Een rechthoek‑pad‑geometrie maken

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: De pad‑string volgt de standaard XPS‑pad‑syntaxis (`M` voor move, `L` voor line, `Z` om te sluiten). Pas de coördinaten aan om de grootte van de rechthoek te wijzigen.

### Stap 4: Een vulling voor rechthoeken toevoegen

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro‑tip*: Gebruik `CreateColor` met RGB‑waarden om uw merkkleuren te matchen.

### Stap 5: Een nieuw canvas zonder transformaties toevoegen

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Hier plaatsen we simpelweg een rechthoek op de pagina zonder extra transformatie — handig als basis‑element.

### Stap 6: Een nieuw canvas met translate‑transformatie toevoegen

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Wat gebeurt er?* De eerste matrix verplaatst de rechthoek omlaag met 200 eenheden. De daaropvolgende `Translate`‑aanroep verschuift hem 500 eenheden naar rechts, waarmee wordt aangetoond hoe meerdere vertalingen kunnen worden gekoppeld.

### Stap 7: Een nieuw canvas met dubbele schaal‑transformatie toevoegen

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Waarom schalen?* Schalen met 2 verdubbelt de breedte en hoogte van de rechthoek, zodat u grotere graphics kunt maken zonder de geometrie opnieuw te definiëren.

### Stap 8: Een nieuw canvas met rotatie‑rond‑een‑punt‑transformatie toevoegen

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Belangrijk inzicht*: `RotateAround` draait het canvas rond een aangepast punt (hier (100, 50)), waardoor u fijne controle krijgt over het rotatie‑anker.

### Stap 9: Het resulterende XPS‑document opslaan

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Nadat alle transformaties zijn toegepast, wordt het document opgeslagen als `output1.xps`. Open het bestand in een XPS‑viewer om de gestapelde rechthoeken met hun respectieve vertalingen, schalingen en rotaties te zien.

## Veelvoorkomende problemen & foutopsporing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Leeg uitvoerbestand | `dataDir` wijst naar een niet‑bestaande map | Zorg dat de map bestaat of gebruik een absoluut pad |
| Rechthoeken staan niet op de verwachte positie | Onjuiste matrix‑waarden | Controleer de volgorde van `Translate`, `Scale` en `RotateAround`‑aanroepen |
| Kleuren komen verkeerd | RGB‑waarden buiten bereik 0‑255 | Gebruik geldige byte‑waarden voor elk kanaal |

## Veelgestelde vragen

**V: Is Aspose.Page voor .NET compatibel met alle .NET‑ontwikkelomgevingen?**  
A: Ja, het werkt naadloos met Visual Studio, Visual Studio Code, Rider en elke IDE die .NET ondersteunt.

**V: Waar vind ik extra voorbeelden en gedetailleerde API‑documentatie?**  
A: Bezoek de officiële documentatie op [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**V: Kan ik Aspose.Page eerst uitproberen voordat ik een licentie koop?**  
A: Absoluut. Een gratis proefversie is hier beschikbaar: [Aspose.Page Free Trial](https://releases.aspose.com/).

**V: Hoe verkrijg ik een tijdelijke licentie voor testen?**  
A: Vraag er een aan via de tijdelijke‑licentie‑pagina: [Temporary License](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik een volledige licentie aanschaffen?**  
A: Direct via de Aspose‑winkel: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Laatst bijgewerkt:** 2026-01-05  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
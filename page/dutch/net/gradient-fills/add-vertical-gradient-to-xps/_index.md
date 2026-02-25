---
date: 2026-02-25
description: Leer hoe u een XPS‑document maakt en een lineaire gradient toepast met
  Aspose.Page voor .NET. Volg onze stapsgewijze handleiding om het XPS‑bestand op
  te slaan.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Maak XPS-document met verticale gradiënt met Aspose.Page
url: /nl/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg verticale gradient toe aan XPS met Aspose.Page voor .NET

## Introductie

In deze tutorial **maak je een XPS-document** dat een vloeiende verticale gradient bevat. Het toevoegen van gradients is een veelgebruikte manier om XPS-bestanden er professioneler uit te laten zien—perfect voor rapporten, brochures of andere afdrukbare afbeeldingen. We lopen elke stap door, van het opzetten van het project tot het opslaan van het uiteindelijke XPS‑bestand, zodat je snel een lineaire gradient op elk pad kunt toepassen.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Een verticale lineaire gradient toevoegen aan een pad in een XPS-document.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.  
- **Kan ik het resultaat opslaan als een XPS‑bestand?** Ja, de `Save`‑methode schrijft het bestand naar schijf.

## Wat is een verticale gradient in XPS?

Een verticale gradient is een kleurovergang die loopt van de bovenkant van een vorm naar de onderkant. In XPS wordt dit bereikt met een **linear gradient brush** die start‑ en eindpunten definieert, plus een verzameling gradient stops die de kleur op specifieke posities regelen.

## Waarom Aspose.Page gebruiken om een XPS‑document met gradients te maken?

- **Volledige .NET‑integratie** – werkt met .NET Framework, .NET Core en .NET 5/6+.  
- **Geen externe afhankelijkheden** – alle rendering wordt afgehandeld door de bibliotheek.  
- **Hoge nauwkeurigheid** – gradients worden precies zoals gedefinieerd gerenderd, overeenkomstig de XPS‑specificatie.  
- **Gemakkelijk te onderhouden** – duidelijk objectmodel voor paden, brushes en kleuren.

## Voorvereisten

- Aspose.Page for .NET Library: Zorg ervoor dat je de Aspose.Page for .NET‑bibliotheek geïnstalleerd hebt in je ontwikkelomgeving. Je kunt het downloaden [hier](https://releases.aspose.com/page/net/).
- Development Environment: Richt een .NET‑ontwikkelomgeving in met je favoriete IDE, zoals Visual Studio.

Nu we alles klaar hebben, duiken we in de code.

## Namespaces importeren

Voeg in je .NET‑applicatie de benodigde namespaces toe om toegang te krijgen tot de Aspose.Page‑klassen en -methoden.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Stap 1: Stel je documentmap in

Definieer de map waarin het gegenereerde XPS‑bestand wordt opgeslagen.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Stap 2: Maak een nieuw XPS‑document

Instantieer een nieuw XPS‑document dat later wordt gevuld met een pad met een gradient.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Stap 3: Definieer gradient stops

Gradient stops bepalen de kleuren en hun posities langs de gradientlijn. Hier maken we vijf stops om een vloeiende verticale overgang te produceren.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Stap 4: Maak een pad met gradient

We tekenen een rechthoekig pad en passen een **linear gradient brush** toe die verticaal loopt van punt (10, 110) naar punt (10, 200). De brush ontvangt de eerder gedefinieerde gradient stops.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Stap 5: Sla het resulterende XPS‑document op

Schrijf tenslotte het XPS‑document naar schijf. Deze **save XPS file** stap produceert `AddVerticalGradient_outXPS.xps` in de map die je hebt opgegeven.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** Controleer de output door het XPS‑bestand te openen in Windows XPS Viewer of een andere viewer om te verzekeren dat de gradient zoals verwacht verschijnt.

## Veelvoorkomende problemen & probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Gradient verschijnt als effen kleur | Gradient stops niet toegevoegd aan de brush | Zorg ervoor dat `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` wordt uitgevoerd. |
| Bestand niet gevonden bij opslaan | `dataDir` verwijst naar een niet‑bestaande map | Maak de map eerst aan of gebruik een absoluut pad. |
| Kleuren zien er anders uit | Kleurwaarden gebruiken ARGB-volgorde; controleer de kanaalvolgorde | Gebruik `CreateColor(alpha, red, green, blue)` correct. |

## Veelgestelde vragen

**Q: Is Aspose.Page compatibel met Visual Studio 2019?**  
A: Ja, Aspose.Page is compatibel met Visual Studio 2019. Zorg ervoor dat je de juiste versie van de bibliotheek geïnstalleerd hebt.

**Q: Kan ik Aspose.Page gebruiken voor commerciële projecten?**  
A: Ja, Aspose.Page kan worden gebruikt voor commerciële projecten. Bezoek [hier](https://purchase.aspose.com/buy) om licentieopties te bekijken.

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, je kunt een gratis proefversie van Aspose.Page krijgen [hier](https://releases.aspose.com/).

**Q: Waar kan ik de Aspose.Page-documentatie vinden?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/page/net/).

**Q: Hoe kan ik ondersteuning krijgen of vragen stellen?**  
A: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

## Conclusie

Je weet nu hoe je een **XPS-document kunt maken**, een **lineaire gradient kunt toepassen**, en een **XPS‑bestand kunt opslaan** met Aspose.Page voor .NET. Deze aanpak geeft je volledige controle over de visuele styling in XPS‑output, waardoor je afdrukbare documenten opvallen.

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
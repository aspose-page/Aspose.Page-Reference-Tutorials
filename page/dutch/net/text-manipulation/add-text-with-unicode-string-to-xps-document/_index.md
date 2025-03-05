---
title: Voeg tekst met Unicode-tekenreeks toe aan XPS-document met Aspose.Page
linktitle: Voeg tekst met Unicode-tekenreeks toe aan XPS-document
second_title: Aspose.Page .NET-API
description: Ontdek de kracht van Aspose.Page voor .NET met onze stapsgewijze handleiding voor het toevoegen van Unicode-tekst aan XPS-documenten.
type: docs
weight: 12
url: /nl/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Invoering

In het voortdurend evoluerende landschap van .NET-ontwikkeling onderscheidt Aspose.Page zich als een krachtig hulpmiddel voor het verwerken van XPS-documenten. Onder de vele functies is de mogelijkheid om tekst met Unicode-tekenreeksen aan een XPS-document toe te voegen een waardevolle functionaliteit. Deze stapsgewijze handleiding begeleidt u door het proces, zodat u deze mogelijkheden effectief kunt benutten.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Een basiskennis van .NET-ontwikkeling.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Page voor .NET-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/page/net/).

## Naamruimten importeren

Zorg er om te beginnen voor dat u de benodigde naamruimten in uw project importeert. Dit biedt de vereiste klassen en functionaliteiten voor het werken met Aspose.Page. Dit zijn de essentiële naamruimten:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stap 1: Stel het document in

Maak eerst een nieuw XPS-document waarin u de Unicode-tekst gaat toevoegen. Volg het onderstaande codefragment:

```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```

## Stap 2: Voeg Unicode-tekst toe

Laten we nu Unicode-tekst aan het XPS-document toevoegen. In dit voorbeeld wordt het lettertype Arial gebruikt, wordt de lettergrootte ingesteld op 20 en wordt de tekst op coördinaten geplaatst (400f, 200f). De Unicode-tekenreeks is in dit geval "TEN. rof SPX.esopsA". Bekijk het codefragment hieronder:

```csharp
// Voeg tekst toe
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Stap 3: Sla het document op

Nadat de Unicode-tekst is toegevoegd, slaat u het resulterende XPS-document op. Dit is de laatste stap:

```csharp
// Sla het resulterende XPS-document op
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gefeliciteerd! U hebt met succes Unicode-tekst aan een XPS-document toegevoegd met Aspose.Page voor .NET.

## Conclusie

In deze zelfstudie hebben we het proces onderzocht van het toevoegen van Unicode-tekst aan XPS-documenten met behulp van Aspose.Page voor .NET. Deze functionaliteit opent deuren naar diverse en dynamische documentcreatie binnen de .NET-omgeving.

## Veelgestelde vragen

### Vraag 1: Is Aspose.Page compatibel met de nieuwste .NET-frameworks?

A1: Ja, Aspose.Page wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworks te garanderen.

### Vraag 2: Kan ik de letterstijl en -grootte aanpassen bij het toevoegen van tekst?

A2: Absoluut! Met de meegeleverde voorbeeldcode kunt u de lettertypestijl, -grootte en andere kenmerken eenvoudig aanpassen.

### V3: Waar kan ik aanvullende documentatie voor Aspose.Page vinden?

 A3: U kunt de documentatie raadplegen[hier](https://reference.aspose.com/page/net/) voor uitgebreide informatie en voorbeelden.

### Vraag 4: Zijn er gratis hulpmiddelen om aan de slag te gaan met Aspose.Page?

 A4: Ja, u kunt de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapsondersteuning en discussies.

### Vraag 5: Is er een proefversie beschikbaar voordat u een aankoop doet?

 A5: Zeker! U kunt toegang krijgen tot de gratis proefversie[hier](https://releases.aspose.com/) voordat u een aankoop doet.
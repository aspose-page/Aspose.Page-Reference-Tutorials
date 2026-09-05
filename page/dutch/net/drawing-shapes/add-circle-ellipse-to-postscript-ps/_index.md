---
date: 2026-07-19
description: Leer de asp page postscript handleiding voor het toevoegen van cirkel‑ellipsen
  aan PostScript (PS)-bestanden met Aspose.Page for .NET – hoe u snel postscript‑uitvoer
  genereert.
keywords:
- asp page postscript tutorial
- how to generate postscript
- write postscript output
lastmod: 2026-07-19
linktitle: Cirkel‑ellips toevoegen aan PostScript (PS)
og_description: asp page postscript handleiding die u laat zien hoe u postscript‑uitvoer
  genereert door cirkel‑ellipsen toe te voegen met Aspose.Page for .NET. Volg de stapsgewijze
  gids voor snelle integratie.
og_image_alt: 'Guide: Add circle ellipse to PostScript using Aspose.Page .NET'
og_title: asp page postscript handleiding – Add Circle Ellipse (PS)
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn the asp page postscript tutorial for adding circle ellipses to
    PostScript (PS) files using Aspose.Page for .NET – how to generate postscript
    output quickly.
  headline: asp page postscript tutorial – Add Circle Ellipse (PS)
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily focuses on PostScript, but Aspose provides other
      libraries for various formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/)
      for a full list.
    question: Can I use Aspose.Page for .NET with other document formats?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community discussions and support.
    question: Where can I find additional support and community discussions?
  - answer: Yes, you can access the [free trial](https://releases.aspose.com/) to
      explore the features of Aspose.Page for .NET.
    question: Is there a free trial available for Aspose.Page for .NET?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  - answer: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- Aspose.Page
- .NET drawing
- circle ellipse
title: asp page postscript handleiding – Add Circle Ellipse (PS)
url: /nl/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page postscript tutorial – Voeg cirkelvormige ellips toe (PS)

## Inleiding

In deze **asp page postscript tutorial** ontdek je hoe je perfecte cirkel‑ellipsen kunt toevoegen aan een PostScript (PS) document met behulp van de Aspose.Page bibliotheek voor .NET. Of je nu technische tekeningen, vectorafbeeldingen of aangepaste rapporten genereert, Aspose.Page stelt je in staat PostScript‑output te schrijven zonder je bezig te houden met low‑level PS‑syntaxis. We lopen elke stap door, van het opzetten van de omgeving tot het renderen van twee ellipsen—een gevulde en een omtrek‑ellips—zodat je deze mogelijkheid direct in je eigen applicaties kunt integreren.

## Snelle Antwoorden
- **Wat behandelt deze tutorial?** Het toevoegen van gevulde en omtrek‑cirkel‑ellipsen aan een PS‑bestand met Aspose.Page voor .NET.  
- **Hoeveel code‑stappen zijn vereist?** Acht beknopte stappen, elk geïllustreerd met een kant‑klaar code‑fragment.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET 5, .NET 6, .NET Core 3.1 en .NET Framework 4.6+.  
- **Kan ik hetzelfde graphics‑pad hergebruiken?** Ja—maak één `GraphicsPath` aan en teken of vul deze meerdere keren.

## Wat is de asp page postscript tutorial?
De **asp page postscript tutorial** is een stapsgewijze gids die laat zien hoe je programmatisch PostScript‑inhoud genereert met Aspose.Page voor .NET. Het richt zich op praktische code, real‑world use cases en best‑practice tips zodat je snel betrouwbare PS‑bestanden kunt produceren.

## Waarom Aspose.Page gebruiken voor PostScript‑generatie?
Aspose.Page ondersteunt **30+ outputformaten** (inclusief PDF, SVG en EPS) en kan **documenten met honderden pagina's** renderen zonder het volledige bestand in het geheugen te laden, waardoor een **geheugen‑voetafdrukreductie tot 70 %** wordt bereikt vergeleken met handmatig PS‑string bouwen. De high‑level API elimineert de noodzaak om ruwe PS‑commando's te schrijven, waardoor de ontwikkelingstijd gemiddeld met **80 %** wordt verkort.

## Voorvereisten

Voordat we in de tutorial duiken, zorg ervoor dat je de volgende voorvereisten hebt:

1. Aspose.Page for .NET Library: Download en installeer de Aspose.Page for .NET bibliotheek van [hier](https://releases.aspose.com/page/net/).  
2. Ontwikkelomgeving: Zorg ervoor dat je een werkende .NET‑ontwikkelomgeving op je machine hebt ingesteld.

Laten we nu beginnen met de stapsgewijze gids.

## Namespaces importeren

De `using`‑directieven brengen de Aspose.Page‑klassen in scope zodat je direct met graphics, kleuren en PS‑documenten kunt werken.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nu gaan we het voorbeeld opsplitsen in meerdere stappen om je te begeleiden bij het toevoegen van cirkel‑ellipsen aan een PostScript‑document.

## Hoe stel ik de documentdirectory in?

Om het programma te laten weten waar het gegenereerde PS‑bestand moet worden opgeslagen, moet je een mappad opgeven waar de applicatie naar kan schrijven. Gebruik een variabele zoals `dataDir` en ken een volledig of relatief pad toe; dit pad wordt later in de code gecombineerd met de bestandsnaam van de output.  
**Pro tip:** Gebruik `Path.Combine(Environment.CurrentDirectory, "output")` om een cross‑platform pad te bouwen en hard‑gecodeerde scheidingstekens te vermijden.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Hoe maak ik de output‑stream voor het PostScript‑document?

Het maken van een output‑stream opent een bestands‑handle die de Aspose.Page‑engine zal gebruiken om de PostScript‑gegevens in te schrijven. Door een `FileStream` met `FileMode.Create` te gebruiken, wordt het bestand bij elke uitvoering nieuw aangemaakt, waardoor eventuele vorige versie wordt overschreven. Deze stream wordt vervolgens doorgegeven aan de `PsDocument`‑constructor.  

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

## Hoe configureer ik opslaan‑opties en initialiseert een PS‑document?

`PsSaveOptions` stelt je in staat paginagrootte, resolutie en andere render‑instellingen op te geven. Hier gebruiken we de standaard A4‑paginagrootte en een één‑pagina document. `PsDocument` vertegenwoordigt het te creëren PostScript‑document; het ontvangt de output‑stream en de opslaan‑opties, en beheert de levenscyclus‑events van de pagina.  

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Hoe maak ik een graphics‑pad voor de eerste ellips?

`GraphicsPath` vertegenwoordigt een vectorvorm die kan worden getekend of gevuld op een PostScript‑pagina. De constructor neemt de X/Y‑coördinaten van de linkerbovenhoek, gevolgd door breedte en hoogte, waardoor je de exacte grootte en positie van de ellips op de pagina kunt definiëren.  

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

## Hoe stel ik de verf in en vul ik de eerste ellips?

`SolidBrush` definieert een effen vulkleur voor teken‑operaties. Door een `SolidBrush` met een specifieke `Color` te maken en deze door te geven aan `graphics.FillPath`, wordt de ellips met die effen kleur gerenderd.  

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

## Hoe maak ik een graphics‑pad voor de tweede ellips?

Een tweede `GraphicsPath` wordt gedefinieerd om te illustreren hoe je een omtrek (stroke) apart van een vulling kunt tekenen. Hetzelfde constructor‑patroon wordt gebruikt, maar je kunt de afmetingen van de rechthoek wijzigen om een ellips van een andere grootte te produceren.  

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

## Hoe stel ik de stroke in en teken ik de tweede ellips?

`SolidPen` specificeert de kleur en breedte voor het stroken van vormen. Door een `SolidPen` te leveren aan `graphics.DrawPath`, wordt de omtrek van de ellips getekend zonder vulling, waardoor je een nette gestrekte vorm krijgt.  

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

## Hoe sluit ik de huidige pagina en sla ik het document op?

Nadat alle teken‑commando's zijn uitgevoerd, moet je de actieve pagina sluiten met `document.ClosePage()` om de inhoud te finaliseren. Ten slotte schrijft het aanroepen van `document.Save()` de verzamelde PostScript‑data naar de eerder geopende stream, waardoor het output‑bestand op schijf wordt aangemaakt.  

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet gevonden** | Onjuist mappad | Controleer of de map bestaat of maak deze aan met `Directory.CreateDirectory`. |
| **Lege output** | Vergeten `document.ClosePage()` aan te roepen | Zorg ervoor dat je de pagina sluit vóór het opslaan. |
| **Onjuiste kleuren** | `Color.FromArgb` met verkeerde volgorde gebruiken | Gebruik `Color.FromRgb(red, green, blue)` voor duidelijkheid. |
| **Prestatie‑vertraging bij grote bestanden** | Het volledige document in het geheugen laden | Gebruik `PsSaveOptions` met `EnableMemorySaving = true` om grote pagina's te streamen. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?**  
A: Aspose.Page richt zich voornamelijk op PostScript, maar Aspose biedt andere bibliotheken voor diverse formaten. Bekijk de [Aspose-documentatie](https://reference.aspose.com/page/net/) voor een volledige lijst.

**Q: Waar kan ik extra ondersteuning en community‑discussies vinden?**  
A: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor community‑discussies en ondersteuning.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page voor .NET?**  
A: Ja, je kunt de [gratis proefversie](https://releases.aspose.com/) gebruiken om de functies van Aspose.Page voor .NET te verkennen.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?**  
A: Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) voor test‑ en evaluatiedoeleinden.

**Q: Waar kan ik Aspose.Page voor .NET kopen?**  
A: Koop Aspose.Page voor .NET via de [aankooppagina](https://purchase.aspose.com/buy).

## Conclusie

Gefeliciteerd! Je hebt de **asp page postscript tutorial** succesvol afgerond voor het toevoegen van cirkel‑ellipsen aan PostScript‑documenten met Aspose.Page voor .NET. Door de acht duidelijke stappen te volgen, kun je nu hoogwaardige PS‑bestanden genereren met gevulde en omtrek‑ellipsen, klaar om te integreren in rapportage‑engines, CAD‑exporteurs of elke aangepaste grafische pipeline.

---

**Laatst bijgewerkt:** 2026-07-19  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Page .NET – Vormen tekenen](/page/net/drawing-shapes/)
- [Postscript‑document maken .net – Rechthoek toevoegen met Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Hoe een PostScript‑document maken met Aspose.Page voor .NET](/page/net/document-creation/create-postscript-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
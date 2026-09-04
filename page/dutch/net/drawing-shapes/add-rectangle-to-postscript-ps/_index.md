---
date: 2026-06-30
description: Leer hoe u een PostScript-document .NET maakt en rechthoeken toevoegt
  met Aspose.Page voor .NET. Stapsgewijze handleiding met codevoorbeelden.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Rechthoek toevoegen aan PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Maak PostScript-document .NET – Voeg een rechthoek toe met Aspose.Page
url: /nl/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechthoek toevoegen aan PostScript (PS) met Aspose.Page voor .NET

## Inleiding

Aspose.Page for .NET is een bibliotheek die het mogelijk maakt om PostScript-, EPS- en XPS-bestanden programmatisch te maken en te bewerken. Als je op zoek bent naar **create postscript document .net**, leidt deze tutorial je stap voor stap door het toevoegen van rechthoeken aan een PostScript-document met Aspose.Page, en biedt je een solide basis voor het genereren van rijkere grafische elementen.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.Page for .NET.  
- **Kan ik een PostScript-document vanaf nul maken?** Ja – de API laat je PS-bestanden programmatisch bouwen.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor basisvormen.

## Wat is het maken van een postscript-document .net?
Een PostScript-document maken in .NET betekent het programmatisch genereren van een `.ps`‑bestand dat paginainhoud beschrijft — tekst, grafische elementen of vormen — met behulp van de Aspose.Page API. Deze aanpak is ideaal voor server‑side grafiekgeneratie, geautomatiseerde rapportcreatie, of elke situatie waarin je nauwkeurige controle over het uitvoerformaat nodig hebt.

## Waarom Aspose.Page voor .NET gebruiken?
Aspose.Page ondersteunt **30+ grafische primitieve** en kan bestanden genereren tot **500 MB** zonder het volledige document in het geheugen te laden, waardoor er high‑performance rendering op Windows, Linux en macOS wordt geleverd. Het geeft je volledige controle over vormen, kleuren en lijnen, terwijl je geen low‑level PostScript‑code hoeft te schrijven.

- **Volledige controle over grafische elementen** – teken vormen, stel kleuren in en pas lijnen toe zonder low‑level PS‑syntaxis te hoeven behandelen.  
- **Cross‑platform** – werkt op Windows-, Linux- en macOS-runtime.  
- **Geen externe afhankelijkheden** – de bibliotheek verwerkt alle PS‑generatie intern.  
- **Rijke documentatie & voorbeelden** – snel aan de slag.

## Voorvereisten

- **Aspose.Page for .NET Library** – download en installeer vanaf [here](https://releases.aspose.com/page/net/).  
- **Ontwikkelomgeving** – Visual Studio, VS Code, of elke .NET‑compatibele IDE.

## Namespaces importeren

De `Aspose.Page` namespace biedt de kernklassen die je nodig hebt, zoals `Document`, `Page`, `SolidBrush` en `Pen`. Importeer deze voordat je begint met coderen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we nu het voorbeeld opsplitsen in duidelijke, genummerde stappen.

## Stap 1: Stel uw documentmap in

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door de map waarin je het resulterende PS‑bestand wilt opslaan.

## Stap 2: Maak een output‑stream voor het PostScript‑document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Deze stream wijst naar **AddRectangle_outPS.ps**. Voel je vrij om het bestand een andere naam te geven of de locatie naar wens te wijzigen.

## Stap 3: Stel opslaan‑opties in en maak het PS‑document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Hier geven we Aspose.Page de opdracht een A4-paginaformaat te gebruiken en een één‑pagina document te maken.

## Stap 4: Voeg een gevulde rechthoek toe

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

We definiëren een rechthoek op (250, 100) met een breedte van 150 en een hoogte van 100, stellen een oranje penseel in en vullen de vorm.

## Stap 5: Voeg een omrande rechthoek toe

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Een tweede rechthoek wordt lager op de pagina gemaakt, dit keer met een rode lijn van 3 punten.

## Stap 6: Sluit de pagina en sla het document op

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Het sluiten van de pagina voltooit de tekening, en `Save()` schrijft het PS‑bestand naar de schijf.

## Hoe maak je een postscript-document .net?
`Document` is de hoofdklasse die een PostScript‑bestand in Aspose.Page vertegenwoordigt. `SaveOptions` specificeert instellingen zoals paginagrootte en uitvoerformaat voor het document. Laad het `Document`‑object, configureer `SaveOptions` voor een A4‑pagina, teken je vormen met `SolidBrush` of `Pen`, en roep vervolgens `document.Save()` aan — de volledige workflow vereist slechts een paar regels code en draait op elke ondersteunde .NET‑runtime. Dit patroon stelt je in staat volledig conforme PostScript‑bestanden te genereren zonder ruwe PS‑syntaxis aan te raken.

## Hoe genereer je een postscript‑bestand
Gebruik de `SaveOptions`‑klasse van Aspose.Page om het uitvoerformaat als PostScript (`SaveFormat.PS`) op te geven. De bibliotheek streamt de inhoud direct naar een bestand of geheugen‑stream, waardoor je grote documenten efficiënt kunt genereren zonder overmatig geheugenverbruik.

## Veelvoorkomende problemen & tips

- **Onjuiste bestands‑pad** – Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken (`\\` of `/`) of gebruik `Path.Combine`.  
- **Ontbrekende licentie** – Pas in een productieomgeving je Aspose‑licentie toe voordat je het document maakt om evaluatiewatermerken te vermijden.  
- **Kleurzichtbaarheid** – Als de rechthoek leeg lijkt, controleer dan of de penseel‑ of pen‑kleuren contrasteren met de paginabackground.

## Veelgestelde vragen

**Q:** Kan ik de kleuren van de rechthoeken aanpassen?  
**A:** Absoluut. Verander de `Color.Orange` of `Color.Red` waarden in de `SolidBrush`‑ en `Pen`‑constructors naar elke `System.Drawing.Color` die je verkiest.

**Q:** Is Aspose.Page compatibel met andere documentformaten?  
**A:** Ja. Naast PostScript ondersteunt Aspose.Page ook XPS- en EPS‑generatie.

**Q:** Hoe kan ik tekst toevoegen aan hetzelfde document?  
**A:** Gebruik de `TextFragment`‑klasse om tekst op gewenste coördinaten te plaatsen, en roep vervolgens `document.Draw(textFragment)` aan.

**Q:** Waar kan ik extra voorbeelden en de volledige API‑referentie vinden?  
**A:** Verken de documentatie [here](https://reference.aspose.com/page/net/) en word lid van de community op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Kan ik Aspose.Page uitproberen voordat ik koop?  
**A:** Ja, download een gratis proefversie [here](https://releases.aspose.com/). Voor een uitgebreide evaluatie, overweeg een [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** Aspose.Page 24.12 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe een PostScript-document maken met Aspose.Page voor .NET](/page/net/document-creation/create-postscript-document/)
- [Afbeelding toevoegen aan PostScript (PS)-document met Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Tekst toevoegen aan PostScript (PS)-document met Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
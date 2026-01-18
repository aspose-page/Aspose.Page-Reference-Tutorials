---
date: 2026-01-18
description: Leer hoe je een PostScript‑document maakt in .NET en rechthoeken toevoegt
  met Aspose.Page voor .NET. Stapsgewijze handleiding met codevoorbeelden.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Postscript‑document maken in .NET – Rechthoek toevoegen met Aspose.Page
url: /nl/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een rechthoek toe aan PostScript (PS) met Aspose.Page voor .NET

## Introduction

Als je een **PostScript-document maken in .NET** wilt, biedt Aspose.Page een krachtige oplossing voor het verwerken van PostScript‑bestanden. In deze tutorial laten we je stap voor stap zien hoe je rechthoeken toevoegt aan een PostScript‑document met Aspose.Page voor .NET, zodat je een solide basis krijgt voor het genereren van rijkere graphics.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.Page for .NET.
- **Kan ik een PostScript‑document vanaf nul maken?** Ja – de API laat je PS‑bestanden programmatically genereren.
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor basisvormen.

## Wat betekent het om een PostScript‑document te maken in .NET?
Een PostScript‑document maken in .NET betekent dat je programmatically een .ps‑bestand genereert dat de paginainhoud beschrijft — tekst, graphics of shapes — met behulp van de Aspose.Page API. Deze aanpak is ideaal voor server‑side graphics‑generatie, geautomatiseerde rapportage of elke situatie waarin je precieze controle over het uitvoerformaat nodig hebt.

## Waarom Aspose.Page voor .NET gebruiken?
- **Volledige controle over graphics** – teken shapes, stel kleuren in en pas strokes toe zonder low‑level PS‑syntaxis.
- **Cross‑platform** – werkt op Windows, Linux en macOS runtimes.
- **Geen externe afhankelijkheden** – de bibliotheek verwerkt alle PS‑generatie intern.
- **Rijke documentatie & voorbeelden** – snel aan de slag.

## Vereisten

- **Aspose.Page for .NET Library** – download en installeer vanaf [here](https://releases.aspose.com/page/net/).
- **Ontwikkelomgeving** – Visual Studio, VS Code, of elke .NET‑compatible IDE.

## Namespaces importeren

Before you start coding, import the namespaces that expose the required classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we nu het voorbeeld opdelen in duidelijke, genummerde stappen.

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

Deze stream wijst naar **AddRectangle_outPS.ps**. Je kunt het bestand gerust hernoemen of de locatie aanpassen indien nodig.

## Stap 3: Stel opslaan‑opties in en maak het PS‑document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Hier geven we Aspose.Page de opdracht een A4‑paginasize te gebruiken en een één‑pagina document te maken.

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

We definiëren een rechthoek op (250, 100) met een breedte van 150 en een hoogte van 100, stellen een oranje brush in en vullen de vorm.

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

Een tweede rechthoek wordt lager op de pagina gemaakt, dit keer met een rode 3‑punt stroke.

## Stap 6: Sluit de pagina en sla het document op

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Het sluiten van de pagina finaliseert de tekening, en `Save()` schrijft het PS‑bestand naar de schijf.

## Veelvoorkomende problemen & tips

- **Onjuist bestandspad** – Zorg ervoor dat `dataDir` eindigt op een pad‑separator (`\\` of `/`) of gebruik `Path.Combine`.
- **Ontbrekende licentie** – Pas in een productie‑omgeving je Aspose‑licentie toe voordat je het document maakt om evaluatiewatermerken te vermijden.
- **Kleurzichtbaarheid** – Als de rechthoek leeg lijkt, controleer dan of de brush‑ of pen‑kleuren contrasteren met de paginabackground.

## Veelgestelde vragen

**Q:** Kan ik de kleuren van de rechthoeken aanpassen?  
**A:** Zeker. Verander de `Color.Orange` of `Color.Red` waarden in de `SolidBrush` en `Pen` constructors naar elke `System.Drawing.Color` die je wilt.

**Q:** Is Aspose.Page compatibel met andere documentformaten?  
**A:** Ja. Naast PostScript ondersteunt Aspose.Page ook XPS‑ en EPS‑generatie.

**Q:** Hoe kan ik tekst toevoegen aan hetzelfde document?  
**A:** Gebruik de `TextFragment`‑klasse om tekst op de gewenste coördinaten te plaatsen, en roep daarna `document.Draw(textFragment)` aan.

**Q:** Waar kan ik extra voorbeelden en de volledige API‑referentie vinden?  
**A:** Verken de documentatie [here](https://reference.aspose.com/page/net/) en sluit je aan bij de community op het [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Kan ik Aspose.Page uitproberen voordat ik koop?  
**A:** Ja, download een gratis proefversie [here](https://releases.aspose.com/). Voor een uitgebreide evaluatie kun je overwegen een [temporary license](https://purchase.aspose.com/temporary-license/) te nemen.

---

**Laatst bijgewerkt:** 2026-01-18  
**Getest met:** Aspose.Page 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
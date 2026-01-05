---
date: 2026-01-05
description: Leer hoe u een knippad toevoegt in PostScript met Aspose.Page voor .NET
  – stapsgewijze handleiding met set paint brush- en draw dashed rectangle‑technieken.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Voeg knippad toe aan PS met Aspose.Page voor .NET
url: /nl/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Clippingpad toevoegen aan PS met Aspose.Page voor .NET

## Inleiding

## Snelle antwoorden
- **Wat doet “add clipping path”?** Het beperkt tekenbewerkingen tot een gedefinieerde vorm, waarbij alles buiten die vorm verborgen wordt.  
- **Welke bibliotheek behandelt clipping in .NET?** Aspose.Page voor .NET biedt een uitgebreide API voor PS/EPS-manipulatie.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik de penseelkleur wijzigen?** Ja, gebruik `SetPaint` met elke `SolidBrush` of gradient die je wilt.  
- **Is het mogelijk om een gestippelde rechthoek te tekenen?** Absoluut – maak een `Pen` met `DashStyle.Dash` en gebruik `Draw`.  

## Wat is een clippingpad in PostScript?
Een clippingpad definieert het zichtbare gebied van daaropvolgende tekenopdrachten. Alles wat buiten het pad wordt getekend, wordt genegeerd, waardoor je complexe gemaskeerde graphics kunt maken zonder de oorspronkelijke inhoud te wijzigen.

## Waarom Aspose.Page gebruiken voor clipping?
- **Geen externe afhankelijkheden** – pure .NET-bibliotheek.  
- **Volledige controle** over de grafische status (save/restore, translate, rotate).  
- **Rijke tekenprimitieven** zoals `SetPaint`, `Clip` en `Draw` met aanpasbare pennen en penselen.  

## Voorvereisten

- Basiskennis van C# programmeren.  
- Aspose.Page voor .NET bibliotheek geïnstalleerd – je kunt het downloaden [hier](https://releases.aspose.com/page/net/).  
- Visual Studio of een andere gewenste .NET IDE.  

## Namespaces importeren

Importeer eerst de namespaces die nodig zijn voor grafische manipulatie:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now let’s break down the example into clear, numbered steps.

### Stap 1: Documentmap instellen

Definieer de map waar je bron- en uitvoerbestanden worden opgeslagen.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Stap 2: Outputstream maken voor PostScript-document

Maak een schrijfbare stream die het gegenereerde PS‑bestand zal bevatten.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Stap 3: Opslagopties maken

Instantieer `PsSaveOptions` met standaardinstellingen. Je kunt later aanpassen indien nodig.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Stap 4: Een nieuw 1‑pagina PS‑document maken

Initialiseer het `PsDocument`‑object dat je PS‑bestand vertegenwoordigt.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Stap 5: Grafisch pad maken van de rechthoek

We gebruiken een rechthoek als basisvorm die later wordt geclipt.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Stap 6: Clipping op vorm

Hier **voegen we een clippingpad toe** met een cirkel, **stellen we de penseel in** op blauw, en vullen we de rechthoek binnen het geclipte gebied.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Stap 7: Bovenliggend grafische status verplaatsen & gestippelde rechthoek tekenen

Na het herstellen van de vorige status verplaatsen we de grafische cursor opnieuw, **tekenen we een gestippelde rechthoek**, en passen we een blauwe lijn toe.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Stap 8: Document sluiten en opslaan

Rond de pagina af en schrijf het PS‑bestand naar schijf.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Je hebt nu succesvol een **clippingpad toegevoegd**, een aangepaste penseel ingesteld, en een gestippelde rechthoek rond je grafische elementen getekend met Aspose.Page voor .NET.

## Veelvoorkomende problemen en oplossingen

- **Clipping niet zichtbaar:** Zorg ervoor dat je `WriteGraphicsSave()` aanroept vóór het vertalen en `WriteGraphicsRestore()` na het vullen.  
- **Onjuiste kleuren:** Controleer dat `SetPaint` wordt aangeroepen na `Clip` en vóór `Fill`.  
- **Gestippelde lijnen verschijnen als solide:** Zorg ervoor dat de `DashStyle` van de `Pen` is ingesteld op `DashStyle.Dash` vóór `SetStroke`.  

## Veelgestelde vragen

### Q1: Kan ik Aspose.Page voor .NET gebruiken met andere programmeertalen?
A: Aspose.Page is voornamelijk ontworpen voor .NET‑applicaties. Aspose biedt echter vergelijkbare bibliotheken voor andere programmeertalen.

### Q2: Waar kan ik extra voorbeelden en documentatie vinden voor Aspose.Page voor .NET?
A: Je kunt meer voorbeelden en gedetailleerde documentatie verkennen op de [Aspose.Page documentatie](https://reference.aspose.com/page/net/).

### Q3: Is er een gratis proefversie beschikbaar voor Aspose.Page voor .NET?
A: Ja, je kunt een gratis proefversie van Aspose.Page voor .NET [hier](https://releases.aspose.com/) verkrijgen.

### Q4: Hoe kan ik een tijdelijke licentie krijgen voor Aspose.Page voor .NET?
A: Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

### Q5: Waar kan ik ondersteuning krijgen of vragen over Aspose.Page bespreken?
A: Bezoek de [Aspose.Page forums](https://forum.aspose.com/c/page/39) voor community‑ondersteuning en discussies.

---

**Laatst bijgewerkt:** 2026-01-05  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
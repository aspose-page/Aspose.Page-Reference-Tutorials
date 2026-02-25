---
date: 2026-02-25
description: Verbeter PostScript‑documenten met een lineaire gradientrechthoek met
  behulp van Aspose.Page voor .NET. Volg onze stapsgewijze handleiding om te leren
  hoe je tekst met een gradientvulling en tekstcontour met een gradient kunt maken.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Voeg een rechthoek met lineair kleurverloop toe aan PostScript (PS) met Aspose.Page
url: /nl/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 other text: "Add a Linear Gradient Rectangle to PostScript (PS) with Aspose.Page" translation.

Make sure to keep bold formatting (**text**) same.

Also bullet list items have bold parts. Keep bold.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een lineaire gradient rechthoek toe aan PostScript (PS) met Aspose.Page

## Introductie

Welkom bij deze uitgebreide tutorial over het toevoegen van een **lineaire gradient rechthoek** aan PostScript (PS) documenten met Aspose.Page voor .NET. Aspose.Page is een krachtige bibliotheek waarmee je documenten kunt maken, wijzigen en renderen in verschillende formaten, en vandaag richten we ons op hoe je opvallende gradients in je PS‑bestanden kunt brengen.

### Snelle antwoorden
- **Wat doet de lineaire gradient rechthoek?** Het vult een rechthoekig gebied met een vloeiende kleurverandering van de ene kant naar de andere.  
- **Welke API behandelt gradient fill text?** `LinearGradientBrush` gecombineerd met `SetPaint` en `FillAndStrokeText`.  
- **Kan ik tekst omranden met een gradient?** Ja—gebruik `SetStroke` met een gradient‑penseel en roep `OutlineText` aan.  
- **Heb ik een licentie nodig voor productie?** Een commerciële Aspose.Page‑licentie is vereist voor niet‑evaluatiegebruik.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Voorvereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- Aspose.Page for .NET Library: Zorg ervoor dat de bibliotheek in je project is gerefereerd. Je kunt deze downloaden via de [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Document Directory: Maak een map op schijf waar het gegenereerde PS‑bestand wordt opgeslagen en vervang **“Your Document Directory”** in de code door dat pad.

## Importer namespaces

Om te beginnen, importeer je de namespaces die je toegang geven tot de teken‑ en PS‑specifieke klassen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Wat is een lineaire gradient rechthoek?

Een **lineaire gradient rechthoek** is simpelweg een rechthoekige vorm waarvan het interieur is geschilderd met een lineaire gradient—kleuren verlopen soepel langs een rechte lijn, meestal van links naar rechts (horizontaal) of van boven naar beneden (verticaal). In Aspose.Page bereik je dit door een `GraphicsPath` die de rechthoek definieert te combineren met een `LinearGradientBrush` die de kleurverloop beschrijft.

## Waarom gradient fill text en outline text gradient gebruiken?

- **Visuele aantrekkingskracht:** Met gradient‑gevulde tekst voeg je diepte en een modern uiterlijk toe aan rapporten, facturen of promotiemateriaal.  
- **Merkconsistentie:** Stem bedrijfs­kleuren af met precieze ARGB‑waarden.  
- **Veelzijdigheid:** Hetzelfde penseel kan worden hergebruikt voor vormvullingen, tekstvullingen en outline‑gradients, waardoor code‑duplicatie wordt verminderd.

## Stap 1: Document instellen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 2: Gradient rechthoek en kleuren definiëren

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Stap 3: Transform instellen voor penseel

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Stap 4: Paint instellen en de rechthoek vullen

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Hoe gradient fill text toepassen

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Outline text gradient gebruiken

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Stap 7: Huidige pagina sluiten en het document opslaan

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Gefeliciteerd! Je hebt met succes een **lineaire gradient rechthoek** toegevoegd aan een PostScript‑document en hetzelfde penseel gebruikt voor **gradient fill text** en een **outline text gradient**.

## Veelvoorkomende use-cases & tips

- **Rapportkoppen:** Vul grote tekstblokken met gradients om sectietitels te accentueren.  
- **Merklogo’s:** Reproduceer logo‑vormen met gradient‑gevulde vormen voor consistente branding.  
- **Pro‑tip:** Hergebruik dezelfde `LinearGradientBrush`‑instantie voor meerdere teken‑aanroepen om kleuren perfect uitgelijnd te houden over vormen en tekst.

## Veelgestelde vragen

### Q1: Kan ik gradients toepassen op andere vormen dan rechthoeken?
**A:** Ja, je kunt gradients toepassen op elke vorm die wordt gedefinieerd door een `GraphicsPath`. Voeg eenvoudig cirkels, polygonen of aangepaste paden toe voordat je `document.Fill(path)` aanroept.

### Q2: Hoe kan ik de gradient‑kleuren wijzigen?
**A:** Pas de `Color.FromArgb`‑waarden aan bij het construeren van `LinearGradientBrush`. De eerste kleur is het begin, de tweede is het einde van de gradient.

### Q3: Is Aspose.Page compatibel met verschillende documentformaten?
**A:** Absoluut. Aspose.Page ondersteunt XPS, PS, PDF en verschillende andere vectorformaten. Raadpleeg de officiële documentatie voor de volledige lijst.

### Q4: Kan ik Aspose.Page gebruiken voor commerciële projecten?
**A:** Ja, commerciële licenties zijn beschikbaar. Zie de aankooppagina voor details: [here](https://purchase.aspose.com/buy).

### Q5: Waar kan ik community‑ondersteuning vinden?
**A:** Word lid van het Aspose.Page community‑forum: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
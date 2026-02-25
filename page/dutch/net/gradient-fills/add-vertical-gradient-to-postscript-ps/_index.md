---
date: 2026-02-25
description: Leer hoe je een C# lineaire verloopkwast gebruikt om een verloop toe
  te voegen aan PS‑bestanden en een rechthoek met verloop te vullen met behulp van
  Aspose.Page voor .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Lineaire Gradientkwast – Voeg verticale gradient toe aan PostScript (PS)
  met Aspose.Page
url: /nl/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 .NET  
**Auteur:** Aspose  

Then closing shortcodes unchanged.

Finally backtop button shortcode unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Voeg verticale gradient toe aan PostScript (PS) met Aspose.Page

## Introductie

In het domein van documentmanipulatie en -creatie, **Aspose.Page for .NET** valt op als een krachtig hulpmiddel voor ontwikkelaars. In deze gids ontdek je hoe je **gradient toevoegt aan PS**-bestanden door een **C# lineaire gradient penseel** te gebruiken om een **rechthoek met gradient te vullen**. Aan het einde van deze tutorial heb je een duidelijk, stap‑voor‑stap begrip van de benodigde code en waarom deze techniek een vloeiende verticale gradient produceert in je PostScript-uitvoer.

## Snelle antwoorden
- **Wat doet een C# lineaire gradient penseel?** Het creëert een vloeiende overgang tussen meerdere kleuren over een vorm.
- **Kan ik dit gebruiken met elke .NET‑versie?** Ja, Aspose.Page ondersteunt .NET Framework 4.5+ en .NET Core/5+.
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor niet‑evaluatie‑builds.
- **Is de gradient echt verticaal?** Het penseel is 90° geroteerd, waardoor een verticale stroom wordt gegarandeerd.
- **Waar wordt de output opgeslagen?** Naar het pad dat je opgeeft in `dataDir` (bijv. `VerticalGradient_outPS.ps`).

## Wat is een C# lineaire gradient penseel?

Een **C# lineaire gradient penseel** is een GDI+‑object (`LinearGradientBrush`) dat een lineaire kleurverloop schildert tussen gedefinieerde punten. In combinatie met de teken‑API van Aspose.Page kun je geavanceerde gradients direct renderen in een PostScript (PS)‑document.

## Waarom een lineaire gradient penseel gebruiken voor PostScript?

- **Hoge kwaliteit output:** Gradients worden gerenderd op printerniveau, waardoor de getrouwheid behouden blijft.
- **Volledige controle:** Je kunt aangepaste kleurstops, rotatie en schaalinstellingen definiëren.
- **Herbruikbare code:** Dezelfde penseellogica werkt voor PDF, SVG en andere formaten die door Aspose.Page worden ondersteund.

## Vereisten

Voordat je aan de tutorial begint, zorg ervoor dat je het volgende hebt:

- Aspose.Page for .NET: Zorg ervoor dat je de Aspose.Page‑bibliotheek geïnstalleerd hebt. Je kunt de benodigde bronnen en documentatie vinden [hier](https://reference.aspose.com/page/net/).
- Ontwikkelomgeving: Richt een geschikte ontwikkelomgeving in, inclusief een Integrated Development Environment (IDE) voor .NET‑ontwikkeling.
- Basiskennis: Maak jezelf vertrouwd met de basis van .NET‑ontwikkeling, inclusief het werken met streams, graphics‑paths en kleurmanipulatie.

## Namespaces importeren

Voeg in je C#‑project de benodigde namespaces toe aan het begin van je code‑bestand:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Documentmap instellen

Begin met het opgeven van het pad naar je documentmap. Dit is de locatie waar je PS‑document wordt opgeslagen.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Output‑stream maken voor PostScript‑document

Genereer een output‑stream voor het PostScript‑document met behulp van de `FileStream`‑klasse.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Stap 3: Opslagopties en PS‑document maken

Maak opslagopties met A4‑formaat en initialiseert een nieuw 1‑pagina PS‑document.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 4: Rechthoekafmetingen definiëren

Geef de afmetingen en positie op van de rechthoek waarin de verticale gradient wordt toegepast.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Stap 5: Graphics‑pad maken

Bouw een graphics‑pad op basis van de gedefinieerde rechthoek.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Stap 6: Interpolatiekleuren definiëren

Stel een array van interpolatiekleuren en posities in voor de gradient.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Stap 7: Lineair gradient penseel maken

Maak een lineair gradient penseel met de rechthoek als grenzen, start‑ en eindkleur.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Stap 8: Penseeltransformatie instellen

Stel een transformatie in voor het penseel, zodat de X‑ en Y‑schaalcomponenten overeenkomen met de breedte en hoogte van de rechthoek.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Stap 9: Paint instellen en de rechthoek vullen

Stel de paint in voor het document, en **vul de rechthoek met gradient** met behulp van het eerder gedefinieerde pad.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Stap 10: Huidige pagina sluiten en het document opslaan

Sluit de huidige pagina en sla het PostScript‑document op.

```csharp
document.ClosePage();
document.Save();
```

Gefeliciteerd! Je hebt met succes **een verticale gradient toegevoegd aan een PostScript‑document** met behulp van een **C# lineaire gradient penseel** met Aspose.Page for .NET. Experimenteer met verschillende parameters en kleuren om diverse visuele effecten in je documenten te bereiken.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Hoe op te lossen |
|-------|----------------|------------|
| Gradient appears horizontal | Brush rotation not applied | Ensure `brushTransform.Rotate(90);` is called before assigning to `brush.Transform`. |
| Colors look washed out | Low‑resolution output stream | Use a higher‑resolution `PsSaveOptions` or increase the document size. |
| Output file is empty | Stream not flushed | Verify that `document.Save();` is called outside the `using` block. |

## Veelgestelde vragen

**Q1: Kan ik meerdere gradients toepassen op verschillende gebieden van hetzelfde document?**  
A: Ja, dat kan. Herhaal eenvoudigweg de stappen voor elk gebied met de specifieke afmetingen en kleurenschema.

**Q2: Hoe kan ik deze code integreren in mijn bestaande .NET‑project?**  
A: Kopieer en plak de code in je projectbestand en zorg ervoor dat de Aspose.Page‑bibliotheek is gerefereerd.

**Q3: Zijn er andere gradient‑typen beschikbaar in Aspose.Page for .NET?**  
A: Aspose.Page ondersteunt verschillende gradient‑typen, waaronder radiale en pad‑gradients. Raadpleeg de documentatie voor meer details.

**Q4: Kan ik Aspose.Page gebruiken voor commerciële projecten?**  
A: Ja, dat kan. Bezoek [hier](https://purchase.aspose.com/buy) om licentieopties te bekijken.

**Q5: Is er een community‑forum voor Aspose.Page waar ik hulp kan zoeken?**  
A: Zeker! Ga naar het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) om contact te maken met andere ontwikkelaars en hulp te krijgen.

---

**Laatst bijgewerkt:** 2026-02-25  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Pas het Texture Tile-patroon toe op PostScript (PS) met Aspose.Page
linktitle: Textuurtegelspatroon toepassen op PostScript (PS)
second_title: Aspose.Page .NET-API
description: Verbeter uw PostScript (PS)-documenten met textuurtegels met behulp van Aspose.Page voor .NET. Volg onze stap-voor-stap handleiding voor een creatief tintje.
weight: 10
url: /nl/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pas het Texture Tile-patroon toe op PostScript (PS) met Aspose.Page

## Invoering

Welkom bij deze stapsgewijze zelfstudie over het toepassen van een textuurpatroon op een PostScript (PS)-document met behulp van Aspose.Page voor .NET. Aspose.Page is een krachtige bibliotheek waarmee u met verschillende documentformaten kunt werken. In deze zelfstudie onderzoeken we hoe u uw PS-documenten kunt verbeteren door textuurtegels toe te voegen.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:

- [Visuele studio](https://visualstudio.microsoft.com/) op uw machine geïnstalleerd.
- Basiskennis van programmeren in C#.
-  Download en installeer de[Aspose.Page voor .NET-bibliotheek](https://releases.aspose.com/page/net/).
- Een afbeeldingsbestand voor het structuurpatroon (bijvoorbeeld "TestTexture.bmp").

## Naamruimten importeren

Zorg ervoor dat u in uw C#-code de benodigde naamruimten importeert:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we het gegeven voorbeeld opsplitsen in meerdere stappen om u door het proces te leiden.

## Stap 1: Documentmap instellen

```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
```

Zorg ervoor dat u "Uw documentenmap" vervangt door het pad waar u uw PS-document wilt opslaan.

## Stap 2: Maak een uitvoerstroom voor PS-document

```csharp
// Maak een uitvoerstroom voor een PostScript-document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Creëer opslagopties met A4-formaat
    PsSaveOptions options = new PsSaveOptions();

    // Maak een nieuw PS-document met één pagina
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Met deze stap stelt u de uitvoerstroom voor het PS-document in, inclusief het definiëren van de documentgrootte.

## Stap 3: Breng het textuurtegelspatroon aan

```csharp
// Maak een Bitmap-object van het afbeeldingsbestand
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Maak een textuurpenseel van de afbeelding
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Voeg schaling in de X-richting toe aan het patroon
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Stel dit textuurpenseel in als de huidige verf
    document.SetPaint(brush);
}
```

Deze stap omvat het maken van een textuurpenseel van een afbeelding en het instellen ervan als de huidige verf voor het document.

## Stap 4: Creëer een rechthoekig pad en vul

```csharp
// Creëer een rechthoekig pad
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Rechthoek vullen
document.Fill(path);
```

Hier definiëren we een rechthoekig pad en vullen dit met het eerder ingestelde textuurpenseel.

## Stap 5: Stel Lijn en Teken in

```csharp
// Koop huidige verf
Brush paint = document.GetPaint();

// Rode streek instellen
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Strijk de rechthoek
document.Draw(path);
```

Deze stap omvat het instellen van lijneigenschappen en het tekenen van de omlijnde rechthoek.

## Stap 6: Tekst vullen en omlijnen met structuurpatroon

```csharp
// Vul tekst met structuurpatroon
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Overzichtstekst met structuurpatroon
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Ten slotte vullen we de tekst en schetsen deze met het structuurpatroon, waardoor de visuele aantrekkingskracht van uw document wordt vergroot.

## Stap 7: Document opslaan en sluiten

```csharp
// Sluit huidige pagina
document.ClosePage();

// Bewaar het document
document.Save();
```

Zorg ervoor dat u de huidige pagina sluit en het document opslaat om de wijzigingen toe te passen.

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u een textuurpatroon kunt toepassen op een PostScript-document met behulp van Aspose.Page voor .NET. Experimenteer met verschillende afbeeldingen en patronen om uw PS-documenten verder aan te passen.

## Veelgestelde vragen

### Vraag 1: Kan ik andere afbeeldingsformaten gebruiken voor het structuurpatroon?

A1: Ja, Aspose.Page ondersteunt verschillende afbeeldingsformaten. Zorg voor compatibiliteit met de bibliotheekdocumentatie.

### V2: Is Aspose.Page compatibel met .NET Core?

A2: Ja, Aspose.Page is compatibel met zowel .NET Framework als .NET Core.

### Vraag 3: Hoe kan ik de grootte van de getextureerde rechthoek aanpassen?

 A3: Wijzig de afmetingen in het`RectangleF` parameters tijdens het maken van het pad.

### V4: Kan ik meerdere structuurpatronen aan één document toevoegen?

A4: Ja, u kunt het proces herhalen met verschillende afbeeldingen en paden.

### Vraag 5: Waar kan ik aanvullende bronnen en ondersteuning vinden?

 A5: Bezoek de[Aspose.Pagina-forum](https://forum.aspose.com/c/page/39) voor gemeenschapsondersteuning en verken de[documentatie](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

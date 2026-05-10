---
date: 2026-03-26
description: Leer hoe u een PostScript‑document in .NET maakt met textuur‑tegelpatronen
  met behulp van Aspose.Page. Volg onze stapsgewijze gids om rijke texturen aan uw
  PS‑bestanden toe te voegen.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Maak PostScript .NET-document met textuurtegeling
url: /nl/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak PostScript .NET‑document met textuur‑tegelpatroon

## Hoe maak je een PostScript‑document .NET met textuur‑tegelpatroon

In deze tutorial leer je hoe je een **PostScript‑document .NET** maakt en verrijkt met een textuur‑tegelpatroon met behulp van de Aspose.Page‑bibliotheek. We lopen stap voor stap door het proces, van het opzetten van je project tot het vullen en omtrekken van tekst met de texture brush, zodat je binnen enkele minuten visueel aantrekkelijke PS‑bestanden kunt produceren.

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Page for .NET  
- **Kan ik .NET Core gebruiken?** Ja, de bibliotheek ondersteunt .NET Core en .NET 5/6  
- **Welke afbeeldingsformaten werken voor de textuur?** Elk formaat dat door System.Drawing wordt ondersteund (BMP, PNG, JPEG, enz.)  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie  

## Voorvereisten

- [Visual Studio](https://visualstudio.microsoft.com/) geïnstalleerd op je machine.  
- Basiskennis van C#‑programmeren.  
- Download en installeer de [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- Een afbeeldingsbestand voor het textuurpatroon (bijv. **TestTexture.bmp**).

## Namespaces importeren

Importeer in je C#‑bestand de benodigde namespaces zodat de compiler weet waar de types die we gebruiken te vinden zijn:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Documentmap instellen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Vervang **Your Document Directory** door de map waarin je het gegenereerde PS‑bestand wilt opslaan.

## Stap 2: Output‑stream voor PS‑document maken

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Dit blok opent een bestandsstream, configureert de paginagrootte (standaard A4) en maakt een nieuwe **PsDocument**‑instantie aan waarop we gaan tekenen.

## Stap 3: Textuur‑tegelpatroon toepassen

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Hier laden we de bitmap, wikkelen deze in een **TextureBrush**, rekken deze eventueel horizontaal uit, en vertellen we de **PsDocument** om deze brush te gebruiken voor de volgende tekenbewerkingen.

## Stap 4: Rechthoekpad maken en vullen

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Er wordt een eenvoudige rechthoek gedefinieerd en gevuld met de texture brush die we eerder hebben ingesteld.

## Stap 5: Omtrek instellen en tekenen

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

We halen de huidige paint (de texture brush) op, maken een rode pen voor de omtrek, en tekenen de rand van de rechthoek.

## Stap 6: Tekst vullen en omtrekken met textuurpatroon

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Deze stap toont de **fill and stroke text**‑functionaliteit: de tekens “ABC” worden gevuld met de texture brush en vervolgens omlijnd, wat een opvallend visueel effect geeft.

## Stap 7: Document opslaan en sluiten

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Het sluiten van de pagina finaliseert de tekenopdrachten, en `Save()` schrijft het PostScript‑bestand naar schijf.

## Veelvoorkomende problemen en oplossingen

- **Textuur wordt onjuist uitgerekt** – Pas de `Matrix`‑waarden aan om de schaal in X/Y‑richting te regelen.  
- **Afbeelding niet gevonden** – Controleer of `dataDir` naar de juiste map wijst en of de bestandsnaam exact overeenkomt, inclusief hoofdletters.  
- **Kleuren zien er verkeerd uit** – Onthoud dat PostScript een apparaat‑onafhankelijke kleurenruimte gebruikt; zorg ervoor dat je `Color`‑objecten gebruikt die correct worden gemapt.

## Veelgestelde vragen

**V:** Kan ik andere afbeeldingsformaten gebruiken voor het textuurpatroon?  
**A:** Ja, elk formaat dat door `System.Drawing.Bitmap` wordt ondersteund (BMP, PNG, JPEG, GIF, enz.) werkt.

**V:** Is Aspose.Page compatibel met .NET Core?  
**A:** Absoluut. De bibliotheek draait op .NET Framework, .NET Core en .NET 5/6.

**V:** Hoe wijzig ik de grootte van de getexturede rechthoek?  
**A:** Pas de `RectangleF`‑waarden aan in de stap waarin de rechthoek wordt gemaakt (bijv. `new RectangleF(0, 0, 300, 150)`).

**V:** Kan ik meerdere textuurpatronen in één document toepassen?  
**A:** Ja. Maak simpelweg een nieuwe `TextureBrush` met een andere afbeelding en roep opnieuw `SetPaint` aan voordat je de volgende vorm of tekst tekent.

**V:** Waar vind ik meer voorbeelden en API‑referentie?  
**A:** Bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning en de officiële [documentatie](https://reference.aspose.com/page/net/) voor gedetailleerd API‑gebruik.

## Conclusie

Je weet nu hoe je een **PostScript‑document .NET** maakt en een textuur‑tegelpatroon toepast, inclusief hoe je **tekst vult en omtrekt** met die textuur. Experimenteer met verschillende afbeeldingen, schaal‑matrices en tekenprimitieven om op maat gemaakte PS‑bestanden te produceren voor rapporten, flyers of elke grafisch intensieve output.

---

**Laatst bijgewerkt:** 2026-03-26  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-29
description: Leer hoe je een lineaire gradientkwast in C# gebruikt om pseudo‑transparantie
  te creëren in PostScript met Aspose.Page voor .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Lineaire Gradientkwast C# voor Pseudo-Transparantie in PS
url: /nl/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lineaire Gradient Penseel C# voor Pseudo-Transparantie in PostScript (PS)

## Introductie

Als u een subtiel doorzichtseffect aan uw PostScript (PS)-bestanden wilt toevoegen, is de **linear gradient brush C#** het perfecte hulpmiddel. Aspose.Page for .NET maakt het eenvoudig om rechthoeken te schilderen met zowel ondoorzichtige als doorschijnende gradientvullingen, waardoor uw documenten er modern en gelaagd uitzien. In deze tutorial lopen we de exacte stappen door die nodig zijn om pseudo-transparantie te creëren met een lineaire gradient penseel in C#.

## Snelle Antwoorden
- **Welke bibliotheek levert de linear gradient brush?** Aspose.Page for .NET
- **Welke graphics‑klasse maakt de gradient?** `LinearGradientBrush`
- **Kan ik de opacity per kleur regelen?** Ja, met `Color.FromArgb(alpha, …)`
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Page‑licentie is vereist
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Wat is een linear gradient brush C#?

Een `LinearGradientBrush` is een GDI+-object dat een vloeiende overgang tussen twee kleuren langs een rechte lijn schildert. Wanneer u het alfacanaal (0‑255) voor elke kleur opgeeft, kunt u doorschijnende gradients maken — precies wat we nodig hebben voor pseudo‑transparantie in PostScript.

## Waarom een linear gradient brush C# gebruiken voor pseudo‑transparantie?

- **Fijne opacity‑regeling:** Pas de alfa van elke kleur aan om het gewenste doorzichtsniveau te bereiken.  
- **Apparaatonafhankelijke weergave:** Het penseel werkt hetzelfde op scherm, PDF, EPS en PS-uitvoer.  
- **Eenvoudige API:** Een paar regels C#‑code leveren visuele effecten van professionele kwaliteit.

## Voorvereisten

Voordat u in de code duikt, zorg ervoor dat u het volgende heeft:

- Aspose.Page for .NET geïnstalleerd. U kunt het downloaden van de [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- Een beschrijfbare map waarin het gegenereerde PostScript‑document wordt opgeslagen.

Nu u de benodigde tools heeft, laten we beginnen met het bouwen van de pseudo‑transparante rechthoeken.

## Namespaces importeren

Voordat we beginnen, importeer de namespaces die de klassen bevatten die we gaan gebruiken:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Maak de output‑stream voor het PostScript‑document

We beginnen met het aanmaken van een bestandsstream die het resulterende PS‑bestand zal bevatten, en initialiseren vervolgens de `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 2: Maak een rechthoek met een **ondoorzichtige** gradientvulling

Hier bouwen we een `LinearGradientBrush` waarvan de kleuren volledig ondoorzichtig zijn (alpha = 255). Deze rechthoek dient als de achtergrondlaag.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Stap 3: Maak een rechthoek met een **doorschijnende** gradientvulling

Nu gebruiken we een **linear gradient brush C#** waarbij de alfabewerkingen lager zijn dan 255 (bijv. 150 en 50). Dit maakt de rechthoek gedeeltelijk doorzichtig, waardoor het pseudo‑transparantie‑effect ontstaat.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Stap 4: Sluit de pagina en sla het document op

Tot slot voltooien we de pagina en schrijven we het PS‑bestand naar schijf.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Door deze vier stappen te volgen kunt u naadloos ondoorzichtige en doorschijnende rechthoeken combineren, waardoor een overtuigend pseudo‑transparant effect ontstaat in elke PostScript‑uitvoer.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Kleuren verschijnen volledig ondoorzichtig | Alfawaarde per ongeluk op 255 gezet | Gebruik `Color.FromArgb(alpha, …)` met `alpha` < 255 |
| Gradient wordt onjuist uitgerekt | Onjuiste transformatie‑matrix | Controleer of de matrix‑parameters overeenkomen met de afmetingen van de rechthoek |
| Uitvoerbestand is leeg | Stream niet gesloten of `Save()` niet aangeroepen | Zorg ervoor dat `document.ClosePage()` en `document.Save()` worden uitgevoerd binnen het `using`‑blok |

## Veelgestelde vragen

**V: Is Aspose.Page compatibel met alle versies van .NET?**  
A: Aspose.Page for .NET is compatibel met verschillende versies van het .NET‑framework, wat flexibiliteit en gemakkelijke integratie garandeert.

**V: Kan ik pseudo‑transparantie toepassen op andere vormen dan rechthoeken?**  
A: Ja, dezelfde principes kunnen op elke vorm worden toegepast door de `GraphicsPath` dienovereenkomstig aan te passen.

**V: Waar kan ik extra voorbeelden en documentatie vinden?**  
A: Bekijk de [Aspose.Page documentation](https://reference.aspose.com/page/net/) voor uitgebreide voorbeelden en gedetailleerde API‑referenties.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Page?**  
A: Ja, u kunt een gratis proefversie van Aspose.Page verkrijgen via [this link](https://releases.aspose.com/).

**V: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?**  
A: Bezoek [this link](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor Aspose.Page te verkrijgen.

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
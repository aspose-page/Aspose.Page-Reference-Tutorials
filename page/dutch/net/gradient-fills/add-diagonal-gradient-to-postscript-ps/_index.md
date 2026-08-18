---
date: 2026-02-23
description: Leer hoe je een gradient toevoegt aan PostScript‑bestanden, een PostScript‑bestand
  opslaat met A4‑paginagrootte en een rechthoek vult met een gradient met behulp van
  Aspose.Page voor .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Hoe een kleurverloop toe te voegen – Diagonaal kleurverloop in PostScript (PS)
  met Aspose.Page .NET
url: /nl/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

 **how to add gradient** left unchanged.

Check bullet lists: we translated.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een gradient toe te voegen: Diagonale gradient aan PostScript (PS) met Aspose.Page .NET

## Introductie

Het toevoegen van een diagonale gradient aan een PostScript (PS) document kan de visuele aantrekkingskracht aanzienlijk verbeteren, vooral wanneer je **how to add gradient** effecten nodig hebt in technische rapporten, brochures of grafisch intensieve toepassingen. In deze tutorial zie je precies hoe je een gradient toevoegt aan een PostScript‑bestand, een A4‑paginaformaat instelt en een rechthoek vult met een vloeiende kleurverloop met behulp van Aspose.Page voor .NET.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for .NET  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Kan ik de richting van de gradient wijzigen?** Ja – roteer de brush‑transformatie zoals getoond in de code  
- **Hoe sla ik het resultaat op?** Gebruik `PsDocument.Save()` die een PostScript‑bestand naar schijf schrijft  
- **Is een licentie nodig voor productie?** Ja, een commerciële licentie ontgrendelt volledige functionaliteit  

## Wat is een diagonale gradient in PostScript?

Een diagonale gradient is een lineaire kleurverandering die onder een hoek (meestal 45°) over een vorm loopt. In PostScript wordt dit bereikt door een `LinearGradientBrush` toe te passen met een aangepaste transformatie‑matrix die de gradient roteert, schaalt en verplaatst om overeen te komen met de gewenste rechthoek.

## Waarom Aspose.Page gebruiken voor gradient‑vullingen?

Aspose.Page abstraheert de low‑level PostScript‑commando's, zodat je kunt werken met vertrouwde .NET‑grafiekobjecten. Je kunt complexe vullingen maken, paginagrootte instellen en direct exporteren naar een **save PostScript file** zonder je bezig te houden met ruwe PS‑syntaxis.

## Voorvereisten

- **Aspose.Page for .NET Library** – download het [hier](https://releases.aspose.com/page/net/).  
- **Document Directory** – een map waar het gegenereerde `*.ps`‑bestand wordt weggeschreven.

Nu we de basis hebben behandeld, laten we de implementatie stap voor stap doorlopen.

## Importeer namespaces

Importeer eerst de namespaces die je toegang geven tot het EPS‑apparaat, teken‑hulpmiddelen en I/O‑klassen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Maak output‑stream voor PostScript‑document (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Stap 2: Stel A4‑paginaformaat in (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Stap 3: Maak een nieuw 1‑pagina PS‑document

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 4: Definieer rechthoek‑parameters

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Stap 5: Maak graphics‑pad

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Stap 6: Maak Linear Gradient Brush (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Stap 7: Maak transformatie voor brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Stap 8: Pas transformaties toe op brush (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Stap 9: Stel transformatie in voor brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Stap 10: Stel paint in en vul de rechthoek

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Stap 11: Sluit de huidige pagina

```csharp
	//Close current page
	document.ClosePage();
```

## Stap 12: Sla het document op (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Hoe een PostScript‑bestand op te slaan

De aanroep `PsDocument.Save()` schrijft de volledig gevormde PostScript‑inhoud naar de stream die je in **Stap 1** hebt geopend. Nadat het `using`‑blok is voltooid, is het bestand `DiagonaGradient_outPS.ps` beschikbaar in de map die je hebt opgegeven.

## Veelvoorkomende gebruikssituaties

- **Technical documentation** die een subtiele achtergrondschaduw nodig heeft.  
- **Marketing brochures** waarbij een diagonale gradient een moderne uitstraling geeft.  
- **Automated report generators** die direct afdrukbare PS‑bestanden genereren.  

## Probleemoplossing & Tips

- **Incorrect colors** – controleer de ARGB‑waarden die aan `LinearGradientBrush` worden doorgegeven.  
- **Gradient not visible** – zorg ervoor dat de transformatie‑matrix correct roteert en schaalt; de aanroep `Rotate(-45)` zet de diagonale hoek.  
- **File not created** – controleer of `dataDir` naar een bestaande map wijst en of de applicatie schrijfrechten heeft.  

## Veelgestelde vragen

**Q: Is Aspose.Page compatible with all .NET frameworks?**  
A: Aspose.Page ondersteunt een breed scala aan .NET‑versies, van .NET Framework 4.5+ tot .NET 6+, waardoor brede compatibiliteit wordt gegarandeerd.

**Q: Can I customize the gradient colors in Aspose.Page?**  
A: Ja, je kunt bij het construeren van `LinearGradientBrush` elke ARGB‑kleur opgeven, waardoor je volledige controle hebt over de begin‑ en eindtinten.

**Q: Is there a trial version available for Aspose.Page?**  
A: Ja, je kunt de functies van Aspose.Page verkennen door de proefversie te downloaden [hier](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page?**  
A: Verkrijg een tijdelijke licentie voor Aspose.Page [hier](https://purchase.aspose.com/temporary-license/) om extra mogelijkheden te ontgrendelen tijdens evaluatie.

**Q: Where can I find community support for Aspose.Page?**  
A: Neem contact op met de Aspose.Page‑community op het [forum](https://forum.aspose.com/c/page/39) voor hulp en discussies.

---

**Laatst bijgewerkt:** 2026-02-23  
**Getest met:** Aspose.Page for .NET (latest stable release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
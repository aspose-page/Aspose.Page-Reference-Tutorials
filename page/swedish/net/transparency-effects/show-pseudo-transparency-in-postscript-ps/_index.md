---
date: 2026-03-29
description: Lär dig hur du använder en linjär gradientpensel i C# för att skapa pseudo‑transparens
  i PostScript med Aspose.Page för .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Linjär gradientpensel C# för pseudo‑transparens i PS
url: /sv/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linjär gradientpensel C# för pseudo‑transparens i PostScript (PS)

## Introduktion

Om du behöver lägga till en subtil genomskinlig effekt i dina PostScript (PS)-filer, är **linear gradient brush C#** det perfekta verktyget. Aspose.Page for .NET gör det enkelt att måla rektanglar med både ogenomskinliga och genomskinliga gradientfyllningar, vilket ger dina dokument ett modernt, lagerat utseende. I den här handledningen går vi igenom de exakta stegen som krävs för att skapa pseudo‑transparens med en linjär gradientpensel i C#.

## Snabba svar
- **Vilket bibliotek tillhandahåller den linjära gradientpenseln?** Aspose.Page for .NET
- **Vilken grafikklass skapar gradienten?** `LinearGradientBrush`
- **Kan jag kontrollera opacitet per färg?** Ja, med `Color.FromArgb(alpha, …)`
- **Behöver jag en licens för produktion?** En giltig Aspose.Page‑licens krävs
- **Stödda .NET-versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Vad är en linjär gradientpensel C#?

En `LinearGradientBrush` är ett GDI+-objekt som målar en mjuk övergång mellan två färger längs en rak linje. När du anger alfakanalen (0‑255) för varje färg kan du skapa genomskinliga gradienter – exakt vad vi behöver för pseudo‑transparens i PostScript.

## Varför använda en linjär gradientpensel C# för pseudo‑transparens?

- **Finjusterad opacitetskontroll:** Justera varje färgs alfa för att uppnå önskad genomskinlighetsnivå.  
- **Enhetsoberoende rendering:** Penseln fungerar likadant på skärm, PDF, EPS och PS‑utdata.  
- **Enkelt API:** Några rader C#‑kod ger visuella effekter av professionell kvalitet.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

- Aspose.Page for .NET installerat. Du kan ladda ner det från [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- En skrivbar mapp där det genererade PostScript‑dokumentet kommer att sparas.

Nu när du har verktygen, låt oss börja bygga de pseudo‑transparenta rektanglarna.

## Importera namnrymder

Innan vi börjar, importera namnrymderna som innehåller de klasser vi ska använda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg 1: Skapa utdataflödet för PostScript‑dokumentet

Vi börjar med att skapa ett fil‑ström som kommer att hålla den resulterande PS‑filen, och initierar sedan `PsDocument`.

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

## Steg 2: Skapa en rektangel med en **ogenomskinlig** gradientfyllning

Här bygger vi en `LinearGradientBrush` vars färger är helt ogenomskinliga (alpha = 255). Denna rektangel fungerar som bakgrundslager.

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

## Steg 3: Skapa en rektangel med en **genomskinlig** gradientfyllning

Nu använder vi en **linear gradient brush C#** där alfavärdena är mindre än 255 (t.ex. 150 och 50). Detta gör rektangeln delvis genomskinlig och skapar pseudo‑transparenseffekten.

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

## Steg 4: Stäng sidan och spara dokumentet

Till sist avslutar vi sidan och skriver PS‑filen till disk.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Genom att följa dessa fyra steg kan du sömlöst blanda ogenomskinliga och genomskinliga rektanglar och skapa en övertygande pseudo‑transparent effekt i vilken PostScript‑utdata som helst.

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Färger visas helt ogenomskinliga | Alfavärdet sattes till 255 av misstag | Använd `Color.FromArgb(alpha, …)` med `alpha` < 255 |
| Gradienten sträcks felaktigt | Felaktig transformationsmatris | Verifiera att matrisparametrarna matchar rektangelns dimensioner |
| Utdatafilen är tom | Strömmen är inte stängd eller `Save()` har inte anropats | Säkerställ att `document.ClosePage()` och `document.Save()` körs inom `using`‑blocket |

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla versioner av .NET?**  
A: Aspose.Page for .NET är kompatibel med olika versioner av .NET‑ramverket, vilket säkerställer flexibilitet och enkel integration.

**Q: Kan jag applicera pseudo‑transparens på andra former än rektanglar?**  
A: Ja, samma principer kan tillämpas på vilken form som helst genom att justera `GraphicsPath` därefter.

**Q: Var kan jag hitta ytterligare exempel och dokumentation?**  
A: Utforska [Aspose.Page documentation](https://reference.aspose.com/page/net/) för omfattande exempel och detaljerade API‑referenser.

**Q: Finns det en gratis provversion av Aspose.Page?**  
A: Ja, du kan få en gratis provversion av Aspose.Page via [denna länk](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Page?**  
A: Besök [denna länk](https://purchase.aspose.com/temporary-license/) för att skaffa en tillfällig licens för Aspose.Page.

---

**Senast uppdaterad:** 2026-03-29  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
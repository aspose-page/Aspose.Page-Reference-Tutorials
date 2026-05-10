---
date: 2026-02-23
description: Lär dig hur du lägger till en gradient i PostScript‑filer, sparar en
  PostScript‑fil med A4‑sidstorlek och fyller en rektangel med gradient med Aspose.Page
  för .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Hur man lägger till gradient – Diagonal gradient i PostScript (PS) med Aspose.Page
  .NET
url: /sv/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

 keep all placeholders unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till gradient: Diagonal gradient till PostScript (PS) med Aspose.Page .NET

## Introduktion

Att lägga till en diagonal gradient i ett PostScript (PS)-dokument kan dramatiskt förbättra den visuella attraktionskraften, särskilt när du behöver **how to add gradient**-effekter i tekniska rapporter, broschyrer eller grafikintensiva applikationer. I den här handledningen kommer du att se exakt hur du lägger till en gradient i en PostScript-fil, ställer in en A4-sidstorlek och fyller en rektangel med en mjuk färgövergång med hjälp av Aspose.Page för .NET.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for .NET  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Kan jag ändra gradientens riktning?** Ja – rotera penselns transform som visas i koden  
- **Hur sparar jag resultatet?** Använd `PsDocument.Save()` som skriver en PostScript-fil till disk  
- **Behövs en licens för produktion?** Ja, en kommersiell licens låser upp full funktionalitet  

## Vad är en diagonal gradient i PostScript?

En diagonal gradient är en linjär färgövergång som löper i en vinkel (vanligtvis 45°) över en form. I PostScript uppnås detta genom att applicera en `LinearGradientBrush` med en anpassad transformationsmatris som roterar, skalar och translaterar gradienten för att matcha den önskade rektangeln.

## Varför använda Aspose.Page för gradientfyllningar?

Aspose.Page abstraherar de lågnivå PostScript-kommandona, så att du kan arbeta med välbekanta .NET-grafikobjekt. Du kan skapa komplexa fyllningar, ställa in siddimensioner och exportera direkt till en **save PostScript file** utan att behöva hantera rå PS-syntax.

## Förutsättningar

- **Aspose.Page for .NET Library** – ladda ner den [här](https://releases.aspose.com/page/net/).  
- **Document Directory** – en mapp där den genererade `*.ps`-filen kommer att skrivas.

Nu när vi har grunderna täckta, låt oss gå igenom implementeringen steg för steg.

## Importera namnrymder

Först, importera namnrymderna som ger dig åtkomst till EPS-enheten, ritverktyg och I/O-klasser.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg 1: Skapa utmatningsström för PostScript-dokument (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Steg 2: Ställ in A4-sidstorlek (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Steg 3: Skapa ett nytt 1‑sidigt PS-dokument

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Steg 4: Definiera rektangelparametrar

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Steg 5: Skapa grafikväg

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Steg 6: Skapa Linear Gradient Brush (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Steg 7: Skapa transform för pensel

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Steg 8: Applicera transformationer på penseln (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Steg 9: Ställ in transform på penseln

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Steg 10: Ställ in färg och fyll rektangeln

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Steg 11: Stäng den aktuella sidan

```csharp
	//Close current page
	document.ClosePage();
```

## Steg 12: Spara dokumentet (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Hur man sparar PostScript-fil

`PsDocument.Save()`-anropet skriver det fullständiga PostScript-innehållet till strömmen du öppnade i **Steg 1**. Efter att `using`-blocket har avslutats kommer filen `DiagonaGradient_outPS.ps` att finnas i den katalog du angav.

## Vanliga användningsområden

- **Teknisk dokumentation** som behöver en subtil bakgrundsskuggning.  
- **Marknadsföringsbroschyrer** där en diagonal gradient ger ett modernt utseende.  
- **Automatiska rapportgeneratorer** som skapar utskrivbara PS-filer i realtid.  

## Felsökning & Tips

- **Felaktiga färger** – dubbelkolla ARGB-värdena som skickas till `LinearGradientBrush`.  
- **Gradienten syns inte** – säkerställ att transformationsmatrisen roterar och skalar korrekt; `Rotate(-45)`-anropet sätter den diagonala vinkeln.  
- **Filen skapades inte** – verifiera att `dataDir` pekar på en befintlig mapp och att applikationen har skrivbehörighet.  

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla .NET-ramverk?**  
A: Aspose.Page stödjer ett brett spektrum av .NET-versioner, från .NET Framework 4.5+ till .NET 6+, vilket säkerställer bred kompatibilitet.

**Q: Kan jag anpassa gradientfärgerna i Aspose.Page?**  
A: Ja, du kan ange valfria ARGB-färger när du konstruerar `LinearGradientBrush`, vilket ger dig full kontroll över start- och slutnyanser.

**Q: Finns det en provversion tillgänglig för Aspose.Page?**  
A: Ja, du kan utforska Aspose.Page:s funktioner genom att ladda ner provversionen [här](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Page?**  
A: Skaffa en tillfällig licens för Aspose.Page [här](https://purchase.aspose.com/temporary-license/) för att låsa upp ytterligare funktioner under utvärderingen.

**Q: Var kan jag hitta community-support för Aspose.Page?**  
A: Engagera dig med Aspose.Page-communityn på [forumet](https://forum.aspose.com/c/page/39) för hjälp och diskussioner.

---

**Senast uppdaterad:** 2026-02-23  
**Testad med:** Aspose.Page for .NET (senaste stabila versionen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
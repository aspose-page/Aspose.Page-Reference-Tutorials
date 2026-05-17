---
date: 2026-02-25
description: Förbättra PostScript‑dokument med en linjär gradientrektangel med Aspose.Page
  för .NET. Följ vår steg‑för‑steg‑guide för att lära dig gradientfyllning av text
  och konturgradient för text.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Lägg till en rektangel med linjär gradient i PostScript (PS) med Aspose.Page
url: /sv/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till en linjär gradientrektangel i PostScript (PS) med Aspose.Page

## Introduction

Välkommen till den här omfattande handledningen om att lägga till en **linjär gradientrektangel** i PostScript (PS)-dokument med Aspose.Page för .NET. Aspose.Page är ett kraftfullt bibliotek som låter dig skapa, modifiera och rendera dokument i en mängd olika format, och idag fokuserar vi på hur du kan införa iögonfallande gradienter i dina PS‑filer.

### Quick Answers
- **Vad gör den linjära gradientrektangeln?** Den fyller ett rektangulärt område med en mjuk färgövergång från ena sidan till den andra.  
- **Vilket API hanterar gradientfylld text?** `LinearGradientBrush` kombinerat med `SetPaint` och `FillAndStrokeText`.  
- **Kan jag konturera text med en gradient?** Ja — använd `SetStroke` med en gradientpensel och anropa `OutlineText`.  
- **Behöver jag en licens för produktion?** En kommersiell Aspose.Page‑licens krävs för icke‑utvärderingsbruk.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prerequisites

Innan vi dyker ner, se till att du har:

- Aspose.Page for .NET Library: Säkerställ att biblioteket är refererat i ditt projekt. Du kan ladda ner det från [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Document Directory: Skapa en mapp på disken där den genererade PS‑filen ska sparas och ersätt **“Your Document Directory”** i koden med den sökvägen.

## Import Namespaces

För att börja, importera namnrymderna som ger dig åtkomst till rit‑ och PS‑specifika klasser:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## What Is a Linear Gradient Rectangle?

En **linjär gradientrektangel** är helt enkelt en rektangulär form vars insida är målade med en linjär gradient — färgerna övergår mjukt längs en rak linje, vanligtvis från vänster till höger (horisontell) eller från topp till botten (vertikal). I Aspose.Page uppnår du detta genom att kombinera ett `GraphicsPath` som definierar rektangeln med en `LinearGradientBrush` som beskriver färgövergången.

## Why Use Gradient Fill Text and Outline Text Gradient?

- **Visuell attraktionskraft:** Gradientfylld text ger djup och modern stil till rapporter, fakturor eller marknadsföringsmaterial.  
- **Varumärkeskonsekvens:** Matcha företagsfärger med exakta ARGB‑värden.  
- **Mångsidighet:** Samma pensel kan återanvändas för formfyllningar, textfyllningar och konturgradienter, vilket minskar kodduplicering.

## Step 1: Set Up the Document

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

## Step 2: Define Gradient Rectangle and Colors

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

## Step 3: Set Transform for Brush

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Step 4: Set Paint and Fill the Rectangle

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## How to Apply Gradient Fill Text

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Using Outline Text Gradient

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Step 7: Close the Current Page and Save the Document

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Grattis! Du har framgångsrikt lagt till en **linjär gradientrektangel** i ett PostScript‑dokument och använt samma pensel för **gradientfylld text** och en **konturtextgradient**.

## Common Use Cases & Tips

- **Rapportrubriker:** Fyll stora textblock med gradienter för att framhäva avsnittsrubriker.  
- **Varumärkeslogotyper:** Återskapa logotypformer med gradientfyllda former för enhetlig branding.  
- **Proffstips:** Återanvänd samma `LinearGradientBrush`‑instans för flera rit‑anrop för att hålla färgerna perfekt synkroniserade över former och text.

## Frequently Asked Questions

### Q1: Kan jag applicera gradienter på andra former än rektanglar?
**A:** Ja, du kan applicera gradienter på vilken form som helst som definieras av ett `GraphicsPath`. Lägg bara till cirklar, polygoner eller anpassade vägar innan du anropar `document.Fill(path)`.

### Q2: Hur kan jag ändra gradientfärgerna?
**A:** Ändra `Color.FromArgb`‑värdena när du konstruerar `LinearGradientBrush`. Den första färgen är startfärgen, den andra är slutfärgen på gradienten.

### Q3: Är Aspose.Page kompatibel med olika dokumentformat?
**A:** Absolut. Aspose.Page stödjer XPS, PS, PDF och flera andra vektorformat. Kontrollera den officiella dokumentationen för den fullständiga listan.

### Q4: Kan jag använda Aspose.Page i kommersiella projekt?
**A:** Ja, kommersiell licensiering finns tillgänglig. Se inköpssidan för detaljer: [here](https://purchase.aspose.com/buy).

### Q5: Var kan jag hitta community‑support?
**A:** Gå med i Aspose.Page‑community‑forumet: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
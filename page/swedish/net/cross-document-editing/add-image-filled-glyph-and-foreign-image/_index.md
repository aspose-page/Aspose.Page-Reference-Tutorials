---
date: 2026-01-07
description: Lär dig hur du skapar XPS‑dokument i .NET med Aspose.Page. Denna guide
  visar hur du lägger till bildfyllda glyfer och främmande bilder för rikare dokumentvisualisering.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument i .NET med Aspose.Page – Bildfylld glyf och främmande bild
url: /sv/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS document .NET med Aspose.Page – Bildfyllda glyfer & främmande bild

## Introduktion

If you need to **create XPS document .NET** applications that look polished and professional, Aspose.Page gives you the tools to embed images directly into glyphs and reuse graphic resources across documents. In this tutorial we’ll walk through building two XPS files, filling glyphs with an image brush, and then reusing that brush in a second document. By the end you’ll understand why this approach saves memory, simplifies styling, and opens up creative possibilities for reports, invoices, or any printable content.

## Snabba svar
- **Vad täcker den här handledningen?** Adding image‑filled glyphs and reusing them across XPS documents with Aspose.Page for .NET.  
- **Vilket primärt nyckelord är inriktat?** `create xps document .net`.  
- **Förutsättningar?** .NET development environment, Aspose.Page for .NET, and a folder for your XPS files.  
- **Hur lång tid tar implementeringen?** About 10‑15 minutes for a working prototype.  
- **Kan jag använda andra bildformat?** Yes – any format supported by .NET’s `System.Drawing.Image`.

## Förutsättningar

Before diving into the code, ensure you have the following ready:

- **Aspose.Page for .NET** – download the latest library from [here](https://releases.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio 2022 (or any IDE that supports .NET 6+).  
- **Dokumentkatalog** – create a folder on your machine that will hold the input images and the generated XPS files; we’ll refer to it as **Your Document Directory** in the snippets.

## Importera namnrymder

Start by pulling in the namespaces required to work with XPS objects and drawing utilities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg‑för‑steg guide

### Steg 1: Skapa det första XPS-dokumentet

We begin by instantiating an empty XPS document that will host the image‑filled glyph.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Steg 2: Lägg till glyfer i det första dokumentet

Next, add a glyph (a text character) that we’ll later fill with an image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Steg 3: Fyll glyfer med en bildpensel

Here we create an `ImageBrush` from a TIFF file located in our data directory and apply it to the glyph. The brush is set to tile mode so the image repeats if the glyph area exceeds the image size.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Steg 4: Skapa det andra XPS-dokumentet

Now we spin up a second XPS document that will reuse the glyph style and image brush from the first one.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Steg 5: Lägg till glyfer med teckensnittet från det första dokumentet

We add a glyph to the second document, re‑using the exact font object from the first document. This ensures visual consistency across both files.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Steg 6: Skapa en bildpensel från fyllningen i det första dokumentet

Instead of loading the image again, we clone the brush from `glyphs1` and assign it to `glyphs2`. This demonstrates how you can **create XPS document .NET** workflows that share resources efficiently.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Steg 7: Spara dokumenten

Finally, persist both XPS files to the disk. You can now open them with any XPS viewer to see the image‑filled glyph effect.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Varför använda bildfyllda glyfer när du skapar XPS document .NET?

- **Visuell påverkan** – Transform plain text into graphic‑rich elements without rasterizing the whole page.  
- **Återanvändning av resurser** – Share brushes and fonts across multiple documents, reducing memory footprint.  
- **Flexibilitet** – Tile, stretch, or rotate the image brush to achieve custom patterns or branding.

## Vanliga problem & tips

- **Fel i filsökväg** – Ensure `dataDir` ends with a path separator (`\` or `/`) appropriate for your OS.  
- **Ej stödda bildformat** – Aspose.Page works best with TIFF, PNG, and JPEG. Convert other formats before use.  
- **TileMode tillämpas inte** – Verify you cast to `XpsImageBrush` before setting `TileMode`; otherwise the property is ignored.

## Vanliga frågor

### Q1: Kan jag använda olika bildformat för att fylla glyfer?

**A:** Yes, Aspose.Page supports TIFF, PNG, JPEG, BMP, and GIF. Just provide the correct file extension in the `CreateImageBrush` call.

### Q2: Hur kan jag anpassa glyfernas utseende ytterligare?

**A:** Explore additional properties on `XpsGlyphs` such as `Opacity`, `RenderTransform`, and `Stroke` to fine‑tune rendering.

### Q3: Är Aspose.Page lämplig för att hantera stora dokumentuppsättningar?

**A:** Absolutely. The library is optimized for high‑performance scenarios and can process thousands of XPS files in batch jobs.

### Q4: Kan jag applicera olika stilar på enskilda glyfer?

**A:** Yes. Each `XpsGlyphs` instance can have its own fill, stroke, and transformation, giving you granular control.

### Q5: Vilka är fördelarna med att använda Aspose.Page jämfört med andra dokumentbehandlingsverktyg?

**A:** Aspose.Page offers a complete, license‑free API for XPS creation, manipulation, and conversion, with extensive documentation and 24/7 support.

---

**Senast uppdaterad:** 2026-01-07  
**Testat med:** Aspose.Page 24.12 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
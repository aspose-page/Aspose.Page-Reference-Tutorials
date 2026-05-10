---
date: 2026-02-23
description: Tanulja meg, hogyan hozhat létre átlós színátmenetes XPS dokumentumokat
  az Aspose.Page for .NET használatával, és emelje fel vizuális prezentációit könnyedén.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Átlós színátmenet XPS létrehozása az Aspose.Page .NET-hez
url: /hu/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

Also ensure we keep markdown formatting.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hozzon létre átlós színátmenetes XPS-t az Aspose.Page for .NET segítségével

## Introduction

Ha **átlós színátmenetes XPS** fájlokat szeretne létrehozni, amelyek felkeltik a figyelmet, az Aspose.Page for .NET egyszerű megoldást kínál. Ebben az útmutatóban lépésről lépésre megtanulja, hogyan adjon átlós színátmenetet egy XPS dokumentumhoz az Aspose.Page API használatával. A végére egy újrahasználható mintát kap, amelyet bármilyen alakra vagy színsémára testre szabhat.

## Quick Answers
- **Mi a API metódus feladata?** Létrehoz egy lineáris színátmenet ecsetet, amely átlósan lefedi az útvonalat.  
- **Melyik osztály képviseli az XPS dokumentumot?** `XpsDocument`.  
- **Szükségem van licencre a minta futtatásához?** A fejlesztéshez egy ingyenes próbaverzió is működik; a termeléshez licenc szükséges.  
- **Meg tudom változtatni a színátmenet irányát?** Igen—állítsa be a kezdő és befejező `PointF` értékeket.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is **create diagonal gradient xps**?
Az átlós színátmenet egy sima színátmenet, amely egy alakzat egyik sarkától a szemközti sarokig fut. XPS-ben ezt a hatást egy `LinearGradientBrush` alkalmazásával érjük el az útvonal kitöltési tulajdonságán. Az Aspose.Page könyvtár elrejti az alacsony szintű XPS jelölést, így a színekre és a geometriára koncentrálhat.

## Why use Aspose.Page for diagonal gradients?
- **Nagy pontosságú renderelés** – a kimenet pontosan megfelel az XPS specifikációnak.  
- **Teljes .NET integráció** – működik C#, VB.NET és bármely .NET nyelvvel.  
- **Nincs külső függőség** – minden a folyamaton belül kezelődik, nincs szükség COM-ra vagy Office-ra.  
- **Skálázható összetett dokumentumokhoz** – több színátmenetet, képet és szöveget kombinálhat ugyanazon az oldalon.

## Prerequisites

1. **Aspose.Page for .NET könyvtár** – töltse le [here](https://releases.aspose.com/page/net/).  
2. **Fejlesztői környezet** – Visual Studio, Rider vagy bármely editor, amely támogatja a .NET projekteket.  

Now, let’s dive into the code.

## Import Namespaces

In your .NET project, include the necessary namespaces from the Aspose.Page library to access the required classes and methods. Add the following namespaces at the beginning of your code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set the Document Directory

Begin by specifying the path to your document directory. This is where the resultant XPS document with the diagonal gradient will be saved.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Initialize a new `XpsDocument` using the Aspose.Page library.

```csharp
XpsDocument doc = new XpsDocument();
```

## Step 3: Define Gradient Colors

Create a list of `XpsGradientStop` objects, each representing a color in the diagonal gradient.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Step 4: Add a Diagonal Gradient to a Path

Create a new path with a defined geometry, and apply the diagonal gradient to it. Adjust the rendering transform and fill properties as needed.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Step 5: Save the Resultant XPS Document

Finally, save the modified XPS document to the specified directory.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

You’ve now successfully **created a diagonal gradient XPS** file. Feel free to experiment with different color stops, geometry strings, or transform matrices to produce a variety of visual effects.

## Common Issues and Solutions
- **Gradient not visible** – Verify that the path geometry is closed and that the brush’s start/end points are within the path bounds.  
- **Incorrect colors** – Ensure you use `CreateColor` with the correct ARGB values; the method expects values in the 0‑255 range.  
- **File not saved** – Check that `dataDir` points to an existing folder and that the application has write permissions.

## Frequently Asked Questions

**Q: Can I apply multiple gradients to different parts of the document?**  
A: Yes, you can create multiple paths and apply distinct gradients to each.

**Q: Are there predefined gradient styles available?**  
A: Aspose.Page allows custom gradients, giving you full control over color transitions.

**Q: Can I use Aspose.Page for .NET with other document formats?**  
A: Aspose.Page primarily focuses on XPS document manipulation.

**Q: How can I handle errors related to document processing?**  
A: Refer to the [documentation](https://reference.aspose.com/page/net/) for error handling best practices.

**Q: Is there a trial version available before purchasing?**  
A: Yes, you can explore the [free trial](https://releases.aspose.com/) to experience Aspose.Page for .NET.

**Q: How do I change the gradient direction to vertical or horizontal?**  
A: Modify the `PointF` arguments in `CreateLinearGradientBrush` to set new start and end points.

**Q: Does the library support transparency in gradients?**  
A: Yes—include an alpha value when creating colors with `CreateColor`.

## Conclusion

Az Aspose.Page for .NET egyszerűsíti az XPS dokumentumok átlós színátmenetekkel való gazdagítását. Ez az útmutató végigvezette Önt a szükséges előkészítéstől a végső fájl mentéséig. Kísérletezzen különböző alakzatokkal és színpalettákkal, hogy XPS jelentései, brosúrái vagy számlái igazán kitűnjenek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---
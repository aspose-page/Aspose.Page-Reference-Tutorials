---
title: Add Tiled Image to XPS Document with Aspose.Page for .NET
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 12
url: /net/image-management/add-tiled-image-to-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;


namespace CSharp.WorkingWithImages
{
    public class AddTiledImageXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Create new XPS Document
            XpsDocument doc = new XpsDocument();
            // Tile image
            // ImageBrush filled rectangle in the right top bellow
            XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
            path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
            ((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
            path.Fill.Opacity = 0.5f;
            // Save resultant XPS document
            doc.Save(dataDir + "AddTiledImage_outXPS.xps");
            // ExEnd:1
        }
    }
}

```

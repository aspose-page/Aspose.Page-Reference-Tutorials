---
title: Add Image to XPS Document with Aspose.Page for .NET
linktitle: Add Image to XPS Document with Aspose.Page for .NET
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 11
url: /net/image-management/add-image-to-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;


namespace CSharp.WorkingWithImages
{
    public class AddImageXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_WorkingWithImages();
            // Create new XPS Document
            XpsDocument doc = new XpsDocument();
            // Add Image
            XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
            //Creating a matrix is optional, it can be used for proper positioning
            path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
            //Create Image Brush
            path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
            // Save resultant XPS document
            doc.Save(dataDir + "AddImage_outXPS.xps");
            // ExEnd:1
        }
    }
}

```

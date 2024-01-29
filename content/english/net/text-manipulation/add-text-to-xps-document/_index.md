---
title: Add Text to XPS Document with Aspose.Page for .NET
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 13
url: /net/text-manipulation/add-text-to-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;

namespace CSharp.WorkingWithText
{
    public class AddTextXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Create new XPS Document
            XpsDocument doc = new XpsDocument();
            //Create a brush 
            XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
            //Add glyph to the document
            XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
            glyphs.Fill = textFill;
            // Save resultant XPS document
            doc.Save(dataDir + "AddText_out.xps");
            // ExEnd:1
        }
    }
}

```

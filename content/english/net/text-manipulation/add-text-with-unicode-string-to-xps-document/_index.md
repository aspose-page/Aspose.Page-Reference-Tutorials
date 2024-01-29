---
title: Add Text with Unicode String to XPS Document with Aspose.Page
linktitle: Add Text with Unicode String to XPS Document with Aspose.Page
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 12
url: /net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;

namespace CSharp.WorkingWithText
{
    public class AddTextUsingUnicodeStringXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Create new XPS Document
            XpsDocument doc = new XpsDocument();
            // Add Text
            XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
            XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
            glyphs.BidiLevel = 1;
            glyphs.Fill = textFill;
            // Save resultant XPS document
            doc.Save(dataDir + "AddTextRTL_out.xps");
            // ExEnd:1
        }
    }
}

```

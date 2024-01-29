---
title: Create XPS Document with Aspose.Page for .NET
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 10
url: /net/document-creation/create-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;

namespace CSharp.WorkingWithDocument
{
    public class CreateDocumentXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dir = "Your Document Directory";
            // Create new XPS Document
            XpsDocument xDocs = new XpsDocument();

            // add glyph to the document
            var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");

            glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);

            // save result
            xDocs.Save(dir + "output.xps");
            // ExEnd:1
        }
    }
}

```
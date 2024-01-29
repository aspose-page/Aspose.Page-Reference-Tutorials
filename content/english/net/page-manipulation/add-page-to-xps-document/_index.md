---
title: Add Page to XPS Document with Aspose.Page for .NET
linktitle: Add Page to XPS Document with Aspose.Page for .NET
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 11
url: /net/page-manipulation/add-page-to-xps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;

namespace CSharp.WorkingWithPages
{
    public class AddPageXPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_WorkingWithPages();
            // Create new XPS Document
            XpsDocument doc = new XpsDocument(dataDir + "Sample1.xps");

            // Insert an empty page at beginning of pages list
            doc.InsertPage(1, true);
            
            // Save resultant XPS document
            doc.Save(dataDir + "AddPages_out.xps");
            // ExEnd:1
        }
    }
}

```

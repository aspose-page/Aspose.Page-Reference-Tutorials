---
title: Add Page to PostScript (PS) Document with Aspose.Page
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 10
url: /net/page-manipulation/add-page-to-postscript-ps-document/
---

## Complete Source Code
```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;

namespace CSharp.WorkingWithPages
{
    public class AddPage1PS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            
            //Create output stream for PostScript document
            using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
            {
                //Create save options with A4 size
                PsSaveOptions options = new PsSaveOptions();

                // Create new 2-paged PS Document
                PsDocument document = new PsDocument(outPsStream, options, 2);

                //Add the first page
                document.OpenPage();

                //Add content

                //Close the first page
                document.ClosePage();

                //Add the second page with different size
                document.OpenPage(400, 700);

                //Add content

                //Close the second page
                document.ClosePage();

                //Save the document
                document.Save();
            }
            // ExEnd:1
        }
    }
}

```
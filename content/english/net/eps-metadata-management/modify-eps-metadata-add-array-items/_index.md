---
title: Add Array Items with Aspose.Page
linktitle: Add Array Items
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 11
url: /net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

## Complete Source Code
```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace CSharp.WorkingWithXMPMetadataInEPS
{
    public class ChangeMetadata_AddArrayItems
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Initialize EPS file input stream
            System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
            // Create PsDocument instance from stream
            PsDocument document = new PsDocument(psStream);            

            try
            {
                // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
                XmpMetadata xmp = document.GetXmpMetadata();

                //Change XMP metadata values

                // Add one more title. I will be added at the end of array by default.
                xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

                // Add one more creator. It will be added in the array by an index (0).
                xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));

                // Save EPS file with changed XMP metadata

                // Create ouput stream
                using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
                {
                    // Save EPS file
                    document.Save(outPsStream);
                }

            }
            finally
            {
                psStream.Close();
            }

            // ExEnd:1
        }
    }
}

```
---
title: Change Values with Aspose.Page for .NET
linktitle: Change Values with Aspose.Page for .NET
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 17
url: /net/eps-metadata-management/modify-eps-metadata-change-values/
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
    public class ChangeMetadata_ChangeValues
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Initialize EPS file input stream
            System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
            // Create PsDocument instance from stream
            PsDocument document = new PsDocument(psStream);            

            try
            {
                // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
                XmpMetadata xmp = document.GetXmpMetadata();

                //Change XMP metadata values


                // Change ModifyDate value
                DateTime now = DateTime.UtcNow;
                xmp["xmp:ModifyDate"] = now;

                // Change Creator value
                XmpValue value = new XmpValue("Aspose.Page");
                xmp.Add("dc:creator", value);

                // Change Title value
                value = new XmpValue("(PAGEJAVA-29.eps)");
                xmp.Add("dc:title", value);

                // Save EPS file with changed XMP metadata

                // Create ouput stream
                using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
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

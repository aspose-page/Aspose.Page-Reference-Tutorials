---
title: Convert Image to EPS Format with Aspose.Page for .NET
linktitle: Convert Image to EPS Format with Aspose.Page for .NET
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 13
url: /net/image-management/convert-image-to-eps-format/
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

namespace CSharp.WorkingWithImageConversion
{
    public class SaveImageAsEPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";

            // Create default options
            PsSaveOptions options = new PsSaveOptions();

            // Save JPEG image to EPS file
            PsDocument.SaveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);

            // ExEnd:1
        }
    }
}

```

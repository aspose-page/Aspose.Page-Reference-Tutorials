---
title: Load License from Stream Object with Aspose.Page for .NET
linktitle: Load License from Stream Object
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 12
url: /net/getting-started/load-license-from-stream-object/
---

## Complete Source Code
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace CSharp.GettingStarted
{
    public class LoadLicenseFromStreamObject
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";
            // Initialize license object
            Aspose.Page.License license = new Aspose.Page.License();
            // Load license in FileStream
            FileStream myStream = new FileStream("Aspose.Total.NET.lic", FileMode.Open);
            // Set license
            license.SetLicense(myStream);
            Console.WriteLine("License set successfully.");
            // ExEnd:1
        }
    }
}

```

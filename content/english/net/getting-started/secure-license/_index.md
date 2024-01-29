---
title: Secure License with Aspose.Page for .NET
linktitle: Secure License
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 13
url: /net/getting-started/secure-license/
---

## Complete Source Code
```csharp
using Ionic.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace CSharp.GettingStarted
{
    public class SecureLicense
    {
        public static void Run()
        {
            // ExStart:1
            using (Stream zip = new SecureLicense().GetType().Assembly.GetManifestResourceStream("Aspose.Total.NET.lic.zip"))
            {
                using (ZipFile zf = ZipFile.Read(zip))
                {
                    MemoryStream ms = new MemoryStream();
                    ZipEntry e = zf["Aspose.Total.NET.lic"];
                    e.ExtractWithPassword(ms, "test");
                    ms.Position = 0;
                }
            }
            // ExEnd:1
        }
    }
}

```

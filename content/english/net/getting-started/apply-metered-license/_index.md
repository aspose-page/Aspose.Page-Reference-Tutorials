---
title: Apply Metered License with Aspose.Page for .NET
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
description: Explore the seamless integration of Aspose.Page for .NET with this step-by-step guide on applying a metered license. Optimize document processing effortlessly.
type: docs
weight: 10
url: /net/getting-started/apply-metered-license/
---
## Introduction

Unlock the full potential of Aspose.Page for .NET by applying a metered license. This tutorial will guide you through the process of setting up and applying the metered license, ensuring smooth and optimized usage of this powerful .NET library.

## Prerequisites

Before diving into the steps, make sure you have the following prerequisites in place:

- A valid Aspose.Page for .NET license: You can obtain it from [purchase.aspose.com](https://purchase.aspose.com/buy).
- Aspose.Page library installed: Refer to the [documentation](https://reference.aspose.com/page/net/) for installation instructions.
- .NET development environment: Ensure that you have a working .NET environment set up on your machine.

## Import Namespaces

In your .NET project, import the necessary namespaces to access Aspose.Page functionalities:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Step 1: Set Metered Public and Private Keys

Initialize the `Aspose.Page.Metered` class and set the metered public and private keys. Replace `<type public key here>` and `<type private key here>` with your actual keys.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Step 2: Load EPS File and Create Document

Specify the path to your EPS file and create a stream to read its content. Then, create an instance of the `PsDocument` class from the stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Step 3: Convert EPS to PNG Image

Create an `ImageDevice` for converting the EPS file to a PNG image. Save the EPS file as an image using the `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Step 4: Retrieve Image Bytes

Get the image bytes, where each byte array represents one page. In this case, we have one page.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Step 5: Save Image Bytes to File

Save the image bytes to a file, ensuring successful conversion from EPS to PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Step 6: Verify Metered License

Check visually if the metered license is applied successfully. If the resulting image doesn't contain the red evaluation message, it indicates that the metered license is applied without any issues.

Now you're ready to leverage the full capabilities of Aspose.Page for .NET with a metered license!

## Conclusion

This step-by-step guide has equipped you with the knowledge to seamlessly apply a metered license using Aspose.Page for .NET. Enhance your document processing capabilities and explore the vast features offered by this powerful library.

## FAQ's

### Q1: How do I obtain a metered license for Aspose.Page for .NET?

A1: Visit [purchase.aspose.com](https://purchase.aspose.com/buy) to acquire a valid license.

### Q2: Where can I find the documentation for Aspose.Page for .NET?

A2: Refer to [Aspose.Page .NET](https://reference.aspose.com/page/net/) for comprehensive documentation.

### Q3: Is there a forum for Aspose.Page discussions and support?

A3: Yes, visit [forum](https://forum.aspose.com/c/page/39) to engage with the community and seek assistance.

### Q4: Can I try Aspose.Page for .NET before purchasing?

A4: Absolutely! Access the free trial at [here](https://releases.aspose.com/).

### Q5: How can I obtain a temporary license for Aspose.Page for .NET?

A5: Visit [temporary license/](https://purchase.aspose.com/temporary-license/) to obtain a temporary license.

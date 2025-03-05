---
title: Change Values with Aspose.Page for .NET
linktitle: Change Values
second_title: Aspose.Page .NET API
description: Master EPS file manipulation with Aspose.Page for .NET. Change XMP metadata values effortlessly.
type: docs
weight: 17
url: /net/eps-metadata-management/modify-eps-metadata-change-values/
---
## Introduction

In the dynamic world of document processing, Aspose.Page for .NET stands out as a powerful tool, offering developers the capability to manipulate EPS files effortlessly. In this tutorial, we will delve into the process of changing values within EPS files using Aspose.Page for .NET. Whether you are a seasoned developer or a curious beginner, this step-by-step guide will equip you with the skills needed to efficiently modify XMP metadata in your EPS files.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

### 1. Aspose.Page for .NET Library

Ensure that you have the Aspose.Page for .NET library installed in your development environment. If not, you can download it [here](https://releases.aspose.com/page/net/).

### 2. Document Directory

Set up a directory for your documents. This will be the location where your EPS files are stored.

Now that we have our prerequisites sorted, let's move on to the next crucial steps.

## Import Namespaces

In any .NET project, it's essential to import the necessary namespaces to utilize the functionalities of Aspose.Page. Here's how you can do it:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Step 1: Initialize EPS file input stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Step 2: Create PsDocument instance from stream

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

Now that we have set the stage, let's proceed to the core of our tutorial - changing XMP metadata values within the EPS file.

## Step 3: Get XMP metadata

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 4: Modify XMP metadata values

Now, let's change some key values in the XMP metadata:

### Step 4.1: Change ModifyDate value

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Step 4.2: Change Creator value

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Step 4.3: Change Title value

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

With these changes made, let's move on to the final step - saving the modified EPS file.

## Step 5: Save EPS file with changed XMP metadata

### Step 5.1: Create output stream

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Step 5.2: Save EPS file

```csharp
// Save EPS file
document.Save(outPsStream);
```

Finally, close the input stream:

```csharp
finally
{
    psStream.Close();
}
```

Congratulations! You've successfully modified XMP metadata values in an EPS file using Aspose.Page for .NET.

## Conclusion

In this tutorial, we explored the seamless process of changing values within EPS files using Aspose.Page for .NET. As a developer, you now have a powerful tool at your disposal for efficient document manipulation.

## FAQ's

### Q1: Can I use Aspose.Page for .NET with other file formats?

A1: Aspose.Page primarily focuses on EPS file manipulation. For other formats, explore Aspose's diverse range of products.

### Q2: Is there a trial version available?

A2: Yes, you can try out Aspose.Page for .NET with the free trial available [here](https://releases.aspose.com/).

### Q3: Where can I find detailed documentation?

A3: The comprehensive documentation can be found [here](https://reference.aspose.com/page/net/).

### Q4: How do I obtain a temporary license?

A4: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: Can I purchase Aspose.Page for .NET?

A5: Absolutely! Visit the purchase page [here](https://purchase.aspose.com/buy) for licensing options.

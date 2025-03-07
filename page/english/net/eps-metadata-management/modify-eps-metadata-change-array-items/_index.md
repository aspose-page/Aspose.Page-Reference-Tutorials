---
title: Change Array Items with Aspose.Page for .NET
linktitle: Change Array Items
second_title: Aspose.Page .NET API
description: Learn how to change array items in EPS files using Aspose.Page for .NET. Follow our step-by-step guide for efficient metadata manipulation.
weight: 15
url: /net/eps-metadata-management/modify-eps-metadata-change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Change Array Items with Aspose.Page for .NET

## Introduction

Welcome to this comprehensive guide on changing array items using Aspose.Page for .NET! Aspose.Page is a powerful library that allows developers to work with various document formats, including EPS files. In this tutorial, we'll focus on manipulating XMP metadata within EPS files, specifically changing array items.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites:

1. Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed. You can download it from [here](https://releases.aspose.com/page/net/).

2. Development Environment: Set up your preferred development environment, whether it's Visual Studio or any other IDE that supports .NET development.

## Import Namespaces

In your .NET application, you need to import the necessary namespaces to access the Aspose.Page functionality. Add the following namespaces at the beginning of your code:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Let's break down the example provided into multiple steps:

## Step 1: Initialize EPS file input stream

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

In this step, we initialize the EPS file input stream and create a `PsDocument` instance from it.

## Step 2: Get XMP metadata

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Retrieve the XMP metadata from the EPS file. If the file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.

## Step 3: Change XMP metadata values

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

Here, we change the title and creator items at index 0 within the XMP metadata.

## Step 4: Save EPS file with changed XMP metadata

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Create an output stream and save the EPS file with the modified XMP metadata.

## Conclusion

Congratulations! You've successfully learned how to change array items in EPS files using Aspose.Page for .NET. This can be a crucial step in customizing and managing metadata within your documents.

## FAQ's

### Q1: Can I use Aspose.Page for .NET with other document formats?

A1: Aspose.Page primarily deals with EPS files, but Aspose provides different libraries for working with various document formats.

### Q2: Where can I find additional documentation?

A2: Refer to the documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

### Q3: Is there a free trial available?

A3: Yes, you can get a free trial version from [here](https://releases.aspose.com/).

### Q4: How can I get a temporary license?

A4: Obtain a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I get support or connect with the community?

A5: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community support and discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Add Array Items with Aspose.Page
linktitle: Add Array Items
second_title: Aspose.Page .NET API
description: Explore how to add array items in EPS files using Aspose.Page for .NET. Follow our step-by-step guide for seamless document manipulation.
weight: 11
url: /net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Array Items with Aspose.Page

## Introduction

In the realm of document manipulation and processing in .NET, Aspose.Page stands out as a powerful tool. Among its many capabilities, handling array items within an EPS file is a common requirement. In this tutorial, we'll explore the step-by-step process of adding array items using Aspose.Page in a .NET environment. Whether you're a seasoned developer or a newcomer, this guide will walk you through the process with clarity and precision.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites in place:

- A basic understanding of .NET programming.
- Aspose.Page for .NET installed. If not, you can download it from [here](https://releases.aspose.com/page/net/).
- A code editor, such as Visual Studio, to follow along with the examples.

## Import Namespaces

In your .NET project, make sure to import the necessary namespaces to utilize the Aspose.Page functionalities. Add the following lines at the beginning of your code:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

These namespaces provide access to the essential classes and methods required for EPS file manipulation.

## Step 1: Initialize EPS file input stream

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

Here, we're setting up the initial input stream for the EPS file and creating a `PsDocument` instance.

## Step 2: Get XMP metadata

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

Retrieve the XMP metadata from the EPS file. If the EPS file lacks XMP metadata, a new one is created with values from PS metadata comments.

## Step 3: Change XMP metadata values

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

Modify the XMP metadata by adding new titles and creators to the array.

## Step 4: Save EPS file with changed XMP metadata

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

Finally, save the EPS file with the updated XMP metadata. The changes made to the array items will be reflected in the output file.

## Conclusion

Adding array items with Aspose.Page in .NET is a straightforward process, as demonstrated in this tutorial. With the right prerequisites and a step-by-step guide, developers can seamlessly manipulate EPS files, ensuring their documents meet specific metadata requirements.

## FAQ's

### Q1: Is Aspose.Page compatible with all .NET environments?

A1: Yes, Aspose.Page is designed to work seamlessly with all .NET environments, providing consistent functionality across platforms.

### Q2: Can I use Aspose.Page for free?

A2: Aspose.Page offers a free trial version, allowing users to explore its features. For continued usage, a license must be purchased from [here](https://purchase.aspose.com/buy).

### Q3: Are temporary licenses available for Aspose.Page?

A3: Yes, temporary licenses can be obtained from [here](https://purchase.aspose.com/temporary-license/) for short-term project needs.

### Q4: Where can I find community support for Aspose.Page?

A4: For community discussions and support, visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### Q5: What is the latest version of Aspose.Page for .NET?

A5: To access the latest version of Aspose.Page for .NET, refer to the [documentation](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

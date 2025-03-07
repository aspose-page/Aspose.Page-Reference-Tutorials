---
title: Add Simple Properties with Aspose.Page for .NET
linktitle: Add Simple Properties
second_title: Aspose.Page .NET API
description: Enhance EPS files with Aspose.Page for .NET. Add simple properties effortlessly for customized document metadata.
weight: 14
url: /net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Simple Properties with Aspose.Page for .NET

## Introduction

In the realm of document manipulation and enhancement, Aspose.Page for .NET emerges as a powerful tool, providing developers with the capability to add and modify XMP metadata within EPS files seamlessly. This tutorial will guide you through the process of adding simple properties to an EPS file using Aspose.Page for .NET.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET: Ensure that you have Aspose.Page for .NET installed in your development environment. If not, you can download it [here](https://releases.aspose.com/page/net/).

2. Document Directory: Set up a directory to store your EPS files. Update the `dataDir` variable in the provided code snippet with the path to your document directory.

## Import Namespaces

To begin, import the necessary namespaces to enable communication with Aspose.Page for .NET. Add the following lines at the beginning of your code file:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Step 1: Initialize EPS File Input Stream

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Step 2: Get XMP Metadata

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 3: Change XMP Metadata Values

```csharp
// Change XMP metadata values
DateTime now = DateTime.UtcNow;

// Add Integer property
xmp.Add("xmp:Intg1", new XmpValue(111));

// Add DateTime property
xmp.Add("xmp:Date1", new XmpValue(now));

// Add Double property
xmp.Add("xmp:Double1", new XmpValue(111.11D));

// Add String property
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Step 4: Save EPS File with Changed XMP Metadata

```csharp
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## Step 5: Close FileStream

```csharp
finally
{
    psStream.Close();
}
```

By following these steps, you can effortlessly incorporate simple properties into your EPS files using Aspose.Page for .NET.

## Conclusion

In conclusion, Aspose.Page for .NET proves to be an invaluable asset for developers seeking to enhance EPS files with custom XMP metadata. By adding simple properties, you can customize and enrich your documents to meet specific requirements, opening up a world of possibilities for document manipulation.

## FAQ's

### Q1: Is Aspose.Page for .NET compatible with all EPS files?

A1: Aspose.Page for .NET supports a wide range of EPS files. However, compatibility may vary based on the complexity and structure of individual files.

### Q2: Can I modify existing XMP metadata with Aspose.Page for .NET?

A2: Absolutely! As demonstrated in this tutorial, you can easily change existing XMP metadata values or add new ones to suit your needs.

### Q3: Are there any limitations to the types of properties I can add?

A3: Aspose.Page for .NET supports various data types for properties, including integers, dates, doubles, and strings. You have flexibility in choosing the appropriate type for your metadata.

### Q4: How can I obtain technical support for Aspose.Page for .NET?

A4: For technical assistance, visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) or explore the [documentation](https://reference.aspose.com/page/net/) for comprehensive guidance.

### Q5: Is there a free trial available for Aspose.Page for .NET?

A5: Yes, you can access a free trial [here](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

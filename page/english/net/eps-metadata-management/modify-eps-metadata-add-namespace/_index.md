---
title: Add Namespace with Aspose.Page for .NET
linktitle: Add Namespace
second_title: Aspose.Page .NET API
description: Enhance EPS files with Aspose.Page for .NET. Add namespaces effortlessly, modify XMP metadata, and boost your .NET development workflow.
weight: 13
url: /net/eps-metadata-management/modify-eps-metadata-add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Namespace with Aspose.Page for .NET

## Introduction

In the dynamic world of .NET development, Aspose.Page stands out as a powerful tool for handling EPS files. Aspose.Page for .NET allows developers to seamlessly manipulate XMP metadata, providing the flexibility to add namespaces and enhance the metadata of EPS files.

In this tutorial, we'll delve into the process of adding namespaces using Aspose.Page for .NET. Follow along to discover step-by-step instructions, from importing namespaces to saving your modified EPS file. Let's get started!

## Prerequisites

Before we dive into the tutorial, ensure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: Download and install the library from the [Aspose.Page documentation](https://reference.aspose.com/page/net/).

2. Development Environment: Have a working .NET development environment set up on your machine.

Now, let's jump into the exciting world of Aspose.Page for .NET.

## Import Namespaces

To kick things off, you need to import the necessary namespaces to access the Aspose.Page functionalities. Here's how you can do it:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Step 1: Initialize Your Project

In your .NET project, open your desired file and initialize the Aspose.Page library. Use the following code snippet:

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Open EPS File

Create a FileStream to open the EPS file as shown below:

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Step 3: Get XMP Metadata

Retrieve the XMP metadata from the EPS file using the following code:

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 4: Change XMP Metadata

Modify the existing XMP metadata or add new values as needed. Here's an example of adding a new XML namespace and a string property:

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## Step 5: Save EPS File

Save the EPS file with the updated XMP metadata using the following code:

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## Conclusion

Congratulations! You've successfully added namespaces to an EPS file using Aspose.Page for .NET. This powerful library opens up a world of possibilities for manipulating XMP metadata, providing a seamless experience for developers working with EPS files.

## FAQ's

### Q1: Is Aspose.Page compatible with all versions of .NET?

A1: Aspose.Page for .NET is compatible with various versions of the .NET framework, ensuring flexibility for developers.

### Q2: Can I use Aspose.Page to extract metadata from EPS files?

A2: Absolutely! Aspose.Page allows you to extract and modify XMP metadata from EPS files effortlessly.

### Q3: Where can I find additional support or assistance?

A3: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

### Q4: Is there a free trial available for Aspose.Page?

A4: Yes, you can explore a free trial of Aspose.Page [here](https://releases.aspose.com/).

### Q5: How can I obtain a temporary license for Aspose.Page?

A5: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

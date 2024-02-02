---
title: Change Named Value with Aspose.Page for .NET
linktitle: Change Named Value
second_title: Aspose.Page .NET API
description: Learn how to change named values in EPS files using Aspose.Page for .NET. Customize XMP metadata effortlessly for tailored document processing.
type: docs
weight: 16
url: /net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Introduction

In the world of document processing, Aspose.Page for .NET stands out as a powerful tool for manipulating EPS files. One of the key functionalities it offers is the ability to change named values within XMP metadata. This tutorial will guide you through the process of changing a named value using Aspose.Page for .NET, empowering you to customize your EPS files according to your specific needs.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET: Ensure that you have the Aspose.Page for .NET library installed. If not, you can download it [here](https://releases.aspose.com/page/net/).

- Document Directory: Have a designated directory for your EPS files where you can perform the named value changes.

## Import Namespaces

In your .NET project, you need to import the necessary namespaces to access the functionality provided by Aspose.Page. Add the following namespaces to your code:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Now, let's break down the code into multiple steps for a comprehensive understanding:

## Step 1: Initialize EPS File Input Stream

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

In this step, we set up the input stream for the EPS file that you want to modify. Make sure to replace "Your Document Directory" with the actual path to your document directory.

## Step 2: Get XMP Metadata

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Retrieve the existing XMP metadata from the EPS file. If the EPS file doesn't contain XMP metadata, a new one will be generated with values from PS metadata comments.

## Step 3: Change XMP Metadata Values

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Here, we demonstrate changing two named values within the "xmpTPg:MaxPageSize" structure. You can customize this according to your specific requirements.

## Step 4: Save EPS File with Changed XMP Metadata

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Save the modified EPS file to the output stream. The file will now reflect the changes made to the XMP metadata.

## Conclusion

With this tutorial, you've learned how to leverage Aspose.Page for .NET to change named values within XMP metadata in EPS files. This functionality opens up a world of possibilities for customizing and tailoring your documents to meet specific requirements.

## FAQ's

### Q1: Can I use Aspose.Page for .NET with other document formats?

A1: Yes, Aspose.Page supports various document formats, including EPS, XPS, and PDF.

### Q2: Is there a trial version available for Aspose.Page for .NET?

A2: Yes, you can access a free trial [here](https://releases.aspose.com/).

### Q3: Where can I find more documentation on Aspose.Page for .NET?

A3: Refer to the documentation [here](https://reference.aspose.com/page/net/).

### Q4: How can I obtain a temporary license for Aspose.Page for .NET?

A4: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: What support options are available for Aspose.Page for .NET users?

A5: Visit the community forum [here](https://forum.aspose.com/c/page/39) for support and discussions.

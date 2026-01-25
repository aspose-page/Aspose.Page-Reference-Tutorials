---
title: How to Set XMP and Change Named Value with Aspose.Page for .NET
linktitle: Change Named Value
second_title: Aspose.Page .NET API
description: Learn how to set XMP and change named value in EPS files using Aspose.Page for .NET. Customize XMP metadata effortlessly for tailored document processing.
weight: 16
url: /net/eps-metadata-management/modify-eps-metadata-change-named-value/
date: 2026-01-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set XMP and Change Named Value with Aspose.Page for .NET

## Introduction

If you need to **how to set XMP** information inside an EPS file and also **change named value** entries in its metadata, you’ve come to the right place. In this tutorial we’ll walk through a real‑world scenario where you modify XMP metadata using Aspose.Page for .NET, giving you full control over document properties, branding, and downstream processing.

## Quick Answers
- **What is XMP?** A standardized format for embedding metadata in graphics and document files.  
- **Why change a named value?** To update specific metadata fields such as page size or custom tags without rewriting the whole file.  
- **Which library helps?** Aspose.Page for .NET provides a straightforward API for both tasks.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **Supported platforms?** .NET Framework, .NET Core, and .NET 5/6+.

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

Here, we demonstrate how to **change named value** entries within the `xmpTPg:MaxPageSize` structure. You can adapt the property names and values to suit your own metadata requirements.

## Step 4: Save EPS File with Changed XMP Metadata

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Save the modified EPS file to the output stream. The file will now reflect the changes made to the XMP metadata.

## Common Issues and Solutions

- **Missing XMP section** – If the source EPS does not contain any XMP, Aspose.Page automatically creates a minimal XMP block. You can then add your custom named values as shown above.  
- **Incorrect namespace prefix** – Ensure that the namespace (e.g., `xmpTPg`) matches the one present in the original metadata; otherwise the API will treat it as a new property.  
- **File access errors** – Verify that the application has read/write permissions for the directory you specify in `dataDir`.

## Frequently Asked Questions

**Q: Can I use Aspose.Page for .NET with other document formats?**  
A: Yes, Aspose.Page supports various document formats, including EPS, XPS, and PDF.

**Q: Is there a trial version available for Aspose.Page for .NET?**  
A: Yes, you can access a free trial [here](https://releases.aspose.com/).

**Q: Where can I find more documentation on Aspose.Page for .NET?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/net/).

**Q: How can I obtain a temporary license for Aspose.Page for .NET?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: What support options are available for Aspose.Page for .NET users?**  
A: Visit the community forum [here](https://forum.aspose.com/c/page/39) for support and discussions.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
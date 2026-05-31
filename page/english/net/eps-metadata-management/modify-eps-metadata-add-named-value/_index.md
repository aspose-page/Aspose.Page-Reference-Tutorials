---
title: How to Edit EPS Files – Add Named Value with Aspose.Page
linktitle: Add Named Value
second_title: Aspose.Page .NET API
description: Learn how to edit EPS files by adding named values using Aspose.Page for .NET. This step‑by‑step guide helps developers manipulate EPS metadata.
weight: 12
url: /net/eps-metadata-management/modify-eps-metadata-add-named-value/
date: 2026-01-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Edit EPS Files – Add Named Value with Aspose.Page

## How to Edit EPS Files – Introduction

In this tutorial on **how to edit EPS** files, we’ll walk you through adding a named value to an EPS document using the Aspose.Page library for .NET. Whether you’re building a batch‑processing tool or need to enrich EPS metadata on the fly, the steps below give you a clear, hands‑on guide.

## Quick Answers
- **What can Aspose.Page do?** It lets you read, modify, and write EPS files, including XMP metadata.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Do I need a license?** A free trial is available, but a commercial license is required for production use.  
- **How long does the implementation take?** Typically under 10 minutes for the basic named‑value scenario.  
- **Is it safe for large EPS files?** Yes – Aspose.Page streams data, keeping memory usage low.

## Prerequisites

Before diving into the tutorial, ensure that you have the following prerequisites in place:

- Basic knowledge of C# programming language.  
- An integrated development environment (IDE) such as Visual Studio installed.  
- Aspose.Page for .NET library. If not installed, you can download it from [here](https://releases.aspose.com/page/net/).

## Import Namespaces

Firstly, let's import the necessary namespaces into your C# code. These namespaces are vital for accessing the functionalities provided by Aspose.Page:

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

The initial step involves initializing the input stream for the EPS file. Replace `"Your Document Directory"` with the path to your document directory:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Step 2: Get XMP Metadata

Retrieve XMP metadata from the EPS file. If the EPS file lacks XMP metadata, a new one will be created, filled with values from PS metadata comments:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 3: Change XMP Metadata Values

Now, let's make changes to the XMP metadata. In this example, we'll add a named value to the `"xmpTPg:MaxPageSize"` structure:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Step 4: Save EPS File with Changed XMP Metadata

Save the EPS file with the updated XMP metadata. Create an output stream and save the modified EPS file:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusion

Congratulations! You've successfully added a named value to an EPS file using Aspose.Page in .NET. This walkthrough demonstrates how straightforward it is to **edit EPS** metadata, empowering you to enrich documents programmatically.

## Frequently Asked Questions

### Q1: Is Aspose.Page compatible with different EPS file versions?

A1: Aspose.Page supports various EPS file versions, ensuring compatibility with a wide range of documents.

### Q2: Can I use Aspose.Page for commercial projects?

A2: Yes, Aspose.Page comes with a commercial license, and you can purchase it [here](https://purchase.aspose.com/buy).

### Q3: Is there a free trial available for Aspose.Page?

A3: Yes, you can explore Aspose.Page with a free trial available [here](https://releases.aspose.com/).

### Q4: How can I get support or connect with the Aspose community?

A4: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to get support and connect with the community.

### Q5: What is a temporary license, and how can I obtain one?

A5: If you need a temporary license for testing or evaluation purposes, you can acquire one [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---
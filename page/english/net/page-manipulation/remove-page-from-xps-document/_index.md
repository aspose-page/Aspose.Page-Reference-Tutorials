---
title: Remove Page from XPS Document with Aspose.Page for .NET
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
description: Explore a comprehensive tutorial on removing pages from XPS documents using Aspose.Page for .NET. Learn the step-by-step process, prerequisites, and FAQs for seamless document manipulation.
weight: 12
url: /net/page-manipulation/remove-page-from-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Remove Page from XPS Document with Aspose.Page for .NET

## Introduction

In this tutorial, we will explore the process of removing a page from an XPS document using Aspose.Page for .NET. Aspose.Page is a powerful library that enables .NET developers to work with XPS (XML Paper Specification) documents seamlessly. If you find yourself in a situation where you need to eliminate a specific page from your XPS document, this step-by-step guide will walk you through the process.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page library installed. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).

- .NET Development Environment: Have a working .NET development environment set up on your machine.

- Sample XPS Document: Prepare a sample XPS document that you'll use for testing the removal process.

## Import Namespaces

In your .NET application, begin by importing the necessary namespaces for working with Aspose.Page. Add the following lines to the top of your code file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

Ensure to replace "Your Document Directory" with the actual path to your document directory.

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

This code initializes a new XPS document based on the provided sample file.

## Step 3: Remove a Page

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

Specify the index of the page you want to remove. In this example, the code removes the page at index 1.

## Step 4: Save the Resultant XPS Document

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

Save the modified XPS document with the removed page.

## Conclusion

Congratulations! You have successfully removed a page from an XPS document using Aspose.Page for .NET. This straightforward process can be seamlessly integrated into your .NET applications, providing flexibility in managing XPS documents.

## FAQ's

### Q1: Can I remove multiple pages at once using Aspose.Page for .NET?

A1: Yes, you can modify the code to remove multiple pages by calling the `RemovePageAt` method multiple times.

### Q2: Is Aspose.Page compatible with the latest .NET framework?

A2: Aspose.Page is regularly updated to ensure compatibility with the latest .NET framework versions.

### Q3: Can I use Aspose.Page for commercial applications?

A3: Yes, you can use Aspose.Page for commercial purposes. Visit [Aspose.Purchase](https://purchase.aspose.com/buy) for licensing details.

### Q4: Where can I find additional support and discussions on Aspose.Page?

A4: Join the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community and seek assistance.

### Q5: Do I need a temporary license for testing Aspose.Page?

A5: Yes, you can obtain a [temporary license](https://purchase.aspose.com/temporary-license/) for testing purposes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

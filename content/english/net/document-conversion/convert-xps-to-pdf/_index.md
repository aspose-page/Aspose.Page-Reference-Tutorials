---
title: Convert XPS to PDF with Aspose.Page for .NET
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
description: Effortlessly convert XPS to PDF in .NET with Aspose.Page. Download the library, explore documentation, and get a free trial.
type: docs
weight: 11
url: /net/document-conversion/convert-xps-to-pdf/
---
## Introduction

In this tutorial, we will delve into the process of converting XPS (XML Paper Specification) documents to PDF (Portable Document Format) using the powerful Aspose.Page for .NET library. Aspose.Page for .NET provides a robust set of features for working with XPS files, enabling developers to seamlessly convert them to PDF format with various customization options.

## Prerequisites

Before we embark on this conversion journey, make sure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it from the [Aspose.Page documentation](https://reference.aspose.com/page/net/).

- Development Environment: Set up a .NET development environment with Visual Studio or any other compatible IDE.

- XPS Document: Prepare the XPS document that you want to convert to PDF. This could be your sample XPS file stored in a designated directory.

## Import Namespaces

Before diving into the code, let's import the necessary namespaces to make the Aspose.Page for .NET functionalities accessible in our code:

```csharp
using Aspose.Page.XPS;
```

## Step 1: Initialize Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Replace "Your Document Directory" with the path to the directory containing your XPS document.

## Step 2: Initialize PDF and XPS Streams

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Open streams for both the output PDF file and the input XPS file. Ensure you have the appropriate file paths set.

## Step 3: Load XPS Document

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Load the XPS document using the Aspose.Page for .NET library.

## Step 4: Initialize PDF Save Options

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Set up the PDF save options, including parameters like JPEG quality level, image compression, text compression, and specific page numbers to include.

## Step 5: Create PDF Rendering Device

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Create a rendering device for the PDF format using the Aspose.Page for .NET library.

## Step 6: Save Document to PDF

```csharp
document.Save(device, options);
```

Save the XPS document to PDF using the specified rendering device and options.

## Conclusion

Congratulations! You've successfully converted an XPS document to PDF using Aspose.Page for .NET. This versatile library provides developers with a powerful toolset for handling various document formats effortlessly.

## FAQ's

### Q1: Can I convert multiple XPS files to a single PDF using Aspose.Page for .NET?

A1: Yes, you can loop through multiple XPS files and follow the same steps to merge them into a single PDF.

### Q2: Are there other output formats supported by Aspose.Page for .NET?

A2: Yes, Aspose.Page for .NET supports various output formats, including TIFF, JPEG, PNG, and more.

### Q3: How can I customize the appearance of the converted PDF document?

A3: You can tweak the options object parameters, such as image compression and text compression, to achieve the desired appearance.

### Q4: Is there a trial version available for Aspose.Page for .NET?

A4: Yes, you can explore the capabilities of Aspose.Page for .NET by obtaining a free trial from [here](https://releases.aspose.com/).

### Q5: Where can I get community support for Aspose.Page for .NET?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community discussions and support.

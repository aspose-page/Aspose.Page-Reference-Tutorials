---
title: Resize EPS Images with Aspose.Page for .NET
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
description: Explore the seamless process of resizing EPS images in .NET using Aspose.Page. Achieve precision in points, inches, millimeters, and percentages effortlessly.
weight: 11
url: /net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Resize EPS Images with Aspose.Page for .NET

## Introduction

Are you looking to resize EPS images seamlessly using Aspose.Page for .NET? This tutorial is your comprehensive guide to effortlessly manipulate the size of EPS images in various units such as points, inches, millimeters, and percentages. Aspose.Page for .NET provides a powerful set of tools, and in this tutorial, we'll walk you through the process step by step.

## Prerequisites

Before diving into the resizing magic, ensure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Make sure you have the Aspose.Page for .NET library installed. You can download it from [here](https://releases.aspose.com/page/net/).

- Document Directory: Create a directory where you'll store your input EPS file and output resized files.

Now that you have everything set up, let's proceed to import the necessary namespaces and delve into the step-by-step guide.

## Import Namespaces

In your .NET project, begin by importing the necessary namespaces to work with Aspose.Page. Add the following code at the beginning of your file:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Step 1: Resizing in Points

Let's start by resizing an EPS image in points. Points are a standard unit of measurement in the printing industry.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Step 2: Resizing in Inches

Now, let's resize an EPS image in inches, a common unit used in graphic design.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Step 3: Resizing in Millimeters

Now, let's resize an EPS image in millimeters, another widely used unit in design and printing.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Step 4: Resizing in Percents

Finally, let's resize an EPS image using percentages, providing a flexible approach to adjust image size.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Feel free to integrate these methods into your project, and you'll be resizing EPS images effortlessly. Experiment with different units to achieve the desired dimensions.

## Conclusion

Congratulations! You've mastered the art of resizing EPS images with Aspose.Page for .NET. This powerful library opens up a world of possibilities for manipulating vector graphics. Whether you're designing for print or digital media, Aspose.Page empowers you to achieve precise and customized results.

## FAQ's

### Q1: Can I resize multiple EPS images simultaneously?

A1: Yes, you can loop through a collection of EPS files, applying the resizing methods accordingly.

### Q2: Is Aspose.Page compatible with other image formats?

A2: Aspose.Page primarily focuses on PostScript and EPS formats. For other image formats, consider using Aspose.Imaging.

### Q3: Are there any licensing considerations for commercial projects?

A3: Yes, ensure you have a valid license. Visit [here](https://purchase.aspose.com/buy) for licensing details.

### Q4: Can I try Aspose.Page before purchasing?

A4: Absolutely! You can get a free trial [here](https://releases.aspose.com/).

### Q5: Where can I seek additional help or discuss issues?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

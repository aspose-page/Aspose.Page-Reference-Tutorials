---
date: 2025-12-08
description: Pelajari cara menambahkan gradien radial di Java PostScript dengan Aspose.Page.
  Panduan langkah demi langkah ini menunjukkan cara membuat efek gradien yang menakjubkan
  dalam dokumen Anda.
language: id
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Cara Menambahkan Gradien Radial di Java PostScript dengan Aspose.Page
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien Radial dalam Java PostScript dengan Aspose.Page

## Introduction
Jika Anda pernah perlu memberikan output PostScript Anda transisi warna yang halus dan menarik, mempelajari **cara menambahkan gradien radial** adalah tempat yang tepat untuk memulai. Dalam tutorial ini kami akan membimbing Anda melalui setiap langkah yang diperlukan untuk menghasilkan file PostScript yang berisi gradien radial yang indah, menggunakan pustaka **Aspose.Page for Java**. Pada akhir tutorial Anda akan memahami API-nya, melihat contoh lengkap yang dapat dijalankan, dan mengetahui cara menyesuaikan warna, posisi, serta radius agar sesuai dengan desain apa pun.

## Quick Answers
- **What library creates radial gradients in PostScript?** Aspose.Page for Java.  
- **How long does the implementation take?** About 10‑15 minutes for a basic example.  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher.  
- **Can I change the gradient’s shape?** Yes – adjust the radius and center point in the `RadialGradientPaint` constructor.

## What is a Radial Gradient?
Gradien radial melukis warna yang memancar keluar dari titik pusat, secara bertahap mencampur ke arah tepi. Tidak seperti gradien linear, transisi warna mengikuti pola melingkar (atau elips), yang ideal untuk sorotan, lampu sorot, atau isian latar belakang yang lembut.

## Why Use Aspose.Page for Radial Gradients?
- **Full control over PostScript output** – no need to hand‑craft low‑level PS commands.  
- **Cross‑platform** – works on any OS that runs Java.  
- **Rich color management** – supports multiple color stops, different color spaces, and cycle methods.  
- **Integration‑ready** – combine with other Aspose.Page features such as text, images, and vector shapes.

## Prerequisites
Sebelum kita menyelam ke kode, pastikan Anda telah menyiapkan hal‑hal berikut:

- **Java Development Kit (JDK) 8+** – verify with `java -version`.  
- **Aspose.Page for Java** – download the latest JAR from the official [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE of your choice** – Eclipse, IntelliJ IDEA, or VS Code with Java extensions.  
- **A writable folder** – where the generated `.ps` file will be saved.

## Import Packages
First, import the classes we’ll need. The `java.awt` package provides the gradient paint objects, while `com.aspose.eps` contains the PostScript document handling classes.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
We start by creating an output stream, configuring the page size (A4 by default), and defining a rectangle that will host the gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** Adjust the rectangle’s coordinates (`200, 100, 200, 200`) to position the gradient anywhere on the page.

### Step 2: Define Colors and Fractions
A radial gradient is built from *color stops* (the colors) and *fractions* (the relative positions of those stops). Here we create an array of six colors and their corresponding fractions.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** By tweaking `fractions` you control how quickly the colors transition, enabling subtle or dramatic effects.

### Step 3: Create Radial Gradient Paint
Now we build the `RadialGradientPaint` object. The constructor takes the gradient’s center point, radius, focus point, fractions, colors, cycle method, color space, and an optional transform.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** `transform` can be `null` if you don’t need additional scaling or rotation. Feel free to experiment with `AffineTransform` for skewed gradients.

### Step 4: Set Paint and Fill the Rectangle
With the paint ready, we tell the `PsDocument` to use it and then fill the rectangle we defined earlier.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

At this point the PostScript page contains a rectangle smoothly filled with the radial gradient we configured.

### Step 5: Close and Save the Document
Finally, close the current page and write the file to disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Open `RadialGradient1_outPS.ps` in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered exactly as defined.

## Common Issues & Solutions
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| Gradien muncul sebagai warna solid | array `fractions` tidak dimulai dari `0.0f` atau tidak berakhir pada `1.0f` | Pastikan fraksi pertama adalah `0.0f` dan fraksi terakhir adalah `1.0f`. |
| Warna tampak pudar | Menggunakan `ColorSpaceType` yang salah | Ganti ke `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` untuk output yang lebih cerah. |
| Tidak ada file output yang dihasilkan | Path `FileOutputStream` tidak valid atau tidak dapat ditulis | Pastikan `dataDir` ada dan aplikasi memiliki izin menulis. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java in commercial projects?**  
A: Yes. A commercial license is required for production use. You can purchase one from the [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Where can I find the official API reference?**  
A: The full documentation is available [here](https://reference.aspose.com/page/java/).

**Q: Is a free trial available for testing?**  
A: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).

**Q: How do I obtain a temporary license for evaluation?**  
A: A temporary license can be requested [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
You now know **how to add radial gradient** to a Java PostScript document using Aspose.Page. By adjusting the rectangle size, color stops, and gradient radius you can create countless visual effects—from subtle background fills to bold spotlight graphics. Feel free to experiment with different `AffineTransform` values to rotate or skew the gradient, and combine this technique with text and images for richer PDF or EPS outputs.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
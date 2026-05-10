---
date: 2026-02-13
description: Pelajari cara membuat gradien PostScript di Java menggunakan Aspose.Page.
  Panduan langkah demi langkah ini menunjukkan cara menambahkan gradien vertikal ke
  dokumen PostScript Anda dengan mudah.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Buat Gradien PostScript di Java – Tambahkan Gradien Vertikal
url: /id/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Gradien PostScript di Java – Tambahkan Gradien Vertikal

## Introduction
Dalam tutorial komprehensif ini, Anda akan belajar cara **membuat gradien PostScript di Java** dengan Aspose.Page for Java. Menambahkan gradien vertikal dapat membuat dokumen Anda terlihat lebih hidup dan profesional, dan dengan hanya beberapa baris kode Anda dapat mencapai efek visual yang menakjubkan. Kami akan memandu Anda melalui setiap langkah, menjelaskan mengapa setiap bagian penting, dan memberi Anda tip praktis untuk menghindari jebakan umum. Pada akhir panduan ini Anda akan dapat menghasilkan file PostScript yang memiliki transisi warna vertikal yang halus dan menarik.

## Quick Answers
- **Library apa yang dibutuhkan?** Aspose.Page for Java  
- **Apakah saya dapat menyesuaikan warna?** Ya, dapat menggunakan `java.awt.Color` apa pun  
- **Apakah rotasi didukung?** Ya, Anda dapat memutar gradien dengan `AffineTransform`  
- **Format output apa yang dihasilkan?** File PostScript standar (.ps)  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan  

## Why add a vertical gradient to a PostScript document?
Mengapa menambahkan gradien vertikal ke dokumen PostScript?

Gradien vertikal memberikan kedalaman pada halaman Anda tanpa memperbesar ukuran file. Mereka sempurna untuk:

* Header atau footer laporan yang memerlukan latar belakang halus.  
* Menyoroti bagian dalam manual teknis atau white‑paper.  
* Memberikan tampilan modern untuk diagram, grafik, atau selebaran promosi.

Karena gradien didefinisikan dalam bentuk vektor, output tetap tajam pada resolusi apa pun.

## Prerequisites
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Aspose.Page for Java library. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/java/).

## Import Packages
Di proyek Java Anda, import paket yang diperlukan untuk memulai:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Sekarang, mari kita jalani proses penambahan gradien vertikal langkah demi langkah.

## How to create PostScript gradient in Java
Berikut adalah panduan langkah‑demi‑langkah yang menunjukkan secara tepat cara **membuat gradien PostScript di Java** menggunakan API Aspose.Page.

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Selamat! Anda telah berhasil menambahkan gradien vertikal ke dokumen PostScript Java Anda menggunakan Aspose.Page for Java.

## Common Issues and Solutions
- **Gradien tampak datar:** Pastikan skala `AffineTransform` sesuai dengan dimensi rectangle.  
- **Warna tampak pudar:** Pastikan Anda menggunakan `ColorSpaceType` yang benar (SRGB) dan bahwa array fraksi diurutkan dari 0.0 hingga 1.0.  
- **File tidak terbuat:** Periksa apakah direktori output (`dataDir`) ada dan aplikasi memiliki izin menulis.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Apakah saya dapat menggunakan Aspose.Page for Java dengan pustaka Java lain?  
Ya, Aspose.Page for Java dirancang untuk bekerja mulus dengan pustaka Java lainnya.

### Is there a free trial available for Aspose.Page for Java?
Apakah tersedia percobaan gratis untuk Aspose.Page for Java?  
Ya, Anda dapat mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

### Where can I find additional documentation?
Di mana saya dapat menemukan dokumentasi tambahan?  
Dokumentasi detail tersedia [di sini](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
Bagaimana cara membeli Aspose.Page for Java?  
Anda dapat membeli Aspose.Page for Java [di sini](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Apakah ada forum untuk diskusi Aspose.Page?  
Ya, Anda dapat bergabung dengan forum komunitas [di sini](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Bisakah saya membuat arah gradien lain (horizontal, diagonal)?**  
A: Tentu saja. Sesuaikan titik awal dan akhir pada `LinearGradientPaint` serta ubah sudut rotasi pada `AffineTransform`.

**Q: Apakah ini juga bekerja dengan output PDF?**  
A: Logika gradien yang sama dapat diterapkan saat menyimpan ke PDF dengan menggunakan `PdfSaveOptions` alih-alih `PsSaveOptions`.

**Q: Bagaimana cara mengubah ukuran gradien secara dinamis?**  
A: Hitung dimensi rectangle pada waktu berjalan dan berikan nilai tersebut ke konstruktor `Rectangle2D` dan `AffineTransform`.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
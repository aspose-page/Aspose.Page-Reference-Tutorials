---
date: 2026-02-13
description: Pelajari cara menambahkan gradien di Java PostScript menggunakan Linear
  Gradient Paint Java dengan Aspose.Page untuk Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Cara Menambahkan Gradien di Java PostScript dengan Linear Gradient Paint
url: /id/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradient dalam Java PostScript dengan Linear Gradient Paint

## Introduction
Dalam tutorial komprehensif ini Anda akan menemukan **cara menambahkan gradient** ke dokumen PostScript menggunakan Java. Kami akan memandu Anda membuat gradient horizontal yang indah dengan memanfaatkan **Linear Gradient Paint Java**, sebuah kelas yang memberi Anda kontrol pixel‑perfect atas transisi warna. Dengan Aspose.Page untuk Java Anda dapat merender gradient pada **bentuk** **dan** teks, memberikan dokumen Anda tampilan yang halus, menarik, dan menonjol.

## Quick Answers
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page for Java (mendukung Linear Gradient Paint Java).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk gradient dasar.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Versi JDK mana yang bekerja?** Java 8 atau lebih baru.  
- **Bisakah saya menggunakan gradient pada bentuk dan teks?** Ya – Anda dapat mengisi bentuk serta memberi stroke atau mengisi teks dengan gradient yang sama.

## What is a Horizontal Gradient and Why Use It?
Gradient horizontal secara halus mencampur warna dari kiri ke kanan pada sebuah bentuk atau teks. Ini ideal untuk membuat elemen UI modern, judul yang disorot, atau efek latar belakang halus dalam laporan. Menggunakan **Linear Gradient Paint Java** memungkinkan Anda menentukan warna awal‑dan akhir yang tepat, opasitas, dan skala, sehingga hasilnya tampak tajam pada perangkat apa pun.

## Prerequisites
Sebelum menyelam ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk Java. Anda dapat mengunduhnya dari [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
Mulailah dengan mengimpor paket‑paket yang diperlukan dalam proyek Java Anda. Impor ini memberi Anda akses ke primitif grafis, penanganan gradient, dan API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Rectangle
Pertama, siapkan output stream, dokumen, dan sebuah persegi panjang yang akan menampung gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 2: Create Horizontal Linear Gradient Paint
Di sini kami membangun objek **Linear Gradient Paint Java** yang mendefinisikan transisi warna horizontal. `AffineTransform` menskalakan gradient agar sesuai dengan lebar dan tinggi persegi panjang.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Step 3: Fill the Rectangle
Sekarang isi persegi panjang dengan gradient yang baru saja kami definisikan.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
Anda juga dapat menerapkan gradient yang sama pada teks, menciptakan efek visual yang mencolok.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
Akhirnya, beri outline pada teks menggunakan gradient sebagai warna stroke.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| Gradient tampak terdistorsi | Skala `AffineTransform` tidak tepat | Pastikan lebar dan tinggi transformasi sesuai dengan dimensi persegi panjang (200 × 100 pada contoh). |
| Warna tampak pudar | Nilai alpha terlalu rendah | Tingkatkan komponen alpha (nilai keempat dalam `new Color(r,g,b,alpha)`). |
| Teks tidak terlihat | Paint tidak diatur sebelum menggambar teks | Panggil `document.setPaint(paint)` **sebelum** pemanggilan `fillAndStrokeText` atau `outlineText` apapun. |

## Frequently Asked Questions
**Q:** Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial?  
**A:** Ya, Aspose.Page untuk Java dapat digunakan dalam proyek komersial. Untuk detail lisensi, kunjungi [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Apakah ada percobaan gratis yang tersedia?  
**A:** Ya, Anda dapat mengakses percobaan gratis Aspose.Page untuk Java [di sini](https://releases.aspose.com/).

**Q:** Di mana saya dapat menemukan dokumentasi dan dukungan tambahan?  
**A:** Kunjungi [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) untuk sumber daya lengkap. Untuk dukungan komunitas, periksa [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Bagaimana cara mendapatkan lisensi sementara?  
**A:** Anda dapat memperoleh lisensi sementara dari [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Q:** Apa persyaratan sistem untuk Aspose.Page untuk Java?  
**A:** Lihat [documentation](https://reference.aspose.com/page/java/) untuk persyaratan sistem yang detail.

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
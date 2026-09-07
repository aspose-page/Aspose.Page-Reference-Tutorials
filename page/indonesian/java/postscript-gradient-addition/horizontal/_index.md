---
date: 2026-09-04
description: Pelajari cara membuat horizontal gradient java dalam file PostScript
  menggunakan Linear Gradient Paint Java dengan Aspose.Page untuk Java. Kode langkah‑demi‑langkah,
  jebakan umum, dan FAQ.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Buat horizontal gradient java di PostScript menggunakan Aspose
og_description: Buat horizontal gradient java di PostScript dengan Linear Gradient
  Paint Java. Tutorial Aspose.Page ini menunjukkan langkah‑langkah tepat, prasyarat,
  dan tips pemecahan masalah dalam waktu kurang dari 15 menit.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Buat horizontal gradient java di PostScript menggunakan Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Buat horizontal gradient java di PostScript menggunakan Aspose
url: /id/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan gradien horizontal di Java PostScript menggunakan Linear Gradient Paint

## Pendahuluan
Dalam tutorial komprehensif ini Anda akan belajar **cara membuat gradien horizontal java** dalam dokumen PostScript dengan menggunakan kelas **Linear Gradient Paint Java** yang disertakan dalam Aspose.Page for Java. Kami akan membahas setiap langkah—dari menyiapkan proyek hingga merender gradien pada bentuk dan teks—sehingga Anda dapat menghasilkan grafik yang halus dan siap cetak dalam hitungan menit. Baik Anda membangun mesin pelaporan, alat otomatisasi desain, atau driver printer khusus, panduan ini memberikan kode tepat yang Anda perlukan.

## Jawaban Cepat
- **Library apa yang diperlukan?** Aspose.Page for Java (termasuk Linear Gradient Paint Java).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk gradien horizontal dasar.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Versi JDK mana yang kompatibel?** Java 8 atau lebih baru.  
- **Bisakah saya menggunakan gradien pada bentuk dan teks?** Ya – instance `LinearGradientPaint` yang sama dapat mengisi bentuk dan diterapkan pada goresan atau isi teks.

## Apa itu gradien horizontal dan mengapa menggunakannya?
Gradien horizontal menggabungkan warna dari tepi kiri objek ke tepi kanannya, menciptakan transisi halus yang menambah kedalaman dan daya tarik visual. Ini ideal untuk komponen UI modern, judul yang disorot, atau latar belakang halus dalam laporan PDF atau PostScript. Menggunakan **Linear Gradient Paint Java** memungkinkan Anda mengontrol warna awal‑dan akhir, opasitas, serta skala dengan tepat, memastikan hasilnya tajam pada perangkat atau printer apa pun.

## Prasyarat
Sebelum menyelami kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.Page for Java. Anda dapat mengunduhnya dari [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Impor paket
Mulailah dengan mengimpor paket yang diperlukan dalam proyek Java Anda. Impor ini memberi Anda akses ke primitif grafis, penanganan gradien, dan API Aspose.Page.

Kelas `PsDocument` mewakili dokumen PostScript yang dapat Anda gambar grafis di atasnya.  

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

## Langkah 1: buat persegi panjang
Pertama, siapkan aliran output, dokumen, dan persegi panjang yang akan menampung gradien.

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

## Langkah 2: buat horizontal linear gradient paint
`LinearGradientPaint` adalah kelas inti yang mendefinisikan transisi warna linear.  
Kelas `LinearGradientPaint` mewakili objek cat yang merender gradien sepanjang garis lurus; Anda menentukan titik awal/akhir, titik warna, dan opsional `AffineTransform` untuk menyesuaikannya dengan bentuk Anda.

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

## Langkah 3: isi persegi panjang
Sekarang isi persegi panjang dengan gradien yang baru saja kita definisikan.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Langkah 4: isi teks dengan gradien
Anda juga dapat menerapkan gradien yang sama pada teks, menciptakan efek visual yang mencolok.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Langkah 5: beri garis tepi pada teks dengan gradien
Akhirnya, beri outline pada teks menggunakan gradien sebagai warna goresannya.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Masalah umum dan solusi
| Masalah | Mengapa terjadi | Perbaikan |
|-------|----------------|-----|
| Gradien muncul terdistorsi | Skala `AffineTransform` tidak tepat | Pastikan lebar dan tinggi transformasi sesuai dengan dimensi persegi panjang (200 × 100 pada contoh). |
| Warna tampak pudar | Nilai alpha terlalu rendah | Tingkatkan komponen alpha (nilai keempat dalam `new Color(r,g,b,alpha)`). |
| Teks tidak terlihat | Paint tidak diatur sebelum menggambar teks | Panggil `document.setPaint(paint)` **sebelum** pemanggilan `fillAndStrokeText` atau `outlineText` apa pun. |

## Pertanyaan yang Sering Diajukan
**Q:** Bisakah saya menggunakan Aspose.Page for Java dalam proyek komersial?  
**A:** Ya, Aspose.Page for Java dapat digunakan dalam proyek komersial. Untuk detail lisensi, kunjungi halaman [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Apakah tersedia trial gratis?  
**A:** Ya, Anda dapat mengakses trial gratis Aspose.Page for Java di halaman [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q:** Di mana saya dapat menemukan dokumentasi dan dukungan tambahan?  
**A:** Kunjungi [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) untuk sumber daya lengkap. Untuk bantuan komunitas, periksa [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Bagaimana cara mendapatkan lisensi sementara?  
**A:** Anda dapat memperoleh lisensi sementara dari halaman [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** Apa persyaratan sistem untuk Aspose.Page for Java?  
**A:** Lihat [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) untuk persyaratan sistem detail.

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutorial Terkait

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Create PostScript Gradient – Radial Gradient in Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-07
description: Pelajari cara menambahkan gradien horizontal di Java PostScript menggunakan
  Linear Gradient Paint Java dengan Aspose.Page untuk Java.
language: id
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Menambahkan Gradien dalam Java PostScript menggunakan Linear Gradient Paint
  Java
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien di PostScript Java menggunakan Linear Gradient Paint Java

## Pendahuluan
Pada tutorial komprehensif ini Anda akan menemukan cara membuat gradien horizontal yang indah dalam dokumen PostScript dengan memanfaatkan **Linear Gradient Paint Java**. Aspose.Page for Java memudahkan kerja dengan PostScript, PDF, dan format vektor lainnya, dan kelas `LinearGradientPaint` memberikan kontrol detail atas transisi warna. Pada akhir panduan ini, Anda akan dapat merender gradien pada bentuk **dan** teks, memberikan dokumen Anda tampilan profesional yang menarik perhatian.

## Jawaban Cepat
- **Library apa yang diperlukan?** Aspose.Page for Java (mendukung Linear Gradient Paint Java).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk gradien dasar.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Versi JDK mana yang bekerja?** Java 8 atau yang lebih baru.  
- **Bisakah saya menggunakan gradien pada bentuk dan teks?** Ya – Anda dapat mengisi bentuk dan memberi garis tepi atau mengisi teks dengan gradien yang sama.

## Prasyarat
Sebelum menyelami kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Pustaka Aspose.Page for Java. Anda dapat mengunduhnya dari [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Impor Paket
Mulailah dengan mengimpor paket yang diperlukan dalam proyek Java Anda. Impor ini memberi Anda akses ke primitif grafis, penanganan gradien, dan API Aspose.Page.

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

## Langkah 1: Buat Rectangle
Pertama, siapkan aliran output, dokumen, dan sebuah rectangle yang akan menampung gradien.

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

## Langkah 2: Buat Horizontal Linear Gradient Paint
Di sini kami membuat objek **Linear Gradient Paint Java** yang mendefinisikan transisi warna horizontal. `AffineTransform` menskalakan gradien agar sesuai dengan lebar dan tinggi rectangle.

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

## Langkah 3: Isi Rectangle
Sekarang isi rectangle dengan gradien yang baru saja kami definisikan.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Langkah 4: Isi Teks dengan Gradien
Anda juga dapat menerapkan gradien yang sama pada teks, menciptakan efek visual yang mencolok.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Langkah 5: Garis Tepi Teks dengan Gradien
Akhirnya, beri garis tepi pada teks menggunakan gradien sebagai warna garis.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| Gradien tampak terdistorsi | Skala `AffineTransform` tidak tepat | Pastikan lebar dan tinggi transformasi sesuai dengan dimensi rectangle (200 × 100 pada contoh). |
| Warna tampak pudar | Nilai alpha diatur terlalu rendah | Tingkatkan komponen alpha (nilai keempat dalam `new Color(r,g,b,alpha)`). |
| Teks tidak terlihat | Paint tidak diatur sebelum menggambar teks | Panggil `document.setPaint(paint)` **sebelum** pemanggilan `fillAndStrokeText` atau `outlineText` apa pun. |

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page for Java dalam proyek komersial?
Ya, Aspose.Page for Java dapat digunakan dalam proyek komersial. Untuk detail lisensi, kunjungi [Aspose.Purchase](https://purchase.aspose.com/buy).

### Apakah tersedia percobaan gratis?
Ya, Anda dapat mengakses percobaan gratis Aspose.Page for Java [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi dan dukungan tambahan?
Kunjungi [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) untuk sumber daya lengkap. Untuk dukungan komunitas, periksa [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### Bagaimana saya dapat memperoleh lisensi sementara?
Anda dapat memperoleh lisensi sementara dari [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Apa persyaratan sistem untuk Aspose.Page for Java?
Lihat [documentation](https://reference.aspose.com/page/java/) untuk persyaratan sistem yang detail.

---

**Terakhir Diperbarui:** 2025-12-07  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
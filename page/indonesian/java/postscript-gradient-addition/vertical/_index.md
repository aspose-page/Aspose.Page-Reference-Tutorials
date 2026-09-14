---
date: 2026-09-14
description: Pelajari cara membuat gradien postscript java dengan Aspose.Page. Panduan
  langkah‑demi‑langkah ini menunjukkan cara menambahkan gradien vertikal ke file PostScript
  hanya dengan beberapa baris kode Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Tambahkan Gradien Vertikal di Java PostScript
og_description: Pelajari cara membuat gradien postscript java dengan Aspose.Page.
  Panduan langkah‑demi‑langkah ini menunjukkan cara menambahkan gradien vertikal ke
  file PostScript hanya dengan beberapa baris kode Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Buat gradien postscript java – gradien vertikal
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Buat gradien postscript java – gradien vertikal
url: /id/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gradien postscript java – gradien vertikal

## Pendahuluan
Aspose.Page for Java adalah sebuah perpustakaan yang memungkinkan pembuatan dan manipulasi file PostScript dan PDF secara programatik. Dalam tutorial komprehensif ini Anda akan belajar cara **create postscript gradient java** menggunakan perpustakaan tersebut. Menambahkan gradien vertikal dapat membuat dokumen Anda terlihat lebih hidup dan profesional, dan dengan hanya beberapa baris kode Anda dapat mencapai efek visual yang menakjubkan. Kami akan memandu Anda melalui setiap langkah, menjelaskan mengapa setiap bagian penting, dan memberikan tips praktis untuk menghindari jebakan umum. Pada akhir panduan ini Anda akan dapat menghasilkan file PostScript yang memiliki transisi warna vertikal yang halus dan menarik.

## Jawaban Cepat
- **Library apa yang dibutuhkan?** Aspose.Page for Java  
- **Bisakah saya menyesuaikan warna?** Yes, any `java.awt.Color` can be used  
- **Apakah rotasi didukung?** Yes, you can rotate the gradient with an `AffineTransform`  
- **Format output apa yang dihasilkan?** A standard PostScript (.ps) file  
- **Apakah saya memerlukan lisensi untuk produksi?** Yes, a commercial license is required  

## Mengapa menambahkan gradien vertikal ke dokumen PostScript?
Menambahkan gradien vertikal memberikan kedalaman pada halaman Anda, meningkatkan hierarki visual, dan menjaga ukuran file tetap kecil karena gradien didefinisikan dalam bentuk vektor bukan gambar raster. Teknik ini sempurna untuk header laporan, manual teknis, atau flyer apa pun yang membutuhkan tampilan modern tanpa mengorbankan skalabilitas.

## Prasyarat
Sebelum menyelami tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) terpasang di mesin Anda.  
- Aspose.Page for Java library. Anda dapat mengunduhnya dari [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Impor paket
Dalam proyek Java Anda, impor paket yang diperlukan untuk memulai:
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

Sekarang, mari kita jalani proses menambahkan gradien vertikal langkah demi langkah.

## Cara membuat postscript gradient java
Muat lingkungan Java Anda, buat instance `PsSaveOptions`, dan panggil `Document.save` – itu adalah urutan inti yang membuat file PostScript dengan gradien vertikal. API menangani interpolasi warna, transformasi koordinat, dan pembersihan halaman untuk Anda, sehingga Anda hanya perlu fokus pada mendefinisikan persegi panjang dan parameter gradien.

### Langkah 1: siapkan direktori dokumen Anda
Objek `File` mewakili folder tempat output akan ditulis. Direktori harus ada sebelum aliran dibuka, jika tidak `IOException` akan dilempar.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Langkah 2: buat aliran output untuk dokumen PostScript
`FileOutputStream` menulis data PostScript biner ke disk. Menggunakan blok `try‑with‑resources` menjamin aliran ditutup bahkan jika terjadi pengecualian.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Langkah 3: buat opsi penyimpanan dengan ukuran A4
`PsSaveOptions` memungkinkan Anda menentukan ukuran halaman, DPI, dan apakah menyertakan font. Menetapkan ukuran ke A4 (595 × 842 points) cocok untuk kebanyakan dokumen yang dapat dicetak.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Langkah 4: buat dokumen PS baru
`Document` adalah objek tingkat atas yang mewakili satu file PostScript dalam memori. Semua perintah menggambar dikeluarkan terhadap objek ini.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Langkah 5: buat persegi panjang
`Rectangle2D.Double` mendefinisikan area yang akan diisi dengan gradien. Koordinat persegi panjang diekspresikan dalam poin (1 point = 1/72 inch).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Langkah 6: siapkan warna dan fraksi untuk gradien
Array `float[]` mendefinisikan posisi setiap titik warna (dari 0.0 hingga 1.0). Objek `Color` menyimpan nilai RGB sebenarnya. Anda dapat menggunakan `java.awt.Color` apa pun yang Anda suka.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Langkah 7: buat transformasi gradien
`AffineTransform` memperbesar dan memutar gradien. Untuk gradien vertikal murni Anda hanya perlu memperbesar sumbu Y; rotasi dapat ditambahkan nanti jika diinginkan.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Langkah 8: buat cat gradien linear vertikal
`LinearGradientPaint` menggabungkan persegi panjang, titik warna, dan transformasi. Objek ini kemudian diteruskan ke konteks grafis.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Langkah 9: setel cat dan isi persegi panjang
`Graphics2D.setPaint` menerapkan gradien, dan `fill` merendernya di dalam persegi panjang yang Anda definisikan sebelumnya.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Langkah 10: tutup halaman saat ini dan simpan dokumen
Memanggil `document.save` menulis seluruh aliran PostScript ke file output dan melepaskan semua sumber daya native.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Selamat! Anda telah berhasil menambahkan gradien vertikal ke dokumen PostScript Java Anda menggunakan Aspose.Page for Java.

## Masalah umum dan solusi
- **Gradien terlihat datar:** Ensure the `AffineTransform` scaling matches the rectangle dimensions.  
- **Warna tampak pudar:** Verify you are using the correct `ColorSpaceType` (SRGB) and that the fractions array is ordered from 0.0 to 1.0.  
- **File tidak dihasilkan:** Check that the output directory (`dataDir`) exists and the application has write permissions.  

## Pertanyaan yang sering diajukan
**Q: Bisakah saya menggunakan Aspose.Page for Java dengan pustaka Java lainnya?**  
A: Ya, Aspose.Page for Java dirancang untuk bekerja secara mulus bersama pustaka Java lainnya seperti Apache Commons atau Spring.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Page for Java?**  
A: Ya, Anda dapat mendapatkan percobaan gratis [free trial download page](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi tambahan?**  
A: Dokumentasi terperinci tersedia [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Bagaimana cara membeli Aspose.Page for Java?**  
A: Anda dapat membeli Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**Q: Apakah ada forum untuk diskusi Aspose.Page?**  
A: Ya, Anda dapat bergabung dengan forum komunitas [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## Pertanyaan tambahan yang sering diajukan
**Q: Bisakah saya membuat arah gradien lain (horizontal, diagonal)?**  
A: Tentu saja. Sesuaikan titik awal dan akhir di `LinearGradientPaint` dan ubah sudut rotasi di `AffineTransform`.

**Q: Apakah ini juga berfungsi dengan output PDF?**  
A: Logika gradien yang sama dapat diterapkan saat menyimpan ke PDF dengan menggunakan `PdfSaveOptions` alih-alih `PsSaveOptions`.

**Q: Bagaimana cara mengubah ukuran gradien secara dinamis?**  
A: Hitung dimensi persegi panjang pada waktu berjalan dan berikan nilai tersebut ke konstruktor `Rectangle2D` dan `AffineTransform`.

---

**Terakhir Diperbarui:** 2026-09-14  
**Diuji Dengan:** Aspose.Page for Java 24.11 (latest)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Gradien Radial di PostScript dengan Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Cara Mengonversi PostScript ke PDF Menggunakan Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Tutorial Transparansi Aspose.Page – Tambahkan Transparansi di PostScript Java](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
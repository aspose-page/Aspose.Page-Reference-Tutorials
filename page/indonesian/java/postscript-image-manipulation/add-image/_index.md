---
date: 2026-08-23
description: Pelajari cara menggunakan aspose.page image manipulation java untuk menyisipkan
  dan memutar gambar dalam file PostScript dengan contoh Java yang jelas.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Tambahkan Gambar di PostScript Java
og_description: Pelajari cara menggunakan aspose.page image manipulation java untuk
  menyisipkan dan memutar gambar dalam file PostScript, dengan contoh kode Java langkah
  demi langkah.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Cara menggunakan aspose.page image manipulation java untuk menambahkan gambar
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Cara menggunakan aspose.page image manipulation java untuk menambahkan gambar
url: /id/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan aspose.page image manipulation java untuk menambahkan gambar

## Pendahuluan
Pada tutorial ini Anda akan belajar cara **menggunakan aspose.page image manipulation java** untuk membuat file PostScript, menyisipkan gambar raster, dan menerapkan transformasi translasi‑dan‑rotasi. Pada akhir panduan Anda akan dapat menghasilkan output PostScript yang pixel‑perfect dari Java—ideal untuk pelaporan otomatis, alur pencetakan, atau alur kerja apa pun yang memerlukan penempatan gambar yang tepat di dalam dokumen PostScript.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Page for Java  
- **Bisakah saya menambahkan beberapa gambar?** Yes – repeat the transform and draw steps for each image  
- **Apakah saya memerlukan lisensi untuk pengembangan?** A free trial works for testing; a license is required for production  
- **Versi Java mana yang didukung?** Java 8 and later  
- **Apakah rotasi gambar didukung?** Absolutely – use `AffineTransform.rotate()`

## Apa itu aspose.page image manipulation java?
`aspose.page image manipulation java` adalah API Aspose.Page yang memungkinkan Anda secara programatis membangun, mengedit, dan merender dokumen PostScript dari kode Java, termasuk kontrol penuh atas penempatan gambar, skala, dan rotasi. Dengan API ini Anda menghindari sintaks PostScript tingkat rendah dan membiarkan perpustakaan menangani konversi format serta penyisipan secara internal.

## Mengapa menggunakan aspose.page untuk manipulasi gambar?
Aspose.Page menyediakan **lebih dari 50 format gambar** (termasuk JPEG, PNG, BMP, TIFF) dan dapat menyisipkannya ke dalam PostScript tanpa memuat seluruh dokumen ke memori, memungkinkan pemrosesan file dengan ratusan halaman sambil menjaga penggunaan memori di bawah 100 MB pada server tipikal. API tingkat tinggi mengabstraksi perintah PostScript yang kompleks, sehingga Anda menulis kode Java yang ringkas alih‑alih operator PS mentah.

## Prasyarat
- Java Development Kit (JDK) 8 atau lebih baru terpasang.  
- Perpustakaan Aspose.Page for Java – unduh **[Halaman unduhan Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- Pemahaman dasar tentang sintaks Java dan pemrograman berorientasi objek.

## Apa itu create postscript java?
Membuat file PostScript dari Java berarti secara programatis menghasilkan dokumen `.ps` yang menggambarkan tata letak halaman, grafik vektor, dan gambar raster menggunakan bahasa PostScript. Aspose.Page menerjemahkan panggilan Java Anda menjadi instruksi PostScript yang valid, memungkinkan Anda menghasilkan file siap cetak tanpa interpreter PostScript terpisah.

## Cara menambahkan gambar dengan translasi dan rotasi langkah demi langkah

Muat gambar Anda, terapkan `AffineTransform`, dan gambar ke halaman. Langkah‑langkah berikut menjelaskan urutan tepat yang harus Anda ikuti.

### Langkah 1: menyimpan grafik
Menyimpan keadaan grafik mengisolasi transformasi Anda sehingga dapat dikembalikan nanti. Ini setara dengan operator `gsave` dalam PostScript mentah.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Langkah 2: translasi dan transformasi (translasi dan rotasi gambar)
Pertama, buat `BufferedImage` dari file sumber, lalu bangun `AffineTransform` yang mentranslasi gambar ke koordinat yang diinginkan dan memutarnya di sekitar pusatnya. `AffineTransform.rotate` mengharapkan sudut dalam radian, jadi konversikan derajat dengan `Math.toRadians(degrees)`.

**AffineTransform** adalah kelas Java yang merepresentasikan transformasi afinn 2‑D seperti translasi, rotasi, skala, atau shearing.  
**BufferedImage** adalah kelas Java yang menyimpan gambar dalam memori sebagai raster piksel.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Langkah 3: menambahkan gambar ke dokumen
Setelah mengonfigurasi transformasi, gambar gambar ke halaman saat ini. Perpustakaan secara otomatis mengonversi `BufferedImage` menjadi aliran gambar PostScript yang sesuai.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Langkah 4: mengembalikan grafik
Memanggil restore (`grestore`) mengembalikan keadaan grafik ke kondisi sebelum penyimpanan, memastikan perintah menggambar berikutnya tidak terpengaruh oleh transformasi sebelumnya.

```java
document.drawImage(image, transform, null);
```

### Langkah 5: menutup halaman saat ini dan menyimpan
Selesaikan halaman, tutup dokumen, dan tulis file output ke disk.

```java
document.writeGraphicsRestore();
```

Anda dapat mengulangi urutan di atas untuk menyisipkan gambar tambahan, menyesuaikan koordinat translasi dan sudut rotasi setiap kali.

## Masalah umum dan solusi
- **FileNotFoundException:** Pastikan bahwa `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) dan nama file gambar cocok persis.  
- **ImageIO.read mengembalikan null:** Pastikan format gambar termasuk dalam daftar yang didukung (JPEG, PNG, BMP, GIF, TIFF).  
- **Sudut rotasi tidak tepat:** `AffineTransform.rotate` bekerja dengan radian; gunakan `Math.toRadians(degrees)` untuk mengonversi dari derajat.  
- **Lonjakan memori pada halaman besar:** Gunakan `Document.save` dengan `saveOptions.setCompress(true)` untuk mengurangi jejak memori.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?**  
A: Perpustakaan inti hanya untuk Java, tetapi Aspose menyediakan API setara untuk .NET, C++, dan Python, masing‑masing disesuaikan dengan platformnya.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?**  
A: Ya, Anda dapat mengakses percobaan gratis **[Halaman percobaan gratis Aspose.Page](https://releases.aspose.com/)**.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
A: Anda dapat memperoleh lisensi sementara **[halaman permintaan lisensi sementara](https://purchase.aspose.com/temporary-license/)**.

**Q: Di mana saya dapat menemukan dukungan komunitas dan diskusi terkait Aspose.Page untuk Java?**  
A: Kunjungi **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk bantuan komunitas.

**Q: Apakah ada sumber tambahan untuk membeli Aspose.Page untuk Java?**  
A: Anda dapat membeli perpustakaan **[Halaman pembelian Aspose.Page](https://purchase.aspose.com/buy)**.

## Kesimpulan
Anda sekarang memiliki contoh lengkap, end‑to‑end dari **aspose.page image manipulation java** yang membuat file PostScript, mentranslasi dan memutar gambar, serta menyimpan hasilnya. Jelajahi **[dokumentasi](https://reference.aspose.com/page/java/)** lengkap untuk menemukan fitur lanjutan seperti grafik vektor, ukuran halaman khusus, dan rendering teks.

---

**Terakhir Diperbarui:** 2026-08-23  
**Diuji Dengan:** Aspose.Page for Java 23.11  
**Penulis:** Aspose  

```java
document.closePage();
document.save();
```

## Tutorial Terkait

- [Cara Mengonversi PostScript ke PDF Menggunakan Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Cara Menambahkan Gradien: Gradien Diagonal di Java PostScript menggunakan Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Cara Menambahkan Pola Hatch di Java PostScript dengan Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-09
description: Pelajari cara membuat dokumen PostScript dengan Java serta memindahkan
  dan memutar gambar menggunakan Aspose.Page untuk manipulasi gambar yang mulus.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Buat Dokumen PostScript Java – Tambahkan Gambar dalam PostScript Java
url: /id/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Dokumen PostScript Java – Menambahkan Gambar dalam PostScript Java

## Introduction
Dalam tutorial ini, Anda akan belajar cara **membuat dokumen PostScript Java** dan menyematkan gambar menggunakan pustaka Aspose.Page for Java. Kami akan memandu Anda melalui setiap langkah, mulai dari menyiapkan dokumen hingga menerapkan transformasi seperti operasi **translate and rotate image**. Pada akhir tutorial, Anda akan dapat menghasilkan file PostScript yang kaya secara programatis dan menyesuaikan penempatan gambar agar sesuai dengan kebutuhan tata letak Anda.

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the transform and draw steps  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** Absolutely – use `AffineTransform.rotate()`

## What is creating a PostScript document in Java?
Dokumen PostScript adalah file bahasa deskripsi halaman yang menggambarkan teks, grafik, dan gambar. Dengan menggunakan Aspose.Page, Anda dapat menghasilkan file-file ini secara programatis di Java, memberi Anda kontrol penuh atas tata letak, status grafik, dan penanganan gambar tanpa memerlukan interpreter PostScript.

## Why use Aspose.Page for image manipulation?
- **High‑level API:** Menyederhanakan perintah PostScript yang kompleks.  
- **Cross‑platform:** Berfungsi pada sistem operasi apa pun yang mendukung Java.  
- **Full graphics state control:** Mudah menyimpan, memulihkan, mentranslate, menskalakan, dan memutar grafik.  
- **No external dependencies:** Menangani pemuatan dan konversi gambar secara internal.

## Prerequisites
Sebelum kita masuk ke kode, pastikan Anda memiliki:

- Java Development Kit (JDK) terpasang di sistem Anda.  
- Pustaka Aspose.Page for Java. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/java/).  
- Pemahaman dasar tentang pemrograman Java.  

## Import Packages
Untuk memulai, impor paket-paket yang diperlukan dalam proyek Java Anda. Gunakan cuplikan kode berikut sebagai referensi:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Write Graphics Save
Langkah pertama melibatkan penulisan perintah graphics save ke dokumen. Ini memastikan bahwa setiap transformasi atau modifikasi yang dilakukan setelahnya dapat dibatalkan jika diperlukan.

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

## Step 2: Translate and Transform (translate and rotate image)
Selanjutnya, translate dokumen dan buat objek `BufferedImage` dari file gambar. Terapkan serangkaian transformasi seperti scaling dan rotation menggunakan `AffineTransform`. Di sinilah operasi **translate and rotate image** terjadi.

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

## Step 3: Add Image to Document
Sekarang, tambahkan gambar yang telah ditransformasi ke dokumen.

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
Setelah menambahkan gambar, tulis perintah graphics restore untuk menyelesaikan perubahan yang telah dibuat.

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
Tutup halaman saat ini dan simpan dokumen.

```java
document.closePage();
document.save();
```

Anda dapat mengulangi langkah-langkah ini untuk menambahkan beberapa gambar atau menyesuaikan transformasi sesuai kebutuhan Anda.

## Common Issues and Solutions
- **FileNotFoundException:** Pastikan jalur `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) dan nama file gambar cocok persis.  
- **ImageIO.read returns null:** Verifikasi bahwa format gambar didukung (mis., JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` mengharapkan radian. Konversi derajat ke radian (`Math.toRadians(degrees)`) jika diperlukan.  

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page primarily supports Java, but there are versions available for other programming languages as well.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find community support and discussions related to Aspose.Page for Java?**  
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community support.

**Q: Are there any additional resources for purchasing Aspose.Page for Java?**  
A: You can buy the library [here](https://purchase.aspose.com/buy).

## Conclusion
Selamat! Anda telah berhasil mempelajari cara **membuat dokumen PostScript Java** dan menyematkan gambar menggunakan Aspose.Page for Java. Jelajahi [dokumentasi](https://reference.aspose.com/page/java/) untuk fitur dan fungsionalitas lanjutan, seperti grafik vektor, rendering teks, dan ukuran halaman khusus.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-02-15
description: Pelajari cara membuat dokumen PostScript Java dan menghasilkan file dokumen
  PostScript dengan translasi serta rotasi gambar menggunakan Aspose.Page untuk Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Buat PostScript Java – Tambahkan Gambar di PostScript Java
url: /id/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat PostScript Java – Tambahkan Gambar dalam PostScript Java

## Pendahuluan
Dalam tutorial ini, Anda akan belajar cara **create postscript java** dokumen dan menyematkan gambar menggunakan pustaka Aspose.Page for Java. Kami akan memandu Anda melalui setiap langkah, mulai dari menginisialisasi file PostScript baru hingga menerapkan transformasi **translate and rotate image**. Pada akhir tutorial, Anda akan dapat menghasilkan file PostScript secara programatis dan mengontrol penempatan gambar dengan akurasi pixel‑perfect—sempurna untuk pelaporan otomatis, alur kerja pencetakan, atau skenario apa pun yang memerlukan output **generate postscript document** dari Java.

## Jawaban Cepat
- **Library apa yang dibutuhkan?** Aspose.Page for Java  
- **Bisakah saya menambahkan beberapa gambar?** Yes – repeat the transform and draw steps  
- **Apakah saya memerlukan lisensi untuk pengembangan?** A free trial works for testing; a license is required for production  
- **Versi Java apa yang didukung?** Java 8 and later  
- **Apakah rotasi gambar didukung?** Absolutely – use `AffineTransform.rotate()`  

## Apa itu create postscript java?
Operasi **create postscript java** menghasilkan file deskripsi halaman PostScript yang mengkodekan teks, grafik vektor, dan gambar raster. Dengan Aspose.Page Anda dapat membangun file-file ini langsung dari kode Java, memberi Anda kontrol programatis penuh atas tata letak, skala, dan rotasi tanpa memerlukan interpreter PostScript terpisah.

## Mengapa menggunakan Aspose.Page untuk manipulasi gambar?
- **High‑level API:** Menyederhanakan perintah PostScript tingkat rendah menjadi metode Java yang sederhana.  
- **Cross‑platform:** Berjalan pada sistem operasi apa pun yang mendukung Java.  
- **Full graphics‑state control:** Menyimpan, memulihkan, mentranslate, menskalakan, dan memutar grafik sesuka hati.  
- **No external dependencies:** Menangani pemuatan gambar, konversi format, dan penyematan secara internal.

## Prasyarat
Sebelum kita menyelam ke dalam kode, pastikan Anda memiliki:

- Java Development Kit (JDK) terinstal pada sistem Anda.  
- Pustaka Aspose.Page for Java. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/java/).  
- Pemahaman dasar tentang pemrograman Java.  

## Impor Paket
Untuk memulai, impor paket yang diperlukan dalam proyek Java Anda. Gunakan cuplikan kode berikut sebagai referensi:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Langkah 1: Tulis Penyimpanan Grafik
Langkah pertama melibatkan penulisan penyimpanan grafik ke dokumen. Ini memastikan bahwa setiap transformasi atau modifikasi yang dilakukan setelahnya dapat dibatalkan jika diperlukan.

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

## Langkah 2: Translate dan Transform (translate and rotate image)
Selanjutnya, translate dokumen dan buat objek `BufferedImage` dari file gambar. Terapkan serangkaian transformasi seperti skala dan rotasi menggunakan `AffineTransform`. Di sinilah operasi **translate and rotate image** terjadi.

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

## Langkah 3: Tambahkan Gambar ke Dokumen
Sekarang, tambahkan gambar yang telah ditransformasi ke dokumen.

```java
document.drawImage(image, transform, null);
```

## Langkah 4: Tulis Pemulihan Grafik
Setelah menambahkan gambar, tulis pemulihan grafik untuk menyelesaikan perubahan yang dibuat.

```java
document.writeGraphicsRestore();
```

## Langkah 5: Tutup Halaman Saat Ini dan Simpan
Tutup halaman saat ini dan simpan dokumen.

```java
document.closePage();
document.save();
```

Anda dapat mengulangi langkah-langkah ini untuk menambahkan beberapa gambar atau menyesuaikan transformasi sesuai kebutuhan Anda.

## Masalah Umum dan Solusinya
- **FileNotFoundException:** Pastikan jalur `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) dan nama file gambar cocok persis.  
- **ImageIO.read returns null:** Verifikasi bahwa format gambar didukung (mis., JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` mengharapkan radian. Konversi derajat ke radian (`Math.toRadians(degrees)`) jika diperlukan.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page for Java dengan bahasa pemrograman lain?**  
A: Aspose.Page terutama mendukung Java, tetapi ada versi yang tersedia untuk bahasa pemrograman lain juga.

**Q: Apakah ada trial gratis yang tersedia untuk Aspose.Page for Java?**  
A: Ya, Anda dapat mengakses trial gratis [di sini](https://releases.aspose.com/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page for Java?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dukungan komunitas dan diskusi terkait Aspose.Page for Java?**  
A: Kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

**Q: Apakah ada sumber tambahan untuk membeli Aspose.Page for Java?**  
A: Anda dapat membeli pustaka tersebut [di sini](https://purchase.aspose.com/buy).

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara **create postscript java** dokumen dan menyematkan gambar menggunakan Aspose.Page for Java. Jelajahi [dokumentasi](https://reference.aspose.com/page/java/) untuk fitur dan fungsionalitas lanjutan, seperti grafik vektor, rendering teks, dan ukuran halaman khusus.

---

**Terakhir Diperbarui:** 2026-02-15  
**Diuji Dengan:** Aspose.Page for Java 23.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
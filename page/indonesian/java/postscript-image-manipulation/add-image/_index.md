---
title: Tambahkan Gambar di Java PostScript
linktitle: Tambahkan Gambar di Java PostScript
second_title: Aspose.Halaman Java API
description: Jelajahi integrasi Aspose.Page Java yang mulus dalam tutorial tentang menambahkan gambar ke dokumen PostScript. Tingkatkan kemampuan manipulasi dokumen Anda.
weight: 10
url: /id/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gambar di Java PostScript

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menambahkan gambar ke dokumen Java PostScript menggunakan pustaka Aspose.Page untuk Java. Aspose.Page adalah perpustakaan canggih yang menyediakan berbagai fitur untuk bekerja dengan file PostScript, memungkinkan pengembang memanipulasi dan menyempurnakan dokumen mereka dengan lancar.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
- Pemahaman dasar tentang pemrograman Java.
## Paket Impor
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
## Langkah 1: Tulis Simpan Grafik
Langkah pertama melibatkan penulisan grafik, simpan ke dokumen. Hal ini memastikan bahwa setiap transformasi atau modifikasi yang dilakukan setelahnya dapat dibatalkan jika diperlukan.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## Langkah 2: Terjemahkan dan Transformasi
Selanjutnya, terjemahkan dokumen dan buat objek BufferedImage dari file gambar. Terapkan serangkaian transformasi seperti penskalaan dan rotasi menggunakan AffineTransform.
```java
document.translate(100, 100);
// Buat objek BufferedImage dari file gambar
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Buat transformasi gambar
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## Langkah 3: Tambahkan Gambar ke Dokumen
Sekarang, tambahkan gambar yang diubah ke dokumen.
```java
document.drawImage(image, transform, null);
```
## Langkah 4: Tulis Pemulihan Grafik
Setelah menambahkan gambar, tulis pemulihan grafis untuk menyelesaikan perubahan yang dilakukan.
```java
document.writeGraphicsRestore();
```
## Langkah 5: Tutup Halaman Saat Ini dan Simpan
Tutup halaman saat ini dan simpan dokumen.
```java
document.closePage();
document.save();
```
Ulangi langkah-langkah ini untuk menambahkan beberapa gambar atau sesuaikan transformasi berdasarkan kebutuhan Anda.
## Kesimpulan
 Selamat! Anda telah berhasil mempelajari cara menambahkan gambar ke dokumen Java PostScript menggunakan Aspose.Page untuk Java. Jelajahi[dokumentasi](https://reference.aspose.com/page/java/) untuk fitur dan fungsi lebih lanjut.
## FAQ
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi ada versi yang tersedia untuk bahasa pemrograman lain juga.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dukungan komunitas dan diskusi terkait Aspose.Page untuk Java?
 Mengunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.
### Apakah ada sumber daya tambahan untuk membeli Aspose.Page untuk Java?
 Anda dapat membeli perpustakaan[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

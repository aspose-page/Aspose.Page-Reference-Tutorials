---
title: Sesuaikan Java PostScript - Menambahkan Persegi Panjang dengan Aspose.Page
linktitle: Tambahkan Persegi Panjang di Java PostScript
second_title: Aspose.Halaman Java API
description: Jelajahi panduan langkah demi langkah tentang menambahkan persegi panjang cerah ke dokumen Java PostScript menggunakan Aspose.Page untuk Java. Tingkatkan penyesuaian dokumen Anda dengan mudah!
type: docs
weight: 11
url: /id/java/postscript-shapes/add-rectangle/
---
## Perkenalan
Apakah Anda ingin menyempurnakan dokumen Java PostScript Anda dengan persegi panjang yang cerah? Tidak perlu mencari lagi! Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menggunakan Aspose.Page untuk Java untuk menambahkan persegi panjang ke dokumen PostScript Anda. Aspose.Page adalah perpustakaan canggih yang menyediakan fitur canggih untuk bekerja dengan file PostScript, menjadikannya pilihan ideal bagi pengembang yang ingin memanipulasi dan menyesuaikan dokumen mereka.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.
-  Aspose.Page untuk perpustakaan Java diinstal. Jika tidak, unduh dari[Aspose.Page untuk dokumentasi Java](https://reference.aspose.com/page/java/).
- Lingkungan pengembangan Java yang disiapkan di mesin Anda.
## Paket Impor
Di proyek Java Anda, mulailah dengan mengimpor paket yang diperlukan:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Tutorial: Menambahkan Persegi Panjang di Java PostScript
## Langkah 1: Atur Cat untuk Mengisi Persegi Panjang
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
// Atur cat untuk mengisi persegi panjang
document.setPaint(Color.ORANGE);        
// Isi persegi panjang pertama
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Langkah 2: Atur Cat untuk Membelai Persegi Panjang
```java
// Atur cat untuk membelai persegi panjang
document.setPaint(Color.RED);
// Atur pukulan
document.setStroke(new BasicStroke(3));
// Goresan (garis besar) persegi panjang kedua
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Langkah 3: Tutup Halaman Saat Ini dan Simpan Dokumen
```java
// Tutup halaman saat ini
document.closePage();
// Simpan dokumennya
document.save();
```
Selamat! Anda telah berhasil menambahkan persegi panjang cerah ke dokumen Java PostScript Anda menggunakan Aspose.Page.
## Kesimpulan
Dalam tutorial ini, kami telah menjelajahi proses menyempurnakan dokumen Java PostScript Anda dengan persegi panjang menggunakan Aspose.Page untuk Java. Perpustakaan yang kuat ini membuka banyak kemungkinan bagi pengembang yang ingin menyesuaikan dan memanipulasi dokumen mereka dengan mudah.
Bersenang-senang bereksperimen dengan berbagai bentuk dan warna untuk membuat dokumen Anda menarik secara visual!
## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi perpustakaan serupa tersedia untuk bahasa lain.
### Apakah ada versi uji coba Aspose.Page untuk Java yang tersedia?
 Ya, Anda dapat menjelajahi fitur Aspose.Page untuk Java dengan[versi percobaan gratis](https://releases.aspose.com/).
### Di mana saya dapat menemukan bantuan dan diskusi tambahan?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk terlibat dengan masyarakat dan mendapatkan bantuan.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli versi berlisensi Aspose.Page untuk Java?
 Beli versi berlisensi[Di Sini](https://purchase.aspose.com/buy).
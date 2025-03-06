---
title: Menambahkan Gambar Java XPS - Panduan Sederhana dengan Aspose.Page
linktitle: Tambahkan Gambar di Java XPS
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan gambar dengan mudah ke dokumen XPS di Java menggunakan Aspose.Page. Tingkatkan pemrosesan dokumen Anda dengan panduan langkah demi langkah ini.
weight: 10
url: /id/java/xps-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Gambar Java XPS - Panduan Sederhana dengan Aspose.Page

Dalam dunia pengembangan Java, kemampuan bekerja dengan dokumen XPS sangat penting untuk berbagai aplikasi. Aspose.Page untuk Java menyediakan seperangkat alat canggih untuk memanipulasi dokumen XPS, dan satu tugas penting adalah menambahkan gambar. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk Java.
## Perkenalan
Menambahkan gambar ke dokumen XPS merupakan persyaratan umum di banyak aplikasi Java, mulai dari pembuatan laporan hingga pemrosesan dokumen. Aspose.Page untuk Java menyederhanakan tugas ini, menawarkan metode efisien untuk mengintegrasikan gambar ke dalam file XPS Anda dengan lancar. Dalam tutorial ini, kami akan mendemonstrasikan cara menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk Java.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Page for Java Library: Unduh dan instal perpustakaan Aspose.Page for Java dari[situs web](https://releases.aspose.com/page/java/).
2. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di mesin Anda.
Sekarang, mari kita lanjutkan ke langkah berikutnya.
## Paket Impor
Dalam proyek Java Anda, impor paket Aspose.Page for Java yang diperlukan untuk mengakses kelas dan metode yang diperlukan.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```
## Langkah 1: Siapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat dokumen XPS dan file gambar akan disimpan.
```java
String dataDir = "Your Document Directory";
```
## Langkah 2: Buat Dokumen XPS Baru
Inisialisasi dokumen XPS baru menggunakan cuplikan kode berikut:
```java
XpsDocument doc = new XpsDocument();
```
## Langkah 3: Tambahkan Gambar ke Dokumen XPS
Untuk menambahkan gambar, buat jalur di dokumen XPS, dan atur kuas gambar menggunakan file gambar dan koordinat yang disediakan.
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```
## Langkah 4: Simpan Dokumen XPS yang Dihasilkan
Simpan dokumen XPS yang dimodifikasi ke direktori yang Anda tentukan.
```java
doc.save(dataDir + "AddImage_out.xps");
```
Ulangi langkah-langkah ini untuk menambahkan lebih banyak gambar atau menyesuaikan gambar yang sudah ada sesuai dengan kebutuhan proyek Anda.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk Java. Keterampilan ini sangat berharga untuk meningkatkan daya tarik visual aplikasi dan dokumen Java Anda.
### Pertanyaan yang Sering Diajukan
### Bisakah saya menambahkan banyak gambar ke dokumen XPS yang sama menggunakan Aspose.Page untuk Java?
Ya, Anda dapat menambahkan banyak gambar dengan mengulangi langkah-langkah yang diuraikan dalam tutorial ini untuk setiap gambar.
### Format gambar apa yang didukung oleh Aspose.Page untuk Java?
Aspose.Page untuk Java mendukung berbagai format gambar, termasuk TIFF, JPEG, PNG, dan GIF.
### Apakah ada versi uji coba Aspose.Page untuk Java yang tersedia?
 Ya, Anda bisa mendapatkan uji coba gratis Aspose.Page untuk Java dari[Link ini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda dapat memperoleh lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dukungan tambahan atau mendiskusikan masalah terkait Aspose.Page untuk Java?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk mencari bantuan, berbagi pengalaman, dan terhubung dengan komunitas Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

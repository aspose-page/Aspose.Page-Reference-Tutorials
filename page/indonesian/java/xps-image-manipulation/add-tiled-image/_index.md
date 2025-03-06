---
title: Tambahkan Gambar Berubin di Java XPS
linktitle: Tambahkan Gambar Berubin di Java XPS
second_title: Aspose.Halaman Java API
description: Jelajahi manipulasi dokumen Java XPS yang mulus dengan Aspose.Page. Pelajari cara menambahkan gambar ubin dengan mudah menggunakan panduan langkah demi langkah ini.
weight: 11
url: /id/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gambar Berubin di Java XPS

## Perkenalan
Dalam dunia perkembangan Java yang dinamis, kebutuhan akan manipulasi dan pembuatan dokumen yang efisien semakin meningkat. Aspose.Page untuk Java muncul sebagai alat yang ampuh, memberikan pengembang kemampuan untuk bekerja dengan dokumen XPS secara lancar. Tutorial ini berfokus pada tugas tertentu – menambahkan gambar ubin ke dokumen Java XPS.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Page for Java: Unduh dan instal Aspose.Page for Java dari[situs web](https://releases.aspose.com/page/java/).
3. Direktori Dokumen Anda: Pilih atau buat direktori tempat Anda ingin menyimpan dokumen XPS Anda.
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Sekarang, mari kita uraikan proses penambahan gambar ubin ke dokumen Java XPS menjadi langkah-langkah yang jelas dan mudah dikelola.
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan menyiapkan proyek Java Anda, pastikan Aspose.Page untuk Java terintegrasi dengan benar.
## Langkah 2: Buat Dokumen XPS
Inisialisasi dokumen XPS baru menggunakan kode berikut:
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```
## Langkah 3: Tentukan Jalur Gambar Berubin
Tentukan jalur ke gambar ubin yang ingin Anda tambahkan ke dokumen XPS.
## Langkah 4: Tambahkan Gambar Berubin
Gunakan cuplikan kode di bawah ini untuk menambahkan gambar ubin ke dokumen XPS:
```java
// Gambar ubin
// Persegi panjang terisi ImageBrush di kanan atas bawah
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Langkah 5: Simpan Dokumen
Terakhir, simpan dokumen XPS yang dihasilkan menggunakan kode di bawah ini:
```java
// Simpan dokumen XPS yang dihasilkan
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Ulangi langkah-langkah ini untuk dengan mudah memasukkan gambar ubin ke dalam dokumen Java XPS Anda menggunakan Aspose.Page.
## Kesimpulan
Aspose.Page untuk Java menyederhanakan proses bekerja dengan dokumen XPS, menawarkan pengembang solusi efisien untuk manipulasi dokumen. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menambahkan gambar ubin ke dokumen Java XPS Anda.

## FAQ
### Apakah Aspose.Page kompatibel dengan semua versi Java?
 Aspose.Page dirancang untuk bekerja dengan berbagai versi Java. Pastikan kompatibilitas dengan memeriksa dokumentasi[Di Sini](https://reference.aspose.com/page/java/).
### Bisakah saya menggunakan Aspose.Page untuk proyek komersial?
Ya, Aspose.Page menawarkan lisensi komersial. Belilah[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia?
 Ya, jelajahi fitur Aspose.Page dengan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan dan diskusi komunitas?
 Terlibat dengan komunitas Aspose.Page di[forum](https://forum.aspose.com/c/page/39).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

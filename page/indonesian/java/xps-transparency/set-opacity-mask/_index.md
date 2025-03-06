---
title: Setel Masker Opacity di Java XPS
linktitle: Setel Masker Opacity di Java XPS
second_title: Aspose.Halaman Java API
description: Temukan kekuatan pengaturan opacity mask di Java XPS dengan Aspose.Page. Ikuti panduan langkah demi langkah kami untuk pengalaman dokumen yang ditingkatkan secara visual.
weight: 11
url: /id/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Setel Masker Opacity di Java XPS

## Perkenalan
Selamat datang di panduan komprehensif kami tentang pengaturan opacity mask di Java XPS menggunakan Aspose.Page. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan dokumen XPS, menambahkan kanvas, dan menerapkan masker opacity ke persegi panjang menggunakan fitur canggih Aspose.Page untuk Java.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:
- Pemahaman dasar tentang pemrograman Java.
-  Aspose.Page untuk perpustakaan Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
-  Lisensi yang valid untuk Aspose.Page. Jika Anda tidak memilikinya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
- Lingkungan pengembangan yang disiapkan untuk menjalankan aplikasi Java.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda. Pastikan Anda memiliki perpustakaan Aspose.Page terintegrasi dengan benar. Di bawah ini cuplikan untuk memandu Anda:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Sekarang, mari kita pecahkan kode contoh menjadi beberapa langkah:
## Langkah 1: Buat Dokumen XPS Baru
```java
// Buat dokumen XPS baru
XpsDocument doc = new XpsDocument();
```
## Langkah 2: Tambahkan Kanvas
```java
// Kanvas baru
XpsCanvas canvas = doc.addCanvas();
```
## Langkah 3: Tambahkan Persegi Panjang dengan Opacity Mask
```java
// Persegi panjang di kiri tengah dengan opacity ditutupi oleh ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Langkah 4: Atur Opacity Mask dengan ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Langkah 5: Simpan Dokumen XPS yang Dihasilkan
```java
// Simpan dokumen XPS yang dihasilkan
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Ikuti langkah-langkah ini dengan hati-hati untuk memasukkan masker opacity ke dalam dokumen Java XPS Anda menggunakan Aspose.Page.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatur opacity mask di Java XPS dengan Aspose.Page. Fitur ini menambahkan lapisan kekayaan visual pada dokumen Anda, menjadikannya lebih menarik dan dinamis.
## FAQ
### Apakah Aspose.Page kompatibel dengan semua lingkungan pengembangan Java?
Ya, Aspose.Page dirancang untuk bekerja secara lancar dengan berbagai lingkungan pengembangan Java.
### Bisakah saya menggunakan Aspose.Page tanpa lisensi?
Meskipun Anda dapat menggunakan Aspose.Page tanpa lisensi, disarankan untuk mendapatkannya untuk mendapatkan berbagai fitur dan dukungan penuh.
### Apakah ada batasan pada versi uji coba?
Versi uji coba mungkin memiliki beberapa keterbatasan fitur. Dianjurkan untuk memeriksa dokumentasi untuk detailnya.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Page?
 Anda dapat mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas atau membeli lisensi untuk bantuan premium.
### Apakah ada jaminan uang kembali untuk Aspose.Page?
 Mengacu kepada[halaman pembelian](https://purchase.aspose.com/buy) untuk informasi tentang kebijakan pengembalian dana.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

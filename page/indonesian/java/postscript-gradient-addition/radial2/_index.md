---
date: 2026-02-13
description: Pelajari cara mengisi bentuk dengan gradien dan menggambar lingkaran
  dengan gradien di Java PostScript menggunakan Aspose.Page. Panduan langkah demi
  langkah dengan kode dan tips.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Isi Bentuk dengan Gradien: Contoh Radial Java PostScript'
url: /id/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Isi Bentuk dengan Gradien: Contoh Radial PostScript Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **mengisi bentuk dengan gradien** dengan membangun contoh gradien radial untuk dokumen PostScript menggunakan Aspose.Page untuk Java. Kami akan membimbing Anda melalui setiap langkah—dari menyiapkan proyek hingga merender lingkaran yang terisi gradien radial yang halus—sehingga Anda dapat menambahkan grafik yang menarik secara visual ke aplikasi Java Anda secara instan.

## Jawaban Cepat
- **Apa yang dibuat tutorial ini?** Sebuah file PostScript (`.ps`) yang berisi lingkaran terisi gradien radial.  
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page untuk Java (versi terbaru).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh yang berfungsi.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi; versi percobaan gratis dapat digunakan untuk pengembangan.  
- **Bisakah saya menggunakan kembali kode ini untuk PDF atau SVG?** Ya—Aspose.Page mendukung banyak format output dengan perubahan minimal.

## Cara Mengisi Bentuk dengan Gradien di PostScript
Sebelum masuk ke kode, mari kita jelaskan mengapa “mengisi bentuk dengan gradien” penting. Menggunakan gradien memberi grafik Anda nuansa profesional dan tiga‑dimensi tanpa perlu gambar raster. Dengan Aspose.Page Anda dapat menerapkan logika gradien yang sama pada bentuk vektor apa pun—lingkaran, persegi panjang, atau jalur khusus—di semua format output yang didukung (PostScript, PDF, SVG).

## Apa Itu Gradien Radial?
Gradien radial mengubah warna secara outward dari titik pusat, menciptakan perpaduan melingkar yang halus. Ini ideal untuk highlight, latar belakang tombol, atau visual apa pun yang memerlukan efek “cahaya” alami.

## Mengapa Menggunakan Aspose.Page untuk Gradien Radial?
- **Rendering independen perangkat** – bekerja sama pada PostScript, PDF, SVG, dan lainnya.  
- **Integrasi penuh dengan Java** – tanpa kode native, hanya API Java biasa.  
- **Output berkualitas tinggi** – mendukung anti‑aliasing dan kontrol ruang warna.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Familiaritas dasar dengan pemrograman Java.  
- JDK 8 atau yang lebih baru terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk Java (unduh dari [dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Impor Paket
Pertama, impor kelas‑kelas yang diperlukan. Ini mencakup tipe grafik AWT standar dan API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Langkah 1: Siapkan Direktori Dokumen
Tentukan folder tempat file PostScript yang dihasilkan akan disimpan. Ganti placeholder dengan jalur aktual di sistem Anda.

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: Buat Output Stream
Buka `FileOutputStream` yang mengarah ke file `.ps` target. Stream ini menyalurkan data biner yang dihasilkan oleh Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Langkah 3: Buat Opsi Penyimpanan
Instansiasi `PsSaveOptions`. Anda dapat menyesuaikan ukuran halaman, kompresi, dll., tetapi nilai default sudah cukup untuk contoh ini.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Langkah 4: Buat Dokumen PS
Buat objek `PsDocument`, dengan memberikan output stream dan opsi penyimpanan. Flag `false` memberi tahu Aspose.Page untuk tidak membuka halaman secara otomatis (kita akan melakukannya secara manual).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 5: Buat Lingkaran
Kita akan menggambar lingkaran menggunakan `Ellipse2D.Float`. Parameternya adalah `(x, y, width, height)`. Menetapkan lebar = tinggi menghasilkan lingkaran sempurna.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Cara Menggambar Lingkaran dengan Gradien
Sekarang kita memiliki bentuk, langkah selanjutnya adalah **menggambar lingkaran dengan gradien**. Dengan menerapkan `RadialGradientPaint` pada lingkaran, operasi pengisian secara otomatis akan menggunakan gradien yang kita definisikan.

## Langkah 6: Definisikan Warna Gradien
Siapkan dua array: satu untuk warna‑warna yang akan muncul dalam gradien dan satu lagi untuk posisi fraksional yang bersesuaian (0 = pusat, 1 = tepi).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Langkah 7: Buat AffineTransform
`AffineTransform` menskalakan dan mentranslasi gradien agar sesuai dengan lingkaran kita. Matriks `(scaleX, 0, 0, scaleY, translateX, translateY)` melakukan pekerjaan tersebut.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Langkah 8: Buat Radial Gradient Paint
Sekarang kita membangun objek `RadialGradientPaint`. Objek ini menerima titik pusat, radius, titik fokus, fraksi warna, array warna, metode siklus, ruang warna, dan transformasi yang baru saja kita definisikan.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Langkah 9: Atur Paint dan Isi Lingkaran
Terapkan paint gradien ke dokumen dan isi lingkaran yang telah didefinisikan sebelumnya. Ini adalah inti dari **contoh gradien radial** kami dan memperlihatkan cara **mengisi bentuk dengan gradien**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Langkah 10: Tutup Halaman dan Simpan Dokumen
Selesaikan halaman, tulis konten ke disk, dan tutup stream. File PostScript Anda kini siap dilihat dengan penampil PS apa pun.

```java
document.closePage();
document.save();
```

Selamat! Anda telah berhasil membuat contoh gradien radial dalam Java PostScript menggunakan Aspose.Page. Anda kini memiliki pola yang dapat digunakan kembali untuk **mengisi bentuk dengan gradien** yang dapat disesuaikan ke bentuk lain dan format output lainnya.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|---------|----------|
| **FileNotFoundException** saat membuka output stream | Pastikan `dataDir` mengarah ke folder yang ada dan Anda memiliki izin menulis. |
| Gradien tampak datar atau tidak muncul | Pastikan array `fractions` memiliki panjang yang sama dengan array `colors` dan `AffineTransform` menskalakan dengan benar. |
| Warna muncul terbalik | Tukar urutan warna dalam array `colors` atau sesuaikan koordinat titik `focus`. |

## Pertanyaan yang Sering Diajukan

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk Java?**  
J: Referensi API lengkap tersedia [di sini](https://reference.aspose.com/page/java/).

**T: Bagaimana cara mengunduh Aspose.Page untuk Java?**  
J: Unduh JAR terbaru dari [halaman rilis](https://releases.aspose.com/page/java/).

**T: Apakah ada versi percobaan gratis?**  
J: Ya—unduh versi percobaan [di sini](https://releases.aspose.com/).

**T: Bisakah saya memperoleh lisensi sementara untuk pengujian?**  
J: Tentu, minta satu dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat mendapatkan dukungan komunitas?**  
J: Bergabunglah dalam diskusi di [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Kesimpulan
Dalam panduan ini kami membangun **contoh gradien radial** lengkap untuk dokumen PostScript menggunakan Aspose.Page untuk Java. Dengan mengikuti langkah‑langkah tersebut, Anda kini memiliki pola yang dapat digunakan kembali untuk **mengisi bentuk dengan gradien**, yang dapat Anda adaptasi ke PDF, SVG, atau format lain yang didukung oleh Aspose.Page. Bereksperimenlah dengan warna, radius, dan bentuk yang berbeda untuk memperkaya proyek grafik Java Anda.

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Page untuk Java 24.11 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
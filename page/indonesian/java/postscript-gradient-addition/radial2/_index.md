---
date: 2026-09-09
description: Pelajari cara membuat gradien di Java PostScript dan menambahkan gradien
  ke bentuk menggunakan Aspose.Page. Ikuti panduan langkah demi langkah ini dengan
  kode dan tip.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient dengan Aspose.Page
og_description: Pelajari cara membuat gradien di Java PostScript dan menambahkan gradien
  ke bentuk menggunakan Aspose.Page. Ikuti panduan langkah demi langkah ini dengan
  kode dan tip.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Cara membuat gradien di Java PostScript dengan radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Cara membuat gradien di Java PostScript dengan radial fill
url: /id/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gradien di Java PostScript dengan isian radial

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara membuat gradien** grafik dalam dokumen PostScript menggunakan Java dan Aspose.Page. Kami akan membimbing Anda melalui setiap langkah—dari penyiapan proyek hingga merender sebuah lingkaran yang diisi dengan gradien radial halus—sehingga Anda dapat **menambahkan gradien ke objek bentuk** secara instan dan meningkatkan kualitas visual aplikasi Java Anda.

## Jawaban Cepat
- **Apa yang dibuat tutorial ini?** Sebuah file PostScript (`.ps`) yang berisi sebuah lingkaran yang diisi dengan gradien radial.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk Java (versi terbaru).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh yang berfungsi.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi; versi percobaan gratis dapat digunakan untuk pengembangan.  
- **Bisakah saya menggunakan kembali kode ini untuk PDF atau SVG?** Ya—Aspose.Page mendukung banyak format output dengan perubahan minimal.

## Cara mengisi bentuk dengan gradien di PostScript
Anda dapat mengisi sebuah bentuk dengan gradien radial di PostScript dengan membuat `PsDocument`, mendefinisikan `RadialGradientPaint`, menerapkannya ke bentuk target, dan akhirnya menyimpan dokumen. Alur kerja yang ringkas ini memungkinkan Anda menghasilkan grafik vektor yang tampak profesional tanpa gambar raster, dan kode yang sama dapat digunakan kembali untuk output PDF atau SVG. Proses ini sederhana dan bekerja secara konsisten di semua format yang didukung.

## Apa itu gradien radial?
Gradien radial mengubah warna secara menyebar dari titik pusat, menciptakan perpaduan melingkar yang halus. Ini ideal untuk sorotan, latar belakang tombol, atau visual apa pun yang membutuhkan efek “cahaya” alami. Dengan mengubah titik warna dan radius, Anda dapat mensimulasikan pencahayaan, kedalaman, dan sifat material dalam bentuk vektor murni.

## Mengapa menggunakan Aspose.Page untuk gradien radial?
Aspose.Page memungkinkan Anda menghasilkan grafik vektor yang independen terhadap perangkat dengan satu API Java. Ia mendukung lebih dari 50 format input dan output—termasuk PostScript, PDF, dan SVG—sementara mempertahankan akurasi warna dan anti‑aliasing untuk output resolusi tinggi. Perpustakaan ini juga menyediakan kelas gradien yang mudah digunakan, sehingga efek visual yang kompleks menjadi sederhana untuk diimplementasikan.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Pemahaman dasar tentang pemrograman Java.  
- JDK 8 atau yang lebih baru terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk Java (unduh dari [dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Impor paket
Pertama, impor kelas-kelas yang kita perlukan. Ini termasuk tipe grafik AWT standar dan API Aspose.Page.

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

## Langkah 1: menyiapkan direktori dokumen
Tentukan folder tempat file PostScript yang dihasilkan akan disimpan. Ganti placeholder dengan jalur aktual di sistem Anda.

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: membuat aliran output
`FileOutputStream` menulis byte mentah ke sebuah file, memungkinkan data biner disimpan. Membuka satu yang menargetkan file `.ps` memungkinkan Aspose.Page mengalirkan data PostScript yang dihasilkan langsung ke disk.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Langkah 3: membuat opsi penyimpanan
`PsSaveOptions` mengonfigurasi cara file PostScript disimpan, termasuk ukuran halaman dan kompresi. Anda dapat menyesuaikan pengaturan ini, tetapi nilai default sudah cukup untuk contoh ini.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Langkah 4: membuat dokumen ps
`PsDocument` merepresentasikan dokumen PostScript dalam memori dan menyediakan metode untuk menambahkan halaman dan grafik.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 5: membuat lingkaran
`Ellipse2D.Float` mendeskripsikan bentuk elips; ketika lebar = tinggi menjadi lingkaran sempurna. Objek ini akan menjadi kanvas untuk isian gradien kami.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Cara menggambar lingkaran dengan gradien
Untuk menggambar lingkaran dengan gradien radial, Anda memuat `RadialGradientPaint` ke dalam konteks grafik dan kemudian mengisi elips yang telah didefinisikan sebelumnya. Operasi tunggal ini melukis bentuk dengan transisi warna halus dari pusat ke luar, menciptakan efek visual yang menarik.

## Langkah 6: mendefinisikan warna gradien
Siapkan dua array: satu untuk warna-warna yang akan muncul dalam gradien dan satu lagi untuk posisi fraksional yang sesuai (0 = pusat, 1 = tepi).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Langkah 7: membuat affinetransform
`AffineTransform` adalah matriks yang dapat mentranslasi, memutar, menskalakan, atau memiringkan objek grafik. Di sini ia menskalakan dan mentranslasi gradien sehingga pas tepat di dalam lingkaran.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Langkah 8: membuat radial gradient paint
`RadialGradientPaint` membuat gradien warna radial berdasarkan titik pusat, radius, dan titik warna.

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

## Langkah 9: mengatur cat dan mengisi lingkaran
Terapkan cat gradien ke dokumen dan isi lingkaran yang telah didefinisikan sebelumnya. Ini adalah inti dari **contoh gradien radial** kami dan menunjukkan cara **mengisi bentuk dengan gradien**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Langkah 10: menutup halaman dan menyimpan dokumen
Selesaikan halaman, tulis konten ke disk, dan tutup aliran. File PostScript Anda kini siap dilihat dengan penampil PS apa pun.

```java
document.closePage();
document.save();
```

Selamat! Anda telah berhasil membuat contoh gradien radial dalam Java PostScript menggunakan Aspose.Page. Anda kini memiliki pola yang dapat digunakan kembali untuk **mengisi bentuk dengan gradien** yang dapat disesuaikan ke bentuk lain dan format output.

## Masalah umum dan solusi
| Masalah | Solusi |
|---------|----------|
| **FileNotFoundException** saat membuka aliran output | Verifikasi bahwa `dataDir` mengarah ke folder yang ada dan Anda memiliki izin menulis. |
| Gradien tampak datar atau hilang | Pastikan array `fractions` memiliki panjang yang sama dengan array `colors` dan bahwa `AffineTransform` menskalakan dengan benar. |
| Warna muncul terbalik | Tukar urutan warna dalam array `colors` atau sesuaikan koordinat titik `focus`. |

## Pertanyaan yang sering diajukan

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk Java?**  
A: Referensi API lengkap tersedia di [dokumentasi API Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q: Bagaimana saya dapat mengunduh Aspose.Page untuk Java?**  
A: Unduh JAR terbaru dari [halaman rilis](https://releases.aspose.com/page/java/).

**Q: Apakah tersedia versi percobaan gratis?**  
A: Ya—unduh versi percobaan dari [halaman unduhan percobaan gratis Aspose](https://releases.aspose.com/).

**Q: Bisakah saya mendapatkan lisensi sementara untuk pengujian?**  
A: Tentu saja, minta satu dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat mendapatkan dukungan komunitas?**  
A: Bergabunglah dalam diskusi di [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Kesimpulan
Dalam panduan ini kami membangun contoh **gradien radial** lengkap untuk dokumen PostScript menggunakan Aspose.Page untuk Java. Dengan mengikuti langkah-langkah, Anda kini memiliki pola yang dapat digunakan kembali untuk **mengisi bentuk dengan gradien**, yang dapat Anda sesuaikan ke PDF, SVG, atau format lain apa pun yang didukung oleh Aspose.Page. Bereksperimenlah dengan warna, radius, dan bentuk yang berbeda untuk memperkaya proyek grafik Java Anda.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Buat Gradien PostScript di Java – Tambahkan Gradien Vertikal](/page/java/postscript-gradient-addition/vertical/)
- [Buat Pola Tekstur di PostScript dengan Aspose.Page untuk Java](/page/java/postscript-texture-patterns/)
- [Tutorial Transparansi Aspose.Page – Tambahkan Transparansi di Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
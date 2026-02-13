---
date: 2026-02-13
description: Pelajari cara membuat gradien PostScript dengan gradien warna radial
  menggunakan Aspose.Page untuk Java. Panduan langkah demi langkah ini menunjukkan
  cara menambahkan gradien warna pada dokumen Anda.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Buat Gradien PostScript – Gradien Radial dalam Java
url: /id/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien Radial dalam Java PostScript dengan Aspose.Page

## Introduction
Jika Anda pernah perlu **membuat gradien PostScript** dengan transisi warna yang halus dan menarik, mempelajari cara menambahkan gradien radial adalah tempat yang tepat untuk memulai. Dalam tutorial ini kami akan memandu Anda melalui setiap langkah yang diperlukan untuk menghasilkan file PostScript yang berisi gradien radial yang indah, menggunakan perpustakaan **Aspose.Page for Java**. Pada akhir tutorial Anda akan memahami API, melihat contoh lengkap yang dapat dijalankan, dan mengetahui cara menyesuaikan warna, posisi, dan radius untuk memenuhi desain apa pun.

## Quick Answers
- **Perpustakaan apa yang membuat gradien radial dalam PostScript?** Aspose.Page for Java.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya mengubah bentuk gradien?** Ya – sesuaikan radius dan titik pusat dalam konstruktor `RadialGradientPaint`.

## How to Create PostScript Gradient with Radial Fill
Berikut ini Anda akan menemukan panduan singkat langkah‑demi‑langkah yang menunjukkan secara tepat cara **membuat konten gradien PostScript** menggunakan isian radial. Setiap langkah mencakup penjelasan singkat diikuti oleh blok kode asli (tidak diubah).

## What is a Radial Gradient?
Gradien radial melukis warna yang memancar keluar dari titik pusat, secara bertahap mencampur ke arah tepi. Tidak seperti gradien linear, transisi warna mengikuti pola melingkar (atau elips), yang ideal untuk sorotan, sorotan lampu, atau isian latar belakang yang lembut.

## Why Use Aspose.Page for Radial Gradients?
- **Kontrol penuh atas output PostScript** – tidak perlu menulis perintah PS tingkat rendah secara manual.  
- **Lintas‑platform** – berfungsi pada sistem operasi apa pun yang menjalankan Java.  
- **Manajemen warna kaya** – mendukung banyak titik warna, ruang warna yang berbeda, dan metode siklus.  
- **Siap integrasi** – menggabungkan dengan fitur Aspose.Page lainnya seperti teks, gambar, dan bentuk vektor.

## Prerequisites
Sebelum kami menyelam ke kode, pastikan Anda memiliki hal‑hal berikut:

- **Java Development Kit (JDK) 8+** – verifikasi dengan `java -version`.  
- **Aspose.Page for Java** – unduh JAR terbaru dari [halaman unduhan Aspose.Page resmi](https://releases.aspose.com/page/java/).  
- **IDE pilihan Anda** – Eclipse, IntelliJ IDEA, atau VS Code dengan ekstensi Java.  
- **Folder yang dapat ditulisi** – tempat file `.ps` yang dihasilkan akan disimpan.

## Import Packages
Pertama, impor kelas yang akan kita gunakan. Paket `java.awt` menyediakan objek cat gradien, sementara `com.aspose.eps` berisi kelas penanganan dokumen PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
Kita mulai dengan membuat aliran output, mengonfigurasi ukuran halaman (A4 secara default), dan mendefinisikan persegi panjang yang akan menampung gradien.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Tip profesional:** Sesuaikan koordinat persegi panjang (`200, 100, 200, 200`) untuk menempatkan gradien di mana saja pada halaman.

### Step 2: Define Colors and Fractions
Gradien radial dibangun dari *titik warna* (warna) dan *fraksi* (posisi relatif titik‑titik tersebut). Di sini kami membuat array enam warna dan fraksi yang bersesuaian.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Mengapa ini penting:** Dengan mengubah `fractions` Anda mengontrol seberapa cepat warna bertransisi, memungkinkan efek yang halus atau dramatis.

### Adding Color Stops Gradient to Your Radial Fill
Saat Anda perlu **menambahkan gradien titik warna**, array `colors` dan `fractions` adalah kuncinya. Silakan mengubah urutan, menambah, atau menghapus entri sesuai desain visual Anda.

### Step 3: Create Radial Gradient Paint
Sekarang kami membangun objek `RadialGradientPaint`. Konstruktornya menerima titik pusat gradien, radius, titik fokus, fraksi, warna, metode siklus, ruang warna, dan transformasi opsional.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Catatan:** `transform` dapat `null` jika Anda tidak memerlukan skala atau rotasi tambahan. Silakan bereksperimen dengan `AffineTransform` untuk gradien miring.

### Step 4: Set Paint and Fill the Rectangle
Dengan cat siap, kami memberi tahu `PsDocument` untuk menggunakannya dan kemudian mengisi persegi panjang yang telah didefinisikan sebelumnya.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Pada titik ini halaman PostScript berisi persegi panjang yang diisi secara halus dengan gradien radial yang telah kami konfigurasikan.

### Step 5: Close and Save the Document
Akhirnya, tutup halaman saat ini dan tulis file ke disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Buka `RadialGradient1_outPS.ps` di penampil PostScript apa pun (misalnya, Ghostscript) dan Anda akan melihat gradien ditampilkan persis seperti yang didefinisikan.

## Common Issues & Solutions
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| Gradien muncul sebagai warna solid | `fractions` array tidak dimulai pada `0.0f` atau berakhir pada `1.0f` | Pastikan fraksi pertama adalah `0.0f` dan yang terakhir adalah `1.0f`. |
| Warna tampak pudar | Menggunakan `ColorSpaceType` yang salah | Ganti ke `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` untuk output yang lebih hidup. |
| Tidak ada file output yang dihasilkan | Path `FileOutputStream` tidak valid atau tidak dapat ditulisi | Verifikasi bahwa `dataDir` ada dan aplikasi memiliki izin menulis. |

## Frequently Asked Questions

**T: Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial?**  
J: Ya. Lisensi komersial diperlukan untuk penggunaan produksi. Anda dapat membeli satu dari [halaman lisensi Aspose](https://purchase.aspose.com/buy).

**T: Di mana saya dapat menemukan referensi API resmi?**  
J: Dokumentasi lengkap tersedia [di sini](https://reference.aspose.com/page/java/).

**T: Apakah tersedia versi percobaan gratis untuk pengujian?**  
J: Tentu saja. Unduh versi percobaan dari [halaman rilis Aspose.Page](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk evaluasi?**  
J: Lisensi sementara dapat diminta [di sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat mendapatkan dukungan komunitas?**  
J: Bergabunglah dengan forum komunitas Aspose.Page di [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
Anda sekarang tahu **cara menambahkan gradien radial** ke dokumen Java PostScript menggunakan Aspose.Page. Dengan menyesuaikan ukuran persegi panjang, titik warna, dan radius gradien Anda dapat membuat tak terhitung efek visual—dari isian latar belakang yang halus hingga grafik sorotan yang tegas. Silakan bereksperimen dengan nilai `AffineTransform` yang berbeda untuk memutar atau memiringkan gradien, dan gabungkan teknik ini dengan teks serta gambar untuk output PDF atau EPS yang lebih kaya.

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Page for Java terbaru (pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
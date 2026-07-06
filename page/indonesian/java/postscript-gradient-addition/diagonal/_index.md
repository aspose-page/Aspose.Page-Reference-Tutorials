---
date: 2026-02-13
description: Tingkatkan dokumen Java PostScript Anda dengan gradien diagonal menggunakan
  Aspose.Page Java. Pelajari cara menambahkan efek gradien dengan LinearGradientPaint
  di Java dan buat transisi warna yang hidup dengan mudah.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'Cara Menambahkan Gradien: Gradien Diagonal di Java PostScript menggunakan
  Aspose.Page Java'
url: /id/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Diagonal di Java PostScript menggunakan Aspose.Page Java

## Introduction
Jika Anda ingin memperkaya file PostScript dengan transisi warna diagonal yang halus, **Aspose.Page Java** membuatnya sangat mudah. Dalam tutorial ini kami akan menjelaskan **cara menambahkan gradien** langkah demi langkah, menggunakan kelas `LinearGradientPaint` dari Java 2D. Pada akhir Anda akan memiliki potongan kode siap‑jalankan yang membuat dokumen PostScript dengan gradien diagonal yang hidup.

## How to Add Gradient in Java PostScript
Menambahkan gradien mungkin terdengar seperti tugas grafis saja, tetapi dengan Aspose.Page Anda mendapatkan kontrol penuh atas perintah PostScript yang mendasarinya sambil tetap berada dalam Java murni. Bagian ini menjelaskan mengapa pendekatan ini berhasil dan apa yang Anda dapatkan dibandingkan menulis PostScript mentah secara manual.

## Quick Answers
- **Perpustakaan apa yang diperlukan?** Aspose.Page for Java.  
- **Kelas mana yang membuat gradien?** `LinearGradientPaint`.  
- **Bisakah saya mengubah warna?** Ya – ubah array `Color[]`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia.  
- **Berapa lama implementasinya?** Sekitar 10 menit untuk gradien dasar.

## What is Aspose.Page Java?
Aspose.Page Java adalah API yang kuat yang memungkinkan pengembang menghasilkan, mengedit, dan mengonversi file PostScript serta PDF tanpa memerlukan perangkat lunak eksternal. API ini mengekspos seluruh kemampuan grafis bahasa PostScript melalui antarmuka Java berorientasi objek yang bersih.

## Why use a diagonal gradient?
Gradien diagonal menambah kedalaman dan daya tarik visual pada diagram, spanduk, atau elemen grafis apa pun yang membutuhkan tampilan modern. Karena gradien berjalan dari satu sudut ke sudut berlawanan, ia cocok untuk latar belakang, kulit tombol, dan bentuk dekoratif.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki:

- Java Development Kit (JDK) 8 atau lebih tinggi.  
- Sebuah IDE seperti Eclipse, IntelliJ IDEA, atau VS Code.  
- **Aspose.Page for Java** library – unduh versi terbaru dari [halaman unduhan resmi](https://releases.aspose.com/page/java/).

## Import Packages
Pertama, impor paket Java 2D dan kelas Aspose yang diperlukan. Impor ini memberi Anda akses ke definisi warna, bentuk geometris, pengecatan gradien, dan API dokumen PostScript.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create Output Stream for PostScript Document
Kami mulai dengan menentukan folder tempat file akan disimpan dan membuka `FileOutputStream`. Stream ini akan menerima data PostScript yang dihasilkan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Step 2: Create Save Options with A4 Size
`PsSaveOptions` memungkinkan Anda menentukan ukuran halaman, resolusi, dan pengaturan output lainnya. Di sini kami menggunakan ukuran A4 default.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create New PS Document
Instansiasi `PsDocument` menggunakan output stream dan opsi penyimpanan. Flag `false` memberi tahu konstruktor untuk tidak secara otomatis membuka halaman baru – kami akan melakukannya nanti.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Create a Rectangle
Tentukan persegi panjang yang akan menerima isian gradien. Posisi persegi panjang (200, 100) dan ukuran (200 × 100) dipilih agar gradien terlihat jelas.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 5: Create Gradient Transform
`AffineTransform` memungkinkan kami memutar, menskalakan, dan mentranslasi gradien sehingga berjalan diagonal melintasi persegi panjang. Rumus di bawah menghitung hipotenusa dan menyesuaikan rasio skala secara tepat.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Step 6: Create Diagonal Linear Gradient Paint
Berikut inti **cara menambahkan gradien** – kami membangun `LinearGradientPaint` yang membentang dari kiri‑atas persegi panjang ke kanan‑bawah, menggunakan transformasi yang telah didefinisikan sebelumnya. `MultipleGradientPaint.CycleMethod.NO_CYCLE` memastikan gradien tidak berulang.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Step 7: Set Paint and Fill the Rectangle
Terapkan cat gradien ke dokumen dan isi bentuk persegi panjang. Langkah ini merender transisi warna diagonal pada halaman PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 8: Close the Current Page and Save the Document
Akhirnya, tutup halaman, flush stream, dan simpan file. File `DiagonalGradient_outPS.ps` yang dihasilkan dapat dibuka dengan penampil PostScript apa pun.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Common Issues & Tips
- **Gradien terlihat datar** – periksa kembali sudut rotasi; rotasi 45° menghasilkan diagonal yang sebenarnya.  
- **Warna tampak pudar** – pastikan Anda menggunakan `MultipleGradientPaint.ColorSpaceType.SRGB` untuk rendering warna yang akurat.  
- **Kesalahan file tidak ditemukan** – pastikan `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis.

## Frequently Asked Questions

**Q: Bisakah saya menggunakan perpustakaan ini untuk operasi grafis lain di Java?**  
A: Ya, Aspose.Page for Java menyediakan rangkaian lengkap primitif menggambar, rendering teks, dan kemampuan penanganan gambar.

**Q: Apakah tersedia versi percobaan gratis untuk Aspose.Page Java?**  
A: Tentu saja. Anda dapat mengunduh percobaan berfungsi penuh dari [halaman percobaan gratis Aspose](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page Java?**  
A: Referensi API resmi tersedia [di sini](https://reference.aspose.com/page/java/).

**Q: Bagaimana cara membeli lisensi untuk Aspose.Page Java?**  
A: Lisensi dapat dibeli langsung melalui [portal pembelian Aspose](https://purchase.aspose.com/buy).

**Q: Butuh bantuan atau memiliki pertanyaan?**  
A: Kunjungi forum komunitas [Aspose.Page](https://forum.aspose.com/c/page/39) untuk bantuan dari insinyur Aspose dan pengembang lainnya.

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Page for Java 24.12 (terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
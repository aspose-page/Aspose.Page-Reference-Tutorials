---
date: 2025-12-17
description: Pelajari cara membuat pseudo transparansi Java menggunakan Aspose.Page.
  Ikuti panduan langkah demi langkah kami untuk menambahkan grafik berwarna cerah
  dalam file PostScript.
linktitle: Show Pseudo-Transparency in Java PostScript
second_title: Aspose.Page Java API
title: Cara membuat pseudo transparansi Java dengan Aspose.Page
url: /id/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript Pseudo-Transparency dengan Aspose.Page

## Introduction
Dalam tutorial komprehensif ini Anda akan **membuat pseudo transparency java** grafik dengan Aspose.Page untuk Java. Kami akan memandu Anda melalui setiap langkah—mulai dari menyiapkan lingkungan hingga merender dua persegi panjang yang saling tumpang tindih yang memberikan ilusi transparansi dalam file PostScript. Pada akhir tutorial, Anda akan memahami mengapa pseudo‑transparency berguna, cara mengimplementasikannya, dan cara menyesuaikan parameter untuk desain Anda sendiri.

## Quick Answers
- **Apa arti pseudo‑transparency?** Itu mensimulasikan transparansi dengan mencampur gradien tembus.
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page untuk Java.
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **IDE apa yang dapat saya gunakan?** Semua IDE Java (IntelliJ IDEA, Eclipse, VS Code) yang mendukung Java 8+.
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## What is pseudo transparency in Java PostScript?
Pseudo transparency adalah teknik yang menggunakan isian gradien semi‑transparan untuk memberikan efek visual objek yang dapat dilihat tembus. Karena PostScript tradisional tidak mendukung saluran alfa sejati, Aspose.Page menirunya dengan melapisi bentuk tembus.

## Why use Aspose.Page for pseudo transparency?
- **Cross‑platform** – Menghasilkan PostScript yang valid di semua OS.
- **No external dependencies** – API Java murni.
- **Fine‑grained control** – Mengatur warna, opasitas, dan arah gradien secara programatis.
- **Consistent output** – Berfungsi sama pada printer dan penampil apa pun.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:
- Pengetahuan dasar tentang Java.
- Familiaritas dengan konsep PostScript.
- Perpustakaan Aspose.Page untuk Java terpasang. Jika belum mengunduhnya, dapatkan **[di sini](https://releases.aspose.com/page/java/)**.
- IDE Java atau alat build (Maven/Gradle) yang siap digunakan.

## Import Packages
Mulailah dengan mengimpor kelas yang diperlukan sehingga Anda dapat bekerja dengan warna, gradien, dan objek dokumen PostScript.

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

## Step 1: Create a PS Document
Pertama, buat aliran output dan inisialisasi `PsDocument` baru. Ini menyiapkan kanvas tempat Anda akan menggambar bentuk-bentuk.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Define Rectangle with Opaque Gradient Fill
Gambar persegi panjang pertama menggunakan gradien yang sepenuhnya tidak tembus. Ini akan berfungsi sebagai latar belakang untuk lapisan pseudo‑transparent kita.

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 3: Define Rectangle with Translucent Gradient Fill
Selanjutnya, letakkan persegi panjang kedua yang menggunakan gradien dengan nilai alfa. Ini menciptakan efek **pseudo transparency** ketika tumpang tindih dengan bentuk pertama.

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 4: Close the Page and Save the Document
Terakhir, tutup halaman saat ini dan tulis file PostScript ke disk.

```java
document.closePage();
document.save();
```

## Common Issues & Troubleshooting
- **FileNotFoundException** – Pastikan `dataDir` mengarah ke folder yang ada dan aplikasi Anda memiliki izin menulis.
- **Incorrect colors** – Pastikan Anda menggunakan konstruktor `Color(int r, int g, int b, int a)` untuk warna tembus; parameter keempat adalah alfa (0‑255).
- **Gradient not visible** – Periksa bahwa parameter `AffineTransform` memetakan gradien dengan benar ke dimensi persegi panjang.

## Frequently Asked Questions
### Can I use Aspose.Page for Java in commercial projects?
Ya, Aspose.Page untuk Java tersedia untuk penggunaan komersial. Anda dapat membeli lisensi **[di sini](https://purchase.aspose.com/buy)**.

### Is there a free trial available?
Ya, Anda dapat mendapatkan percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Where can I find additional documentation?
Dokumentasi terperinci tersedia **[di sini](https://reference.aspose.com/page/java/)**.

### How can I get temporary licensing for testing purposes?
Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

### Need help or want to discuss Aspose.Page?
Kunjungi **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Page untuk Java 24.12 (terbaru)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-11
description: Pelajari cara menggambar bentuk persegi panjang di Java PostScript menggunakan
  Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara mengatur cat, mengatur
  warna persegi panjang di Java, dan membuat grafik yang hidup.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page
url: /id/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page

## Introduction
Jika Anda perlu **how to draw rectangle** shapes di dalam file Java PostScript, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan cara menggunakan Aspose.Page untuk Java untuk menambahkan persegi panjang berwarna, mengontrol isian dan garis tepinya, serta menyimpan hasilnya sebagai dokumen PostScript. Anda akan melihat secara tepat **how to set paint**, cara mendefinisikan geometri persegi panjang, dan mengapa pendekatan ini ideal untuk menghasilkan grafik cetak secara programatis.

## Quick Answers
- **Perpustakaan apa yang diperlukan?** Aspose.Page for Java  
- **Apakah saya dapat mengubah warna persegi panjang?** Ya – gunakan `setPaint` dengan `java.awt.Color` apa pun  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi  
- **Ukuran halaman apa yang digunakan dalam contoh?** A4 (default `PsSaveOptions`)  
- **Apakah kode kompatibel dengan Java 8+?** Tentu – menggunakan kelas AWT standar  

## Prerequisites
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang pemrograman Java.  
- Aspose.Page for Java library terpasang. Jika belum, unduh dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Lingkungan pengembangan Java yang telah diatur di mesin Anda.

## Import Packages
Di proyek Java Anda, mulai dengan mengimpor paket yang diperlukan:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cara Menggambar Persegi Panjang di Java PostScript
Berikut adalah alur kerja lengkap yang dibagi menjadi langkah‑langkah jelas. Setiap langkah mencakup penjelasan singkat diikuti oleh blok kode asli (tidak diubah).

### Langkah 1: Atur Cat untuk Mengisi Persegi Panjang  
**How to set paint** – kami memilih warna isi oranye untuk persegi panjang pertama.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Langkah 2: Atur Cat untuk Garis Tepi Persegi Panjang  
**Set rectangle color java** – sekarang kami mengubah cat menjadi merah dan menentukan lebar garis.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Langkah 3: Tutup Halaman Saat Ini dan Simpan Dokumen  
Setelah menggambar, kami menutup halaman dan menyimpan file.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Mengapa Menggunakan Aspose.Page untuk Grafik Persegi Panjang?
- **Cross‑platform**: Menghasilkan PostScript standar yang dapat bekerja pada printer apa pun.  
- **Fine‑grained control**: Anda dapat mengatur warna isi, warna garis tepi, dan lebar garis secara terpisah.  
- **No external dependencies**: Hanya menggunakan kelas geometri AWT bawaan.  

## Masalah Umum & Tips
- **File path errors** – pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`).  
- **License exceptions** – versi percobaan menambahkan watermark; dapatkan lisensi penuh untuk penggunaan produksi.  
- **Color visibility** – beberapa printer mungkin menafsirkan nilai RGB tertentu secara berbeda; uji dulu dengan persegi panjang hitam sederhana.

## Kesimpulan
Dalam panduan ini kami menunjukkan **how to draw rectangle** dalam dokumen Java PostScript, membahas **how to set paint**, dan memperlihatkan cara **set rectangle color java** menggunakan Aspose.Page. Silakan bereksperimen dengan berbagai bentuk, warna, dan gaya garis untuk membuat grafik cetak yang kaya untuk laporan, faktur, atau cetakan khusus.

## Frequently Asked Questions

### Apakah saya dapat menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi perpustakaan serupa tersedia untuk bahasa lain.

### Apakah ada versi percobaan Aspose.Page untuk Java yang tersedia?
Ya, Anda dapat menjelajahi fitur Aspose.Page untuk Java dengan [free trial version](https://releases.aspose.com/).

### Di mana saya dapat menemukan bantuan tambahan dan diskusi?
Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk berinteraksi dengan komunitas dan mendapatkan bantuan.

### Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk Java?
Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat membeli versi berlisensi Aspose.Page untuk Java?
Beli versi berlisensi [di sini](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Yes – simply modify the `Rectangle2D.Float(x, y, width, height)` parameters before calling `fill` or `draw`.

**Q:** *Apakah saya dapat mengubah ukuran persegi panjang secara dinamis?*  
**A:** Ya – cukup ubah parameter `Rectangle2D.Float(x, y, width, height)` sebelum memanggil `fill` atau `draw`.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolutely. After drawing the rectangle, use `document.drawString(...)` with the desired font and position.

**Q:** *Apakah memungkinkan menambahkan teks di dalam persegi panjang?*  
**A:** Tentu. Setelah menggambar persegi panjang, gunakan `document.drawString(...)` dengan font dan posisi yang diinginkan.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Yes, the API provides methods such as `drawEllipse` and `drawPolygon` for a variety of vector graphics.

**Q:** *Apakah Aspose.Page mendukung bentuk lain seperti lingkaran atau poligon?*  
**A:** Ya, API menyediakan metode seperti `drawEllipse` dan `drawPolygon` untuk berbagai grafik vektor.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-02-18
description: Pelajari cara menggambar bentuk persegi panjang di Java PostScript menggunakan
  Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara mengatur cat, mengatur
  warna persegi panjang di Java, dan membuat grafik yang hidup sambil menjelaskan
  cara menggambar persegi panjang secara efisien.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page
url: /id/java/postscript-shapes/add-rectangle/
weight: 11
---

 content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page

## Pendahuluan
Jika Anda perlu **how to draw rectangle** bentuk di dalam file Java PostScript, Anda berada di tempat yang tepat. Pada tutorial ini kami akan menjelaskan cara menggunakan Aspose.Page untuk Java guna menambahkan persegi panjang berwarna, mengontrol isian dan garis tepinya, serta menyimpan hasilnya sebagai dokumen PostScript. Anda akan melihat secara tepat **how to set paint**, cara mendefinisikan geometri persegi panjang, dan mengapa pendekatan ini ideal untuk menghasilkan grafik cetak secara programatis. Pada akhir panduan Anda juga akan memahami konteks yang lebih luas dari teknik **draw rectangle java** dan bagaimana mereka cocok dalam alur kerja **java awt rectangle drawing**.

## Jawaban Cepat
- **What library is required?** Aspose.Page for Java  
- **Can I change rectangle colors?** Ya – gunakan `setPaint` dengan `java.awt.Color` apa pun  
- **Do I need a license for development?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi  
- **Which page size is used in the example?** A4 (default `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** Tentu – menggunakan kelas AWT standar  

## Apa Itu “How to Draw Rectangle” dalam PostScript?
Menggambar persegi panjang dalam dokumen PostScript berarti mendefinisikan area persegi dan mengisinya, memberi garis tepi, atau keduanya. Dengan Aspose.Page Anda dapat melakukan ini menggunakan kelas **java awt rectangle drawing** yang familiar, sehingga kode mudah dibaca dan dipelihara.

## Mengapa Menggunakan Aspose.Page untuk Grafik Persegi Panjang?
- **Cross‑platform**: Menghasilkan PostScript standar yang dapat bekerja pada printer apa pun.  
- **Fine‑grained control**: Anda dapat mengatur warna isian, warna garis tepi, dan lebar garis secara terpisah.  
- **No external dependencies**: Hanya menggunakan kelas geometri AWT bawaan, sehingga tidak memerlukan perpustakaan grafis tambahan.  

## Prasyarat
Sebelum memulai tutorial, pastikan Anda telah menyiapkan hal‑hal berikut:
- Pemahaman dasar tentang pemrograman Java.  
- Perpustakaan Aspose.Page for Java terpasang. Jika belum, unduh dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Lingkungan pengembangan Java telah dikonfigurasi di mesin Anda.

## Impor Paket
Di proyek Java Anda, mulailah dengan mengimpor paket‑paket yang diperlukan. Impor ini memberi Anda akses ke kelas `Color`, `BasicStroke`, dan `Rectangle2D` dari AWT, serta kelas inti penanganan dokumen Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Panduan Langkah‑demi‑Langkah untuk Menggambar Persegi Panjang di Java PostScript

### Langkah 1: Atur Paint untuk Mengisi Persegi Panjang  
**How to set paint** – kami memilih warna isian oranye untuk persegi panjang pertama. Ini menunjukkan kemampuan **set rectangle color java**.

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

### Langkah 2: Atur Paint untuk Menyapu Persegi Panjang  
**Set rectangle color java** – kini kami mengubah paint menjadi merah dan menentukan lebar garis. Bagian contoh ini menunjukkan cara **draw rectangle java** dengan ketebalan garis khusus.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Langkah 3: Tutup Halaman Saat Ini dan Simpan Dokumen  
Setelah menggambar, kami menutup halaman dan menyimpan file. Menutup halaman memastikan semua perintah gambar dikirim ke aliran PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Kasus Penggunaan Umum untuk Menggambar Persegi Panjang
- **Invoice or receipt generation** – persegi panjang berfungsi sebagai batas atau menyorot bagian.  
- **Label creation** – gambar kotak berwarna untuk memisahkan informasi produk.  
- **Simple charts** – gunakan persegi panjang terisi sebagai elemen diagram batang.  
- **Custom printable forms** – gabungkan persegi panjang dengan teks untuk membangun bidang formulir.

## Masalah Umum & Tips
- **File path errors** – pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`).  
- **License exceptions** – versi percobaan menambahkan watermark; dapatkan lisensi penuh untuk penggunaan produksi.  
- **Color visibility** – beberapa printer dapat menafsirkan nilai RGB tertentu secara berbeda; uji dulu dengan persegi panjang hitam sederhana.  
- **Memory usage** – untuk dokumen besar, pertimbangkan untuk mengosongkan aliran setelah setiap halaman (`document.closePage()`).

## Pertanyaan yang Sering Diajukan

**Q:** *Can I use Aspose.Page for Java with other programming languages?*  
A: Aspose.Page terutama mendukung Java, namun perpustakaan serupa tersedia untuk bahasa lain.

**Q:** *Is there a trial version of Aspose.Page for Java available?*  
A: Ya, Anda dapat menjelajahi fitur Aspose.Page for Java dengan [free trial version](https://releases.aspose.com/).

**Q:** *Where can I find additional help and discussions?*  
A: Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk berinteraksi dengan komunitas dan mendapatkan bantuan.

**Q:** *How can I obtain a temporary license for Aspose.Page for Java?*  
A: Dapatkan lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

**Q:** *Where can I purchase a licensed version of Aspose.Page for Java?*  
A: Beli versi berlisensi [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
A: Ya – cukup ubah parameter `Rectangle2D.Float(x, y, width, height)` sebelum memanggil `fill` atau `draw`.

**Q:** *Is it possible to add text inside the rectangle?*  
A: Tentu. Setelah menggambar persegi panjang, gunakan `document.drawString(...)` dengan font dan posisi yang diinginkan.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
A: Ya, API menyediakan metode seperti `drawEllipse` dan `drawPolygon` untuk berbagai grafik vektor.

## Kesimpulan
Dalam panduan ini kami menunjukkan **how to draw rectangle** dalam dokumen Java PostScript, membahas **how to set paint**, dan memperlihatkan cara **set rectangle color java** menggunakan Aspose.Page. Anda kini memiliki dasar yang kuat untuk membuat grafik cetak berwarna, baik untuk faktur, label, atau formulir khusus. Jangan ragu bereksperimen dengan warna berbeda, gaya garis, dan bentuk AWT tambahan untuk memperkaya output Anda.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-11
description: Pelajari cara membuat elips PostScript di Java menggunakan Aspose.Page.
  Panduan langkah demi langkah ini menunjukkan cara mengisi elips dengan warna dan
  menggambar elips menggunakan Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Cara membuat elips PostScript di Java dengan Aspose.Page
url: /id/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat elips PostScript di Java dengan Aspose.Page

## Pendahuluan
Membuat **elips PostScript** secara programatik memberi Anda kontrol detail atas grafik vektor dalam laporan, faktur, atau dokumen yang dapat dicetak. Pada tutorial ini Anda akan belajar cara **membuat elips PostScript** menggunakan pustaka Aspose.Page untuk Java, mengisi elips dengan warna, dan menggambar garis tepi elips. Pada akhir tutorial Anda siap menyematkan grafik khusus langsung ke output PostScript Anda.

## Jawaban Cepat
- **Perpustakaan apa yang terbaik untuk menggambar grafik PostScript di Java?** Aspose.Page untuk Java.  
- **Apakah saya dapat mengisi elips dengan warna solid?** Ya – gunakan `document.setPaint(Color.YOUR_COLOR)` sebelum `fill`.  
- **Bagaimana cara menggambar hanya garis tepi elips?** Atur paint dan stroke, lalu panggil `document.draw(...)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan; lisensi sementara tersedia untuk pengujian.  
- **Versi Java apa yang didukung?** Semua runtime Java 8+ dapat bekerja dengan rilis Aspose.Page saat ini.

## Apa itu elips PostScript?
Elips PostScript adalah bentuk vektor yang didefinisikan oleh persegi panjang pembatas. Tidak seperti gambar raster, ia dapat diskalakan tanpa kehilangan kualitas, menjadikannya ideal untuk pencetakan resolusi tinggi dan konversi ke PDF.

## Mengapa menggunakan Aspose.Page untuk membuat elips PostScript?
- **Kontrol penuh** atas primitif menggambar (garis, kurva, elips).  
- **Lintas‑platform** – bekerja di Windows, Linux, dan macOS.  
- **Tanpa ketergantungan eksternal** – API Java murni, tanpa kode native.  
- **Integrasi mudah** dengan aplikasi Java yang ada dan alat build.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
2. Pustaka Aspose.Page untuk Java yang telah ditambahkan ke proyek Anda. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  

## Impor Paket
Di file sumber Java Anda, impor kelas‑kelas yang diperlukan untuk menggambar dan menyimpan konten PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: Siapkan dokumen PostScript
Buat aliran output, konfigurasikan ukuran halaman, dan buat instance `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Langkah 2: Isi elips dengan warna
Atur paint ke warna isi yang diinginkan dan panggil `fill` dengan instance `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Langkah 3: Garis tepi elips dengan stroke
Ganti paint ke warna stroke, definisikan `BasicStroke` untuk ketebalan garis, dan gambar garis tepi elips.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Langkah 4: Tutup dan simpan dokumen
Selesaikan halaman dan tulis file PostScript ke disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Sekarang Anda memiliki file PostScript yang berisi dua elips—satu diisi dengan oranye dan satu lagi bergaris tepi merah. Silakan bereksperimen dengan koordinat, ukuran, dan warna yang berbeda untuk menyesuaikan kebutuhan desain Anda.

## Jebakan umum dan pemecahan masalah
- **Path file tidak benar** – Pastikan `dataDir` diakhiri dengan pemisah (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Lisensi hilang** – Tanpa lisensi yang valid, pustaka berjalan dalam mode evaluasi dan mungkin menambahkan watermark.  
- **Warna tidak diterapkan** – Ingatlah untuk memanggil `document.setPaint(...)` *sebelum* setiap pemanggilan `fill` atau `draw`; pengaturan paint tidak bertahan secara otomatis antar operasi terpisah.

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat menggunakan Aspose.Page untuk Java bersama pustaka Java lain?**  
J: Ya, Aspose.Page untuk Java dirancang untuk terintegrasi mulus dengan pustaka Java lainnya.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
J: Dapatkan lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)** untuk keperluan pengujian.

**T: Apakah Aspose.Page cocok untuk proyek komersial?**  
J: Tentu saja! Kunjungi **[di sini](https://purchase.aspose.com/buy)** untuk menjelajahi opsi lisensi komersial.

**T: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.Page?**  
J: Bergabunglah dengan komunitas di **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk diskusi dan bantuan.

**T: Apakah ada sumber daya gratis untuk mempelajari lebih lanjut tentang Aspose.Page untuk Java?**  
J: Manfaatkan **[trial gratis](https://releases.aspose.com/)** dan jelajahi contoh dalam dokumentasi.

## Kesimpulan
Aspose.Page untuk Java memudahkan **pembuatan elips PostScript**, baik Anda memerlukan bentuk terisi sederhana atau garis tepi yang kompleks. Dengan langkah‑langkah di atas Anda dapat dengan cepat menambahkan grafik vektor kelas profesional ke dokumen yang dapat dicetak. Untuk eksplorasi lebih dalam—seperti menggabungkan beberapa bentuk, menerapkan gradien, atau mengonversi ke PDF—lihat **[dokumentasi resmi](https://reference.aspose.com/page/java/)**.

---

**Terakhir Diperbarui:** 2025-12-11  
**Diuji Dengan:** Aspose.Page untuk Java 24.11  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

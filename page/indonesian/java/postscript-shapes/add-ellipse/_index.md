---
date: 2026-02-18
description: Pelajari cara mengatur warna cat dan membuat elips PostScript di Java
  menggunakan Aspose.Page. Panduan ini menunjukkan cara mengisi elips di Java, menggambar
  kontur elips, dan mengatur ketebalan goresan.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Atur warna cat untuk menggambar elips PostScript di Java
url: /id/java/postscript-shapes/add-ellipse/
weight: 10
---

 none. Ensure code block placeholders remain unchanged.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set paint color to draw PostScript ellipse in Java

## Pendahuluan
Jika Anda perlu **set paint color** saat menggambar grafik vektor, perpustakaan Aspose.Page untuk Java memberi Anda kontrol penuh atas setiap goresan dan isi. Dalam tutorial ini Anda akan menemukan cara **set paint color**, **fill ellipse Java**, dan **draw ellipse outline** menggunakan pendekatan sederhana langkah demi langkah. Pada akhir tutorial, Anda akan dapat menambahkan elips PostScript berkualitas tinggi ke faktur, laporan, atau dokumen yang dapat dicetak apa pun.

## Jawaban Cepat
- **Library apa yang terbaik untuk menggambar grafik PostScript di Java?** Aspose.Page for Java.  
- **Bisakah saya mengisi elips dengan warna solid?** Ya – gunakan `document.setPaint(Color.YOUR_COLOR)` sebelum `fill`.  
- **Bagaimana cara menggambar hanya kontur elips?** Atur paint dan stroke, lalu panggil `document.draw(...)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan; lisensi sementara tersedia untuk pengujian.  
- **Versi Java apa yang didukung?** Runtime Java 8+ apa pun dapat bekerja dengan rilis Aspose.Page saat ini.

## Apa itu elips PostScript?
Elips PostScript adalah bentuk vektor yang didefinisikan oleh sebuah persegi panjang pembatas. Tidak seperti gambar raster, elips ini dapat diskalakan tanpa kehilangan kualitas, menjadikannya ideal untuk pencetakan resolusi tinggi dan konversi PDF.

## Mengapa menggunakan Aspose.Page untuk membuat elips PostScript?
- **Kontrol penuh** atas primitif menggambar (garis, kurva, elips).  
- **Lintas‑platform** – bekerja di Windows, Linux, dan macOS.  
- **Tanpa dependensi eksternal** – API Java murni, tanpa kode native.  
- **Integrasi mudah** dengan aplikasi Java yang ada dan alat build.

## Prasyarat
Sebelum Anda mulai, pastikan Anda memiliki:

1. Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
2. Perpustakaan Aspose.Page untuk Java ditambahkan ke proyek Anda. Anda dapat mengunduhnya **[here](https://releases.aspose.com/page/java/)**.  

## Impor Paket
Dalam file sumber Java Anda, impor kelas-kelas yang diperlukan untuk menggambar dan menyimpan konten PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cara mengatur warna cat untuk sebuah elips
Mengatur warna cat adalah langkah pertama sebelum operasi isi atau goresan apa pun. Metode `setPaint` menentukan warna yang akan digunakan untuk perintah menggambar berikutnya.

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

### Langkah 2: Cara mengisi elips – gunakan set paint color
Untuk **fill ellipse**, Anda harus pertama memanggil `setPaint` dengan warna isi yang diinginkan, kemudian memanggil `fill` dengan instance `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Langkah 3: Gambar kontur elips dan atur ketebalan stroke
Setelah mengisi, Anda dapat mengubah paint ke warna lain, mendefinisikan `BasicStroke` untuk mengontrol lebar garis, dan menggambar kontur elips.

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

Sekarang Anda memiliki file PostScript yang berisi dua elips—satu diisi dengan warna oranye dan satu lagi berkontur merah. Silakan bereksperimen dengan koordinat, ukuran, dan warna yang berbeda untuk menyesuaikan kebutuhan desain Anda.

## Kesalahan umum dan pemecahan masalah
- **Path file tidak benar** – Pastikan `dataDir` diakhiri dengan pemisah (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Lisensi hilang** – Tanpa lisensi yang valid, perpustakaan berjalan dalam mode evaluasi dan mungkin menambahkan watermark.  
- **Warna tidak diterapkan** – Ingat untuk mengatur `document.setPaint(...)` *sebelum* setiap pemanggilan `fill` atau `draw`; pengaturan paint tidak bertahan secara otomatis antar operasi terpisah.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, Aspose.Page untuk Java dirancang untuk terintegrasi secara mulus dengan perpustakaan Java lainnya.

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk Java?**  
A: Dapatkan lisensi sementara **[here](https://purchase.aspose.com/temporary-license/)** untuk keperluan pengujian.

**Q: Apakah Aspose.Page cocok untuk proyek komersial?**  
A: Tentu saja! Kunjungi **[here](https://purchase.aspose.com/buy)** untuk menjelajahi opsi lisensi untuk penggunaan komersial.

**Q: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.Page?**  
A: Bergabunglah dengan komunitas di **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** untuk diskusi dan bantuan.

**Q: Apakah ada sumber daya gratis untuk mempelajari lebih lanjut tentang Aspose.Page untuk Java?**  
A: Manfaatkan **[free trial](https://releases.aspose.com/)** dan jelajahi contoh dalam dokumentasi.

## Kesimpulan
Aspose.Page untuk Java memudahkan **set paint color**, **fill ellipse**, dan **draw ellipse outline**—baik Anda membutuhkan bentuk sederhana yang diisi atau grafik berstroke kompleks. Dengan langkah-langkah di atas Anda dapat dengan cepat menambahkan grafik vektor kelas profesional ke dokumen apa pun yang dapat dicetak. Untuk eksplorasi lebih dalam—seperti menggabungkan beberapa bentuk, menerapkan gradien, atau mengonversi ke PDF—lihat **[documentation](https://reference.aspose.com/page/java/)** resmi.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
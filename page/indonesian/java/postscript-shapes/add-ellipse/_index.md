---
date: 2026-10-31
description: Pelajari cara mengatur warna cat dan mengisi elips di Java PostScript
  menggunakan Aspose.Page. Panduan ini menunjukkan cara mengisi elips, menggambar
  kontur elips, dan mengatur ketebalan goresan dengan langkah‑langkah kode yang jelas.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Tambahkan Elips di Java PostScript
og_description: Pelajari cara mengisi elips dan mengatur warna cat di Java PostScript
  menggunakan Aspose.Page. Ikuti kode langkah‑demi‑langkah untuk menggambar elips
  yang terisi dan berkontur dalam hitungan detik.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Cara mengisi elips dan mengatur warna cat di Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Cara mengisi elips dan mengatur warna cat di Java PostScript
url: /id/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengisi elips dan mengatur warna cat dalam Java PostScript

## Pendahuluan
Jika Anda perlu **set paint color** saat menggambar grafik vektor, perpustakaan Aspose.Page untuk Java memberi Anda kontrol penuh atas setiap stroke dan fill. Dalam tutorial ini Anda akan menemukan cara **set paint color**, **fill ellipse**, dan **draw ellipse outline** menggunakan pendekatan sederhana langkah demi langkah. Pada akhirnya, Anda akan dapat menambahkan elips PostScript berkualitas tinggi ke faktur, laporan, atau dokumen yang dapat dicetak apa pun.

## Jawaban Cepat
- **Library apa yang terbaik untuk menggambar grafik PostScript di Java?** Aspose.Page for Java.  
- **Bisakah saya mengisi elips dengan warna solid?** Yes – use `document.setPaint(Color.YOUR_COLOR)` before `fill`.  
- **Bagaimana cara menggambar hanya garis tepi elips?** Set the paint and stroke, then call `document.draw(...)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** A commercial license is required; a temporary license is available for testing.  
- **Versi Java apa yang didukung?** Any Java 8+ runtime works with the current Aspose.Page release.

## Apa itu elips PostScript?
Elips PostScript adalah bentuk vektor yang didefinisikan oleh persegi panjang pembatas. Tidak seperti gambar raster, ia dapat diskalakan tanpa kehilangan kualitas, menjadikannya ideal untuk pencetakan resolusi tinggi dan konversi PDF. Karena bentuk ini dijelaskan secara matematis, ia dapat dirender pada ukuran atau resolusi apa pun sambil mempertahankan tepi yang tajam dan kurva yang halus.

## Mengapa menggunakan Aspose.Page untuk membuat elips PostScript?
Aspose.Page memberi Anda kontrol deterministik atas setiap primitif gambar. Ia mendukung **3 sistem operasi utama (Windows, Linux, macOS)**, **0 ketergantungan native**, dan dapat merender **lebih dari 50 primitif vektor** per detik pada server tipikal. Perpustakaan ini murni Java, sehingga Anda dapat menyematkannya dalam aplikasi Java 8+ apa pun tanpa perpustakaan native tambahan.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
2. Perpustakaan Aspose.Page untuk Java yang ditambahkan ke proyek Anda. Anda dapat mengunduhnya **[from the Aspose.Page for Java release page](https://releases.aspose.com/page/java/)**.  

## Impor paket
Di file sumber Java Anda, impor kelas-kelas yang diperlukan untuk menggambar dan menyimpan konten PostScript.

Paket `java.awt` menyediakan tipe grafik dasar seperti `Color`, `Ellipse2D`, dan `BasicStroke`. Paket `com.aspose.page` menyediakan kelas `PsDocument` yang menulis output PostScript.

- **`Color`** – mewakili warna sRGB yang digunakan untuk melukis.  
- **`Ellipse2D`** – menggambarkan bentuk elips yang didefinisikan oleh persegi panjang pembatas.  
- **`BasicStroke`** – menentukan lebar garis, pola dash, dan gaya ujung untuk menggambar garis tepi.  
- **`PsDocument`** – mewakili dokumen PostScript dan menyediakan metode untuk menggambar grafik serta mengelola halaman.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cara mengatur warna cat untuk sebuah elips
Langkah pertama adalah memberi tahu dokumen warna apa yang akan digunakan untuk operasi menggambar berikutnya. Metode `setPaint` menetapkan warna solid yang akan diterapkan pada fill atau stroke, tergantung pada pemanggilan selanjutnya.

### Langkah 1: Menyiapkan dokumen PostScript
Buat output stream, konfigurasikan ukuran halaman, dan buat instance `PsDocument`.

`PsDocument` adalah kelas inti yang mewakili file PostScript dalam memori. Semua perintah menggambar diarahkan melalui objek ini, dan ia menangani tata letak halaman, manajemen sumber daya, serta pembuatan file akhir.

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

### Langkah 2: Mengisi elips – gunakan set paint color
Untuk **fill ellipse**, Anda harus terlebih dahulu memanggil `setPaint` dengan warna isi yang diinginkan, kemudian memanggil `fill` dengan instance `Ellipse2D`.

`setPaint` menetapkan warna gambar saat ini yang digunakan untuk operasi fill atau stroke berikutnya.  
`Ellipse2D` mendefinisikan batas geometris elips; konstruktor-nya menerima koordinat X‑Y sudut kiri atas serta lebar dan tinggi.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Langkah 3: Menggambar garis tepi elips dan mengatur ketebalan stroke
Setelah mengisi, Anda dapat mengubah paint ke warna lain, mendefinisikan `BasicStroke` untuk mengontrol lebar garis, dan menggambar garis tepi elips.

`BasicStroke` menentukan lebar garis, pola dash, dan gaya ujung untuk menggambar garis tepi. Dengan menyesuaikan properti `width`-nya, Anda mengontrol seberapa tebal batas elips muncul.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Langkah 4: Menutup dan menyimpan dokumen
Selesaikan halaman dan tulis file PostScript ke disk.

Memanggil `document.close()` membersihkan semua perintah menggambar yang tertunda dan melepaskan sumber daya. File `.ps` yang dihasilkan dapat dibuka dengan penampil PostScript apa pun atau dikonversi ke PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Sekarang Anda memiliki file PostScript yang berisi dua elips—satu diisi dengan warna oranye dan satu lagi memiliki garis tepi merah. Silakan bereksperimen dengan koordinat, ukuran, dan warna yang berbeda untuk menyesuaikan kebutuhan desain Anda.

## Kesalahan umum dan pemecahan masalah
- **Incorrect file path** – Pastikan `dataDir` diakhiri dengan pemisah (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Missing license** – Tanpa lisensi yang valid, perpustakaan berjalan dalam mode evaluasi dan mungkin menambahkan watermark.  
- **Color not applied** – Ingat untuk mengatur `document.setPaint(...)` *sebelum* setiap pemanggilan `fill` atau `draw`; pengaturan paint tidak bertahan secara otomatis antar operasi terpisah.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, Aspose.Page untuk Java dirancang untuk terintegrasi secara mulus dengan perpustakaan Java lainnya.

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk Java?**  
A: Dapatkan lisensi sementara **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)** untuk keperluan pengujian.

**Q: Apakah Aspose.Page cocok untuk proyek komersial?**  
A: Tentu saja! Kunjungi **[the Aspose purchase page](https://purchase.aspose.com/buy)** untuk menjelajahi opsi lisensi untuk penggunaan komersial.

**Q: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.Page?**  
A: Bergabunglah dengan komunitas di **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** untuk diskusi dan bantuan.

**Q: Apakah ada sumber daya gratis untuk mempelajari lebih lanjut tentang Aspose.Page untuk Java?**  
A: Manfaatkan **[Aspose free trial page](https://releases.aspose.com/)** dan jelajahi contoh-contoh dalam dokumentasi.

## Kesimpulan
Aspose.Page untuk Java memudahkan **set paint color**, **fill ellipse**, dan **draw ellipse outline**—baik Anda memerlukan bentuk terisi sederhana atau grafik berstroke kompleks. Dengan langkah-langkah di atas Anda dapat dengan cepat menambahkan grafik vektor kelas profesional ke dokumen apa pun yang dapat dicetak. Untuk eksplorasi lebih mendalam—seperti menggabungkan beberapa bentuk, menerapkan gradien, atau mengonversi ke PDF—lihat **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)** resmi.

---

**Terakhir Diperbarui:** 2026-10-31  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Cara Menambahkan Teks Unicode di Java PostScript dengan Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Membuat Gradien Radial di PostScript dengan Aspose.Page untuk Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
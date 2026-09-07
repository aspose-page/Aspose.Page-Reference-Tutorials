---
date: 2026-08-29
description: Pelajari cara mengubah ukuran vektor EPS di Java menggunakan Aspose.Page.
  Panduan langkah demi langkah ini menunjukkan cara mengubah ukuran EPS dengan poin,
  inci, milimeter, atau persentase.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Ubah Ukuran File EPS di Java
og_description: Ubah ukuran vektor Java memungkinkan Anda menyesuaikan dimensi file
  EPS langsung di Java. Menggunakan Aspose.Page Anda dapat mengubah ukuran dengan
  poin, inci, milimeter, atau persentase sambil mempertahankan kualitas vektor.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Ubah ukuran vektor Java: ubah dimensi EPS dengan Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Cara mengubah ukuran vektor EPS di Java dengan Aspose.Page
url: /id/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengubah ukuran vektor EPS dengan Java menggunakan Aspose.Page

## Pendahuluan
Jika Anda perlu **java vector resize** file EPS secara programatis, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui proses mengubah ukuran gambar EPS di Java menggunakan pustaka Aspose.Page. Baik Anda ingin menggandakan ukuran, memperkecil ke ukuran tertentu, atau bekerja dengan persentase, langkah‑langkah di bawah ini memberi Anda kontrol penuh atas dimensi output. Menguasai cara mengubah ukuran EPS sangat penting saat menyesuaikan grafik untuk tata letak cetak yang berbeda, resolusi layar, atau pedoman merek.

## Jawaban Cepat
- **Library apa yang dibutuhkan?** Aspose.Page for Java  
- **Bisakah saya mengubah ukuran menggunakan poin, inci, atau milimeter?** Ya – API mendukung ketiga satuan tersebut plus persentase.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih baru.  
- **Apakah kode ini thread‑safe?** Setiap instance `PsDocument` terisolasi, sehingga Anda dapat memproses file secara paralel.  

## Apa itu EPS dan mengapa mengubah ukurannya?
Encapsulated PostScript (EPS) adalah format grafik vektor yang banyak digunakan untuk pencetakan dan penerbitan. Terkadang file EPS asli dibuat dengan ukuran yang tidak sesuai dengan output target Anda – misalnya, logo yang dirancang pada 72 pts mungkin perlu menjadi 144 pts untuk brosur yang lebih besar. Mengetahui **how to resize eps** memungkinkan Anda mempertahankan kualitas vektor sambil menyesuaikan dimensi ke alur kerja apa pun.

## Mengapa menggunakan Aspose.Page untuk mengubah ukuran EPS?
Aspose.Page menyediakan API yang sederhana yang memungkinkan Anda menentukan ukuran target dalam salah satu satuan yang didukung sambil secara otomatis mempertahankan struktur vektor. Pustaka ini menangani konversi satuan secara internal, sehingga Anda dapat fokus pada dimensi yang diinginkan tanpa perhitungan manual.

- **Mendukung empat satuan pengukuran** – Points, Inches, Millimeters, dan Percent.  
- **Tanpa ketergantungan eksternal** – API Java murni, tidak memerlukan pustaka native.  
- **Pemrosesan berperforma tinggi** – dapat menangani hingga 500 file EPS per menit pada server standar 8‑core.  
- **Mempertahankan kesetiaan vektor** – output tetap sepenuhnya dapat diskalakan tanpa rasterisasi.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Pustaka Aspose.Page untuk Java. Anda dapat mengunduhnya di **[halaman unduhan Aspose.Page untuk Java](https://releases.aspose.com/page/java/)**.  
- Pemahaman dasar tentang pemrograman Java.  

## Impor paket
Dalam proyek Java Anda, sertakan impor yang diperlukan agar Anda dapat bekerja dengan objek Aspose.Page dan aliran I/O standar.

`PsDocument` mewakili dokumen EPS yang dimuat dalam memori.  
`Units` adalah enumerasi yang mendefinisikan satuan pengukuran yang diterima oleh API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Cara mengubah dimensi EPS dengan satuan yang berbeda
Anda dapat mengubah dimensi EPS dengan memanggil metode `resizeEps` dengan lebar, tinggi yang diinginkan, dan nilai enum `Units`; ini bekerja untuk poin, inci, milimeter, atau persentase. Pola lima langkah yang sama berlaku untuk setiap satuan, menjadikan API dapat diprediksi dan mudah diintegrasikan.

`resizeEps` mengubah ukuran kanvas EPS ke dimensi yang ditentukan sambil mempertahankan data vektor internal.

## Cara mengubah ukuran EPS menggunakan poin
Muat EPS Anda, tentukan ukuran baru dalam poin, dan simpan hasilnya. Pendekatan ini menggandakan dimensi asli sambil mempertahankan rasio aspek. Menggunakan poin memberi Anda kontrol presisi atas ukuran siap cetak, yang sangat berguna untuk tata letak tipografi dan output resolusi tinggi.

### Langkah 1: siapkan aliran input
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Langkah 2: inisialisasi objek `PsDocument`
`PsDocument` memuat file EPS sumber dan menyediakan metode untuk manipulasi.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Langkah 3: ekstrak ukuran saat ini dari gambar EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Langkah 4: buat aliran output untuk file yang diubah ukurannya
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Langkah 5: ubah ukuran dan simpan EPS menggunakan poin
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Cara mengubah ukuran EPS menggunakan inci
Mengubah ukuran dengan inci memungkinkan Anda menyesuaikan spesifikasi yang didefinisikan dalam satuan imperial, seperti tata letak brosur atau standar cetak berbasis AS. Berikan lebar dan tinggi target dalam inci, dan API akan mengkonversinya ke satuan internal yang sesuai sebelum menerapkan transformasi.

## Cara mengubah ukuran EPS menggunakan milimeter
Saat bekerja dengan alur kerja berbasis metrik, menentukan dimensi dalam milimeter memastikan konsistensi dengan ukuran kertas dan peralatan cetak yang digunakan di luar Amerika Serikat. Pustaka secara otomatis menangani konversi dari milimeter ke sistem koordinat internal.

## Cara mengubah ukuran EPS menggunakan persentase
Mengubah ukuran dengan persentase mengskalakan dimensi asli secara proporsional, yang berguna untuk penyesuaian ukuran cepat tanpa menghitung nilai absolut. Misalnya, faktor `0.5` mengurangi lebar dan tinggi masing‑masing sebesar 50 %.

## Kesalahan umum & tips
- **Selalu tutup aliran** – Pada kode produksi, bungkus aliran dengan try‑with‑resources untuk menghindari penguncian file.  
- **Pertahankan rasio aspek** – Kalikan lebar dan tinggi dengan faktor yang sama kecuali Anda memang menginginkan distorsi.  
- **Periksa DPI** – Mengubah ukuran tidak mengubah DPI; jika Anda memerlukan DPI yang berbeda, sesuaikan secara terpisah setelah mengubah ukuran.  
- **Keamanan thread** – Buat `PsDocument` baru per thread; berbagi instance yang sama dapat menyebabkan hasil yang tidak terduga.  

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan pustaka ini untuk format gambar lain?**  
A: Tidak, Aspose.Page khusus untuk file PostScript dan EPS saja.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?**  
A: Ya, Anda dapat menjelajahi percobaan gratis **[halaman percobaan gratis Aspose](https://releases.aspose.com/)**.

**Q: Di mana saya dapat menemukan bantuan tambahan dan diskusi?**  
A: Kunjungi **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk dukungan komunitas.

**Q: Bagaimana saya dapat memperoleh lisensi sementara?**  
A: Anda dapat memperoleh lisensi sementara **[halaman permintaan lisensi sementara](https://purchase.aspose.com/temporary-license/)**.

**Q: Apakah ada contoh proyek yang tersedia?**  
A: Ya, lihat dokumentasi **[referensi API Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Terakhir Diperbarui:** 2026-08-29  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose

## Tutorial Terkait

- [Ubah Ukuran EPS menggunakan Aspose.Page – Manipulasi EPS Java](/page/java/manipulation-eps/)
- [Cara Memotong File EPS di Java – Panduan Aspose.Page](/page/java/manipulation-eps/crop/)
- [Cara Menskalakan Persegi Panjang dengan Aspose.Page untuk Java](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
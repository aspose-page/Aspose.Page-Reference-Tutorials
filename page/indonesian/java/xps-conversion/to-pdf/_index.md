---
date: 2025-12-23
description: Pelajari cara mengonversi XPS ke PDF dalam Java menggunakan Aspose.Page.
  Panduan ini menunjukkan konversi langkah demi langkah, cara merender PDF dari XPS,
  dan menentukan nomor halaman PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Cara Mengonversi XPS ke PDF di Java
url: /id/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi XPS ke PDF di Java

## Cara Mengonversi XPS ke PDF di Java
Dalam dunia pengembangan Java, **cara mengonversi XPS ke PDF** adalah pertanyaan yang sering muncul. Baik Anda sedang membangun sistem manajemen dokumen atau perlu menghasilkan laporan yang dapat dicetak, mengonversi file XPS secara andal dapat menjadi pengubah permainan. Untungnya, Aspose.Page untuk Java memudahkan **render PDF dari XPS** dengan hanya beberapa baris kode.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.Page untuk Java.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk pengaturan dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk produksi.  
- **Bisakah saya mengonversi hanya halaman tertentu?** Ya – gunakan opsi *specify PDF page numbers*.  
- **Apakah konversinya loss‑less?** Perpustakaan ini mempertahankan fidelitas grafik vektor dan teks.

## Apa itu konversi XPS ke PDF?
XPS (XML Paper Specification) adalah format dokumen berlayout tetap milik Microsoft. Mengonversinya ke PDF memungkinkan Anda berbagi, mencetak, atau mengarsipkan dokumen menggunakan standar PDF yang diterima secara universal.

## Mengapa menggunakan Aspose.Page untuk Java dalam merender PDF dari XPS?
- **Fidelitas tinggi** – mempertahankan grafik vektor, font, dan tata letak.  
- **Kontrol detail** – Anda dapat mengatur kualitas gambar, kompresi, dan bahkan memilih halaman tertentu.  
- **Tanpa ketergantungan eksternal** – murni Java, bekerja pada platform apa pun yang mendukung JDK.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- **Java Development Kit (JDK)** – versi terbaru (disarankan 8+).  
- **Aspose.Page untuk Java** – unduh perpustakaan dari [documentation](https://reference.aspose.com/page/java/).  
- Sebuah file XPS yang ingin Anda konversi.

## Impor Paket
Di proyek Java Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.Page untuk Java. Langkah ini penting untuk mengakses fungsionalitas yang dibutuhkan dalam konversi XPS ke PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Atur Direktori Dokumen
Tentukan jalur ke folder yang berisi file XPS sumber Anda.

```java
String dataDir = "Your Document Directory";
```

### Langkah 2: Inisialisasi PDF Output Stream
Buat `FileOutputStream` yang akan menerima PDF yang dihasilkan.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Langkah 3: Muat Dokumen XPS
Muat file XPS menggunakan Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Langkah 4: Inisialisasi PDF Save Options  
Buat opsi untuk konversi. Di sini Anda dapat **specify PDF page numbers**, menyesuaikan kualitas gambar, dan mengatur kompresi.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Langkah 5: Buat PDF Rendering Device  
Siapkan perangkat rendering yang akan menulis output PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Langkah 6: Simpan Dokumen  
Akhirnya, simpan dokumen XPS sebagai PDF menggunakan opsi dan perangkat yang telah Anda konfigurasikan.

```java
document.save(device, options);
```

Ulangi langkah‑langkah ini, sesuaikan jalur file dan opsi sesuai skenario spesifik Anda.

## Cara Menentukan Nomor Halaman PDF Saat Mengonversi XPS
Jika Anda hanya memerlukan sebagian halaman dari XPS asli, isi array `setPageNumbers` dengan indeks halaman yang diinginkan (dimulai dari 1). Ini membantu mengurangi ukuran file dan waktu pemrosesan.

## Masalah Umum & Pemecahan Masalah
- **FileNotFoundException** – Pastikan `dataDir` mengarah ke folder yang benar dan nama file XPS cocok.  
- **LicenseException** – Lisensi Aspose.Page yang valid diperlukan untuk penggunaan produksi; jika tidak, perpustakaan berjalan dalam mode evaluasi dengan watermark.  
- **Kualitas gambar rendah** – Tingkatkan `setJpegQualityLevel` atau beralih ke kompresi lossless bila diperlukan.

## Pertanyaan yang Sering Diajukan
### Bisakah saya mengonversi file XPS dengan banyak halaman menggunakan Aspose.Page untuk Java?
Ya, Anda dapat **specify PDF page numbers** dalam `PdfSaveOptions` (lihat Langkah 4) untuk menyertakan halaman apa pun yang Anda butuhkan.

### Di mana saya dapat menemukan dukungan tambahan atau berdiskusi tentang pertanyaan terkait Aspose.Page?
Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

### Apakah ada versi percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat menjelajahi fitur dengan [free trial](https://releases.aspose.com/).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
Kunjungi [this link](https://purchase.aspose.com/temporary-license/) untuk detail lisensi sementara.

### Di mana saya dapat membeli lisensi Aspose.Page untuk Java?
Anda dapat membeli lisensi [here](https://purchase.aspose.com/buy).

---

**Terakhir Diperbarui:** 2025-12-23  
**Diuji Dengan:** Aspose.Page untuk Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
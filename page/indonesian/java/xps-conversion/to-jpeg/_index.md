---
date: 2026-03-13
description: Pelajari cara mengonversi XPS ke JPEG dalam Java dengan Aspose.Page Java.
  Panduan langkah demi langkah ini menunjukkan cara mengonversi XPS ke JPEG secara
  efisien menggunakan pustaka Aspose.Page Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Cara Mengonversi XPS ke JPEG di Java menggunakan Aspose.Page Java
url: /id/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi XPS ke JPEG di Java menggunakan Aspose.Page Java

## Pendahuluan tentang Aspose.Page Java
Dalam tutorial ini **Anda akan belajar cara mengonversi XPS ke JPEG** dengan perpustakaan **Aspose.Page Java**. Mengonversi file XPS ke gambar JPEG adalah kebutuhan yang sering muncul ketika Anda perlu menampilkan halaman dokumen sebagai grafik raster di portal web, penampil desktop, atau lampiran email. Kami akan membahas setiap baris kode, menjelaskan mengapa setiap pengaturan penting, dan berbagi tips praktis sehingga Anda dapat menyematkan alur konversi ini ke dalam aplikasi Java Anda dengan percaya diri.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.Page Java  
- **Apakah saya dapat memilih halaman tertentu?** Ya – gunakan `setPageNumbers` di `JpegSaveOptions`  
- **Kualitas gambar apa yang dapat saya kontrol?** Mode smoothing, resolusi, dan pengaturan kualitas JPEG  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan (versi percobaan gratis tersedia)  
- **Apakah kode ini kompatibel dengan Java 8?** Tentu – API bekerja dengan Java 8 dan yang lebih baru  

## Apa itu XPS dan Mengapa Mengonversi XPS ke JPEG?
XPS (XML Paper Specification) adalah format dokumen berlayout tetap yang mirip dengan PDF. Mengonversi XPS ke JPEG berguna ketika Anda memerlukan gambar raster untuk thumbnail, lampiran email, atau saat mengintegrasikan dengan sistem yang hanya menerima file gambar. JPEG menawarkan keseimbangan yang baik antara kualitas visual dan ukuran file, menjadikannya ideal untuk pratinjau berbasis web.

## Prasyarat
Sebelum kita menyelam ke kode, pastikan Anda memiliki hal berikut:

- **Lingkungan Pengembangan Java** – JDK 8 atau yang lebih baru terpasang dan terkonfigurasi.  
- **Aspose.Page untuk Java** – Unduh perpustakaan terbaru dari situs resmi [here](https://releases.aspose.com/page/java/).  
- **Dokumen XPS Contoh** – File XPS yang ingin Anda ubah menjadi gambar JPEG.  

## Impor Paket
Mulailah dengan mengimpor kelas yang diperlukan ke dalam file sumber Java Anda:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Langkah 1: Inisialisasi Jalur dan Muat Dokumen XPS
Tetapkan direktori yang berisi file XPS sumber Anda dan buat instance `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Pro tip:** Gunakan `Paths.get()` dari `java.nio.file` untuk penanganan jalur yang independen platform.

## Langkah 2: Konfigurasikan Opsi Penyimpanan JPEG
Tentukan bagaimana gambar JPEG harus dirender—resolusi, smoothing, dan halaman mana yang akan diekspor:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` menghasilkan output beresolusi tinggi yang cocok untuk pencetakan.  
- `setPageNumbers` memungkinkan Anda memilih hanya halaman yang diperlukan, menghemat waktu dan memori.

## Langkah 3: Buat Perangkat Rendering
`ImageDevice` menangkap halaman yang dirender sebagai array byte:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Langkah 4: Render Dokumen XPS ke JPEG
Panggil metode `save`, dengan memberikan perangkat dan opsi yang telah Anda konfigurasikan:

```java
document.save(device, options);
```

Pada titik ini `device` menyimpan array dua dimensi di mana setiap elemen mewakili halaman yang dikodekan JPEG.

## Langkah 5: Iterasi Hasil dan Tulis File
Loop melalui halaman yang dirender dan tulis setiap array byte ke file JPEG terpisah:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Setiap file akan diberi nama `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, memudahkan identifikasi dokumen sumber dan nomor halaman.

## Kasus Penggunaan Umum
- **Membuat thumbnail** untuk sistem manajemen dokumen.  
- **Menyematkan pratinjau halaman** dalam aplikasi web yang hanya mendukung format gambar.  
- **Pemrosesan batch arsip XPS besar** menjadi JPEG untuk keperluan arsip atau pelaporan.  

## Masalah Umum & Pemecahan Masalah
| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| **File JPEG kosong** | Aliran output tidak di‑flush atau ditutup dengan benar | Pastikan `imageStream.close()` dipanggil di dalam loop dalam (seperti yang ditunjukkan). |
| **Kesalahan out‑of‑memory** pada file XPS besar | Merender semua halaman sekaligus mengonsumsi terlalu banyak RAM | Proses halaman dalam batch lebih kecil atau tingkatkan heap JVM (`-Xmx`). |
| **Halaman hilang** | `setPageNumbers` tidak mencakup halaman yang diinginkan | Verifikasi array nomor halaman sesuai dengan indeks halaman XPS yang sebenarnya (berbasis 1). |

## Pertanyaan yang Sering Diajukan

### Q: Apakah Aspose.Page cocok untuk proyek komersial?
A: Ya, Aspose.Page adalah produk komersial dengan opsi lisensi yang tersedia. Periksa [here](https://purchase.aspose.com/buy) untuk detailnya.

### Q: Bisakah saya mencoba Aspose.Page sebelum membeli?
A: Ya, Anda dapat memperoleh versi percobaan gratis [here](https://releases.aspose.com/).

### Q: Di mana saya dapat menemukan dokumentasi Aspose.Page?
A: Dokumentasi tersedia [here](https://reference.aspose.com/page/java/).

### Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Page?
A: Kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39) untuk dukungan berbasis komunitas.

### Q: Apakah saya memerlukan lisensi sementara untuk pengujian?
A: Ya, Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Anda kini telah menguasai **cara mengonversi XPS ke JPEG** menggunakan **Aspose.Page Java**. Dengan mengikuti panduan langkah‑demi‑langkah ini, Anda dapat mengintegrasikan alur konversi ini ke dalam aplikasi Java apa pun—baik itu alat desktop, layanan web, atau utilitas pemrosesan batch. Jangan ragu untuk bereksperimen dengan resolusi berbeda, pemilihan halaman, dan format gambar untuk menyesuaikan kebutuhan proyek Anda.

---

**Terakhir Diperbarui:** 2026-03-13  
**Diuji Dengan:** Aspose.Page 24.11 untuk Java (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
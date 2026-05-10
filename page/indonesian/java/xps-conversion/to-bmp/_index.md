---
date: 2026-03-08
description: Pelajari cara mengonversi XPS ke BMP di Java dan mengatur resolusi BMP
  menggunakan pustaka konversi gambar Aspose.Page java. Panduan ini mencakup output
  berkualitas tinggi dan tips yang ramah memori.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Konversi XPS ke BMP di Java – Atur Resolusi untuk Output Berkualitas Tinggi
url: /id/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi XPS ke BMP di Java

## Pendahuluan
Selamat datang di panduan langkah‑demi‑langkah ini tentang cara **mengonversi XPS ke BMP** di Java dan mengatur resolusi untuk kualitas gambar optimal menggunakan Aspose.Page. Baik Anda membangun alur kerja pencetakan, menghasilkan thumbnail, atau membutuhkan grafik beresolusi tinggi, mengontrol DPI memberi Anda fleksibilitas untuk memenuhi semua kebutuhan.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Page untuk Java adalah **perpustakaan konversi gambar java** yang paling lengkap untuk XPS → BMP.  
- **Apakah saya dapat mengontrol kualitas gambar?** Ya – gunakan `BmpSaveOptions` untuk **mengatur resolusi BMP** dan mode smoothing.  
- **Bagaimana cara menghindari OutOfMemoryError Java saat memproses file XPS besar?** Render halaman dalam partisi atau tingkatkan heap JVM (`-Xmx`).  
- **Apakah saya perlu mengonversi hanya halaman tertentu?** Tentu saja, `options.setPageNumbers()` memungkinkan Anda memilih halaman yang tepat.  
- **Versi Java mana yang didukung?** Semua versi Java modern (8 ke atas) bekerja dengan mulus.

## Apa tujuan mengatur resolusi?
Resolusi menentukan jumlah titik per inci (DPI) dalam gambar BMP yang dihasilkan. DPI yang lebih tinggi menghasilkan gambar yang lebih tajam, yang penting untuk pencetakan atau pekerjaan grafis detail. Mengatur resolusi memberi Anda kontrol penuh atas kualitas output alur kerja **convert xps to bmp** Anda.

## Mengapa menggunakan Aspose.Page untuk konversi XPS → BMP?
- **Fidelity tinggi** – mempertahankan kualitas vektor dari XPS asli.  
- **Kontrol halus** – Anda dapat mengatur DPI, smoothing, dan bahkan memilih halaman tertentu untuk dikonversi.  
- **Tanpa dependensi eksternal** – Java murni, tidak memerlukan pustaka native.  
- **Skalabel** – bekerja untuk dokumen satu halaman maupun file XPS multi‑halaman yang besar.  

## Prasyarat
Sebelum memulai proses konversi, pastikan Anda memiliki prasyarat berikut:
- **Lingkungan Pengembangan Java** – Java 8 atau lebih baru terpasang di mesin Anda.  
- **Pustaka Aspose.Page untuk Java** – Unduh dan sertakan pustaka Aspose.Page untuk Java dalam proyek Anda. Anda dapat menemukan pustaka tersebut [di sini](https://releases.aspose.com/page/java/).  
- **File XPS Contoh** – Siapkan dokumen XPS contoh yang ingin Anda konversi ke BMP.

## Impor Paket
Sertakan paket Aspose.Page yang diperlukan dalam kode Java Anda:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Cara Mengatur Resolusi untuk Konversi XPS ke BMP
Berikut adalah panduan singkat berurutan yang menunjukkan secara tepat di mana dan bagaimana mengatur resolusi, serta cara **mengonversi halaman tertentu**.

### Langkah 1: Muat Dokumen XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Langkah 2: Inisialisasi Opsi (Resolusi & Pemilihan Halaman)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Langkah 3: Buat Perangkat Rendering
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Langkah 4: Simpan Dokumen Menggunakan Opsi
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Langkah 5: Iterasi Gambar yang Dirender dan Tulis File
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Ulangi langkah-langkah ini untuk setiap penyesuaian atau modifikasi tambahan yang Anda perlukan dalam proses konversi.

## Cara Menghindari OutOfMemoryError Java Saat Mengonversi File XPS Besar
- **Proses dalam partisi** – Contoh ini sudah merender dokumen dalam partisi (`device.getResult()`), yang mengurangi tekanan memori.  
- **Tingkatkan heap JVM** – Gunakan flag `-Xmx` (mis., `-Xmx2g`) untuk mengalokasikan lebih banyak memori bagi dokumen besar.  
- **Buang sumber daya** – Panggil `document.close()` setelah selesai untuk membebaskan sumber daya native.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Output BMP berkualitas rendah** | Verifikasi `options.setResolution()` diatur ke nilai ≥ 300 DPI. |
| **Hanya sebagian dokumen yang dikonversi** | Pastikan `options.setPageNumbers()` mencakup semua indeks halaman yang diinginkan. |
| **OutOfMemoryError pada file XPS besar** | Proses dokumen dalam partisi yang lebih kecil atau tingkatkan ukuran heap JVM (`-Xmx`). |
| **File tidak ditemukan** | Periksa kembali jalur `dataDir` dan pastikan file XPS input ada. |

## Pertanyaan yang Sering Diajukan
### Q: Bisakah saya menyesuaikan resolusi gambar BMP?
A: Ya, Anda dapat mengubah resolusi dengan memodifikasi parameter `options.setResolution()` dalam kode.

### Q: Apakah Aspose.Page kompatibel dengan berbagai versi Java?
A: Ya, Aspose.Page mendukung berbagai versi Java. Pastikan Anda memiliki versi yang kompatibel terpasang.

### Q: Bagaimana saya dapat mengonversi file XPS dari rentang halaman tertentu?
A: Gunakan metode `options.setPageNumbers()` untuk menentukan nomor halaman yang ingin Anda konversi.

### Q: Apakah ada format output lain yang didukung oleh Aspose.Page?
A: Ya, Aspose.Page mendukung berbagai format output. Lihat dokumentasi untuk daftar lengkap.

### Q: Di mana saya dapat menemukan bantuan atau dukungan tambahan?
A: Kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
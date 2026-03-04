---
date: 2025-12-23
description: Dengan mudah **mengonversi XPS ke PNG** dalam Java menggunakan Aspose.Page.
  Panduan ini menunjukkan cara merender XPS ke file gambar dengan solusi yang andal
  dan ramah pengembang.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Mengonversi XPS ke PNG di Java
url: /id/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi XPS ke PNG di Java

## Perkenalan
Di dunia pengembangan perangkat lunak yang dinamis, kebutuhan untuk **mengonversi XPS ke PNG** (Spesifikasi Kertas XML ke Portable Network Graphics) muncul secara sering. Untuk menyelesaikan tugas ini dengan mulus di Java, Aspose.Page menyediakan solusi yang kuat. Pada tutorial ini, kami akan memandu proses mengubah XPS ke PNG menggunakan Aspose.Page untuk Java.

## Jawaban Cepat
- **Pustaka apa yang menangani konversi?** Aspose.Page untuk Java
- **Format apa saja yang terlibat?** XPS (sumber) → PNG (output)
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan
- **Dapatkah saya menyetel resolusi gambar?** Ya, menggunakan `PngSaveOptions.setResolution()`
- **Apakah mungkin untuk memilih halaman tertentu?** Tentu saja – berikan nomor halaman di objek opsi

## Mengapa Mengonversi XPS ke PNG?
Merender XPS ke file gambar berguna ketika Anda perlu menampilkan dokumen di web, menyematkannya dalam laporan, atau menghasilkan thumbnail untuk kepuasan. PNG menawarkan kompresi lossless dan dukungan browser yang luas, menjadikannya pilihan ideal untuk representasi visual berkualitas tinggi dari konten XPS.

## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Pastikan JDK terinstal di sistem Anda.
2. Aspose.Page untuk Java: Unduh dan instal pustaka Aspose.Page. Anda dapat menemukan tautan unduhan [di sini](https://releases.aspose.com/page/java/).
3. Integrated Development Environment (IDE): Pilih IDE yang kompatibel dengan Java seperti IntelliJ IDEA atau Eclipse.

## Cara mengonversi XPS ke PNG di Java
Berikut adalah panduan langkah‑demi‑langkah yang menjelaskan **cara mengubah XPS** menjadi gambar PNG, termasuk potongan kode yang dapat Anda salin langsung ke proyek Anda.

### Impor Paket
Di proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Tambahkan pernyataan impor berikut di awal file Java Anda:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Langkah 1: Atur Direktori Dokumen
Tentukan folder yang berisi file XPS sumber Anda dan tempat file PNG akan disimpan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Langkah 2: Muat Dokumen XPS
Buat instance `XpsDocument` yang memuat file XPS sumber.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Langkah 3: Inisialisasi Opsi
Konfigurasikan opsi output PNG. Di sini Anda dapat mengatur smoothing, resolusi, dan menentukan halaman mana yang akan dirender.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Langkah 4: Buat Perangkat Rendering
Buat `ImageDevice` yang akan menampung data gambar yang dirender.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Langkah 5: Simpan dan Ulangi
Render dokumen XPS, kemudian tulis setiap array byte PNG yang dihasilkan ke file di disk.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Dengan mengikuti langkah‑langkah ini, Anda dapat dengan mudah **merender XPS ke gambar** dalam format PNG menggunakan Aspose.Page untuk Java.

## Kesimpulan
Kesimpulannya, Aspose.Page untuk Java, dengan proses konversi XPS ke PNG yang mudah dan efisien, memberikan pengembang alat yang andal. Integrasikan pustaka ini ke dalam proyek Java Anda untuk mempermudah tugas peninjauan dokumen.

## Pertanyaan Tambahan yang Sering Diajukan

**T: Dapatkah saya mengkonversi hanya halaman-halaman tertentu dari file XPS?**
J: Tentu saja. Gunakan metode `setPageNumbers` di `PngSaveOptions` untuk menentukan halaman yang ingin Anda render.

**T: Resolusi gambar apa yang direkomendasikan untuk PNG berkualitas tinggi?**
J: Resolusi 300dpi adalah keseimbangan yang baik antara kualitas dan ukuran file, tetapi Anda dapat menyesuaikannya melalui `options.setResolution()`.

**T: Apakah API mendukung konversi multi-threaded untuk dokumen besar?**
J: Ya, Anda dapat memanggil logika konversi dalam thread paralel, masing-masing menangani halaman atau partisi dokumen yang berbeda.

**T: Bagaimana cara menangani penggunaan memori saat mengonversi file XPS yang sangat besar?**
J: Proses halaman secara berurutan dan lepaskan `FileOutputStream` setelah setiap penulisan, seperti yang ditunjukkan dalam kode contoh.

**T: Apakah ada cara untuk menambahkan metadata khusus ke file PNG yang dihasilkan?**
J: Meskipun `PngSaveOptions` tidak secara langsung mengekspos bidang metadata, Anda dapat memproses PNG menggunakan pustaka gambar standar untuk menyematkan metadata.

---

**Terakhir Diperbarui:** 2025-12-23
**Diuji Dengan:** Aspose.Page untuk Java 24.12 (terbaru)
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
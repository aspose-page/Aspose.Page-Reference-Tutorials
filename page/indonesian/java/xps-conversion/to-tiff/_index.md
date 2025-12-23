---
date: 2025-12-23
description: Konversi XPS ke TIFF dengan mudah menggunakan Aspose.Page Java. Ikuti
  panduan langkah demi langkah kami untuk integrasi yang mulus menggunakan Aspose.Page
  Java. Unduh sekarang!
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Mengonversi XSP ke TIFF di Java menggunakan Aspose.Page Java
url: /id/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi XSP ke TIFF di Java menggunakan Aspose.Page Java

Dalam lanskap perangkat lunak yang bergerak cepat saat ini, **aspose page java** membuat konversi dokumen Java menjadi sederhana dan dapat diandalkan. Baik Anda perlu **convert XPS to TIFF** untuk arsip, pencetakan, atau pemrosesan batch, tutorial ini memandu Anda melalui langkah‑langkah yang tepat, menjelaskan “mengapa” di balik setiap tindakan, dan memberikan tip praktis yang dapat langsung Anda terapkan.

## Quick Answers
- **Library apa yang menangani konversi XPS‑to‑TIFF?** Aspose.Page Java.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi Aspose.Page Java yang valid diperlukan.  
- **Versi Java mana yang didukung?** JDK 8 atau lebih tinggi.  
- **Bisakah saya mengonversi beberapa file XPS sekaligus?** Ya – Anda dapat membuat loop konversi XPS batch dengan kode yang sama.  
- **Resolusi apa yang paling cocok untuk TIFF siap cetak?** 300 DPI adalah pilihan umum, tetapi Anda dapat menyesuaikannya melalui TiffSaveOptions.

## What is Aspose.Page Java?
Aspose.Page Java adalah API yang kuat yang memungkinkan **java document conversion** dari XPS (XML Paper Specification) ke berbagai format raster dan vektor, termasuk TIFF. Ia menangani tata letak halaman yang kompleks, font, dan grafik tanpa memerlukan Microsoft XPS Document Writer.

## Why Use Aspose.Page Java for XPS to TIFF Conversion?
- **High fidelity:** Mempertahankan data vektor dan rendering teks.  
- **Performance:** Dioptimalkan untuk file besar dan skenario konversi XPS batch.  
- **Flexibility:** Menyetel output secara detail dengan `tiff save options` seperti resolusi, kompresi, dan pemilihan halaman.  
- **Cross‑platform:** Berfungsi pada sistem operasi apa pun yang mendukung Java, menjadikannya ideal untuk pemrosesan sisi server.

## Prerequisites
Sebelum menyelami proses konversi, pastikan Anda memiliki:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Aspose.Page for Java library. Anda dapat mengunduhnya [here](https://releases.aspose.com/page/java/).  
- Lisensi yang valid untuk Aspose.Page for Java. Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/), atau membeli lisensi penuh [here](https://purchase.aspose.com/buy).

## Import Packages
Mulailah dengan mengimpor paket yang diperlukan dalam proyek Java Anda. Pastikan JAR Aspose.Page untuk Java ditambahkan ke jalur build Anda.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Step 1: Set Up Document Directory
Tentukan jalur ke folder yang berisi file XPS sumber Anda.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Load XPS Document
Buat instance `XpsDocument` yang menunjuk ke file input.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## Step 3: Initialize TiffSaveOptions
Konfigurasikan **tiff save options** yang mengontrol kualitas gambar, resolusi, dan halaman mana yang akan diekspor.

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## Step 4: Create Rendering Device
Instansiasi `ImageDevice` yang akan merender halaman menjadi gambar TIFF.

```java
ImageDevice device = new ImageDevice();
```

## Step 5: Save Document to TIFF
Render dokumen XPS menggunakan perangkat dan opsi yang telah didefinisikan sebelumnya.

```java
document.save(device, options);
```

## Step 6: Iterate and Save TIFF Images
Loop melalui buffer gambar yang dirender dan tulis setiap halaman ke file TIFF terpisah.

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Selamat! Anda telah berhasil **convert XPS to TIFF** di Java menggunakan **aspose page java**. Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsionalitas pustaka ini di [documentation](https://reference.aspose.com/page/java/).

## Conclusion
Dalam tutorial ini kami membahas semua yang perlu Anda ketahui untuk melakukan **java document conversion** dari XPS ke TIFF, mulai dari menyiapkan lingkungan hingga menyetel `tiff save options` secara detail. Dengan Aspose.Page Java Anda juga dapat membangun pipeline **batch XPS conversion** yang memproses puluhan atau ratusan file secara otomatis.

## Frequently Asked Questions
### Bisakah saya menggunakan Aspose.Page untuk Java tanpa lisensi?
Meskipun Anda dapat memperoleh lisensi sementara untuk evaluasi, lisensi yang valid diperlukan untuk penggunaan produksi. Dapatkan lisensi Anda [here](https://purchase.aspose.com/buy).

### Apakah ada batasan pada ukuran file XPS untuk konversi?
Aspose.Page untuk Java menangani dokumen dengan berbagai ukuran, tetapi disarankan untuk menguji dengan file yang lebih besar di lingkungan spesifik Anda.

### Bagaimana saya dapat mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.Page untuk Java?
Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

### Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat menjelajahi pustaka dengan percobaan gratis. Unduh [here](https://releases.aspose.com/).

### Apa resolusi yang direkomendasikan untuk gambar TIFF dalam konversi ini?
Contoh ini menggunakan resolusi 300 DPI, tetapi Anda dapat menyesuaikannya berdasarkan kebutuhan spesifik Anda.

---

**Terakhir Diperbarui:** 2025-12-23  
**Diuji Dengan:** Aspose.Page Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
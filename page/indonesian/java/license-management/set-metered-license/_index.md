---
date: 2026-09-24
description: Pelajari cara menggunakan Aspose.Page untuk mengonversi EPS ke PNG di
  Java, mengonfigurasi lisensi bermeter, dan menulis kode Java untuk file PNG secara
  efisien.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Atur Lisensi Metered di Java
og_description: Aspose.Page mengonversi EPS ke PNG di Java dengan lisensi bermeter.
  Panduan ini menunjukkan langkah demi langkah cara mengonfigurasi lisensi, merender
  EPS, dan menulis kode Java untuk file PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page mengonversi EPS ke PNG di Java (lisensi bermeter)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page mengonversi EPS ke PNG di Java (lisensi bermeter)
url: /id/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page mengonversi EPS ke PNG di Java (lisensi terukur)

## Pendahuluan
Jika Anda perlu **menyimpan EPS sebagai PNG** dalam aplikasi Java sambil menjaga lisensi tetap sederhana, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui konfigurasi **lisensi terukur** untuk Aspose.Page, memuat file EPS (Encapsulated PostScript), dan mengonversinya menjadi gambar PNG. Pada akhir tutorial, Anda akan memahami cara **merender EPS ke PNG secara efisien** dan cara **menulis kode Java untuk file PNG** yang berfungsi andal di produksi.

## Jawaban cepat
- **Apa arti “save EPS as PNG”?** Ini mengonversi file EPS vektor menjadi gambar PNG raster, mempertahankan transparansi dan kompresi lossless.  
- **Mengapa menggunakan lisensi terukur?** Anda hanya membayar untuk halaman yang diproses, yang ideal untuk beban kerja yang bervariasi.  
- **Apakah saya memerlukan koneksi internet?** Tidak, kunci terukur divalidasi secara lokal pada JVM.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih tinggi didukung sepenuhnya.  
- **Berapa lama proses penyiapan?** Sekitar 10 menit untuk implementasi dasar.

## Apa itu “save EPS to PNG”?
Menyimpan EPS sebagai PNG mengonversi dokumen Encapsulated PostScript vektor menjadi gambar PNG raster, mempertahankan transparansi dan menawarkan kompresi lossless. Transformasi ini berguna ketika Anda membutuhkan grafik siap web, thumbnail, atau pratinjau cetak yang dapat ditampilkan di browser apa pun tanpa memerlukan interpreter PostScript.

## Mengapa merender EPS ke PNG dengan Aspose.Page?
Aspose.Page menyediakan API pure‑Java yang merasterisasi file EPS dengan fidelitas tinggi, mendukung lebih dari 50 format output, dan menawarkan lisensi terukur sehingga Anda hanya membayar untuk apa yang Anda konversi. Perpustakaan ini dapat memproses dokumen ratusan halaman tanpa memuat seluruh file ke memori, memberikan rendering cepat dan akurat pada platform apa pun yang mendukung JVM.

## Prasyarat
- Pengalaman dasar pengembangan Java.  
- Perpustakaan Aspose.Page yang diunduh dari [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Sepasang kunci publik dan privat terukur dari akun Aspose Anda.  

## Impor paket
Pernyataan `import` membawa kelas yang diperlukan ke dalam ruang lingkup. Pertahankan blok ini persis seperti yang ditampilkan agar kode dapat dikompilasi tanpa perubahan.

Kelas `java.io` menangani aliran file, sementara kelas Aspose.Page mengelola lisensi, pemuatan dokumen, dan rendering gambar.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Cara menyimpan EPS sebagai PNG menggunakan Aspose.Page Java
Berikut adalah panduan langkah demi langkah yang menggabungkan lisensi, pemuatan, rendering, dan penulisan file PNG akhir.

### Jawaban langsung
Muat file EPS Anda, terapkan lisensi terukur, konfigurasikan `ImageSaveOptions` untuk PNG, render dokumen ke `ImageDevice`, dan akhirnya tulis array byte yang dihasilkan ke disk. Urutan ini menyelesaikan alur kerja **save EPS as PNG** dalam hanya beberapa baris kode Java.

### Langkah 1: inisialisasi dokumen dan format gambar
Pertama, atur kunci terukur dan tentukan format output (PNG). Ini membangun fondasi untuk konversi.

Kelas `MeteredLicense` menyimpan kunci publik dan privat Anda, sementara `ImageSaveOptions` memberi tahu Aspose.Page untuk menghasilkan output PNG.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Langkah 2: inisialisasi aliran input PostScript
Buka file EPS yang ingin Anda konversi. Aliran tersebut memberi dokumen ke Aspose.Page.

`FileInputStream` membaca file EPS dari disk, memungkinkan konstruktor `Document` untuk mengurai data PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Langkah 3: periksa lisensi dokumen
Selalu verifikasi bahwa lisensi terukur telah diterapkan dengan benar sebelum memproses.

Metode `isLicensed()` mengembalikan `true` hanya ketika kunci yang diberikan valid, mencegah penggunaan tidak sengaja perpustakaan yang tidak berlisensi.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Langkah 4: inisialisasi opsi dan perangkat gambar
Buat objek opsi yang mengontrol pengaturan konversi dan perangkat yang akan menerima gambar yang dirender.

`ImageDevice` menangkap output raster dalam memori, sementara `ImageSaveOptions` memungkinkan Anda menyesuaikan DPI, tingkat kompresi, dan kedalaman warna.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Langkah 5: simpan file EPS sebagai gambar
Ini adalah pemanggilan inti **save EPS as PNG**. Dokumen dirender ke perangkat gambar menggunakan opsi yang telah kami konfigurasikan.

Metode `document.save(device, options)` melakukan rasterisasi dalam satu langkah.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Langkah 6: dapatkan dan simpan byte gambar
Ekstrak byte PNG dari perangkat dan tulis ke file di disk. Langkah ini menunjukkan cara **menulis file PNG Java** dengan aman.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` menyimpan gambar tanpa perpustakaan tambahan.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Masalah umum dan solusi
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| **Lisensi tidak dikenali** | Kunci tidak benar atau `setMeteredKey` dipanggil setelah pemrosesan dokumen. | Periksa kembali string kunci publik/privat dan pastikan `setMeteredKey` dijalankan sebelum panggilan Aspose.Page apa pun. |
| **File output kosong** | `device.getImagesBytes()` mengembalikan `null` karena file EPS tidak dapat diparse. | Verifikasi bahwa file EPS valid dan bahwa `ImageSaveOptions` menentukan ukuran kanvas non‑nol. |
| **OutOfMemoryError pada EPS besar** | Merender file vektor besar mengonsumsi banyak memori heap. | Proses halaman satu per satu atau tingkatkan heap JVM (`-Xmx2g`). |

## Pertanyaan yang sering diajukan

**Q: Bagaimana cara saya mendapatkan kunci publik dan privat terukur?**  
A: Masuk ke akun Aspose Anda, buka bagian **Metered License**, dan salin kunci publik serta privat yang dihasilkan.

**Q: Apakah perpustakaan Aspose.Page gratis?**  
A: Aspose.Page menawarkan percobaan gratis dengan fungsionalitas penuh; penggunaan produksi memerlukan lisensi berbayar. Unduh percobaan [Aspose trial download page](https://releases.aspose.com/).

**Q: Apakah saya dapat menggunakan Aspose.Page untuk proyek komersial?**  
A: Ya, lisensi komersial memungkinkan penyebaran di lingkungan produksi. Beli lisensi [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Di mana saya dapat menemukan dokumentasi tambahan?**  
A: Referensi API lengkap tersedia di [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk evaluasi?**  
A: Lisensi sementara disediakan melalui portal Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Bagaimana jika saya perlu mengonversi file EPS multi‑halaman?**  
A: Lakukan loop melalui setiap halaman menggunakan `device.getImagesBytes()` dan tulis setiap array byte ke file PNG terpisah.

**Q: Apakah saya dapat mengubah kualitas PNG atau kedalaman warna?**  
A: Ya, konfigurasikan `ImageSaveOptions` (mis., `options.setCompressionLevel(9)`) sebelum memanggil `document.save(...)`.

---

**Terakhir diperbarui:** 2026-09-24  
**Diuji dengan:** Aspose.Page 24.12 for Java (latest)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Mengatur Lisensi untuk Aspose.Page Java API – Manajemen Lisensi](/page/java/license-management/)
- [Mengonversi PS ke PNG dengan Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Ubah ukuran EPS menggunakan Aspose.Page – Manipulasi EPS Java](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
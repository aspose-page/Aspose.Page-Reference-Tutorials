---
date: 2025-12-03
description: Pelajari cara menyimpan EPS sebagai PNG menggunakan Aspose.Page untuk
  Java sambil mengonfigurasi lisensi bermeteri. Panduan langkah demi langkah dengan
  contoh kode lengkap.
language: id
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Simpan EPS sebagai PNG dengan Aspose.Page Java (Lisensi Metered)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan EPS sebagai PNG dengan Aspose.Page Java (Lisensi Metered)

## Pendahuluan
Jika Anda perlu **menyimpan EPS sebagai PNG** dalam aplikasi Java dan menginginkan cara yang mudah untuk mengelola lisensi, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui konfigurasi lisensi metered untuk Aspose.Page, memuat file PostScript (EPS), dan mengonversinya menjadi gambar PNG—semua dengan langkah‑langkah jelas yang dapat Anda ikuti langsung.

## Jawaban Cepat
- **Apa arti “menyimpan EPS sebagai PNG”?** Itu mengonversi file EPS vektor menjadi gambar raster PNG.  
- **Mengapa menggunakan lisensi metered?** Anda hanya membayar untuk halaman yang diproses, cocok untuk beban kerja yang berubah-ubah.  
- **Apakah saya memerlukan koneksi internet?** Tidak, kunci metered divalidasi secara lokal.  
- **Versi Java mana yang diperlukan?** Java 8 atau lebih tinggi.  
- **Berapa lama proses penyiapan?** Sekitar 10 menit untuk implementasi dasar.

## Apa itu “menyimpan EPS sebagai PNG”?
Menyimpan EPS sebagai PNG mengubah dokumen Encapsulated PostScript yang dapat diskalakan menjadi format bitmap yang didukung secara luas. PNG mempertahankan transparansi dan menawarkan kompresi lossless, menjadikannya ideal untuk grafik web, thumbnail, dan pratinjau cetak.

## Mengapa menggunakan Aspose.Page untuk tugas ini?
- **Pure Java API** – tanpa ketergantungan native.  
- **Fidelity tinggi** – grafik vektor dirender secara akurat.  
- **Lisensi metered** – Anda hanya membayar apa yang Anda konversi.  
- **Dukungan untuk banyak format output** – PNG, JPEG, TIFF, dll.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Page terpasang – unduh dari [here](https://releases.aspose.com/page/java/).  
- Kunci publik dan privat metered, yang dapat Anda peroleh melalui akun Aspose Anda.

## Impor Paket
Pertama, impor kelas‑kelas yang diperlukan. Jaga blok impor persis seperti yang ditunjukkan agar kode dapat dikompilasi tanpa perubahan.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Langkah 1: Inisialisasi Dokumen dan Format Gambar
Di sini kami mengatur kunci metered dan mendefinisikan format output (PNG). Ini adalah fondasi untuk operasi **menyimpan EPS sebagai PNG**.

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

## Langkah 2: Inisialisasi Aliran Input PostScript
Buka file EPS yang ingin Anda konversi. Aliran ini memberi dokumen ke Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Langkah 3: Periksa Lisensi Dokumen
Selalu verifikasi bahwa lisensi metered telah diterapkan dengan benar sebelum memproses.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Langkah 4: Inisialisasi Opsi dan Perangkat Gambar
Buat objek opsi yang mengontrol pengaturan konversi dan perangkat yang akan menerima gambar yang dirender.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Langkah 5: Simpan File EPS sebagai Gambar
Ini adalah panggilan inti **menyimpan EPS sebagai PNG**. Dokumen dirender ke perangkat gambar menggunakan opsi yang telah kami konfigurasikan.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Langkah 6: Dapatkan dan Simpan Byte Gambar
Ekstrak byte PNG dari perangkat dan tulis ke file di disk.

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

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|---------|-----------------|--------|
| **Lisensi tidak dikenali** | Kunci salah atau ditempatkan dalam urutan yang salah. | Periksa kembali string kunci publik/privat dan pastikan `setMeteredKey` dipanggil sebelum pemrosesan dokumen apa pun. |
| **File output kosong** | `device.getImagesBytes()` mengembalikan `null`. | Pastikan file EPS valid dan `ImageSaveOptions` tidak diatur ke kanvas berukuran nol. |
| **OutOfMemoryError pada EPS besar** | Merender file vektor besar mengonsumsi banyak memori. | Proses halaman satu per satu atau tingkatkan heap JVM (`-Xmx2g`). |

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara mendapatkan kunci publik dan privat metered?**  
J: Anda dapat memperoleh kunci tersebut melalui akun Aspose Anda.

**T: Apakah perpustakaan Aspose.Page gratis?**  
J: Aspose.Page menawarkan versi percobaan gratis dan versi berbayar. Kunjungi [here](https://releases.aspose.com/) untuk percobaan gratis.

**T: Dapatkah saya menggunakan Aspose.Page untuk proyek komersial?**  
J: Ya, Aspose.Page menyediakan lisensi komersial. Anda dapat membelinya [here](https://purchase.aspose.com/buy).

**T: Di mana saya dapat menemukan dokumentasi tambahan?**  
J: Lihat dokumentasi [here](https://reference.aspose.com/page/java/).

**T: Bagaimana cara mendapatkan lisensi sementara?**  
J: Lisensi sementara dapat diperoleh [here](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2025-12-03  
**Diuji Dengan:** Aspose.Page 24.12 untuk Java  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

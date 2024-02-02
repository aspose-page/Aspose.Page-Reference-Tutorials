---
title: Konversi XPS ke BMP di Java
linktitle: Konversi XPS ke BMP di Java
second_title: Aspose.Halaman Java API
description: Pelajari cara mengonversi XPS ke BMP di Java dengan Aspose.Page. Ikuti panduan mudah kami untuk konversi dokumen yang efisien dan berkualitas tinggi.
type: docs
weight: 10
url: /id/java/xps-conversion/to-bmp/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah tentang mengonversi file XPS (Spesifikasi Kertas XML) ke format BMP (Bitmap) di Java menggunakan Aspose.Page. Aspose.Page untuk Java adalah perpustakaan canggih yang menyediakan fitur komprehensif untuk bekerja dengan dokumen XPS. Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file XPS menjadi gambar BMP dengan mudah.
## Prasyarat
Sebelum mendalami proses konversi, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda.
-  Aspose.Page untuk Perpustakaan Java: Unduh dan sertakan perpustakaan Aspose.Page untuk Java dalam proyek Anda. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/page/java/).
- Contoh File XPS: Siapkan contoh dokumen XPS yang ingin Anda konversi ke BMP.
## Paket Impor
Sertakan paket Aspose.Page yang diperlukan dalam kode Java Anda:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
Mari kita bagi proses konversi menjadi langkah-langkah yang mudah diikuti:
## Langkah 1: Muat Dokumen XPS
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Muat dokumen XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Langkah 2: Inisialisasi Opsi
```java
// Inisialisasi objek opsi dengan parameter yang diperlukan.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[]{1, 2, 6});
```
## Langkah 3: Buat Perangkat Rendering
```java
// Buat perangkat rendering untuk format BMP
ImageDevice device = new ImageDevice();
```
## Langkah 4: Simpan Dokumen
```java
// Simpan dokumen XPS ke BMP menggunakan opsi dan perangkat
document.save(device, options);
```
## Langkah 5: Ulangi dan Simpan Gambar
```java
// Iterasi melalui partisi dokumen
for (int i = 0; i < device.getResult().length; i++) {
    // Iterasi melalui halaman partisi
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inisialisasi aliran keluaran gambar
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Tulis gambar
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
Ulangi langkah-langkah ini untuk penyesuaian atau modifikasi tambahan apa pun yang mungkin Anda perlukan dalam proses konversi.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengonversi file XPS ke BMP di Java menggunakan Aspose.Page. Fleksibilitas dan kemudahan penggunaan yang disediakan oleh Aspose.Page menjadikannya alat yang berharga untuk menangani tugas konversi dokumen.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menyesuaikan resolusi gambar BMP?
 A: Ya, Anda dapat menyesuaikan resolusi dengan memodifikasi`options.setResolution()`parameter dalam kode.
### T: Apakah Aspose.Page kompatibel dengan versi Java yang berbeda?
J: Ya, Aspose.Page mendukung berbagai versi Java. Pastikan Anda menginstal versi yang kompatibel.
### T: Bagaimana cara mengonversi file XPS dari rentang halaman tertentu?
 J: Gunakan`options.setPageNumbers()` metode untuk menentukan nomor halaman yang ingin Anda konversi.
### T: Apakah ada format keluaran lain yang didukung oleh Aspose.Page?
J: Ya, Aspose.Page mendukung berbagai format output. Lihat dokumentasi untuk daftar lengkap.
### T: Di mana saya bisa mendapatkan bantuan atau dukungan tambahan?
 J: Kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.
---
title: Konversi XSP ke TIFF di Java
linktitle: Konversi XSP ke TIFF di Java
second_title: Aspose.Halaman Java API
description: Konversikan XPS ke TIFF dengan mudah menggunakan Aspose.Page untuk Java. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar. Unduh sekarang!
weight: 14
url: /id/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi XSP ke TIFF di Java

Di era digital saat ini, konversi dokumen memegang peranan penting dalam berbagai aplikasi. Jika Anda seorang pengembang Java yang mencari solusi tangguh untuk mengonversi dokumen XPS (Spesifikasi Kertas XML) ke TIFF (Tagged Image File Format), Aspose.Page untuk Java adalah perpustakaan pilihan Anda. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui prosesnya, memastikan Anda mendapatkan pengalaman yang lancar dengan penjelasan mendetail dan cuplikan kode.
## Prasyarat
Sebelum mendalami proses konversi, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
-  Lisensi yang valid untuk Aspose.Page untuk Java. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) , atau beli lisensi penuh[Di Sini](https://purchase.aspose.com/buy).
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan dalam proyek Java Anda. Pastikan Anda memiliki perpustakaan Aspose.Page untuk Java yang ditambahkan ke proyek Anda.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Langkah 1: Siapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat file input XPS berada.
```java
String dataDir = "Your Document Directory";
```
## Langkah 2: Muat Dokumen XPS
Muat dokumen XPS menggunakan perpustakaan Aspose.Page.
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Langkah 3: Inisialisasi TiffSaveOptions
Inisialisasi objek TiffSaveOptions dengan parameter yang diperlukan, seperti mode penghalusan, resolusi, dan nomor halaman tertentu.
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Langkah 4: Buat Perangkat Rendering
Buat perangkat rendering untuk format TIFF menggunakan kelas ImageDevice.
```java
ImageDevice device = new ImageDevice();
```
## Langkah 5: Simpan Dokumen ke TIFF
Simpan dokumen XPS ke format TIFF menggunakan opsi dan perangkat rendering yang ditentukan.
```java
document.save(device, options);
```
## Langkah 6: Ulangi dan Simpan Gambar TIFF
Iterasi melalui partisi dan halaman dokumen, inisialisasi aliran keluaran gambar dan simpan gambar TIFF.
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 Selamat! Anda telah berhasil mengonversi XPS ke TIFF di Java menggunakan Aspose.Page. Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsi perpustakaan di[dokumentasi](https://reference.aspose.com/page/java/).
## Kesimpulan
Dalam tutorial ini, kami telah membahas langkah-langkah penting untuk mengonversi XPS ke TIFF di Java menggunakan Aspose.Page. Konversi dokumen kini ada di ujung jari Anda, memungkinkan Anda menyempurnakan aplikasi Anda dengan dukungan format file serbaguna.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java tanpa lisensi?
 Meskipun Anda bisa mendapatkan lisensi sementara untuk evaluasi, lisensi yang valid diperlukan untuk penggunaan produksi. Dapatkan lisensi Anda[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada batasan ukuran file XPS untuk konversi?
Aspose.Page untuk Java menangani dokumen dengan berbagai ukuran, namun disarankan untuk menguji dengan file yang lebih besar di lingkungan spesifik Anda.
### Bagaimana saya bisa mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.Page untuk Java?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat menjelajahi perpustakaan dengan uji coba gratis. Unduh itu[Di Sini](https://releases.aspose.com/).
### Berapa resolusi yang disarankan untuk gambar TIFF dalam konversi ini?
Contoh yang diberikan menggunakan resolusi 300 DPI, namun Anda dapat menyesuaikannya berdasarkan kebutuhan spesifik Anda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

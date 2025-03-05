---
title: Konversi XPS ke JPEG di Java
linktitle: Konversi XPS ke JPEG di Java
second_title: Aspose.Halaman Java API
description: Pelajari cara mengonversi XPS ke JPEG di Java menggunakan Aspose.Page. Panduan komprehensif dengan petunjuk langkah demi langkah untuk integrasi yang lancar.
type: docs
weight: 11
url: /id/java/xps-conversion/to-jpeg/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengonversi file XPS (Spesifikasi Kertas XML) menjadi gambar JPEG menggunakan Aspose.Page untuk Java. Aspose.Page adalah perpustakaan Java yang kuat yang memungkinkan pengembang untuk bekerja dengan XPS dan format dokumen lainnya dengan lancar. Panduan langkah demi langkah ini akan membantu Anda memahami proses dan menerapkannya dalam aplikasi Java Anda.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di mesin Anda.
-  Aspose.Page untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.Page untuk Java. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/page/java/).
- Contoh Dokumen XPS: Miliki contoh dokumen XPS yang ingin Anda konversi ke JPEG.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke kelas Java Anda:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Langkah 1: Inisialisasi Jalur dan Dokumen XPS
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Inisialisasi aliran input XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Langkah 2: Atur JpegSaveOptions
```java
// Inisialisasi objek opsi dengan parameter yang diperlukan.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Langkah 3: Buat Perangkat Rendering
```java
// Buat perangkat rendering untuk format PDF
ImageDevice device = new ImageDevice();
```
## Langkah 4: Simpan XPS sebagai JPEG
```java
document.save(device, options);
```
## Langkah 5: Ulangi dan Simpan Halaman JPEG
```java
//Iterasi melalui partisi dokumen (dokumen tetap, dalam istilah XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterasi melalui halaman partisi
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inisialisasi aliran keluaran gambar
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Tulis gambar
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //tutup alirannya
        imageStream.close();
    }
}
```
Serangkaian langkah ini akan secara efektif mengonversi dokumen XPS Anda menjadi gambar JPEG, masing-masing disimpan secara terpisah.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengonversi XPS ke JPEG di Java menggunakan Aspose.Page. Proses ini sangat berharga bagi pengembang yang bekerja dengan konversi dokumen dalam aplikasi Java.
## Pertanyaan yang Sering Diajukan

### T: Apakah Aspose.Page cocok untuk proyek komersial?
 J: Ya, Aspose.Page adalah produk komersial dengan opsi lisensi yang tersedia. Memeriksa[Di Sini](https://purchase.aspose.com/buy) untuk detailnya.
### T: Dapatkah saya mencoba Aspose.Page sebelum membeli?
 A: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi Aspose.Page?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/page/java/).
### T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Page?
 J: Kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk dukungan berbasis komunitas.
### T: Apakah saya memerlukan lisensi sementara untuk pengujian?
 A: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
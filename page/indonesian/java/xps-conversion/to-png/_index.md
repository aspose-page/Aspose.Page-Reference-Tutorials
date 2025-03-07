---
title: Konversi XPS ke PNG di Java
linktitle: Konversi XPS ke PNG di Java
second_title: Aspose.Halaman Java API
description: Konversi XPS ke PNG dengan mudah di Java menggunakan Aspose.Page. Sederhanakan tugas dokumen dengan solusi yang andal dan ramah pengembang ini.
weight: 13
url: /id/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi XPS ke PNG di Java

## Perkenalan
Dalam dunia pengembangan perangkat lunak yang dinamis, kebutuhan untuk mengonversi dokumen XPS (Spesifikasi Kertas XML) menjadi gambar PNG (Portable Network Graphics) sering muncul. Untuk menyelesaikan tugas ini dengan lancar di Java, Aspose.Page menyediakan solusi yang ampuh. Dalam tutorial ini, kita akan memandu proses konversi XPS ke PNG menggunakan Aspose.Page untuk Java.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda telah menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Page untuk Java: Unduh dan instal perpustakaan Aspose.Page. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/page/java/).
3. Lingkungan Pengembangan Terintegrasi (IDE): Pilih IDE yang kompatibel dengan Java seperti IntelliJ IDEA atau Eclipse.
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Tambahkan pernyataan import berikut di awal file Java Anda:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Langkah 1: Atur Direktori Dokumen
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
## Langkah 2: Muat Dokumen XPS
```java
// Muat dokumen XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Langkah 3: Inisialisasi Opsi
```java
// Inisialisasi objek opsi dengan parameter yang diperlukan.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Langkah 4: Buat Perangkat Rendering
```java
// Buat perangkat rendering untuk format PDF
ImageDevice device = new ImageDevice();
```
## Langkah 5: Simpan dan Ulangi
```java
// Simpan dokumen XPS ke PNG menggunakan opsi dan perangkat
document.save(device, options);
//Iterasi melalui partisi dokumen (dokumen tetap, dalam istilah XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterasi melalui halaman partisi
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inisialisasi aliran keluaran gambar
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Tulis gambar
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Tutup Aliran
        imageStream.close();
    }
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengonversi dokumen XPS ke gambar PNG menggunakan Aspose.Page untuk Java.
## Kesimpulan
Kesimpulannya, Aspose.Page untuk Java menyederhanakan proses konversi XPS ke PNG, menyediakan alat yang andal dan efisien bagi pengembang. Gabungkan perpustakaan ini ke dalam proyek Java Anda untuk menyederhanakan tugas manipulasi dokumen.
## FAQ
### Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial?
 Ya, Aspose.Page adalah produk komersial. Anda dapat menemukan informasi perizinan[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 Dokumentasi komprehensif tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah ada forum komunitas untuk diskusi Aspose.Page?
 Ya, kunjungi forum komunitas[Di Sini](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

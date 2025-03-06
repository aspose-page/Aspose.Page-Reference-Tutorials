---
title: Konversi XPS ke PDF di Java
linktitle: Konversi XPS ke PDF di Java
second_title: Aspose.Halaman Java API
description: Pelajari cara mengonversi XPS ke PDF di Java dengan mudah dengan Aspose.Page. Ikuti panduan langkah demi langkah kami untuk konversi dokumen yang efisien.
weight: 11
url: /id/java/file-merging/xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi XPS ke PDF di Java

## Perkenalan
Dalam bidang pengembangan Java, mengonversi XPS ke PDF adalah tugas umum, dan memiliki alat yang andal untuk mencapai hal ini dengan lancar adalah hal yang terpenting. Aspose.Page untuk Java adalah perpustakaan teladan yang menawarkan fungsionalitas tangguh untuk menangani dokumen XPS. Tutorial ini akan memandu Anda melalui proses konversi XPS ke PDF menggunakan Aspose.Page, memastikan kesederhanaan dan efisiensi.
## Prasyarat
Sebelum mendalami proses konversi, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK terbaru di sistem Anda.
2.  Aspose.Page untuk Perpustakaan Java: Unduh dan sertakan perpustakaan Aspose.Page untuk Java dalam proyek Anda. Anda dapat menemukan perpustakaan dan dokumentasinya[Di Sini](https://reference.aspose.com/page/java/).
## Paket Impor
Setelah Anda menyiapkan proyek Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.Page. Berikut cuplikan untuk memandu Anda:
```java

import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Langkah 1: Tetapkan Jalur Direktori Dokumen
```java
String dataDir = "Your Document Directory";
```
Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke dokumen XPS Anda.
## Langkah 2: Inisialisasi Aliran Output PDF
```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```
Buat objek FileOutputStream untuk file PDF, tentukan jalur keluaran yang diinginkan.
## Langkah 3: Muat Dokumen XPS
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
Muat dokumen XPS menggunakan kelas XpsDocument.
## Langkah 4: Inisialisasi Opsi Penyimpanan PDF
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
Konfigurasikan opsi penyimpanan PDF berdasarkan kebutuhan Anda, seperti pengaturan kompresi gambar dan teks.
## Langkah 5: Buat Perangkat Rendering untuk Format PDF
```java
PdfDevice device = new PdfDevice(pdfStream);
```
Inisialisasi objek PdfDevice untuk merender dokumen XPS ke PDF.
## Langkah 6: Simpan Dokumen
```java
document.save(device, options);
```
Terakhir, simpan dokumen XPS ke PDF menggunakan metode simpan.
Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah mengonversi XPS ke PDF di Java menggunakan Aspose.Page, memberikan solusi yang andal dan efisien untuk kebutuhan konversi dokumen Anda.
## Kesimpulan
Kesimpulannya, Aspose.Page untuk Java menyederhanakan proses konversi XPS ke PDF, memungkinkan pengembang Java mengintegrasikan fungsi ini ke dalam aplikasi mereka dengan lancar. Panduan langkah demi langkah memastikan pengalaman yang lancar, sehingga dapat diakses oleh pemula dan pengembang berpengalaman.
## FAQ
### T: Apakah Aspose.Page kompatibel dengan versi Java yang berbeda?
J: Ya, Aspose.Page dirancang agar kompatibel dengan berbagai versi Java.
### T: Dapatkah saya menyesuaikan pengaturan kompresi untuk PDF yang dikonversi?
J: Tentu saja, Aspose.Page menyediakan opsi untuk menyesuaikan pengaturan kompresi gambar dan teks.
### T: Di mana saya bisa mendapatkan dukungan tambahan atau diskusi komunitas?
 J: Kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk diskusi dan dukungan komunitas.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page?
 J: Ya, Anda dapat mencoba uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?
 J: Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Aspose.Page Manipulasi Teks Java
linktitle: Tambahkan Teks di Java PostScript
second_title: Aspose.Halaman Java API
description: Jelajahi kekuatan Aspose.Page untuk Java dalam tutorial kami tentang menambahkan teks ke dokumen PostScript. Belajar menggunakan sistem dan font khusus dengan mudah.
weight: 10
url: /id/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Manipulasi Teks Java

## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang menambahkan teks di Java PostScript menggunakan Aspose.Page untuk Java. Aspose.Page untuk Java adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi dokumen PostScript dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan teks, menggunakan sistem dan font khusus, menguraikan teks, dan menggabungkan guratan untuk hasil yang menarik secara visual.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Aspose.Page untuk perpustakaan Java diinstal. Anda dapat mengunduhnya dari[Aspose.Page untuk halaman unduh Java](https://releases.aspose.com/page/java/).
-  Font yang diperlukan tersedia di folder yang ditentukan. Anda dapat menemukan informasi tambahan di[Aspose.Page untuk dokumentasi Java](https://reference.aspose.com/page/java/).
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk Aspose.Page untuk Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Langkah 1: Siapkan Dokumen
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Teks untuk ditulis ke file PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Buat Dokumen PS 1 halaman baru
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Langkah 2: Menggunakan Font Sistem untuk Mengisi Teks
```java
// Menggunakan font sistem untuk mengisi teks
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Isi teks dengan warna default atau yang sudah ditentukan (hitam)
document.fillText(str, font, 50, 100);
// Isi teks dengan warna biru
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Langkah 3: Menggunakan Font Kustom untuk Mengisi Teks
```java
// Menggunakan font khusus untuk mengisi teks
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Isi teks dengan warna default atau yang sudah ditentukan (hitam)
document.fillText(str, drFont, 50, 200);
// Isi teks dengan warna biru
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Langkah 4: Menguraikan Teks dengan Font Sistem
```java
// Menggunakan font sistem untuk menguraikan teks
document.outlineText(str, font, 50, 300);
// Buat kerangka teks dengan pena lebar 2 titik berwarna biru-ungu
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Isi teks dengan warna oranye dan coret dengan pena lebar 2 titik berwarna biru
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Langkah 5: Menguraikan Teks dengan Font Kustom
```java
// Menggunakan font khusus untuk menguraikan teks
document.outlineText(str, drFont, 50, 450);
// Buat kerangka teks dengan pena lebar 2 titik berwarna biru-ungu
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Isi teks dengan warna oranye dan coret dengan pena lebar 2 titik berwarna biru
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Langkah 6: Simpan Dokumen
```java
// Tutup halaman saat ini
document.closePage();
// Simpan dokumennya
document.save();
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan teks di Java PostScript menggunakan Aspose.Page untuk Java. Bereksperimenlah dengan berbagai font, warna, dan opsi kerangka untuk menyempurnakan dokumen Anda lebih lanjut.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan font khusus saya sendiri dengan Aspose.Page untuk Java?
 Ya, Anda dapat menggunakan font khusus dengan menentukan nama dan ukuran font di dalamnya`DrFont` kelas.
### Bagaimana cara mengubah warna teks?
 Anda dapat mengatur warna yang diinginkan menggunakan`Color` kelas saat mengisi atau menguraikan teks.
### Apakah mungkin menambahkan banyak halaman ke dokumen PostScript?
Sangat! Anda dapat membuat banyak halaman dengan mengulangi langkah pembuatan dan penyimpanan dokumen.
###  Apa tujuan dari`ExternalFontCache` class?
`ExternalFontCache` digunakan untuk mengambil font khusus, memastikan font tersebut tersedia untuk manipulasi teks.
### Bisakah saya menerapkan goresan berbeda pada teks yang digariskan?
 Ya, Anda dapat menyesuaikan lebar dan warna guratan menggunakan`Stroke` kelas dan`Color` kelas, masing-masing.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

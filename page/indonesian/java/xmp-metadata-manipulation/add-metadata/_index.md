---
title: Tambahkan Metadata di XMP menggunakan Java
linktitle: Tambahkan Metadata di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Jelajahi integrasi Aspose.Page untuk Java yang lancar dan pelajari cara menambahkan metadata XMP ke file EPS Anda dengan mudah. Tingkatkan permainan manajemen dokumen Anda hari ini!
type: docs
weight: 11
url: /id/java/xmp-metadata-manipulation/add-metadata/
---
## Perkenalan
Apakah Anda ingin meningkatkan metadata dokumen Anda dengan menambahkan informasi XMP menggunakan Java? Tidak perlu mencari lagi! Panduan langkah demi langkah ini akan memandu Anda melalui proses menambahkan metadata ke file EPS menggunakan pustaka Aspose.Page untuk Java. Aspose.Page adalah alat canggih yang menyederhanakan tugas manipulasi dokumen dalam aplikasi Java.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Aspose.Page untuk perpustakaan Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
- File EPS yang ingin Anda modifikasi.
## Paket Impor
Pertama, impor paket yang diperlukan ke program Java Anda:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Langkah 1: Dapatkan Metadata XMP
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, yang baru dibuat menggunakan nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.getXmpMetadata();
```
Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya tempat dokumen Anda disimpan.

## Langkah 2: Ambil Nilai CreatorTool
```java
// Dapatkan nilai "CreatorTool".
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Langkah 3: Ambil Nilai CreateDate
```java
// Dapatkan nilai "CreateDate".
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Langkah 4: Ambil Nilai Judul
```java
// Dapatkan nilai "Judul".
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Langkah 5: Ambil Nilai Format
```java
//Dapatkan nilai "format".
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Langkah 6: Ambil Nilai Pencipta
```java
// Dapatkan nilai "pencipta".
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Langkah 7: Ambil Nilai MetadataDate
```java
// Dapatkan nilai "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Langkah 8: Simpan Dokumen dengan Metadata XMP Baru
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Simpan dokumen dengan metadata XMP baru
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Terakhir, jangan lupa untuk menutup aliran input EPS:
```java
// Tutup aliran EPS masukan
psStream.close();
```
Sekarang, Anda telah berhasil menambahkan metadata ke file EPS Anda menggunakan Aspose.Page untuk Java!
## Kesimpulan
Dalam tutorial ini, kita menjelajahi proses menambahkan metadata XMP ke file EPS menggunakan pustaka Aspose.Page untuk Java. Alat canggih ini memungkinkan Anda memanipulasi dokumen dengan lancar, sehingga meningkatkan pengalaman pengelolaan dokumen Anda secara keseluruhan.
## FAQ
### T: Apakah Aspose.Page untuk Java gratis digunakan?
 J: Aspose.Page untuk Java adalah produk komersial. Anda dapat menjelajahi fitur-fiturnya melalui uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/page/java/).
### T: Bagaimana cara mendapatkan lisensi sementara Aspose.Page untuk Java?
 A: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Format file apa yang didukung Aspose.Page untuk Java?
J: Aspose.Page untuk Java mendukung berbagai format, termasuk EPS, PDF, dan XPS.
### T: Dapatkah saya membeli Aspose.Page untuk Java?
 J: Ya, Anda dapat membeli Aspose.Page untuk Java[Di Sini](https://purchase.aspose.com/buy).
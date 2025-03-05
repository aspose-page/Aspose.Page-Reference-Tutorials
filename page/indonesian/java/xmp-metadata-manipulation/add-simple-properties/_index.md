---
title: Tambahkan Properti Sederhana di XMP menggunakan Java
linktitle: Tambahkan Properti Sederhana di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Buka Aspose.Page untuk potensi Java dengan panduan kami tentang menambahkan properti ke metadata XMP dalam file EPS. Tingkatkan pemrosesan dokumen dengan mudah!
type: docs
weight: 14
url: /id/java/xmp-metadata-manipulation/add-simple-properties/
---
## Perkenalan
Dalam lanskap pemrosesan dokumen yang terus berkembang, pengelolaan metadata secara efisien sangatlah penting. Aspose.Page untuk Java memberdayakan pengembang untuk memanipulasi data Extensible Metadata Platform (XMP) dengan lancar. Dalam tutorial ini, kita akan menjelajahi proses menambahkan properti sederhana ke XMP menggunakan Java, memberi Anda panduan langkah demi langkah yang komprehensif.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Aspose.Page untuk perpustakaan Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
- Contoh file EPS yang berisi metadata. Jika Anda tidak memilikinya, silakan gunakan file "xmp3.eps" yang disediakan.
## Paket Impor
Pastikan Anda mengimpor paket yang diperlukan untuk memulai proyek Anda:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Langkah 1: Dapatkan Metadata XMP
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, kami mendapatkan file baru yang berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Langkah 2: Tambahkan Properti Tanggal
```java
// Tambahkan nilai properti tanggal "xmp:Date1".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Langkah 3: Tambahkan Properti Integer
```java
// Tambahkan nilai properti integer "xmp:Intg1".
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Langkah 4: Tambahkan Properti Ganda
```java
// Tambahkan nilai properti ganda "xmp:Double1".
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Langkah 5: Tambahkan Properti String
```java
// Tambahkan nilai properti string "xmp:String1".
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Langkah 6: Simpan Dokumen
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Simpan dokumen dengan metadata XMP yang diubah
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Langkah 7: Tutup Aliran
```java
// Tutup aliran EPS masukan
psStream.close();
```
## Kesimpulan
Aspose.Page for Java menyederhanakan proses manipulasi metadata XMP dalam file EPS. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menambahkan properti sederhana untuk menyempurnakan metadata dokumen Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi ada versi yang tersedia untuk bahasa lain seperti .NET.
### Apakah uji coba gratis tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat menjelajahi fitur Aspose.Page dengan mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Page untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Lisensi sementara dapat diperoleh[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli Aspose.Page untuk Java?
 Anda dapat membeli produknya[Di Sini](https://purchase.aspose.com/buy).
---
title: Tambahkan Item Array di Metadata XMP menggunakan Java
linktitle: Tambahkan Item Array di Metadata XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Sempurnakan file EPS dengan Aspose.Page untuk Java. Pelajari cara menambahkan item array ke metadata XMP dengan mudah. Ikuti panduan langkah demi langkah kami sekarang!
type: docs
weight: 10
url: /id/java/xmp-metadata-manipulation/add-array-items/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang penggunaan Aspose.Page untuk Java guna menambahkan item array dalam metadata XMP. Aspose.Page adalah perpustakaan Java yang kuat yang memungkinkan Anda memanipulasi dan bekerja dengan berbagai format dokumen, termasuk file EPS. Dalam tutorial ini, kita akan fokus pada tugas khusus menambahkan item array dalam metadata XMP menggunakan Java.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Aspose.Page untuk perpustakaan Java diinstal.
- Pemahaman dasar pemrograman Java.
- File EPS yang valid dengan metadata XMP atau komentar metadata PS yang ada.
## Paket Impor
Untuk memulai, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan Aspose.Page. Sertakan baris berikut di awal file Java Anda:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
Pada langkah ini, kami mengambil metadata XMP yang ada dari file EPS. Jika file EPS belum berisi metadata XMP, Aspose.Page akan membuat yang baru dan mengisinya dengan nilai dari komentar metadata PS.
## Langkah 2: Tambahkan Item Array "dc:title".
```java
// Tambahkan satu lagi item array "dc:title".
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Sekarang, kita menambahkan item array baru ke properti "dc:title" di metadata XMP. Ganti "Judul Baru" dengan judul yang diinginkan.
## Langkah 3: Tambahkan Item Array "dc:creator".
```java
// Tambahkan satu lagi item array "dc:creator".
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Demikian pula, kami menambahkan item array baru ke properti "dc:creator" di metadata XMP. Ganti "NewCreator" dengan informasi pembuat yang diinginkan.
## Langkah 4: Inisialisasi Aliran File EPS Keluaran
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Siapkan aliran file EPS keluaran tempat dokumen yang dimodifikasi dengan metadata XMP yang diperbarui akan disimpan.
## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diubah
```java
//Simpan dokumen dengan metadata XMP yang diubah
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Simpan dokumen dengan metadata XMP yang diperbarui ke file EPS keluaran.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan item array dalam metadata XMP menggunakan Aspose.Page untuk Java. Pustaka yang kuat ini menyederhanakan proses manipulasi file EPS dan menyediakan fungsionalitas ekstensif untuk pemrosesan dokumen.
## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.Page untuk Java dengan format dokumen lain?
Ya, Aspose.Page mendukung berbagai format dokumen, termasuk EPS, PDF, dan XPS.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Bagaimana saya bisa membeli Aspose.Page untuk Java?
 Anda dapat membeli produknya[Di Sini](https://purchase.aspose.com/buy).
### Apakah lisensi sementara tersedia untuk Aspose.Page untuk Java?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
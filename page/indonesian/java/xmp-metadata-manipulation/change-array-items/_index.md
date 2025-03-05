---
title: Ubah Item Array di XMP menggunakan Java
linktitle: Ubah Item Array di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Pelajari cara mengubah item array di XMP menggunakan Aspose.Page untuk Java. Ubah metadata dengan mudah menggunakan panduan langkah demi langkah kami. Sempurnakan dokumen EPS Anda sekarang!
type: docs
weight: 15
url: /id/java/xmp-metadata-manipulation/change-array-items/
---
## Perkenalan
Selamat datang di panduan komprehensif kami tentang mengubah item array di XMP menggunakan Aspose.Page untuk Java! Aspose.Page adalah pustaka Java canggih yang memungkinkan Anda bekerja dengan metadata XMP dalam file EPS dengan lancar. Dalam tutorial ini, kami akan memandu Anda melalui proses memodifikasi item array dalam metadata XMP, membantu Anda menyempurnakan dan menyesuaikan dokumen EPS Anda.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Pustaka Aspose.Page untuk Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Untuk memulai, mari impor paket yang diperlukan ke proyek Java Anda. Pastikan Anda memiliki perpustakaan Aspose.Page yang disertakan dalam proyek Anda.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Langkah 1: Dapatkan Metadata XMP
Pertama, ambil metadata XMP dari file EPS Anda. Jika file EPS belum berisi metadata XMP, yang baru akan dibuat dengan nilai dari komentar metadata PS seperti %%Creator, %%CreateDate, %%Title, dll.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, file baru akan diisi dengan nilai dari komentar metadata PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Langkah 2: Setel Item Array "dc:title".
Sekarang, mari kita atur item array "dc:title" pada indeks 0 dengan nilai baru.
```java
// Setel item array "dc:title" berdasarkan indeks 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Langkah 3: Setel Item Array "dc:creator".
Demikian pula, atur item array "dc:creator" pada indeks 0 dengan nilai pencipta baru.
```java
// Setel item array "dc:creator" berdasarkan indeks 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Langkah 4: Inisialisasi Aliran File EPS Keluaran
Siapkan aliran file EPS keluaran tempat dokumen yang dimodifikasi akan disimpan.
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diubah
Simpan dokumen dengan metadata XMP yang diperbarui.
```java
//Simpan dokumen dengan metadata XMP yang diubah
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengubah item array di XMP menggunakan Aspose.Page untuk Java. Tutorial ini memberikan panduan langkah demi langkah, memastikan Anda dapat dengan mudah menyempurnakan dokumen EPS Anda dengan metadata yang disesuaikan.

## FAQ
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama dirancang untuk Java, tetapi Aspose menyediakan perpustakaan serupa untuk bahasa lain.
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Page untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli Aspose.Page versi lengkap untuk Java?
 Anda dapat membeli versi lengkapnya[Di Sini](https://purchase.aspose.com/buy).
---
title: Dapatkan Metadata dari XMP menggunakan Java
linktitle: Dapatkan Metadata dari XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Buka kekuatan Aspose.Page untuk Java untuk mengekstrak metadata XMP dengan mudah. Tingkatkan analisis dokumen dengan panduan langkah demi langkah kami!
type: docs
weight: 18
url: /id/java/xmp-metadata-manipulation/get-metadata/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami dalam memanfaatkan Aspose.Page untuk Java untuk mengekstrak metadata dari file XMP. XMP (Extensible Metadata Platform) menyediakan cara standar untuk menyimpan metadata dalam file. Tutorial ini berfokus pada mengambil informasi penting dari XMP menggunakan Java, menawarkan wawasan tentang detail dokumen.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK): Pastikan Anda telah menginstal Java di mesin Anda.
-  Aspose.Page untuk Java: Unduh dan instal perpustakaan Aspose.Page, yang dapat Anda temukan[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Langkah 1: Inisialisasi Aliran File EPS Masukan
Mulailah dengan mengatur jalur ke direktori dokumen Anda dan menginisialisasi aliran file input EPS.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Langkah 2: Dapatkan Metadata XMP
Ambil metadata XMP dari file EPS. Jika file tidak memiliki metadata XMP, yang baru akan dibuat dengan nilai dari komentar metadata PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Langkah 3: Ekstrak Informasi CreatorTool
Periksa dan cetak nilai "CreatorTool" dari metadata XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Langkah 4: Ekstrak Informasi CreateDate
Periksa dan cetak nilai "CreateDate" dari metadata XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Langkah 5: Ambil Lebar Thumbnail
Jika ada thumbnail, ekstrak dan cetak lebar thumbnail pertama.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Langkah 6: Ekstrak Informasi Format
Periksa dan cetak nilai "format" dari metadata XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Langkah 7: Dapatkan DocumentID
Periksa dan cetak nilai "DocumentID" dari metadata XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengekstrak metadata XMP menggunakan Aspose.Page untuk Java. Panduan ini memberikan ikhtisar proses yang komprehensif, memastikan Anda dapat mengambil informasi penting dari dokumen Anda secara efektif.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
 Ya, Aspose.Page mendukung berbagai bahasa, termasuk Java, .NET, dan lainnya. Periksalah[dokumentasi](https://reference.aspose.com/page/java/) untuk detailnya.
### Apakah uji coba gratis tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Page untuk Java?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.
### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah ada sumber daya tambahan untuk Aspose.Page untuk Java?
 Jelajahi secara lengkap[dokumentasi](https://reference.aspose.com/page/java/) dan unduh perpustakaannya[Di Sini](https://releases.aspose.com/page/java/).
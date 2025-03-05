---
title: Ubah Nilai di XMP menggunakan Java
linktitle: Ubah Nilai di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Sempurnakan dokumen EPS dengan Aspose.Page untuk Java. Ubah metadata XMP dengan mudah untuk konten yang disesuaikan dan profesional. #Pengembangan Java
type: docs
weight: 17
url: /id/java/xmp-metadata-manipulation/change-values/
---
## Perkenalan
Dalam bidang pemrosesan dan manipulasi dokumen, Aspose.Page untuk Java menonjol sebagai alat yang ampuh. Tutorial ini mempelajari proses mengubah nilai XMP (Extensible Metadata Platform) dalam dokumen EPS (Encapsulated PostScript) menggunakan Java dengan perpustakaan Aspose.Page. Dengan mengikuti panduan langkah demi langkah yang diberikan, Anda akan mempelajari cara mengubah metadata dengan mudah, memastikan dokumen Anda disesuaikan dengan kebutuhan spesifik Anda.
## Prasyarat
Sebelum kita memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda memiliki lingkungan pengembangan Java yang berfungsi di mesin Anda.
2.  Aspose.Page untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.Page untuk Java. Anda dapat menemukan paket yang diperlukan[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda. Paket-paket ini sangat penting untuk berinteraksi dan memanipulasi dokumen EPS.
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
Ambil metadata XMP dari dokumen EPS. Jika file EPS tidak berisi metadata XMP, yang baru akan dibuat dengan nilai dari komentar metadata PS seperti %%Creator, %%CreateDate, dan %%Title.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, file baru akan dibuat dengan nilai dari komentar metadata PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Langkah 2: Ubah Nilai "ModifyDate".
Ubah nilai "ModifyDate" di metadata XMP untuk mencerminkan tanggal yang diinginkan.
```java
// Ubah nilai "ModifyDate".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Langkah 3: Ubah Nilai "Pencipta".
Perbarui nilai "Pembuat" di metadata XMP untuk menentukan pembuat dokumen.
```java
// Ubah nilai "pencipta".
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Langkah 4: Ubah Nilai "Judul".
Ubah nilai "Judul" di metadata XMP untuk menetapkan judul yang sesuai untuk dokumen.
```java
//Ubah nilai "judul".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diubah
Simpan dokumen dengan metadata XMP yang diperbarui ke file EPS baru.
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Simpan dokumen dengan metadata XMP yang diubah
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Kesimpulan
Selamat! Anda telah berhasil menavigasi proses mengubah nilai XMP dalam dokumen EPS menggunakan Aspose.Page untuk Java. Tutorial ini telah membekali Anda dengan pengetahuan untuk mengubah metadata, memastikan dokumen Anda selaras dengan kebutuhan spesifik Anda.
## FAQ
### T: Bagaimana cara menangani pertimbangan zona waktu saat mengubah nilai XMP?
 Memanfaatkan`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` untuk memastikan konsistensi dalam pengaturan zona waktu.
### T: Bisakah saya mengubah beberapa nilai XMP dalam satu operasi?
 Ya, dengan menggunakan`put` metode untuk setiap nilai yang diinginkan, Anda dapat mengubah beberapa nilai XMP secara bersamaan.
### T: Di mana saya dapat menemukan dokumentasi tambahan untuk Aspose.Page untuk Java?
 Jelajahi dokumentasi komprehensif[Di Sini](https://reference.aspose.com/page/java/).
### T: Apakah tersedia uji coba gratis untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan lisensi sementara Aspose.Page untuk Java?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
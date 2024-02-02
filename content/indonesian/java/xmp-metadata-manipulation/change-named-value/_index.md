---
title: Ubah Nilai Bernama di XMP menggunakan Java
linktitle: Ubah Nilai Bernama di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Temukan Aspose.Page untuk Java - Ubah metadata XMP dalam file EPS dengan mudah menggunakan panduan langkah demi langkah kami untuk pemrosesan dokumen yang efisien.
type: docs
weight: 16
url: /id/java/xmp-metadata-manipulation/change-named-value/
---
Dalam bidang manipulasi dokumen, Aspose.Page untuk Java menonjol sebagai alat yang ampuh, memungkinkan pengembang bekerja dengan lancar dengan metadata XMP dalam file EPS. Panduan langkah demi langkah ini akan memandu Anda melalui proses mengubah nilai bernama di XMP menggunakan Aspose.Page untuk Java. Sebelum kita mempelajari detailnya, mari kita mulai dengan pendahuluan.
## Perkenalan
Aspose.Page for Java adalah pustaka Java tangguh yang memfasilitasi manipulasi dan pemrosesan file EPS. Ketika menangani metadata XMP dalam file-file ini, Aspose.Page memberdayakan pengembang dengan serangkaian fitur yang komprehensif. Dalam tutorial ini, kami akan fokus pada perubahan nilai bernama di XMP, menawarkan panduan yang jelas dan ringkas bagi pengembang yang ingin meningkatkan kemampuan pemrosesan dokumen mereka.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di mesin Anda.
2.  Aspose.Page untuk Perpustakaan Java: Unduh dan integrasikan perpustakaan Aspose.Page untuk Java ke dalam proyek Anda. Anda dapat menemukan perpustakaan dan dokumentasi terperinci[Di Sini](https://reference.aspose.com/page/java/).
3. Contoh File EPS: Siapkan contoh file EPS untuk eksperimen. Jika Anda tidak memilikinya, Anda dapat menggunakan contoh file yang disediakan bernama "xmp4.eps."
## Paket Impor
Untuk memulai prosesnya, impor paket yang diperlukan dalam kode Java Anda. Paket-paket ini penting untuk berinteraksi dengan Aspose.Page untuk Java. Sertakan baris berikut di awal file Java Anda:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
Sekarang, mari kita uraikan proses mengubah nilai bernama di XMP menggunakan Aspose.Page untuk Java menjadi beberapa langkah:
## Langkah 1: Inisialisasi Aliran File EPS Masukan
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
        
// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## Langkah 2: Inisialisasi PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## Langkah 3: Dapatkan Metadata XMP
```java
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, kami mendapatkan file baru yang berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Langkah 4: Tetapkan Nilai Baru di XMP
```java
// Tetapkan nilai string baru "Inci" untuk nilai bernama "stDim:unit" dari struktur "xmpTPg:MaxPageSize"
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## Langkah 5: Inisialisasi Aliran File EPS Keluaran
```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## Langkah 6: Simpan Dokumen dengan Metadata XMP yang Diubah
```java
//Simpan dokumen dengan metadata XMP yang diubah
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Langkah 7: Tutup Aliran EPS Masukan
```java
// Tutup aliran EPS masukan
psStream.close();
```
Panduan langkah demi langkah ini memastikan pendekatan sistematis untuk mengubah nilai bernama di XMP menggunakan Aspose.Page untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengintegrasikan fungsi ini dengan lancar ke dalam aplikasi Java Anda.
## Kesimpulan
Kesimpulannya, Aspose.Page for Java menyederhanakan proses bekerja dengan metadata XMP dalam file EPS. Tutorial ini telah membekali Anda dengan pengetahuan untuk mengubah nilai bernama di XMP secara efisien, sehingga meningkatkan kemampuan pemrosesan dokumen Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi Aspose menyediakan perpustakaan serupa untuk berbagai bahasa pemrograman.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat menjelajahi uji coba gratis Aspose.Page untuk Java[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan dan diskusi tambahan tentang Aspose.Page untuk Java?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli Aspose.Page untuk Java?
 Untuk membeli Aspose.Page untuk Java, kunjungi[halaman pembelian](https://purchase.aspose.com/buy).
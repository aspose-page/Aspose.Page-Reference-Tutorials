---
date: 2025-12-20
description: Pelajari cara membuat metadata XMP EPS dalam file EPS menggunakan Aspose.Page
  untuk Java. Panduan langkah demi langkah untuk menambahkan properti XMP sederhana
  secara programatis.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Cara membuat metadata XMP EPS dengan Java
url: /id/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Properti Sederhana di XMP menggunakan Java

## Pendahuluan
Dalam alur kerja dokumen modern, kemampuan untuk **membuat file EPS metadata XMP** secara programatik memberi Anda kontrol penuh atas cara grafik Anda dideskripsikan, dicari, dan diarsipkan. Dengan Aspose.Page untuk Java Anda dapat membaca, memodifikasi, dan menulis paket XMP di dalam dokumen EPS tanpa meninggalkan ekosistem Java. Pada tutorial ini kami akan memandu Anda langkah demi langkah menambahkan properti XMP sederhana ke file EPS, sehingga Anda dapat memperkaya grafik dengan metadata khusus secara cepat dan andal.

## Jawaban Cepat
- **Apa arti “create xmp metadata eps”?** Menambahkan paket XMP (metadata berbasis XML) ke file EPS.  
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page untuk Java (dapat diunduh dari situs Aspose).  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa banyak baris kode?** Kurang dari 30 baris Java ditambah beberapa pernyataan import.  
- **Bisakah saya menambahkan tipe data lain?** Ya – tanggal, integer, double, string, dan bahkan array didukung.

## Apa itu create xmp metadata eps?
 XMP (Extensible Metadata Platform) adalah standar untuk menyematkan metadata kaya di dalam file. Ketika Anda **create XMP metadata EPS**, Anda menyisipkan paket XML di dalam dokumen EPS (Encapsulated PostScript), memungkinkan aplikasi downstream membaca penulis, tanggal pembuatan, tag khusus, dan lainnya.

## Mengapa menambahkan metadata XMP ke file EPS?
- **Kemudahan pencarian:** Memungkinkan pengindeksan otomatis oleh sistem DAM.  
- **Kepatuhan:** Menyimpan informasi hukum atau lisensi langsung di dalam file.  
- **Otomatisasi:** Membiarkan pipeline downstream membuat keputusan berdasarkan data yang disematkan.  
- **Portabilitas:** Metadata ikut bersama EPS, memastikan konsistensi lintas platform.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- File EPS contoh yang berisi metadata. Jika Anda belum memilikinya, silakan gunakan file **`xmp3.eps`** yang disediakan.

## Import Packages
Pertama, impor kelas‑kelas yang diperlukan. Import tetap persis seperti contoh asli:

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

## Langkah 1: Muat dokumen EPS dan dapatkan metadata XMP
Kami membuka file EPS, membuat instance `PsDocument`, dan mengambil (atau membuat) paket XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 2: Tambahkan properti Tanggal
Menambahkan tanggal semudah membuat objek `Date` dan memasukkannya ke dalam peta XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Langkah 3: Tambahkan properti Integer
Anda dapat menyimpan pengidentifikasi numerik atau nomor versi menggunakan nilai integer.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Langkah 4: Tambahkan properti Double
Angka floating‑point berguna untuk pengukuran atau penilaian.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Langkah 5: Tambahkan properti String
Tag teks khusus (misalnya, kode proyek) disimpan sebagai string.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Langkah 6: Simpan file EPS yang telah diperbarui
Setelah semua properti ditambahkan, tulis kembali dokumen ke disk.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Langkah 7: Bersihkan sumber daya
Selalu tutup aliran input untuk menghindari kebocoran handle file.

```java
// Close input EPS stream
psStream.close();
```

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| **Null XMP metadata** | File EPS tidak memiliki paket XMP dan perpustakaan tidak dapat menafsirkan komentar PS. | Pastikan EPS sumber berisi setidaknya satu komentar PS (misalnya, `%%Creator`). Perpustakaan akan secara otomatis menghasilkan paket XMP minimal. |
| **Ketidaksesuaian zona waktu** | Tanggal terlihat bergeser ketika dibuka di aplikasi lain. | Atur `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` sebelum membuat objek `Date`, seperti pada Langkah 2. |
| **Pengecualian lisensi** | Runtime melempar `LicenseException`. | Terapkan lisensi Aspose.Page yang valid sebelum menggunakan API, atau jalankan dalam mode percobaan untuk evaluasi. |

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **create XMP metadata EPS** menggunakan Aspose.Page untuk Java. Menambahkan properti sederhana seperti tanggal, integer, double, dan string sangat mudah, dan file EPS yang dihasilkan membawa metadata kaya yang dapat dicari, memberi manfaat bagi alur kerja downstream apa pun.

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi ada versi yang tersedia untuk bahasa lain seperti .NET.

### Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat menjelajahi fitur Aspose.Page dengan mendapatkan percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Page untuk Java?
Dokumentasi tersedia **[di sini](https://reference.aspose.com/page/java/)**.

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page untuk Java?
Lisensi sementara dapat diperoleh **[di sini](https://purchase.aspose.com/temporary-license/)**.

### Di mana saya dapat membeli Aspose.Page untuk Java?
Anda dapat membeli produk **[di sini](https://purchase.aspose.com/buy)**.

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Page untuk Java 24.11 (versi terbaru saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
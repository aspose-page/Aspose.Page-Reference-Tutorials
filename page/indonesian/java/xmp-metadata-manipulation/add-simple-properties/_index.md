---
date: 2026-05-20
description: Pelajari cara menambahkan metadata XMP ke file EPS dengan Aspose.Page
  untuk Java. Panduan langkah demi langkah untuk menyematkan properti XMP sederhana
  secara programatik.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Tambahkan Properti Sederhana dalam XMP menggunakan Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Tambahkan Metadata XMP ke File EPS Menggunakan Java
url: /id/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Metadata XMP ke File EPS Menggunakan Java

## Pendahuluan
Pada pipeline grafis modern, kemampuan untuk **menambahkan metadata XMP** ke file EPS secara programatik memberi Anda kontrol penuh atas cara ilustrasi Anda dideskripsikan, dicari, dan diarsipkan. Dengan Aspose.Page untuk Java Anda dapat membaca, memodifikasi, dan menulis paket XMP di dalam dokumen EPS tanpa meninggalkan ekosistem Java. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah tepat untuk menambahkan properti XMP sederhana ke file EPS, sehingga Anda dapat memperkaya grafik dengan metadata khusus secara cepat dan andal.

## Jawaban Cepat
- **Apa arti “menambahkan metadata XMP ke EPS”?** Menyematkan paket XMP (metadata berbasis XML) di dalam file EPS.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk Java (dapat diunduh dari situs Aspose).  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa banyak baris kode?** Kurang dari 30 baris Java ditambah beberapa pernyataan import.  
- **Bisakah saya menambahkan tipe data lain?** Ya – tanggal, integer, double, string, dan bahkan array didukung.

## Cara menambahkan metadata XMP ke file EPS menggunakan Java?
Muat file EPS dengan `new PsDocument("input.eps")`, ambil atau buat paket XMP‑nya, sisipkan properti yang diinginkan, lalu simpan dokumen kembali ke disk – semuanya dalam kurang dari sepuluh baris kode Java. Pendekatan ini memungkinkan Anda menyematkan metadata yang dapat dicari dan sesuai standar tanpa harus mengedit sumber EPS secara manual.

## Apa itu metadata XMP dalam EPS?
Metadata XMP dalam EPS adalah paket XML yang berada di dalam file EPS dan menyimpan informasi seperti penulis, tanggal pembuatan, dan tag khusus. Menyematkan paket ini memungkinkan alat‑alat hilir membaca dan memanfaatkan data tanpa memerlukan file sampingan terpisah.

## Mengapa menambahkan metadata XMP ke file EPS?
Menyematkan metadata XMP membuat aset EPS dapat dicari secara langsung, memastikan kepatuhan dengan menyimpan informasi lisensi di dalam file, memungkinkan pipeline otomatis membuat keputusan berdasarkan tag yang disematkan, dan menjamin metadata ikut bersama grafik di semua platform. Aspose.Page dapat memproses file hingga 500 MB tanpa memuat seluruh dokumen ke memori, memberikan kinerja cepat untuk beban kerja berskala besar.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- File EPS contoh yang berisi metadata. Jika Anda belum memilikinya, silakan gunakan file **`xmp3.eps`** yang disediakan.

## Impor Paket
Pertama, impor kelas‑kelas yang Anda perlukan. Pernyataan import tetap persis sama seperti pada contoh asli:

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
Kelas `PsDocument` mewakili file EPS dan menyediakan metode untuk mengakses konten serta metadata-nya.  
Objek `XmpMetadata` menyimpan paket XMP yang terkait dengan dokumen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 2: Tambahkan properti Date
Kelas `Date` mewakili suatu momen spesifik dalam waktu, dengan presisi milidetik.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Langkah 3: Tambahkan properti Integer
Kelas `Integer` membungkus nilai primitif `int` sebagai sebuah objek.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Langkah 4: Tambahkan properti Double
Kelas `Double` membungkus nilai primitif `double` sebagai sebuah objek.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Langkah 5: Tambahkan properti String
Kelas `String` mewakili urutan karakter.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Langkah 6: Simpan file EPS yang diperbarui
Metode `save` menulis dokumen yang telah dimodifikasi kembali ke disk, mempertahankan struktur EPS.

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
Selalu tutup stream untuk menghindari kebocoran handle file dan memastikan semua buffer ter-flush.

```java
// Close input EPS stream
psStream.close();
```

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Null XMP metadata** | File EPS tidak memiliki paket XMP dan perpustakaan tidak dapat menyimpulkan komentar PS. | Pastikan EPS sumber berisi setidaknya satu komentar PS (mis., `%%Creator`). Perpustakaan akan secara otomatis menghasilkan paket XMP minimal. |
| **Time zone mismatch** | Tanggal terlihat bergeser ketika dibuka di aplikasi lain. | Atur `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` sebelum membuat objek `Date`, seperti yang ditunjukkan pada Langkah 2. |
| **License exception** | Runtime melempar `LicenseException`. | Terapkan lisensi Aspose.Page yang valid sebelum menggunakan API, atau jalankan dalam mode percobaan untuk evaluasi. |

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?**  
A: Aspose.Page terutama mendukung Java, tetapi perpustakaan setara tersedia untuk .NET, C++, dan Python.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?**  
A: Ya, Anda dapat menjelajahi fitur Aspose.Page dengan memperoleh percobaan gratis **[di sini](https://releases.aspose.com/)**.

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Page untuk Java?**  
A: Dokumentasi tersedia **[di sini](https://reference.aspose.com/page/java/)**.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
A: Lisensi sementara dapat diperoleh **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q: Di mana saya dapat membeli Aspose.Page untuk Java?**  
A: Anda dapat membeli produk tersebut **[di sini](https://purchase.aspose.com/buy)**.

---

**Terakhir Diperbarui:** 2026-05-20  
**Diuji Dengan:** Aspose.Page untuk Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membaca Metadata XMP menggunakan Java – Panduan Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [tutorial xmp aspose.page – Tambahkan Namespace dalam XMP menggunakan Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Tambahkan Item Array dalam Metadata XMP menggunakan Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
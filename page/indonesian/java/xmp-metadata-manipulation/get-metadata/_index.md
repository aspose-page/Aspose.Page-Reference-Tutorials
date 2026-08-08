---
date: 2026-05-25
description: Pelajari cara membaca XMP menggunakan Aspose.Page dengan Java. Panduan
  langkah demi langkah ini menunjukkan cara mengekstrak metadata XMP, informasi pembuat,
  cap waktu, thumbnail, dan lainnya.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Cara Membaca Metadata XMP menggunakan Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Baca XMP menggunakan Aspose.Page – Panduan Java
url: /id/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Metadata dari XMP menggunakan Java

## Cara membaca XMP menggunakan Aspose.Page (Java)?

Muat file EPS dengan `new Document("file.eps")`—kelas `Document` mewakili file yang telah dimuat. Panggil `getXmpMetadata()`, yang mengekstrak paket XMP, kemudian query objek `XmpMetadata` yang dikembalikan—sebuah antarmuka mirip peta untuk properti XMP—untuk mengambil kunci yang Anda butuhkan. Semua ini diperlukan untuk membaca XMP menggunakan Aspose.Page. API mengabstraksi parsing tingkat rendah, sehingga Anda mendapatkan peta properti siap pakai dalam hanya dua baris kode.

Selamat datang di tutorial langkah‑demi‑langkah kami yang menunjukkan **cara membaca XMP** metadata dengan Java dan pustaka Aspose.Page. XMP (Extensible Metadata Platform) adalah standar yang banyak diadopsi untuk menyematkan metadata kaya di dalam dokumen. Pada akhir panduan ini Anda akan dapat membaca XMP format dokumen, mengambil informasi pembuat, cap waktu, thumbnail, dan lainnya—memberdayakan Anda untuk membangun solusi analisis dokumen yang lebih cerdas.

## Jawaban Cepat
- **Apa arti “membaca XMP”?** Itu berarti mengekstrak paket XMP secara programatik yang menyimpan metadata di dalam file.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk Java (unduh dari halaman resmi [di sini](https://releases.aspose.com/page/java/)).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya membaca XMP dari format lain?** Ya – Aspose.Page mengekstrak XMP dari EPS, PDF, JPEG, PNG, dan lebih dari 20 format lainnya.

## Prasyarat
Sebelum menyelami kode, pastikan Anda memiliki:

- **Java Development Kit (JDK)** – Java 8+ terpasang dan dikonfigurasi di mesin Anda.  
- **Aspose.Page untuk Java** – Unduh pustaka dari situs resmi [di sini](https://releases.aspose.com/page/java/).  
- File EPS yang berisi metadata XMP (misalnya `xmp1.eps`).  

## Impor Paket
Kelas `XmpMetadata` berada di namespace `com.aspose.page.xmp`, sedangkan kelas `Document` berada di `com.aspose.page`. Impor keduanya agar Anda dapat bekerja dengan file EPS dan metadata-nya.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Langkah 1: Inisialisasi Stream File EPS Masukan
Mulailah dengan mengatur path ke direktori dokumen Anda dan menginisialisasi stream file EPS masukan.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Langkah 2: Dapatkan Metadata XMP
`XmpMetadata` adalah objek Aspose.Page yang menyimpan paket XMP yang diekstrak dari sebuah dokumen. Dapatkan dengan `document.getXmpMetadata()`. Jika file tidak memiliki XMP, API akan mensintesis paket minimal dari komentar PostScript yang ada.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 3: Ekstrak Informasi CreatorTool
Kunci `CreatorTool` berada di bawah namespace `xmp` dan mencatat aplikasi yang menghasilkan file. Periksa keberadaannya dan cetak nilainya.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Langkah 4: Ekstrak Informasi CreateDate
`CreateDate` menyimpan cap waktu ketika dokumen pertama kali dibuat. Gunakan pola `containsKey`/`get` yang sama untuk membacanya.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Langkah 5: Dapatkan Lebar Thumbnail
Jika thumbnail ada, array `xmp:Thumbnails` berisi satu atau lebih entri. Setiap entri memiliki `width`, `height`, dan data biner. Contoh ini mengekstrak lebar thumbnail pertama.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Langkah 6: Ekstrak Informasi Format
Kunci `format` memberi tahu Anda format file asli (misalnya “application/postscript”). Ini berguna ketika Anda perlu mencatat atau memvalidasi tipe sumber.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Langkah 7: Dapatkan DocumentID
`DocumentID` adalah pengidentifikasi unik yang diberikan oleh aplikasi pembuat. Ini dapat digunakan untuk deduplikasi dalam perpustakaan aset besar.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Mengapa Ini Penting
Aspose.Page dapat membaca XMP dari **lebih dari 20** format file dan memproses dokumen hingga **500 MB** tanpa memuat seluruh file ke memori, memberi Anda akses cepat dengan overhead rendah ke metadata penting. Kemampuan ini penting untuk pipeline pemrosesan batch, sistem manajemen aset digital, dan solusi apa pun yang bergantung pada atribut dokumen yang dapat dicari dan dibaca mesin.

## Kesalahan Umum & Tips
- **XMP Hilang:** Beberapa file EPS mungkin tidak berisi XMP. Pemanggilan `getXmpMetadata()` akan mensintesis set minimal berdasarkan komentar PS yang ada, tetapi Anda tidak akan mendapatkan metadata lengkap kecuali tersemat.  
- **Array Thumbnail:** Kunci `xmp:Thumbnails` dapat berisi beberapa entri. Contoh ini mengekstrak hanya yang pertama; iterasi array jika Anda membutuhkan semua thumbnail.  
- **Kesadaran Namespace:** Kunci XMP menggunakan namespace (misalnya `xmp:`, `dc:`). Pastikan Anda merujuk nama kunci yang tepat; jika tidak `containsKey` akan mengembalikan false.  

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Ya, Aspose.Page mendukung Java, .NET, dan beberapa bahasa lain. Lihat daftar lengkapnya di [dokumentasi](https://reference.aspose.com/page/java/).

### Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Page untuk Java?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk bantuan komunitas dan dukungan resmi.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Apakah ada sumber daya tambahan untuk Aspose.Page untuk Java?
Jelajahi [dokumentasi](https://reference.aspose.com/page/java/) lengkap dan unduh pustaka [di sini](https://releases.aspose.com/page/java/).

## FAQ Tambahan
**Q: Apakah pendekatan ini bekerja dengan file PDF yang berisi XMP?**  
A: Ya, Aspose.Page dapat membaca XMP dari PDF, EPS, dan beberapa format gambar.

**Q: Bisakah saya memodifikasi metadata XMP setelah membacanya?**  
A: Tentu saja. Objek `XmpMetadata` dapat diubah; Anda dapat menambah, memperbarui, atau menghapus kunci dan kemudian menyimpan dokumen.

**Q: Apakah ada cara untuk mengekstrak semua gambar thumbnail, bukan hanya dimensinya?**  
A: Anda dapat mengambil data biner dari properti `xmpGImg:data` setiap entri thumbnail dan menuliskannya ke file.

## Kesimpulan
Anda kini telah menguasai **cara membaca XMP** metadata menggunakan Java dan Aspose.Page. Dengan mengikuti langkah‑langkah ini Anda dapat mengekstrak alat pembuat, cap waktu, thumbnail, informasi format, dan ID dokumen—memberikan wawasan penuh tentang metadata yang tertanam dalam file EPS Anda. Jangan ragu untuk bereksperimen dengan namespace XMP tambahan untuk memperoleh data yang lebih kaya bagi aplikasi Anda.

---

**Terakhir Diperbarui:** 2026-05-25  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest)  
**Penulis:** Aspose

## Tutorial Terkait

- [Tutorial Aspose Page Java – Tambahkan Metadata XMP ke File EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [tutorial aspose.page xmp – Tambahkan Namespace dalam XMP menggunakan Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [tutorial aspose page xmp – Ubah Nilai Bernama dalam XMP menggunakan Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
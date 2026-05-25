---
date: 2026-05-25
description: Pelajari cara mengubah xmp dalam dokumen EPS menggunakan Java dengan
  Aspose.Page. Perbarui metadata dengan cepat dan dapat diandalkan.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Mengubah Nilai di XMP menggunakan Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: cara mengubah xmp dengan Aspose.Page – Mengubah Nilai di XMP menggunakan Java
url: /id/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah Nilai XMP menggunakan Java

## Pendahuluan
Jika Anda mencari **cara memodifikasi xmp** di dalam file EPS dengan Java, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui setiap langkah—membaca blok XMP yang ada, memperbarui bidang seperti pembuat, judul, dan tanggal modifikasi, serta akhirnya menyimpan perubahan kembali ke dokumen EPS. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dalam alur kerja otomatis apa pun, memastikan file Anda membawa metadata yang tepat untuk branding, kepatuhan, atau pengindeksan mesin pencari.

## Jawaban Cepat
- **Apa yang dilakukan “aspose.page modify xmp”?** Memungkinkan Anda membaca dan menulis metadata XMP dalam file EPS melalui Aspose.Page Java API.  
- **Versi perpustakaan apa yang diperlukan?** Semua rilis terbaru Aspose.Page untuk Java (API stabil di semua versi).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah beberapa bidang XMP sekaligus?** Ya—panggil `put` untuk setiap bidang sebelum menyimpan dokumen.  
- **Apakah penanganan zona waktu diperlukan?** Menetapkan zona waktu default (mis., UTC) memastikan nilai tanggal konsisten.

## Apa itu XMP dan Mengapa Memodifikasinya?
XMP (Extensible Metadata Platform) adalah format standar berbasis XML untuk menyematkan metadata kaya langsung di dalam file seperti EPS, PDF, dan gambar. Memperbarui XMP memungkinkan Anda mengontrol cara dokumen diindeks, ditampilkan, dan dicari—kritikal untuk konsistensi merek, kepatuhan regulasi, dan pipeline konten otomatis.

## Mengapa Menggunakan Aspose.Page untuk Java?
Aspose.Page menyediakan **API Java murni yang lengkap** yang menghilangkan kebutuhan akan alat eksternal atau perpustakaan native. Ia mendukung **lebih dari 50 format input dan output** serta dapat memproses file EPS hingga **500 MB** tanpa memuat seluruh dokumen ke memori, memberikan manipulasi metadata yang cepat dan hemat memori pada sistem operasi apa pun yang menjalankan Java.

## Prasyarat
Sebelum memulai tutorial ini, pastikan Anda telah menyiapkan hal‑hal berikut:
1. **Lingkungan Pengembangan Java** – JDK (8 atau lebih baru) serta IDE atau alat build pilihan Anda.  
2. **Aspose.Page untuk Java** – Unduh dan instal perpustakaan Aspose.Page untuk Java. Anda dapat menemukan paket yang diperlukan [di sini](https://releases.aspose.com/page/java/).

## Impor Paket
Mulailah dengan mengimpor paket yang diperlukan ke dalam proyek Java Anda. Paket‑paket ini penting untuk berinteraksi dengan dan memanipulasi dokumen EPS.

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

## Cara memodifikasi XMP dalam EPS menggunakan Java?
`Document` adalah kelas Aspose.Page yang mewakili file EPS dan menyediakan akses ke konten serta metadata-nya. `XmpMetadata` mewakili blok XMP yang terlampir pada dokumen dan memungkinkan pembacaan serta penulisan bidang metadata. `put` menambahkan atau memperbarui entri metadata dalam objek XmpMetadata. `save` menulis dokumen yang telah dimodifikasi, termasuk metadata XMP yang diperbarui, ke sebuah file.

Muat file EPS dengan `new Document("input.eps")`, ambil objek `XmpMetadata`‑nya, perbarui kunci yang diinginkan menggunakan `put`, dan akhirnya panggil `save` untuk menulis perubahan kembali ke file baru. Alur singkat ini menangani blok XMP yang hilang secara otomatis, membuat satu dari komentar PostScript bila diperlukan, dan memastikan tanggal konsisten dengan zona waktu.

## Langkah 1: Dapatkan Metadata XMP
Kelas `XmpMetadata` mewakili blok XMP yang terlampir pada dokumen EPS. Ketika Anda memanggil `document.getXmpMetadata()`, API akan mengembalikan blok yang ada atau membangun yang baru dari komentar PS seperti `%%Creator`, `%%CreateDate`, dan `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 2: Ubah Nilai "ModifyDate"
Perbarui entri `"ModifyDate"` untuk mencerminkan timestamp modifikasi baru. Gunakan `java.util.Date` yang digabungkan dengan `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` untuk menjamin nilai yang disimpan tidak bergantung pada zona waktu.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Langkah 3: Ubah Nilai "Creator"
Kunci `"Creator"` menyimpan nama aplikasi atau orang yang menghasilkan file EPS. Panggil `xmp.put("dc:creator", "Your Company Name")` untuk mengganti nilai yang ada dengan pengidentifikasi khusus.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Langkah 4: Ubah Nilai "Title"
Bidang `"Title"` ditampilkan oleh banyak sistem manajemen aset. Menetapkannya melalui `xmp.put("dc:title", "New Document Title")` memastikan dokumen muncul dengan benar di katalog dan hasil pencarian.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diubah
Setelah semua modifikasi selesai, panggil `document.save("output.eps")`. Perpustakaan akan menulis blok XMP yang diperbarui kembali ke aliran EPS sambil mempertahankan konten grafis asli tidak berubah.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Masalah Umum dan Solusinya
- **Blok XMP tidak ada** – API secara otomatis membuat satu dari komentar PS, namun Anda juga dapat membuat `XmpMetadata` secara manual bila diperlukan.  
- **Ketidaksesuaian zona waktu** – Selalu setel `TimeZone.setDefault` sebelum membuat objek `Date` untuk menghindari offset yang tidak terduga.  
- **Kesalahan akses file** – Pastikan jalur input dan output sudah benar serta aplikasi Anda memiliki izin baca/tulis.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana saya dapat menangani pertimbangan zona waktu saat memodifikasi nilai XMP?**  
**A:** Gunakan `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` untuk memastikan konsistensi pengaturan zona waktu.

**Q: Bisakah saya mengubah beberapa nilai XMP dalam satu operasi?**  
**A:** Ya, dengan menggunakan metode `put` untuk setiap nilai yang diinginkan, Anda dapat memodifikasi beberapa nilai XMP secara bersamaan.

**Q: Di mana saya dapat menemukan dokumentasi tambahan untuk Aspose.Page untuk Java?**  
**A:** Jelajahi dokumentasi lengkap [di sini](https://reference.aspose.com/page/java/).

**Q: Apakah ada versi percobaan gratis untuk Aspose.Page untuk Java?**  
**A:** Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
**A:** Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Apakah memodifikasi XMP memengaruhi konten visual EPS?**  
**A:** Tidak. Perubahan XMP hanya pada metadata dan tidak mengubah elemen grafis file EPS.

**Q: Bisakah saya secara programatik membaca kembali nilai yang diperbarui untuk memverifikasi perubahan?**  
**A:** Tentu—cukup panggil `xmp.get("dc:creator")` (atau kunci yang relevan) setelah menyimpan dan sebelum menutup dokumen.

## Kesimpulan
Selamat! Anda telah menguasai **cara memodifikasi xmp** dalam dokumen EPS menggunakan Aspose.Page untuk Java. Dengan menyematkan metadata pembuat, judul, dan tanggal modifikasi yang akurat, Anda memastikan aset Anda dapat dicari, mematuhi regulasi, dan selaras dengan standar branding. Silakan integrasikan pola ini ke dalam pipeline pemrosesan batch, langkah CI/CD, atau alur kerja otomatis pembuatan dokumen apa pun.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Tutorial Terkait

- [Tutorial Aspose Page Java – Tambahkan Metadata XMP ke File EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Cara Membaca Metadata XMP menggunakan Java – Panduan Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Ubah Item Array dalam XMP menggunakan Java](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
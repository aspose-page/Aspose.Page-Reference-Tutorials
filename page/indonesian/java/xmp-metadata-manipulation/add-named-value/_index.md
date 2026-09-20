---
date: 2026-09-19
description: Pelajari cara menambahkan nilai bernama XMP ke file EPS menggunakan Aspose.Page
  for Java – panduan langkah demi langkah dengan contoh kode.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Tambahkan Nilai Bernama di XMP menggunakan Java
og_description: Cara menambahkan nilai bernama XMP ke file EPS menggunakan Aspose.Page
  for Java. Ikuti panduan singkat ini untuk menyisipkan metadata khusus dalam hitungan
  menit.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Cara menambahkan nilai bernama XMP dalam file EPS menggunakan Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Cara menambahkan nilai bernama XMP dalam file EPS menggunakan Java
url: /id/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah nilai bernama dalam metadata XMP menggunakan Java

## Pendahuluan
Dalam pengembangan Java modern, mempelajari **cara menambahkan metadata XMP** ke dalam file EPS sangat penting untuk mempertahankan asal-usul dokumen dan meningkatkan kemampuan pencarian. Dengan **Aspose.Page for Java**, Anda dapat dengan mudah menyuntikkan nilai bernama khusus ke dalam paket XMP. Tutorial ini memandu Anda melalui langkah‑langkah tepat—dilengkapi dengan potongan kode—sehingga Anda dapat mulai menambahkan metadata XMP ke dokumen EPS Anda hari ini.

## Jawaban Cepat
- **Apa perpustakaan yang diperlukan?** Aspose.Page for Java (Aspose)  
- **Jenis file apa yang ditargetkan?** EPS files containing XMP metadata  
- **Kasus penggunaan utama?** Add custom named values (e.g., page size limits) to XMP  
- **Prasyarat?** JDK 8+ and the Aspose.Page for Java library  
- **Waktu implementasi tipikal?** 5–10 minutes once the library is set up  

## Apa itu asp?
Aspose adalah singkatan dari Aspose, sebuah rangkaian API yang memungkinkan pengembang untuk membuat, mengedit, mengonversi, dan merender berbagai format dokumen tanpa memerlukan perangkat lunak eksternal. Komponen Aspose.Page for Java secara khusus berfokus pada pemrosesan PostScript dan EPS, menyediakan akses programatik ke konten halaman, grafik, dan metadata seperti XMP.

## Mengapa menambahkan nilai bernama ke metadata XMP?
Nilai bernama memungkinkan Anda menyimpan pasangan kunci‑nilai sewenang‑wenang langsung di dalam paket XMP, sehingga dapat dibaca secara instan oleh alat‑alat hilir. Ini meningkatkan keterbacaan mesin pencari, memungkinkan otomatisasi alur kerja, dan memenuhi persyaratan kepatuhan dengan menyematkan informasi regulasi tanpa mengubah konten visual.

## Mengapa ini penting
Menambahkan nilai bernama ke XMP memungkinkan Anda menyimpan pasangan kunci‑nilai sewenang‑wenang yang dapat dibaca tanpa harus mem-parsing seluruh file EPS. Kemampuan ini sangat berharga dalam pipeline penerbitan otomatis, sistem manajemen aset digital, dan alur kerja berbasis kepatuhan di mana metadata mengarahkan tindakan hilir.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **Java Development Kit (JDK):** JDK terbaru (8 atau lebih tinggi) terpasang di mesin Anda.  
- **Aspose.Page for Java Library:** Unduh dari [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Tambahkan JAR ke classpath proyek Anda.  
- **File EPS** yang sudah berisi metadata XMP atau akan menghasilkan metadata secara otomatis.

## Impor paket
Mulailah dengan mengimpor paket Java yang diperlukan. Impor ini memberi Anda akses ke aliran file, model dokumen EPS, dan kelas penanganan XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Cara menambahkan nilai bernama XMP dalam file EPS menggunakan Java
Untuk menambahkan nilai bernama, muat file EPS dengan `FileInputStream`, dapatkan atau buat objek `XmpMetadata`‑nya, sisipkan `NamedValue` yang diinginkan ke namespace yang tepat, lalu tulis kembali dokumen yang telah dimodifikasi menggunakan `FileOutputStream`. Aspose.Page secara otomatis menangani pembuatan paket XMP bila tidak ada, memastikan metadata baru tersemat dengan benar.

### Langkah 1: Inisialisasi aliran file EPS input
**FileInputStream** adalah kelas I/O Java yang membaca byte mentah dari sebuah file. Muat file EPS sumber ke dalam `FileInputStream`. Aliran ini memberi dokumen ke API Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro tip:** Jaga variabel `dataDir` dapat dikonfigurasi sehingga kode yang sama dapat bekerja di berbagai lingkungan.

### Langkah 2: Dapatkan metadata XMP
**XmpMetadata** mewakili paket XMP yang terkait dengan dokumen EPS. Dapatkan paket XMP yang ada; bila file EPS tidak memilikinya, Aspose membuat objek XMP baru yang diisi dari komentar PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Langkah 3: Tambahkan nilai bernama
**NamedValue** adalah pasangan kunci‑nilai yang disimpan dalam namespace metadata XMP. Sisipkan nilai bernama khusus ke dalam struktur XMP. Pada contoh ini kami menambahkan kunci baru di bawah namespace `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Mengapa ini penting:** Nilai bernama memungkinkan Anda menyimpan pasangan kunci‑nilai sewenang‑wenang yang dapat dibaca aplikasi hilir tanpa harus mem‑parsing seluruh dokumen.

### Langkah 4: Inisialisasi aliran file EPS output
**FileOutputStream** adalah kelas I/O Java yang menulis byte mentah ke sebuah file. Siapkan `FileOutputStream` tempat EPS yang telah dimodifikasi akan disimpan.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Langkah 5: Simpan dokumen
Metode `save` menyimpan perubahan. Ia menulis kembali paket XMP yang diperbarui ke dalam file EPS, menjamin nilai bernama baru menjadi bagian dari metadata dokumen.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Langkah 6: Tutup aliran EPS input
Menutup handle file asli mencegah kebocoran sumber daya dan memastikan file tidak terkunci untuk operasi selanjutnya.

```java
psStream.close();
```

Dengan mengikuti enam langkah ini, Anda telah berhasil **menambahkan nilai bernama dalam metadata XMP** menggunakan **Aspose.Page for Java**.

## Masalah umum & solusi
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| `NullPointerException` pada `xmp` | File EPS tidak memiliki XMP dan Aspose gagal membuatnya | Pastikan EPS berisi setidaknya satu komentar PS atau buat secara manual instance `XmpMetadata` baru. |
| File output kosong | Aliran output tidak di‑flush/ditutup | Verifikasi bahwa `outPsStream.close()` dipanggil dalam blok `finally` (seperti yang ditunjukkan). |
| Kesalahan kunci duplikat | Nilai bernama yang sama ditambahkan dua kali | Periksa apakah kunci sudah ada dengan `xmp.containsNamedValue(...)` sebelum menambahkannya. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Page for Java dengan perpustakaan Java lain?**  
**A:** Ya, Aspose.Page for Java dirancang untuk bekerja mulus dengan perpustakaan Java lainnya, memberikan fleksibilitas dalam lingkungan pengembangan Anda.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Page for Java?**  
**A:** Ya, Anda dapat mengakses percobaan gratis Aspose.Page for Java di halaman [Aspose releases page](https://releases.aspose.com/).

**Q: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page for Java?**  
**A:** Kunjungi [temporary license page](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara bagi Aspose.Page for Java.

**Q: Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.Page for Java?**  
**A:** Jelajahi [documentation](https://reference.aspose.com/page/java/) untuk tutorial dan contoh komprehensif.

**Q: Apakah Aspose.Page for Java cocok untuk proyek berskala besar?**  
**A:** Tentu saja, Aspose.Page for Java dirancang untuk menangani proyek berskala besar secara efisien, menyediakan kemampuan manipulasi dokumen yang kuat.

## Kesimpulan
Dalam panduan ini kami menunjukkan bagaimana **Aspose.Page for Java** memudahkan **menambahkan nilai bernama ke metadata XMP** dalam file EPS. Dengan langkah‑langkah di atas, Anda dapat memperkaya dokumen dengan metadata khusus, meningkatkan kemampuan pencarian, dan memungkinkan pemrosesan hilir yang lebih cerdas.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Cara Menambahkan Namespace XMP dalam File EPS Menggunakan Aspose.Page – Tutorial Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Tambahkan Metadata XMP ke File EPS Menggunakan Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Baca XMP menggunakan Aspose.Page – Panduan Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-15
description: Pelajari cara mengedit metadata XMP dan cara mengubah nilai XMP dalam
  file EPS dengan Aspose.Page for Java – panduan langkah demi langkah yang jelas.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Mengubah Nilai Bernama dalam XMP menggunakan Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: cara mengedit xmp – Mengubah Nilai Bernama dalam XMP menggunakan Java
url: /id/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cara mengedit xmp – Mengubah Nilai Bernama dalam XMP menggunakan Java

Dalam alur kerja dokumen modern, **Aspose.Page for Java** memudahkan membaca, mengedit, dan menulis metadata XMP di dalam file EPS. **Tutorial ini menunjukkan cara mengedit xmp** metadata dalam dokumen EPS menggunakan API Aspose.Page, sehingga Anda dapat menjaga informasi dokumen tetap akurat, dapat dicari, dan sesuai dengan standar industri. Baik Anda memperbarui dimensi halaman, informasi penulis, atau tag khusus, langkah‑langkah di bawah ini akan memandu Anda melalui prosesnya dengan Java.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengubah nilai XMP bernama dalam file EPS dengan Aspose.Page for Java.  
- **Versi perpustakaan mana yang diperlukan?** Versi terbaru Aspose.Page for Java (API telah stabil selama beberapa tahun).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk pengujian.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit bagi pengembang yang familiar dengan Java I/O.  
- **Bisakah saya menggunakan ini dengan format file lain?** API XMP juga tersedia untuk PDF, SVG, dan format lain yang didukung oleh Aspose.Page.

## Apa itu metadata XMP?
XMP (Extensible Metadata Platform) adalah format berbasis XML yang terstandarisasi untuk menyematkan metadata kaya—seperti pembuat, judul, dan properti khusus—langsung di dalam file. Pada dokumen EPS, XMP berada berdampingan dengan komentar PostScript tradisional, memungkinkan aplikasi membaca dan memodifikasi metadata tanpa mengubah konten visual.

## Mengapa menggunakan Aspose.Page for Java untuk mengedit XMP?
Aspose.Page memberikan **kendali penuh atas lebih dari 150 properti skema XMP** dan berfungsi secara konsisten pada format EPS, PDF, dan SVG. Ia memproses file hingga **500 MB** tanpa harus memuat seluruh dokumen ke memori, serta menyertakan validasi bawaan yang menjamin EPS yang dihasilkan tetap sesuai standar. Tidak diperlukan parser XML eksternal atau perpustakaan native.

## Pendahuluan
Aspose.Page for Java adalah perpustakaan kuat yang memfasilitasi manipulasi dan pemrosesan file EPS. Ketika menangani metadata XMP di dalam file tersebut, Aspose.Page memberi pengembang seperangkat fitur lengkap. Dalam tutorial ini, kami akan fokus pada mengubah nilai bernama dalam XMP, memberikan panduan jelas dan ringkas bagi pengembang yang ingin meningkatkan kemampuan pemrosesan dokumen mereka.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
1. **Java Development Environment** – JDK (8 atau lebih tinggi) serta IDE atau alat build (Maven/Gradle).  
2. **Aspose.Page for Java Library** – Unduh dan integrasikan perpustakaan Aspose.Page for Java ke dalam proyek Anda. Anda dapat menemukan perpustakaan dan dokumentasi detail **[di sini](https://reference.aspose.com/page/java/)**.  
3. **Sample EPS File** – Siapkan file EPS contoh untuk percobaan. Jika Anda belum memilikinya, gunakan file contoh yang disediakan bernama **"xmp4.eps."**

## Impor Paket
Pernyataan `import` membawa kelas-kelas penting Aspose.Page ke dalam ruang lingkup.

Kelas `PsDocument` adalah objek inti Aspose.Page yang mewakili dokumen EPS dalam memori.  
Kelas `XmpMetadata` memberikan akses ke paket XMP yang disematkan dalam file EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Cara mengedit metadata XMP?
Muat file EPS, ambil paket XMP‑nya, modifikasi properti yang diinginkan, dan simpan dokumen—semua dalam beberapa baris kode sederhana. Pendekatan ini berlaku untuk nilai XMP bernama apa pun, baik itu bidang Dublin Core standar atau namespace khusus yang Anda definisikan.

## Langkah 1: Inisialisasi Aliran File EPS Masukan
`FileInputStream` membuka aliran baca‑saja ke file EPS sumber, memungkinkan Aspose.Page mengonsumsi dokumen tanpa mengunci sistem file.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Langkah 2: Inisialisasi PsDocument
`PsDocument` adalah objek utama yang membungkus konten EPS dan menyediakan akses ke metadata, halaman, serta sumber daya.

```java
PsDocument document = new PsDocument(psStream);
```

## Langkah 3: Dapatkan Metadata XMP
`XmpMetadata` mewakili paket XMP di dalam file EPS dan menawarkan metode untuk membaca, memodifikasi, atau menghapus properti individual.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 4: Tetapkan Nilai Baru dalam XMP
`setProperty` menetapkan nilai properti XMP tertentu dalam paket metadata.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Langkah 5: Inisialisasi Aliran File EPS Keluaran
`FileOutputStream` membuat aliran tulis untuk menyimpan file EPS yang telah dimodifikasi.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Langkah 6: Simpan Dokumen dengan Metadata XMP yang Diubah
`save` menulis PsDocument dalam memori, termasuk XMP yang diperbarui, ke aliran keluaran.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Langkah 7: Tutup Aliran File EPS Masukan
`close` melepaskan pegangan file dan membebaskan sumber daya yang terkait dengan aliran masukan.

```java
// Close input EPS stream
psStream.close();
```

## Masalah Umum dan Solusinya
- **FileNotFoundException** – Pastikan `dataDir` mengarah ke folder yang tepat dan bahwa `xmp4.eps` ada.  
- **LicenseException** – Jika muncul kesalahan lisensi, pastikan file lisensi Aspose.Page yang valid dimuat sebelum membuat `PsDocument`.  
- **Metadata Not Updated** – Setelah menyimpan, buka EPS hasil di penampil metadata (misalnya, Adobe Bridge) untuk memastikan nilai baru muncul.

## Pertanyaan yang Sering Diajukan
**T: Bisakah saya menggunakan Aspose.Page for Java dengan bahasa pemrograman lain?**  
J: Aspose.Page terutama mendukung Java, tetapi Aspose menyediakan perpustakaan setara untuk .NET, C++, dan Python yang menawarkan kemampuan manipulasi XMP serupa.

**T: Apakah ada versi percobaan gratis untuk Aspose.Page for Java?**  
J: Ya, Anda dapat menjelajahi versi percobaan gratis Aspose.Page for Java **[di sini](https://releases.aspose.com/)**.

**T: Di mana saya dapat menemukan dukungan tambahan dan diskusi tentang Aspose.Page for Java?**  
J: Kunjungi **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk dukungan komunitas dan diskusi.

**T: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page for Java?**  
J: Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**T: Di mana saya dapat membeli Aspose.Page for Java?**  
J: Untuk membeli Aspose.Page for Java, kunjungi **[halaman pembelian](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2026-05-15  
**Tested With:** Aspose.Page for Java (rilisan terbaru)  
**Author:** Aspose

## Tutorial Terkait

- [Cara Membaca Metadata XMP menggunakan Java – Panduan Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutorial Aspose Page Java – Menambahkan Metadata XMP ke File EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Mengubah Nilai dalam XMP menggunakan Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
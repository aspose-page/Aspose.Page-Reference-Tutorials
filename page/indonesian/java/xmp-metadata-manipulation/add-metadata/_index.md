---
date: 2025-12-20
description: Pelajari cara menambahkan metadata XMP ke file EPS dengan tutorial Aspose
  Page Java. Ikuti panduan langkah demi langkah ini untuk meningkatkan manajemen dokumen
  Anda.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Tutorial Aspose Page Java – Tambahkan Metadata XMP ke File EPS
url: /id/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah Metadata dalam XMP menggunakan Java

## Pendahuluan
Dalam **aspose page java tutorial** ini, Anda akan belajar cara meningkatkan metadata dokumen Anda dengan menambahkan informasi XMP menggunakan Java. Panduan langkah‑demi‑langkah ini akan memandu Anda membaca file EPS yang ada, mengekstrak metadata XMP‑nya, dan menyimpan perubahan kembali ke disk dengan library Aspose.Page untuk Java. Pada akhir tutorial, Anda akan memiliki pola yang kuat dan dapat digunakan kembali untuk bekerja dengan XMP dalam alur kerja EPS apa pun.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Page for Java  
- **Bisakah saya menambahkan XMP ke file EPS apa pun?** Ya – API membuat blok XMP baru jika belum ada.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk pembaruan metadata dasar.

## Gambaran Umum Tutorial Aspose Page Java
Tutorial ini menunjukkan langkah‑langkah inti yang diperlukan untuk memanipulasi metadata XMP dalam file EPS. Memahami langkah‑langkah ini akan membantu Anda mengintegrasikan penanganan metadata ke dalam pipeline pemrosesan dokumen yang lebih besar, meningkatkan kemampuan pencarian, dan mematuhi standar industri untuk manajemen aset digital.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- Library Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/java/).  
- File EPS yang ingin Anda modifikasi.

## Impor Paket
Pertama, impor paket yang diperlukan ke program Java Anda:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Langkah 1: Dapatkan Metadata XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya tempat dokumen Anda disimpan.

## Langkah 2: Ambil Nilai CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Langkah 3: Ambil Nilai CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Langkah 4: Ambil Nilai Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Langkah 5: Ambil Nilai Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Langkah 6: Ambil Nilai Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Langkah 7: Ambil Nilai MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Langkah 8: Simpan Dokumen dengan Metadata XMP Baru
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Akhirnya, jangan lupa menutup aliran EPS input:

```java
// Close input EPS stream
psStream.close();
```

Sekarang, Anda telah berhasil menambahkan metadata ke file EPS Anda menggunakan Aspose.Page untuk Java!

## Kesimpulan
Dalam **aspose page java tutorial** ini, kami menjelajahi cara menambahkan metadata XMP ke file EPS menggunakan library Aspose.Page untuk Java. API yang kuat ini memungkinkan Anda memanipulasi metadata dokumen secara programatik, membantu Anda menjaga aset tetap terorganisir dan dapat dicari.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page untuk Java gratis digunakan?**  
A: Aspose.Page untuk Java adalah produk komersial. Anda dapat menjelajahi fiturnya melalui percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk Java?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/page/java/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk Java?**  
A: Anda dapat mendapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Format file apa yang didukung oleh Aspose.Page untuk Java?**  
A: Aspose.Page untuk Java mendukung berbagai format, termasuk EPS, PDF, dan XPS.

**Q: Bisakah saya membeli Aspose.Page untuk Java?**  
A: Ya, Anda dapat membeli Aspose.Page untuk Java [di sini](https://purchase.aspose.com/buy).

**Q: Bagaimana cara menangani file EPS besar saat menambahkan metadata?**  
A: Proses file secara streaming (seperti yang ditunjukkan) untuk menjaga penggunaan memori tetap rendah, dan tutup aliran dengan cepat.

**Q: Bisakah saya memodifikasi bidang XMP yang ada alih-alih hanya membacanya?**  
A: Tentu – Anda dapat menggunakan `xmp.put(key, value)` untuk memperbarui atau menambahkan entri baru sebelum menyimpan.

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-05
description: Pelajari cara menambahkan item array dc:title dalam metadata XMP file
  EPS menggunakan Aspose.Page untuk Java. Ikuti panduan langkah demi langkah ini untuk
  hasil cepat.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cara Menambahkan Item Array dc:title dalam Metadata XMP menggunakan Java
url: /id/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Item Array dalam Metadata XMP menggunakan Java

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara menambahkan dc:title** (dan item array lainnya) ke metadata XMP di dalam file EPS dengan Aspose.Page untuk Java. Memperbarui metadata XMP berguna ketika Anda perlu menyematkan informasi yang dapat dicari—seperti judul, pembuat, atau kata kunci—langsung ke dalam file grafis Anda. Kami akan membimbing Anda melalui setiap langkah, menjelaskan mengapa setiap baris penting, dan menunjukkan cara memverifikasi perubahan.

## Jawaban Cepat
- **Apa yang dimaksud dengan “dc:title”?** Itu adalah properti judul Dublin Core yang disimpan sebagai array XMP.  
- **Mengapa memodifikasi metadata XMP?** Hal ini memungkinkan manajemen aset yang lebih baik, kemampuan pencarian, dan kepatuhan terhadap standar.  
- **Apakah saya memerlukan blok XMP yang sudah ada?** Tidak—Aspose.Page akan menghasilkan satu dari komentar PS jika tidak ada.  
- **Versi perpustakaan apa yang diperlukan?** Versi terbaru Aspose.Page untuk Java (diuji dengan build 2026 terbaru).  
- **Bisakah saya menambahkan properti array lain?** Ya—gunakan metode `addArrayItem` yang sama untuk properti seperti `dc:creator`.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Perpustakaan Aspose.Page untuk Java terpasang (tambahkan JAR ke classpath proyek Anda).  
- Pengalaman dasar pengembangan Java (JDK 8+ disarankan).  
- File EPS yang sudah berisi metadata XMP atau setidaknya komentar metadata PS (misalnya, `%%Title`, `%%Creator`).  

## Impor Paket
Untuk memulai, impor kelas yang diperlukan untuk membaca, memanipulasi, dan menyimpan file EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Langkah 1: Muat Dokumen EPS dan Dapatkan Metadata XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Di sini kami membuka file EPS dan meminta Aspose.Page untuk blok XMP‑nya. Jika file tidak memiliki XMP, perpustakaan secara otomatis membuatnya menggunakan komentar PS yang ada, memastikan Anda selalu memiliki wadah metadata untuk bekerja.

## Langkah 2: Tambahkan Item Array **dc:title** Baru  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Baris ini menunjukkan **cara menambahkan dc:title**. Ganti `"NewTitle"` dengan judul sebenarnya yang ingin Anda sematkan. Metode ini menambahkan nilai ke array judul yang sudah ada, mempertahankan judul‑judul sebelumnya.

## Langkah 3: Tambahkan Item Array **dc:creator** Baru  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Demikian pula, Anda dapat memperkaya properti `dc:creator`. Beberapa pembuat dapat disimpan; setiap pemanggilan menambahkan entri lain.

## Langkah 4: Siapkan Stream Output  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Kami membuat stream untuk file EPS yang telah dimodifikasi. Menggunakan nama file yang berbeda (`xmp3_changed.eps`) menjaga file asli tetap tidak tersentuh.

## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diperbarui  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Pemanggilan `save` menulis data EPS bersama dengan blok XMP yang diperbarui. Blok `finally` menjamin handle file dilepaskan meskipun terjadi pengecualian.

## Mengapa Ini Penting
Menyematkan nilai `dc:title` dan `dc:creator` yang akurat meningkatkan:

- **Kemampuan pencarian** dalam sistem manajemen aset digital (DAM).  
- **Kepatuhan** terhadap standar penerbitan yang memerlukan metadata.  
- **Kolaborasi**, karena rekan tim dapat dengan cepat mengidentifikasi isi file tanpa membuka EPS.

## Kesalahan Umum & Tips
- **Kesalahan:** Menimpa item array yang sudah ada secara tidak sengaja.  
  **Tips:** Gunakan `xmp.getArrayItems("dc:title")` untuk memeriksa nilai saat ini sebelum menambahkan yang baru.  
- **Kesalahan:** Lupa menutup stream, yang menyebabkan file terkunci.  
  **Tips:** Selalu bungkus I/O dengan try‑with‑resources atau blok `finally` seperti yang ditunjukkan.  
- **Tips:** Anda dapat men-chain beberapa pemanggilan `addArrayItem` untuk menambahkan beberapa judul atau pembuat sekaligus.

## Pertanyaan yang Sering Diajukan

### Apakah saya dapat menggunakan Aspose.Page untuk Java dengan format dokumen lain?
Ya, Aspose.Page mendukung berbagai format dokumen, termasuk EPS, PDF, dan XPS.

### Apakah ada trial gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat mengakses trial gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk Java?
Dokumentasi tersedia [di sini](https://reference.aspose.com/page/java/).

### Bagaimana cara membeli Aspose.Page untuk Java?
Anda dapat membeli produk [di sini](https://purchase.aspose.com/buy).

### Apakah lisensi sementara tersedia untuk Aspose.Page untuk Java?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-03-05  
**Diuji Dengan:** Aspose.Page untuk Java (rilis terbaru 2026)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-21
description: tutorial aspose page xmp – Pelajari cara mengubah metadata XMP dalam
  file EPS dengan Aspose.Page untuk Java dalam panduan yang jelas, langkah demi langkah.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Tutorial XMP Halaman Aspose – Mengubah Nilai Bernama dalam XMP menggunakan
  Java
url: /id/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tutorial aspose page xmp – Mengubah Nilai Bernama dalam XMP menggunakan Java

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengubah nilai XMP bernama dalam file EPS menggunakan Aspose.Page untuk Java.  
- **Versi perpustakaan apa yang diperlukan?** Versi terbaru Aspose.Page untuk Java (API telah stabil selama beberapa tahun).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk produksi; trial gratis dapat digunakan untuk pengujian.  
- **Berapa lama waktu implementasinya?** Sekitar 10‑15 menit untuk pengembang yang familiar dengan Java I/O.  
- **Bisakah saya menggunakan ini dengan format file lain?** API XMP juga tersedia untuk PDF, SVG, dan format lain yang didukung oleh Aspose.Page.

## Apa itu metadata XMP?
XMP (Extensible Metadata Platform) adalah format standar untuk menyematkan metadata kaya—seperti pembuat, judul, dan properti khusus—langsung di dalam file. Pada dokumen EPS, XMP berada berdampingan dengan komentar PostScript tradisional, memungkinkan aplikasi membaca dan memodifikasi metadata tanpa mengubah konten visual.

## Mengapa menggunakan Aspose.Page untuk Java untuk mengedit XMP?
- **Kontrol penuh** – Akses properti XMP apa pun, termasuk struktur khusus, tanpa harus mem-parsing XML mentah.  
- **Konsistensi lintas format** – API yang sama bekerja untuk EPS, PDF, dan SVG, menyederhanakan pemeliharaan kode.  
- **Tanpa dependensi eksternal** – Perpustakaan Java murni, tanpa kode native atau parser tambahan.  
- **Penanganan error yang kuat** – Validasi bawaan memastikan EPS yang dihasilkan tetap sesuai standar.

## Pendahuluan
Aspose.Page untuk Java adalah perpustakaan Java yang kuat yang memfasilitasi manipulasi dan pemrosesan file EPS. Ketika berhubungan dengan metadata XMP di dalam file tersebut, Aspose.Page memberikan pengembang seperangkat fitur lengkap. Dalam tutorial ini, kami akan fokus pada mengubah nilai bernama dalam XMP, memberikan panduan yang jelas dan ringkas bagi pengembang yang ingin meningkatkan kemampuan pemrosesan dokumen mereka.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki hal‑hal berikut:
1. **Lingkungan Pengembangan Java** – Pastikan Anda memiliki lingkungan pengembangan Java yang terpasang di mesin Anda.  
2. **Aspose.Page untuk Java** – Unduh dan integrasikan perpustakaan Aspose.Page untuk Java ke dalam proyek Anda. Anda dapat menemukan perpustakaan dan dokumentasi lengkapnya [di sini](https://reference.aspose.com/page/java/).  
3. **File EPS Contoh** – Siapkan file EPS contoh untuk percobaan. Jika Anda belum memilikinya, gunakan file contoh yang disediakan dengan nama **"xmp4.eps."**

## Impor Paket
Untuk memulai proses, impor paket yang diperlukan dalam kode Java Anda. Paket‑paket ini penting untuk berinteraksi dengan Aspose.Page untuk Java. Tambahkan baris berikut di awal file Java Anda:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Sekarang, mari kita uraikan proses mengubah nilai bernama dalam XMP menggunakan Aspose.Page untuk Java menjadi beberapa langkah:

## Langkah 1: Inisialisasi Stream File EPS Masukan
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Langkah 2: Inisialisasi PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## Langkah 3: Dapatkan Metadata XMP
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 4: Set Nilai Baru dalam XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Langkah 5: Inisialisasi Stream File EPS Keluaran
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Langkah 6: Simpan Dokumen dengan Metadata XMP yang Diubah
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Langkah 7: Tutup Stream File EPS Masukan
```java
// Close input EPS stream
psStream.close();
```

Panduan langkah‑demi‑langkah ini memastikan pendekatan sistematis untuk mengubah nilai bernama dalam XMP menggunakan Aspose.Page untuk Java. Dengan mengikuti langkah‑langkah ini, Anda dapat dengan mulus mengintegrasikan fungsionalitas ini ke dalam aplikasi Java Anda.

## Masalah Umum dan Solusi
- **FileNotFoundException** – Pastikan `dataDir` mengarah ke folder yang benar dan bahwa `xmp4.eps` memang ada.  
- **LicenseException** – Jika Anda melihat error lisensi, pastikan file lisensi Aspose.Page yang valid telah dimuat sebelum membuat `PsDocument`.  
- **Metadata Tidak Terupdate** – Setelah menyimpan, buka EPS hasilnya dengan penampil metadata (misalnya Adobe Bridge) untuk memastikan nilai baru muncul.

## Kesimpulan
Sebagai kesimpulan, Aspose.Page untuk Java menyederhanakan proses bekerja dengan metadata XMP dalam file EPS. Tutorial ini telah membekali Anda dengan pengetahuan untuk secara efisien mengubah nilai bernama dalam XMP, meningkatkan kemampuan pemrosesan dokumen Anda.

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, namun Aspose menyediakan perpustakaan serupa untuk berbagai bahasa pemrograman.

### Apakah ada trial gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat mencoba trial gratis Aspose.Page untuk Java [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan tambahan dan diskusi tentang Aspose.Page untuk Java?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat membeli Aspose.Page untuk Java?
Untuk membeli Aspose.Page untuk Java, kunjungi [halaman pembelian](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose
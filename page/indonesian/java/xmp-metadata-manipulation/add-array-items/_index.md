---
date: 2025-12-18
description: Pelajari cara menambahkan metadata dengan menyisipkan item array ke dalam
  metadata XMP file EPS menggunakan Aspose.Page untuk Java. Ikuti panduan langkah
  demi langkah kami.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cara Menambahkan Metadata – Menambahkan Item Array di XMP (Java)
url: /id/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Item Array dalam Metadata XMP menggunakan Java

## Cara Menambahkan Metadata
Selamat datang di panduan langkah‑demi‑langkah kami tentang **cara menambahkan metadata** ke file EPS dengan Aspose.Page for Java. Dalam tutorial ini kami akan memandu Anda menambahkan item array ke metadata XMP—sebuah kebutuhan umum ketika Anda perlu memperkaya informasi dokumen seperti judul atau pembuat. Pada akhir tutorial, Anda akan memahami mengapa XMP berharga, cara memanipulasinya secara programatik, dan cara menyimpan file EPS yang telah diperbarui.

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.Page for Java  
- **Format file apa yang ditargetkan?** EPS (Encapsulated PostScript)  
- **Bisakah saya menambahkan beberapa judul?** Ya, gunakan `xmp.addArrayItem("dc:title", ...)` berulang kali  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi Aspose.Page yang valid diperlukan  
- **Apakah kode kompatibel dengan Java 8+?** Tentu saja, ini bekerja dengan semua versi Java modern  

## Prasyarat
Sebelum kami masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Perpustakaan Aspose.Page for Java terinstal.
- Pemahaman dasar tentang pemrograman Java.
- File EPS yang valid dengan metadata XMP yang ada atau komentar metadata PS.

## Impor Paket
Untuk memulai, Anda perlu mengimpor paket-paket yang diperlukan untuk bekerja dengan Aspose.Page. Sertakan baris-baris berikut di awal file Java Anda:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Langkah 1: Dapatkan Metadata XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Pada langkah ini, kami mengambil metadata XMP yang ada dari file EPS. Jika file EPS belum memiliki metadata XMP, Aspose.Page akan menghasilkan yang baru dan mengisinya dengan nilai-nilai dari komentar metadata PS.

## Langkah 2: Tambahkan Item Array "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Sekarang, kami menambahkan item array baru ke properti **dc:title** dalam metadata XMP. Ganti `"NewTitle"` dengan judul yang diinginkan.

## Langkah 3: Tambahkan Item Array "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Demikian pula, kami menambahkan item array baru ke properti **dc:creator** dalam metadata XMP. Ganti `"NewCreator"` dengan informasi pembuat yang diinginkan.

## Langkah 4: Inisialisasi Stream File EPS Output
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Siapkan stream file EPS output tempat dokumen yang dimodifikasi dengan metadata XMP yang diperbarui akan disimpan.

## Langkah 5: Simpan Dokumen dengan Metadata XMP yang Diubah
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Simpan dokumen dengan metadata XMP yang diperbarui ke file EPS output.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari **cara menambahkan metadata** dengan menyisipkan item array dalam metadata XMP menggunakan Aspose.Page for Java. Perpustakaan yang kuat ini menyederhanakan proses memanipulasi file EPS dan menyediakan fungsionalitas yang luas untuk pemrosesan dokumen.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.Page for Java dengan format dokumen lain?
Ya, Aspose.Page mendukung berbagai format dokumen, termasuk EPS, PDF, dan XPS.

### Apakah ada percobaan gratis yang tersedia untuk Aspose.Page for Java?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.Page for Java?
Dokumentasi tersedia [di sini](https://reference.aspose.com/page/java/).

### Bagaimana cara membeli Aspose.Page for Java?
Anda dapat membeli produk [di sini](https://purchase.aspose.com/buy).

### Apakah lisensi sementara tersedia untuk Aspose.Page for Java?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan Tambahan yang Sering Diajukan

**Q: Bisakah saya menambahkan lebih dari satu item array ke properti yang sama?**  
A: Tentu saja. Panggil `xmp.addArrayItem` beberapa kali untuk properti yang sama guna membangun daftar nilai.

**Q: Apakah pendekatan ini bekerja dengan skema XMP yang ada selain Dublin Core?**  
A: Ya, Anda dapat menambahkan item array ke properti XMP apa pun selama namespace direferensikan dengan benar.

**Q: Bagaimana saya dapat memverifikasi bahwa metadata telah ditambahkan dengan benar?**  
A: Buka file EPS hasil dalam penampil yang mendukung XMP (mis., Adobe Bridge) atau ekstrak metadata secara programatik menggunakan metode `XmpMetadata`.

---

**Terakhir Diperbarui:** 2025-12-18  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
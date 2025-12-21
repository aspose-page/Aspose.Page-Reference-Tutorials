---
date: 2025-12-21
description: Pelajari cara membaca metadata XMP menggunakan Java dengan Aspose.Page.
  Panduan langkah demi langkah ini menunjukkan cara membaca XMP format dokumen dan
  mengekstrak properti utama.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cara Membaca Metadata XMP menggunakan Java – Panduan Aspose.Page
url: /id/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Metadata dari XMP menggunakan Java

## Cara Membaca Metadata XMP menggunakan Java

Selamat datang di tutorial langkah‑demi‑langkah kami yang menunjukkan **cara membaca XMP** metadata dengan Java dan perpustakaan Aspose.Page. XMP (Extensible Metadata Platform) adalah standar yang banyak diadopsi untuk menyematkan metadata kaya di dalam dokumen. Pada akhir panduan ini Anda akan dapat membaca XMP format dokumen, mengambil informasi pembuat, cap waktu, thumbnail, dan lainnya—memberdayakan Anda untuk membangun solusi analisis dokumen yang lebih cerdas.

## Jawaban Cepat
- **Apa arti “cara membaca xmp”?** Itu merujuk pada ekstraksi metadata XMP dari file secara programatis.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk Java (tersedia dari halaman unduhan Aspose).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi; percobaan gratis tersedia.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya membaca XMP dari format lain?** Ya, Aspose.Page dapat menangani EPS, PDF, dan beberapa tipe gambar yang menyematkan XMP.

## Prasyarat
Sebelum menyelam ke dalam kode, pastikan Anda memiliki:

- **Java Development Kit (JDK)** – Java 8+ terpasang dan dikonfigurasi di mesin Anda.  
- **Aspose.Page untuk Java** – Unduh perpustakaan dari situs resmi [here](https://releases.aspose.com/page/java/).  
- File EPS yang berisi metadata XMP (misalnya `xmp1.eps`).  

## Impor Paket
Di proyek Java Anda, impor paket yang diperlukan:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Langkah 1: Inisialisasi Aliran File EPS Masukan
Mulailah dengan menetapkan jalur ke direktori dokumen Anda dan menginisialisasi aliran file EPS masukan.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Langkah 2: Dapatkan Metadata XMP
Ambil metadata XMP dari file EPS. Jika file tidak memiliki metadata XMP, yang baru akan dihasilkan dengan nilai‑nilai dari komentar metadata PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 3: Ekstrak Informasi CreatorTool
Periksa dan cetak nilai "CreatorTool" dari metadata XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Langkah 4: Ekstrak Informasi CreateDate
Periksa dan cetak nilai "CreateDate" dari metadata XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Langkah 5: Dapatkan Lebar Thumbnail
Jika thumbnail ada, ekstrak dan cetak lebar thumbnail pertama.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Langkah 6: Ekstrak Informasi Format
Periksa dan cetak nilai "format" dari metadata XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Langkah 7: Dapatkan DocumentID
Periksa dan cetak nilai "DocumentID" dari metadata XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Mengapa Ini Penting
Membaca metadata XMP memungkinkan Anda secara programatis menemukan asal, tanggal pembuatan, dan atribut penting lainnya dari sebuah dokumen tanpa harus membukanya di penampil. Hal ini sangat berguna untuk pemrosesan batch, sistem manajemen konten, dan pipeline aset digital di mana metadata menggerakkan pengindeksan dan pencarian.

## Kesalahan Umum & Tips
- **XMP Hilang:** Beberapa file EPS mungkin tidak berisi XMP. Pemanggilan `getXmpMetadata()` akan menyintesis set minimal berdasarkan komentar PS yang ada, tetapi Anda tidak akan mendapatkan metadata lengkap kecuali disematkan.  
- **Array Thumbnail:** Kunci `xmp:Thumbnails` dapat menyimpan beberapa entri. Contoh ini mengekstrak hanya yang pertama; iterasi array jika Anda membutuhkan semua thumbnail.  
- **Kesadaran Namespace:** Kunci XMP menggunakan namespace (mis., `xmp:`, `dc:`). Pastikan Anda merujuk nama kunci yang tepat; jika tidak `containsKey` akan mengembalikan false.

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Ya, Aspose.Page mendukung banyak bahasa, termasuk Java, .NET, dan lainnya. Periksa [documentation](https://reference.aspose.com/page/java/) untuk detail.

### Apakah tersedia percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat mengakses percobaan gratis [here](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Page untuk Java?
Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

### Apakah ada sumber daya tambahan untuk Aspose.Page untuk Java?
Jelajahi [documentation](https://reference.aspose.com/page/java/) lengkap dan unduh perpustakaan [here](https://releases.aspose.com/page/java/).

## FAQ Tambahan
**Q: Apakah pendekatan ini bekerja dengan file PDF yang berisi XMP?**  
A: Ya, Aspose.Page dapat membaca XMP dari PDF, EPS, dan beberapa format gambar.

**Q: Bisakah saya memodifikasi metadata XMP setelah membacanya?**  
A: Tentu saja. Objek `XmpMetadata` dapat diubah; Anda dapat menambah, memperbarui, atau menghapus kunci dan kemudian menyimpan dokumen.

**Q: Apakah ada cara untuk mengekstrak semua gambar thumbnail, bukan hanya dimensinya?**  
A: Anda dapat mengambil data biner dari properti `xmpGImg:data` setiap entri thumbnail dan menuliskannya ke file.

## Kesimpulan
Anda kini telah menguasai **cara membaca XMP** metadata menggunakan Java dan Aspose.Page. Dengan mengikuti langkah‑langkah ini Anda dapat mengekstrak alat pembuat, cap waktu, thumbnail, informasi format, dan ID dokumen—memberikan wawasan penuh tentang metadata yang disematkan di file EPS Anda. Jangan ragu untuk bereksperimen dengan namespace XMP tambahan untuk menarik data yang lebih kaya bagi aplikasi Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest)  
**Penulis:** Aspose
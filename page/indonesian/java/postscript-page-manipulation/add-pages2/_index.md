---
date: 2025-12-11
description: Pelajari cara mengatur ukuran halaman khusus dan menambahkan halaman
  ke dokumen Java PostScript menggunakan Aspose.Page. Ikuti panduan langkah demi langkah
  kami untuk manipulasi dokumen yang mulus.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Tutorial Aspose.Page Java – Mengatur Ukuran Halaman Khusus Saat Menambahkan
  Halaman dalam PostScript
url: /id/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – menetapkan ukuran halaman kustom saat Menambahkan Halaman dalam PostScript

## Pendahuluan
Dalam aplikasi Java modern, **menetapkan ukuran halaman kustom** untuk output PostScript sering diperlukan—baik Anda menghasilkan faktur, tiket, atau grafik kustom. Aspose.Page untuk Java membuat tugas ini sederhana. Dalam tutorial ini Anda akan belajar cara menambahkan halaman dan menetapkan ukuran halaman kustom dalam dokumen PostScript, langkah demi langkah, sehingga Anda dapat menghasilkan tata letak yang tepat setiap saat.

## Jawaban Cepat
- **Bisakah saya menetapkan ukuran halaman yang berbeda untuk setiap halaman?** Ya, Anda dapat membuka halaman dengan dimensi kustom menggunakan `document.openPage(width, height)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Page yang valid diperlukan untuk penyebaran non‑evaluasi.  
- **Versi Java mana yang didukung?** Perpustakaan ini bekerja dengan Java 8 dan yang lebih baru.  
- **Apakah API thread‑safe?** Instansi Document tidak thread‑safe; buat `PsDocument` terpisah per thread.  
- **Seberapa besar file PostScript dapat?** Aspose.Page menangani file multi‑megabyte secara efisien; penggunaan memori skala dengan konten, bukan jumlah halaman.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Pemahaman dasar tentang pemrograman Java.  
- Aspose.Page untuk Java ditambahkan ke proyek Anda (Maven/Gradle atau JAR manual).  
- Lingkungan pengembangan Java (IDE, JDK 8+).  

## Impor Paket
Untuk memulai, impor kelas yang diperlukan dari pustaka Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Langkah 1: Buat Dokumen PostScript Multipage
Pertama, buat `PsDocument` baru yang dikonfigurasi untuk beberapa halaman. Ini menyiapkan aliran output dan memberi tahu pustaka bahwa kita akan bekerja dengan file multipage.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Langkah 2: Tambahkan Konten ke Halaman Pertama
Dengan dokumen siap, Anda dapat menambahkan konten apa pun yang diperlukan ke halaman pertama. Setelah selesai, tutup halaman untuk mengunci kontennya.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Cara menetapkan ukuran halaman kustom
Jika ukuran halaman default tidak sesuai, Anda dapat **menetapkan ukuran halaman kustom** saat membuka halaman baru. Ini berguna untuk kwitansi, label, atau tata letak non‑standar apa pun.

## Langkah 3: Tambahkan Halaman Kedua dengan Ukuran Berbeda
Di bawah ini kami membuka halaman kedua dan secara eksplisit memberikan lebar dan tinggi kustom (dalam poin). Ini menunjukkan cara menetapkan ukuran halaman kustom untuk masing‑masing halaman.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Langkah 4: Simpan Dokumen
Akhirnya, simpan perubahan dengan menyimpan dokumen. Semua halaman—termasuk yang memiliki ukuran kustom—ditulis ke file output.

```java
// Save the document
document.save();
```

Dengan mengikuti langkah‑langkah ini, Anda dapat dengan mulus menambahkan halaman dan **menetapkan ukuran halaman kustom** dalam dokumen PostScript Java menggunakan Aspose.Page, memberi Anda kontrol penuh atas tata letak setiap halaman.

## Kesimpulan
Aspose.Page untuk Java menyediakan API yang kuat dan ramah pengembang untuk menangani dokumen PostScript. Anda kini tahu cara menambahkan beberapa halaman, menerapkan dimensi kustom, dan menyimpan hasilnya—memberdayakan Anda untuk menghasilkan output yang diformat dengan tepat untuk solusi berbasis Java apa pun.

## Pertanyaan yang Sering Diajukan
### Bisakah saya menambahkan halaman dengan ukuran berbeda dalam satu dokumen PostScript?
Ya, seperti yang ditunjukkan dalam tutorial ini, Anda dapat menambahkan halaman dengan ukuran yang bervariasi dalam dokumen PostScript multipage.  
### Apakah ada batasan pada jumlah halaman yang dapat saya tambahkan?
Aspose.Page mendukung penambahan jumlah halaman yang secara virtual tidak terbatas ke sebuah dokumen.  
### Bisakah saya menambahkan konten kustom, seperti gambar atau grafik, ke halaman?
Tentu saja! Aspose.Page memungkinkan Anda menambahkan berbagai konten, termasuk teks, gambar, dan elemen grafis lainnya.  
### Apakah Aspose.Page cocok untuk menangani dokumen besar?
Ya, Aspose.Page dirancang untuk menangani dokumen kecil maupun besar dengan efisien.  
### Di mana saya dapat menemukan sumber daya tambahan dan dukungan untuk Aspose.Page?
Jelajahi dokumentasi [Aspose.Page documentation](https://reference.aspose.com/page/java/), atau kunjungi forum [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.  

**Additional Q&A**

**Q:** *Format gambar apa yang didukung saat menggambar pada halaman PostScript?*  
**A:** Anda dapat menyematkan gambar PNG, JPEG, BMP, dan GIF secara langsung menggunakan API gambar.  

**Q:** *Bagaimana cara mengubah DPI default untuk dokumen?*  
**A:** Setel `PsSaveOptions.setResolution(int dpi)` sebelum membuat `PsDocument`.  

**Q:** *Bisakah saya mengenkripsi file PostScript dengan password?*  
**A:** PostScript sendiri tidak mendukung enkripsi, tetapi Anda dapat membungkus output dalam PDF dan menerapkan pengaturan keamanan jika diperlukan.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

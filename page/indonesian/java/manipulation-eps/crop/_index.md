---
date: 2026-09-04
description: Pelajari cara mengurangi ukuran file EPS dengan memotong file EPS di
  Java menggunakan Aspose.Page – panduan langkah demi langkah yang menunjukkan cara
  memotong EPS, memotong gambar EPS, dan memangkas file EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Potong File EPS di Java
og_description: Pelajari cara mengurangi ukuran file EPS dengan memotong file EPS
  di Java menggunakan Aspose.Page – panduan singkat dengan kode dan tips.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Cara memotong file EPS di Java untuk mengurangi ukuran file EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Cara memotong file EPS di Java untuk mengurangi ukuran file EPS
url: /id/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara memotong file EPS di Java untuk mengurangi ukuran file EPS

## Pendahuluan
Jika Anda perlu **memotong EPS** secara programatis dalam aplikasi Java dan ingin **mengurangi ukuran file EPS**, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas seluruh proses memotong gambar EPS menggunakan pustaka Aspose.Page untuk Java yang kuat. Pada akhir panduan, Anda akan memahami mengapa pemotongan EPS penting, melihat kode tepat yang Anda butuhkan, dan siap mengintegrasikan solusi ini ke dalam proyek Anda sendiri.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pemotongan EPS di Java?** Aspose.Page for Java.  
- **Berapa lama waktu yang dibutuhkan untuk mengimplementasikan pemotongan dasar?** Approximately 5‑10 minutes.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** A free trial works for evaluation; a commercial license is required for production.  
- **Versi Java mana yang didukung?** Java 8 and newer.  
- **Apakah saya dapat menentukan bounding box khusus?** Yes – you provide the coordinates you need.

## Apa itu pemotongan EPS dan mengapa menggunakannya?
**Pemotongan EPS membuat bounding box baru yang menentukan wilayah yang terlihat dari sebuah file EPS.**  
Memotong file EPS menghilangkan ruang putih yang tidak diinginkan dan memangkas grafik ke area yang benar‑benar Anda butuhkan, yang secara langsung **mengurangi ukuran file EPS** dan meningkatkan konsistensi tata letak dalam dokumen turunannya seperti PDF atau laporan.

## Mengapa memotong file EPS?
Memotong file EPS memungkinkan Anda **mengurangi ukuran file hingga 30 %**, menghilangkan margin berlebih, dan menstandarisasi grafik untuk alur pemrosesan batch. Ini sangat berguna ketika Anda perlu menyematkan banyak aset EPS ke dalam satu PDF atau ketika Anda ingin mempercepat rendering pada perangkat berdaya rendah.

## Prasyarat
Sebelum kita menyelami kode, pastikan Anda memiliki:

- **Aspose.Page for Java** library terpasang – unduh dari halaman resmi [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 atau yang lebih baru terpasang di mesin Anda.  
- **Sebuah folder** untuk menyimpan EPS input Anda (`input.eps`) dan file yang dipotong hasilnya (`output_crop.eps`).

## Impor paket
Pertama, impor kelas Java yang diperlukan. Potongan kode ini tetap persis sama seperti dalam tutorial asli:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Cara memotong gambar EPS di Java
Muat EPS sumber Anda, tentukan bounding box baru, dan panggil API pemotongan – seluruh operasi selesai dalam lima langkah singkat.

### Langkah 1: atur direktori dokumen dan aliran input
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Di sini kami mengarahkan kode ke folder yang berisi file EPS sumber kami dan membuka aliran untuk membacanya.

### Langkah 2: inisialisasi objek PsDocument
Kelas `PsDocument` mewakili file EPS dalam memori, memungkinkan Anda membaca dan memodifikasi propertinya.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
Objek ini memberi Anda akses ke bounding box asli dan metadata lainnya.

### Langkah 3: ekstrak bounding box awal
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Mengekstrak bounding box asli memberi Anda koordinat area yang terlihat saat ini – berguna untuk memutuskan berapa banyak yang perlu Anda pangkas.

### Langkah 4: buat aliran output
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Kami membuka aliran tempat EPS yang dipotong akan ditulis.

### Langkah 5: tentukan bounding box baru dan potong
Metode `cropEps` memangkas dokumen ke bounding box baru dan menulis hasilnya ke aliran output.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Berikan empat koordinat (x kiri‑bawah, y kiri‑bawah, x kanan‑atas, y kanan‑atas) yang menentukan area yang ingin Anda pertahankan. Metode ini melakukan pemotongan dan menulis hasilnya ke `output_crop.eps`.

## Masalah umum dan solusi
- **Koordinat tidak tepat:** EPS menggunakan poin (1/72 inci). Jika hasil pemotongan tampak salah, periksa kembali konversi satuan.  
- **Kesalahan file tidak ditemukan:** Pastikan `dataDir` diakhiri dengan pemisah path yang sesuai (`/` atau `\`).  
- **Pengecualian lisensi:** Menjalankan kode tanpa lisensi yang valid dapat menambahkan watermark pada output. Terapkan lisensi sementara atau permanen Anda sebelum penggunaan produksi.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Page kompatibel dengan Java 8?**  
A: Ya, Aspose.Page bekerja dengan Java 8 dan versi selanjutnya.

**Q: Bisakah saya menggunakan Aspose.Page untuk proyek komersial?**  
A: Tentu saja. Lisensi komersial diperlukan untuk penerapan produksi. Anda dapat memperoleh satu di [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Di mana saya dapat menemukan sumber daya tambahan dan dukungan komunitas?**  
A: Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) resmi untuk diskusi, contoh kode, dan tips pemecahan masalah.

**Q: Apakah ada percobaan gratis yang tersedia untuk pengujian?**  
A: Ya, Anda dapat mengunduh percobaan gratis Aspose.Page dari halaman rilis [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk evaluasi jangka pendek?**  
A: Lisensi sementara dapat diminta melalui portal lisensi [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Anda sekarang tahu **cara memotong EPS** file di Java menggunakan Aspose.Page untuk **mengurangi ukuran file EPS**. Dengan mendefinisikan bounding box khusus dan memanggil `cropEps`, Anda dapat memangkas margin yang tidak diinginkan atau mengisolasi bagian tertentu dari grafik EPS hanya dengan beberapa baris kode. Integrasikan potongan kode ini ke dalam alur pemrosesan dokumen Anda yang lebih besar untuk mengotomatisasi manipulasi EPS, **memotong aset gambar EPS**, dan **memangkas konten file EPS** secara efisien.

---

**Terakhir Diperbarui:** 2026-09-04  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Mengubah Ukuran File EPS di Java dengan Aspose.Page](/page/java/manipulation-eps/resize/)
- [Konversi EPS ke PNG dengan Aspose.Page Java (Lisensi Metered)](/page/java/license-management/set-metered-license/)
- [Tutorial Aspose Page Java – Tambahkan Metadata XMP ke File EPS](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-30
description: Pelajari cara membuat dokumen XPS di Java menggunakan Aspose.Page dan
  menambahkan gambar berulang dengan mudah melalui panduan langkah demi langkah ini.
  Cara membuat file XPS dengan cepat.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Tambah Gambar Berulang di Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cara Membuat Dokumen XPS dengan Gambar Berulang di Java
url: /id/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Dokumen XPS dengan Gambar Berulang di Java

## Pendahuluan
Membuat dokumen XPS secara programatik adalah keterampilan inti bagi pengembang Java yang membutuhkan output yang dapat dicetak dan independen perangkat. **How to create XPS** file secara efisien dijawab oleh Aspose.Page untuk Java, yang mengabstraksi detail rendah XML Paper Specification dan memungkinkan Anda fokus pada desain visual. Dalam panduan ini Anda akan melihat secara tepat cara membuat dokumen XPS, menambahkan gambar berulang sebagai latar belakang atau pola, dan menyimpan hasilnya—semua dengan kode yang singkat dan siap produksi.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Page?** Ini menyediakan API tingkat tinggi untuk menghasilkan dan memanipulasi dokumen XPS di Java.  
- **Apakah saya dapat mengulang gambar?** Ya – gunakan `XpsImageBrush` dengan `XpsTileMode.Tile`.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau komersial diperlukan untuk penggunaan produksi.  
- **Versi Java apa yang didukung?** Semua JDK 8+ kompatibel.  
- **Berapa lama waktu implementasinya?** Sekitar 10–15 menit untuk skenario gambar berulang dasar.

## Apa itu “membuat dokumen XPS”?
`XpsDocument` adalah objek tingkat atas Aspose.Page yang mewakili satu file XPS dalam memori. Ia mengenkapsulasi halaman, sumber daya, dan metadata, memungkinkan Anda membangun dokumen secara programatik. Membuat dokumen XPS berarti menginstansiasi kelas ini, menambahkan elemen visual, dan akhirnya memanggil `save` untuk menulis file tata letak tetap ke disk. Pendekatan ini menghilangkan penanganan XML manual dan menjamin kepatuhan terhadap XML Paper Specification.

## Mengapa menambahkan gambar berulang?
Pengulangan (tiling) menggandakan grafik di seluruh area yang ditentukan, yang ideal untuk latar belakang, watermark, atau isian pola. Dengan menggunakan `XpsTileMode.Tile` gambar akan otomatis diulang tanpa duplikasi manual, menghemat waktu pengembangan dan memastikan render yang konsisten pada perangkat apa pun. Gambar berulang juga menjaga ukuran file tetap kecil karena sumber bitmap yang sama digunakan kembali alih-alih disematkan berulang kali.

## Prasyarat
1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terpasang.  
2. **Aspose.Page for Java** – unduh dari [website](https://releases.aspose.com/page/java/).  
3. **A writable directory** – tempat file XPS yang dihasilkan akan disimpan.

## Impor Paket
Dalam proyek Java Anda, impor kelas yang diperlukan:

`XpsDocument` adalah objek utama yang mewakili file XPS.  
`XpsImageBrush` melukis bentuk menggunakan sumber gambar.  
`XpsTileMode` menentukan cara gambar diulang.  
`Rectangle2D` menggambarkan wilayah persegi panjang untuk penempatan.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Proyek Anda
Tambahkan file JAR Aspose.Page ke classpath proyek Anda dan verifikasi bahwa pernyataan impor dapat dikompilasi tanpa error.

### Langkah 2: Buat Dokumen XPS
`XpsDocument` adalah kontainer inti yang menyimpan halaman, jalur, dan sumber daya. Instansiasikan dengan ukuran halaman yang diinginkan, kemudian Anda dapat mulai menambahkan elemen grafis.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Langkah 3: Tentukan Jalur Gambar Berulang
Letakkan gambar yang ingin Anda ulang (misalnya `R08LN_NN.jpg`) di dalam direktori yang dirujuk oleh `dataDir`. Gambar tersebut akan digunakan sebagai pola kuas.

### Langkah 4: Tambahkan Gambar Berulang
Buat jalur persegi panjang dan isi dengan `XpsImageBrush`. Dengan mengatur mode ubin ke `Tile`, gambar akan diulang di seluruh persegi panjang. Sesuaikan persegi panjang sumber dan tujuan untuk mengontrol ukuran ubin dan penempatan.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Langkah 5: Simpan Dokumen
Simpan file XPS ke disk. File output akan berisi gambar berulang yang baru saja Anda definisikan dan dapat dibuka dengan viewer XPS apa pun.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ulangi langkah-langkah ini setiap kali Anda perlu **menambahkan gambar berulang** ke halaman atau bentuk lain dalam dokumen XPS yang sama.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|---------|--------|
| Gambar tidak muncul | Verifikasi bahwa jalur file (`dataDir + "R08LN_NN.jpg"`) benar dan gambar dapat diakses. |
| Pola ubin terlihat terdistorsi | Sesuaikan nilai `Rectangle2D` sumber dan tujuan untuk mengontrol ukuran ubin. |
| Opacity tidak berpengaruh | Pastikan opacity kuas diatur **setelah** konfigurasi mode ubin. |

## Pertanyaan yang Sering Diajukan

**Q:** Apakah Aspose.Page kompatibel dengan semua versi Java?  
**A:** Aspose.Page mendukung Java 8 hingga Java 21; Anda dapat menemukan matriks kompatibilitas lengkap [di sini](https://reference.aspose.com/page/java/).

**Q:** Apakah saya dapat menggunakan Aspose.Page untuk proyek komersial?  
**A:** Ya, lisensi komersial diperlukan untuk penggunaan produksi. Opsi pembelian terdaftar [di sini](https://purchase.aspose.com/buy).

**Q:** Apakah tersedia trial gratis?  
**A:** Trial gratis yang berfungsi penuh dapat diunduh dari halaman rilis Aspose [di sini](https://releases.aspose.com/).

**Q:** Di mana saya dapat mendapatkan dukungan komunitas?  
**A:** Bergabunglah dengan forum komunitas Aspose.Page di [forum](https://forum.aspose.com/c/page/39) untuk mengajukan pertanyaan dan berbagi contoh.

**Q:** Bagaimana cara mendapatkan lisensi sementara untuk evaluasi?  
**A:** Lisensi sementara disediakan atas permintaan melalui portal Aspose [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Anda kini memiliki alur kerja lengkap dan siap produksi untuk **how to create XPS** dokumen dengan gambar berulang menggunakan Aspose.Page untuk Java. Dengan memanfaatkan `XpsImageBrush` dan `XpsTileMode.Tile`, Anda dapat menghasilkan grafik kaya yang dapat diulang tanpa memperbesar ukuran file. Bereksperimenlah dengan ukuran ubin yang berbeda, tingkat opacity, dan bentuk untuk membangun tata letak dokumen yang canggih. Untuk langkah selanjutnya, jelajahi penambahan bentuk vektor atau overlay teks untuk lebih meningkatkan file XPS Anda.

---

**Terakhir Diperbarui:** 2026-05-30  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menambahkan Gambar ke Dokumen XPS Java – Panduan Sederhana dengan Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Tutorial Menambahkan Halaman ke XPS](/page/java/xps-page-manipulation/add-page/)
- [Konversi XPS ke PDF di Java menggunakan Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
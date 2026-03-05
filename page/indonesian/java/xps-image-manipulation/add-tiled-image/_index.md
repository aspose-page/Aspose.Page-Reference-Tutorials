---
date: 2025-12-28
description: Pelajari cara membuat dokumen XPS di Java menggunakan Aspose.Page dan
  menambahkan gambar ubin dengan mudah melalui panduan langkah demi langkah ini.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Cara Membuat Dokumen XPS dengan Gambar Berulang di Java
url: /id/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS dan Tambahkan Gambar Berulang di Java

## Pendahuluan
Dalam pengembangan Java modern, kemampuan untuk **membuat file dokumen XPS** secara programatik merupakan keterampilan yang berharga, terutama ketika Anda perlu memperkaya dokumen dengan grafik seperti gambar berulang. Aspose.Page untuk Java membuat proses ini menjadi sederhana, memungkinkan Anda fokus pada desain visual daripada penanganan file tingkat rendah. Pada tutorial ini Anda akan belajar cara membuat dokumen XPS, **menambahkan gambar berulang**, dan menyimpan hasilnya, semua dengan contoh kode langkah demi langkah yang jelas.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Page?** Menyediakan API tingkat tinggi untuk menghasilkan dan memanipulasi dokumen XPS di Java.  
- **Apakah saya dapat membuat gambar berulang?** Ya – gunakan `XpsImageBrush` dengan `XpsTileMode.Tile`.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau komersial diperlukan untuk penggunaan produksi.  
- **Versi Java apa yang didukung?** Semua JDK 8+ kompatibel.  
- **Berapa lama implementasinya?** Sekitar 10–15 menit untuk skenario gambar berulang dasar.

## Apa itu “membuat dokumen XPS”?
File XPS (XML Paper Specification) adalah format dokumen berlayout tetap yang mirip dengan PDF. Membuat dokumen XPS secara programatik memungkinkan Anda menghasilkan file yang dapat dicetak dan bersifat device‑independent langsung dari kode Java.

## Mengapa menambahkan gambar berulang?
Membuat gambar berulang menyalin grafik ke seluruh area yang ditentukan, yang sangat cocok untuk latar belakang, watermark, atau pola isi. Dengan `XpsTileMode.Tile` dari Aspose.Page Anda dapat mencapainya hanya dengan beberapa baris kode.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terinstal.  
2. **Aspose.Page untuk Java** – unduh dari [situs web](https://releases.aspose.com/page/java/).  
3. **Direktori yang dapat ditulisi** – tempat file XPS yang dihasilkan akan disimpan.

## Impor Paket
Di proyek Java Anda, impor kelas‑kelas yang diperlukan:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Proyek Anda
Tambahkan file JAR Aspose.Page ke classpath proyek Anda dan pastikan pernyataan impor dapat dikompilasi tanpa error.

### Langkah 2: Buat Dokumen XPS
Instansiasi objek `XpsDocument` baru. Ini adalah kontainer utama yang akan menampung semua halaman, path, dan sumber daya.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Langkah 3: Tentukan Jalur Gambar Berulang
Letakkan gambar yang ingin Anda ulangi (misalnya `R08LN_NN.jpg`) di dalam direktori yang dirujuk oleh `dataDir`. Gambar ini akan digunakan sebagai pola kuas.

### Langkah 4: Tambahkan Gambar Berulang
Buat path persegi panjang dan isi dengan `XpsImageBrush`. Dengan mengatur mode ubin ke `Tile`, gambar akan diulang di seluruh persegi panjang.

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
Persist file XPS ke disk. File output akan berisi gambar berulang yang baru saja Anda definisikan.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ulangi langkah‑langkah ini setiap kali Anda perlu **menambahkan gambar berulang** ke halaman atau bentuk lain dalam dokumen XPS yang sama.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| Gambar tidak muncul | Pastikan jalur file (`dataDir + "R08LN_NN.jpg"`) benar dan gambar dapat diakses. |
| Pola ubin tampak terdistorsi | Sesuaikan nilai `Rectangle2D` sumber dan tujuan untuk mengontrol ukuran ubin. |
| Opasitas tidak berpengaruh | Pastikan opasitas kuas diatur **setelah** konfigurasi mode ubin. |

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Page kompatibel dengan semua versi Java?
Aspose.Page dirancang untuk bekerja dengan berbagai versi Java. Pastikan kompatibilitas dengan memeriksa dokumentasi [di sini](https://reference.aspose.com/page/java/).

### Bisakah saya menggunakan Aspose.Page untuk proyek komersial?
Ya, Aspose.Page menawarkan lisensi komersial. Beli lisensinya [di sini](https://purchase.aspose.com/buy).

### Apakah tersedia versi percobaan gratis?
Ya, jelajahi fitur Aspose.Page dengan percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan komunitas dan diskusi?
Berinteraksilah dengan komunitas Aspose.Page di [forum](https://forum.aspose.com/c/page/39).

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page?
Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2025-12-28  
**Diuji Dengan:** Aspose.Page untuk Java 24.12 (terbaru)  
**Penulis:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

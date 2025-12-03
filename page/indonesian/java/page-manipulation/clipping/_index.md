---
date: 2025-12-03
description: Jelajahi cara menyimpan sebagai PostScript dan memotong bentuk menggunakan
  Aspose.Page untuk Java. Pelajari cara mengatur gaya goresan dan menerapkan wilayah
  pemotongan dalam pemotongan grafis Java.
language: id
linktitle: Save as PostScript – Clipping in Java Page Manipulation
second_title: Aspose.Page Java API
title: Simpan sebagai PostScript – Pemotongan dalam Manipulasi Halaman Java
url: /java/page-manipulation/clipping/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan sebagai PostScript – Clipping dalam Manipulasi Halaman Java

## Pendahuluan
Ketika Anda perlu **menyimpan sebagai PostScript** saat membuat grafik yang kompleks, clipping menjadi sekutu paling kuat Anda. Dalam Java Page Manipulation dengan Aspose.Page, clipping memungkinkan Anda menentukan wilayah tepat di mana operasi menggambar terlihat, memberikan kontrol halus atas output akhir. Tutorial ini memandu Anda melalui **cara memotong bentuk**, **mengatur gaya stroke**, dan **menerapkan wilayah clipping** menggunakan pustaka Aspose.Page untuk Java, sehingga Anda dapat menghasilkan file PostScript yang halus dengan percaya diri.

## Jawaban Cepat
- **Apa arti “save as PostScript”?**  
  Ini membuat file .ps yang menyimpan grafik vektor dalam bahasa PostScript, ideal untuk pencetakan dan rendering resolusi tinggi.  
- **Pustaka mana yang menangani clipping di Java?**  
  Aspose.Page untuk Java menyediakan API yang sederhana untuk `java graphics clipping`.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?**  
  Lisensi sementara cukup untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah tampilan stroke?**  
  Ya—gunakan `set stroke style` dengan `BasicStroke` untuk menyesuaikan lebar, pola dash, dan caps.  
- **Apakah kode ini kompatibel dengan Java 8+?**  
  Tentu saja, contoh ini berjalan pada runtime Java 8 atau yang lebih baru.

## Apa itu “save as PostScript” di Aspose.Page?
Menyimpan dokumen sebagai PostScript mengonversi perintah menggambar Anda ke dalam bahasa deskripsi halaman PostScript. File `.ps` yang dihasilkan dapat dibuka oleh printer, penampil, atau dikonversi ke PDF tanpa kehilangan kualitas.

## Mengapa menggunakan clipping dalam grafik Java?
Clipping memungkinkan Anda **menerapkan wilayah clipping** untuk membatasi gambar ke bentuk tertentu—sempurna untuk membuat masker, tata letak kompleks, atau memfokuskan perhatian pada area tertentu dari halaman. Ini juga membantu mengurangi ukuran file dengan menghindari perintah menggambar yang tidak diperlukan di luar wilayah yang terlihat.

## Prasyarat
Sebelum kita melanjutkan, pastikan Anda memiliki:

- **Aspose.Page untuk Java** – unduh dari [dokumentasi Aspose.Page](https://reference.aspose.com/page/java/).  
- **Lingkungan Pengembangan Java** – JDK 8 atau lebih baru, dengan IDE pilihan Anda (IntelliJ, Eclipse, dll.).  

## Impor Paket
Di proyek Java Anda, impor kelas yang diperlukan:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Impor ini memberi Anda akses ke definisi bentuk, penanganan warna, konfigurasi stroke, dan API Aspose.Page untuk membuat dokumen PostScript.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Dokumen dan Output Stream
Pertama, buat `PsDocument` dan arahkan ke output stream tempat file **PostScript** akan ditulis.

```java
String dataDir = "Your Document Directory";
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Clipping_outPS.ps");
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Tip profesional:** Simpan `dataDir` secara absolut atau gunakan `Paths.get(...)` untuk jalur yang independen platform.

### Langkah 2: Buat Bentuk dan **cara memotong bentuk**
Sekarang kita mendefinisikan geometri yang akan digunakan—sebuah persegi panjang dan sebuah lingkaran. Kita kemudian **menerapkan wilayah clipping** menggunakan lingkaran sehingga hanya bagian persegi panjang di dalam lingkaran yang dirender.

```java
Shape rectangle = new Rectangle2D.Float(0, 0, 300, 200);
document.setPaint(Color.BLUE);
// Clipping by shape
document.writeGraphicsSave();
document.translate(100, 100);
Shape circle = new Ellipse2D.Float(50, 0, 200, 200);
document.clip(circle);
document.fill(rectangle);
document.writeGraphicsRestore();
```

Pasangan `writeGraphicsSave()` / `writeGraphicsRestore()` mempertahankan keadaan grafik, memastikan clipping hanya memengaruhi perintah menggambar yang dimaksud.

### Langkah 3: **Atur gaya stroke** dan gambar outline
Setelah mengisi persegi panjang yang terpotong, kami mendemonstrasikan **java graphics clipping** dengan menggambar batas persegi panjang menggunakan pola dash khusus.

```java
document.translate(100, 100);
BasicStroke stroke = new BasicStroke(2, BasicStroke.CAP_BUTT, BasicStroke.JOIN_MITER, 10.0f, new float[]{5.0f}, 0.0f);
document.setStroke(stroke);
document.draw(rectangle);
```

Di sini, `BasicStroke` mendefinisikan garis selebar 2 piksel dengan dash 5 piksel, menampilkan cara **mengatur gaya stroke** untuk efek visual yang lebih kaya.

### Langkah 4: Tutup halaman dan **simpan sebagai PostScript**
Akhirnya, selesaikan halaman dan tulis file output.

```java
document.closePage();
document.save();
```

File `Clipping_outPS.ps` Anda kini berisi persegi panjang biru yang dipotong oleh wilayah lingkaran, dengan outline dash—siap untuk dicetak atau dikonversi lebih lanjut.

## Masalah Umum & Solusi
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **File tidak ditemukan** | Jalur `dataDir` salah | Gunakan jalur absolut atau `new File(dataDir).mkdirs()` sebelum membuat stream. |
| **Clipping tidak diterapkan** | `writeGraphicsSave()` / `writeGraphicsRestore()` hilang | Pastikan Anda membungkus kode clipping dengan pemanggilan ini untuk mempertahankan keadaan. |
| **Stroke muncul solid** | Array dash `BasicStroke` tidak diset | Verifikasi bahwa array pola dash (`new float[]{5.0f}`) diberikan dengan benar. |

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Page kompatibel dengan berbagai format dokumen?
Ya, Aspose.Page mendukung berbagai format dokumen, memberikan fleksibilitas dalam tugas pemrosesan dokumen.

### Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial saya?
Tentu saja! Aspose.Page menawarkan lisensi komersial untuk pengembang, memastikan penggunaannya dalam proyek pribadi maupun komersial.

### Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?
Dapatkan lisensi sementara untuk pengujian dari [sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan contoh dan dokumentasi lebih lanjut?
Jelajahi [dokumentasi](https://reference.aspose.com/page/java/) dan [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk banyak sumber daya.

### Apakah tersedia trial gratis?
Ya, Anda dapat mengakses trial gratis Aspose.Page [di sini](https://releases.aspose.com/).

**Tambahan Q&A**

**T:** *Apa yang sebenarnya dilakukan “apply clipping region” pada pipeline rendering?*  
**J:** Itu memberi tahu mesin grafik untuk mengabaikan perintah menggambar yang berada di luar bentuk yang didefinisikan, secara efektif memask output.

**T:** *Bisakah saya menggabungkan beberapa bentuk clipping?*  
**J:** Ya—panggil `document.clip()` beberapa kali; setiap pemanggilan menginterseksi wilayah clipping saat ini dengan bentuk baru.

**T:** *Apakah memungkinkan mengubah bentuk clipping setelah menggambar?*  
**J:** Hanya dalam keadaan grafik yang disimpan. Gunakan `writeGraphicsSave()` sebelum clipping dan `writeGraphicsRestore()` untuk mengembalikan.

## Kesimpulan
Dengan menguasai **save as PostScript**, **cara memotong bentuk**, **set stroke style**, dan **apply clipping region**, Anda memperoleh kontrol presisi atas rendering grafik Java dengan Aspose.Page. Bereksperimenlah dengan berbagai geometri, pola dash, dan warna untuk membuka potensi penuh pembuatan dokumen berbasis vektor.

---

**Terakhir Diperbarui:** 2025-12-03  
**Diuji Dengan:** Aspose.Page untuk Java 24.11  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

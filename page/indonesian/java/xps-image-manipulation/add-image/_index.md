---
date: 2025-12-28
description: Pelajari cara menambahkan gambar ke dokumen XPS dalam Java menggunakan
  Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara menambahkan gambar
  dengan mudah dan meningkatkan pemrosesan dokumen Anda.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Gambar ke Dokumen XPS Java – Panduan Sederhana dengan Aspose.Page
url: /id/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gambar ke Dokumen Java XPS dengan Aspose.Page

Menambahkan gambar ke file XPS adalah kebutuhan umum bagi pengembang Java yang perlu memperkaya laporan, faktur, atau dokumen visual apa pun. Dalam tutorial ini Anda akan menemukan **cara menambahkan gambar** ke dokumen XPS menggunakan pustaka Aspose.Page for Java yang kuat. Kami akan membimbing Anda melalui setiap langkah, menjelaskan mengapa setiap baris kode penting, dan memberi tip untuk menghindari jebakan umum.

## Jawaban Cepat
- **Pustaka apa yang dibutuhkan?** Aspose.Page for Java  
- **Apakah saya dapat menambahkan beberapa gambar?** Ya – ulangi langkah penambahan gambar untuk setiap foto  
- **Format gambar yang didukung?** TIFF, JPEG, PNG, GIF (dan lainnya yang didukung oleh .NET)  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi  
- **Waktu implementasi tipikal?** Sekitar 10‑15 menit untuk penyisipan gambar dasar

## Pendahuluan
Menambahkan gambar ke dokumen XPS adalah kebutuhan umum dalam banyak aplikasi Java, mulai dari pembuatan laporan hingga pemrosesan dokumen. Aspose.Page for Java menyederhanakan tugas ini, menawarkan metode efisien untuk mengintegrasikan gambar secara mulus ke dalam file XPS Anda. Dalam tutorial ini, kami akan menunjukkan cara menambahkan gambar ke dokumen XPS menggunakan Aspose.Page for Java.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
1. **Aspose.Page for Java Library** – Unduh dan instal pustaka Aspose.Page for Java dari [website](https://releases.aspose.com/page/java/).  
2. **Lingkungan Pengembangan Java** – Pastikan Anda memiliki lingkungan pengembangan Java yang sudah terpasang di mesin Anda.

Sekarang, mari lanjut ke langkah berikutnya.

## Mengimpor Paket
Di proyek Java Anda, impor paket Aspose.Page for Java yang diperlukan untuk mengakses kelas dan metode yang dibutuhkan.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Langkah 1: Menyiapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat file XPS dan gambar akan disimpan.

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: Membuat Dokumen XPS Baru
Inisialisasi dokumen XPS baru menggunakan cuplikan kode berikut:

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Menambahkan Gambar ke Dokumen XPS
Untuk menambahkan gambar, buat path di dalam dokumen XPS, dan atur image brush menggunakan file gambar yang disediakan serta koordinatnya.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Langkah 4: Menyimpan Dokumen XPS Hasil
Simpan dokumen XPS yang telah dimodifikasi ke direktori yang Anda tentukan.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Ulangi langkah-langkah ini untuk menambahkan lebih banyak gambar atau menyesuaikan gambar yang ada sesuai kebutuhan proyek Anda.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari **cara menambahkan gambar** ke dokumen XPS menggunakan Aspose.Page for Java. Keahlian ini sangat berharga untuk meningkatkan daya tarik visual aplikasi dan dokumen Java Anda.

### Pertanyaan yang Sering Diajukan
### Apakah saya dapat menambahkan beberapa gambar ke dokumen XPS yang sama menggunakan Aspose.Page for Java?
Ya, Anda dapat menambahkan beberapa gambar dengan mengulangi langkah‑langkah yang dijelaskan dalam tutorial ini untuk setiap gambar.

### Format gambar apa yang didukung oleh Aspose.Page for Java?
Aspose.Page for Java mendukung berbagai format gambar, termasuk TIFF, JPEG, PNG, dan GIF.

### Apakah tersedia versi percobaan Aspose.Page for Java?
Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Page for Java dari [tautan ini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page for Java?
Anda dapat memperoleh lisensi sementara dari [tautan ini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dukungan tambahan atau berdiskusi tentang masalah terkait Aspose.Page for Java?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas Aspose.Page.

## Tips Tambahan & Kesalahan Umum
- **Akurasi Path Geometry** – Pastikan string path bergaya SVG sesuai dengan dimensi gambar Anda; jika tidak, gambar dapat tampak terdistorsi atau terpotong.  
- **Skala Image Brush** – Metode `createImageBrush` menerima persegi sumber dan tujuan; menyesuaikan nilai‑nilai ini memungkinkan Anda mengontrol posisi dan skala dengan tepat.  
- **Aktivasi Lisensi** – Jika Anda menjalankan kode tanpa lisensi yang valid, Aspose akan menambahkan watermark pada file XPS yang dihasilkan.

---

**Terakhir Diperbarui:** 2025-12-28  
**Diuji Dengan:** Aspose.Page for Java 23.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
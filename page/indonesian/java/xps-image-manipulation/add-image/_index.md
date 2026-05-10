---
date: 2026-03-16
description: Pelajari cara asp asp dan cara menambahkan gambar ke dokumen XPS dalam
  Java menggunakan Aspose.Page. Panduan ini memandu Anda menambahkan gambar dengan
  cepat.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: asp asp – Tambahkan Gambar ke Dokumen XPS Java dengan Aspose.Page
url: /id/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp asp – Menambahkan Gambar ke Dokumen Java XPS dengan Aspose.Page

Menambahkan gambar ke file XPS adalah kebutuhan yang sering bagi pengembang Java yang ingin memperkaya laporan, faktur, atau dokumen visual apa pun. Dalam tutorial ini Anda akan belajar **cara menambahkan gambar** ke dokumen XPS menggunakan pustaka Aspose.Page for Java yang kuat, dan Anda akan melihat mengapa pendekatan **asp asp** membuat proses ini dapat diandalkan dan cepat. Kami akan melangkah melalui setiap langkah, menjelaskan mengapa setiap baris penting, dan memberi Anda tip praktis untuk menghindari jebakan umum.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page for Java  
- **Apakah saya dapat menambahkan beberapa gambar?** Yes – repeat the image‑adding steps for each picture  
- **Format gambar yang didukung?** TIFF, JPEG, PNG, GIF (and others supported by .NET)  
- **Apakah saya memerlukan lisensi?** A free trial works for evaluation; a commercial license is required for production  
- **Waktu implementasi tipikal?** About 10‑15 minutes for a basic image insertion  

## asp asp: Menambahkan Gambar ke Dokumen XPS
Metodologi **asp asp** berpusat pada pola sederhana yang dapat diulang: membuat dokumen, menentukan jalur, menerapkan image brush, dan menyimpan. Pola ini menjaga kode Anda tetap bersih dan memudahkan penyisipan grafik tambahan di kemudian hari.

## Apa itu Aspose.Page untuk Java?
Aspose.Page adalah API khusus yang memungkinkan Anda membuat, mengedit, dan merender dokumen XPS (XML Paper Specification) tanpa memerlukan Microsoft XPS Viewer. API ini menyembunyikan detail tingkat rendah dari markup XPS, sehingga Anda dapat fokus pada tata letak visual dokumen Anda.

## Mengapa menambahkan gambar ke XPS?
- **Professional look:** Gambar seperti logo, diagram, atau foto produk memberikan dokumen Anda tampilan yang halus.  
- **Brand consistency:** Menyematkan logo perusahaan Anda memastikan setiap faktur atau laporan yang dihasilkan membawa merek Anda.  
- **Dynamic content:** Anda dapat secara programatis menyisipkan kode QR, barcode, atau grafik yang dihasilkan pengguna saat runtime.

## Pendahuluan
Menambahkan gambar ke dokumen XPS adalah kebutuhan umum dalam banyak aplikasi Java, mulai dari pembuatan laporan hingga pemrosesan dokumen. Aspose.Page untuk Java menyederhanakan tugas ini, menawarkan metode efisien untuk mengintegrasikan gambar secara mulus ke dalam file XPS Anda. Dalam tutorial ini, kami akan menunjukkan cara menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk Java.

## Prasyarat
Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. **Aspose.Page for Java Library** – Unduh dan instal pustaka Aspose.Page for Java dari [website](https://releases.aspose.com/page/java/).  
2. **Java Development Environment** – Pastikan Anda memiliki lingkungan pengembangan Java yang terpasang di mesin Anda.

Sekarang, mari kita lanjutkan ke langkah berikutnya.

## Impor Paket
Dalam proyek Java Anda, impor paket Aspose.Page for Java yang diperlukan untuk mengakses kelas dan metode yang dibutuhkan.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Langkah 1: Menyiapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat dokumen XPS dan file gambar akan disimpan.

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: Membuat Dokumen XPS Baru
Inisialisasi dokumen XPS baru menggunakan cuplikan kode berikut:

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Menambahkan Gambar ke Dokumen XPS
Untuk menambahkan gambar, buat jalur dalam dokumen XPS, dan atur image brush menggunakan file gambar yang disediakan serta koordinatnya.

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

Ulangi langkah-langkah ini untuk menambahkan lebih banyak gambar atau menyesuaikan yang sudah ada sesuai kebutuhan proyek Anda.

## Masalah Umum dan Solusinya
- **Image appears stretched:** Verifikasi bahwa source rectangle (`new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f)`) sesuai dengan dimensi sebenarnya dari gambar Anda. Sesuaikan destination rectangle untuk mempertahankan rasio aspek.  
- **Watermark shows up:** Jika Anda menjalankan kode tanpa lisensi yang valid, Aspose menambahkan watermark. Aktifkan lisensi Anda lebih awal dalam aplikasi untuk menghindarinya.  
- **FileNotFoundException:** Pastikan `dataDir` mengarah ke folder yang benar dan nama file gambar (`QL_logo_color.tif`) cocok dengan file di disk.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari **cara menambahkan gambar** ke dokumen XPS menggunakan Aspose.Page untuk Java. Keterampilan ini sangat berharga untuk meningkatkan daya tarik visual aplikasi Java dan dokumen Anda. Dengan mengikuti pola **asp asp**, Anda dapat dengan mudah memperluas contoh ini untuk menyisipkan banyak grafik, mengubah skalanya secara dinamis, atau bahkan menghasilkan diagram secara langsung.

### Pertanyaan yang Sering Diajukan
### Apakah saya dapat menambahkan beberapa gambar ke dokumen XPS yang sama menggunakan Aspose.Page untuk Java?
Ya, Anda dapat menambahkan beberapa gambar dengan mengulangi langkah-langkah yang dijelaskan dalam tutorial ini untuk setiap gambar.

### Format gambar apa yang didukung oleh Aspose.Page untuk Java?
Aspose.Page untuk Java mendukung berbagai format gambar, termasuk TIFF, JPEG, PNG, dan GIF.

### Apakah tersedia versi percobaan Aspose.Page untuk Java?
Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Page untuk Java dari [tautan ini](https://releases.aspose.com/).

### Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk Java?
Anda dapat memperoleh lisensi sementara dari [tautan ini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dukungan tambahan atau mendiskusikan masalah terkait Aspose.Page untuk Java?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk mencari bantuan, berbagi pengalaman, dan terhubung dengan komunitas Aspose.Page.

---

**Terakhir Diperbarui:** 2026-03-16  
**Diuji Dengan:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
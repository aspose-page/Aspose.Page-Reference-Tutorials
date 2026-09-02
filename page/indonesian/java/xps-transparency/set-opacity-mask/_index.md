---
date: 2026-04-30
description: Pelajari cara membuat dokumen XPS dengan Java dan menambahkan opacity
  mask menggunakan Aspose.Page Java. Panduan langkah demi langkah dengan contoh kode.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Atur Masker Opasitas di Java XPS
second_title: Aspose.Page Java API
title: Buat Dokumen XPS Java – Atur Masker Opasitas dengan Aspose.Page
url: /id/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Opacity Mask di Java XPS menggunakan Aspose.Page Java

## Pendahuluan
Pada tutorial ini Anda akan **create XPS document Java** file dan belajar cara menerapkan opacity mask yang memberikan grafik Anda tampilan yang halus, semi‑transparan. Kami akan membimbing Anda melalui seluruh proses—dari menginisialisasi dokumen XPS, menambahkan canvas, menggambar persegi panjang, hingga melampirkan opacity mask berbasis gambar—menggunakan API Aspose.Page Java yang intuitif. Pada akhir tutorial, Anda akan dapat menghasilkan file XPS profesional secara programatis dan menggunakan kembali mask pada bentuk apa pun yang Anda perlukan.

## Jawaban Cepat
- **Apa yang dilakukan opacity mask?** Ini mendefinisikan tingkat transparansi yang bervariasi untuk sebuah bentuk, memungkinkan konten di bawahnya terlihat.  
- **Perpustakaan mana yang diperlukan?** Aspose.Page for Java (aspose page java).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Berapa banyak baris kode?** Sekitar 20 baris Java ditambah beberapa pernyataan setup.  
- **Bisakah saya menggunakan kembali mask pada beberapa bentuk?** Ya, Anda dapat menetapkan `ImageBrush` yang sama ke beberapa path.

## Apa itu Opacity Mask di XPS?
Opacity mask adalah bitmap atau vektor yang mengontrol alpha (transparansi) setiap piksel dalam sebuah bentuk. Ketika diterapkan pada persegi panjang, bagian-bagian persegi panjang menjadi sepenuhnya tidak tembus, sebagian transparan, atau sepenuhnya transparan, menciptakan efek visual yang canggih tanpa lapisan gambar tambahan.

## Mengapa Menggunakan Aspose.Page Java untuk **create XPS document java**?
- **Pure Java API** – Tanpa dependensi native, sehingga kode yang sama dapat dijalankan di Windows, Linux, atau macOS.  
- **Full XPS spec compliance** – Mask dirender persis seperti yang didefinisikan oleh standar XPS.  
- **Object‑oriented design** – Mirip dengan .NET, memudahkan Anda yang telah menggunakan Aspose dalam bahasa lain.  
- **High performance** – Dioptimalkan untuk dokumen besar dan pemrosesan batch.

## Contoh Penggunaan Umum
- **Watermarking** – Terapkan logo semi‑transparan di seluruh halaman.  
- **Dynamic theming** – Ubah gaya visual elemen UI dalam laporan yang dihasilkan.  
- **Print‑ready previews** – Tampilkan bagaimana desain akan terlihat dengan opacity yang bervariasi sebelum dikirim ke printer.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:
- Pemahaman dasar tentang pemrograman Java.  
- Perpustakaan Aspose.Page untuk Java terinstal. Anda dapat mengunduhnya **[here](https://releases.aspose.com/page/java/)**.  
- Lisensi yang valid untuk Aspose.Page. Jika Anda belum memilikinya, dapatkan lisensi sementara **[here](https://purchase.aspose.com/temporary-license/)**.  
- Lingkungan pengembangan yang dapat mengompilasi dan menjalankan aplikasi Java (mis., IntelliJ IDEA, Eclipse, atau VS Code).

## Impor Paket
Mulailah dengan mengimpor kelas yang diperlukan dari perpustakaan Aspose.Page. Ini memastikan API tersedia untuk proyek Anda.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Dokumen XPS Baru
Pertama, buat instance dokumen XPS baru yang akan menampung semua grafik kami.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Langkah 2: Tambahkan Canvas
Canvas berfungsi sebagai permukaan gambar di dalam halaman XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Langkah 3: Tambahkan Persegi Panjang dan Terapkan Isian Solid
Di sini kami membuat path persegi panjang dan memberinya isian merah solid. Persegi panjang ini nantinya akan menerima opacity mask.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Langkah 4: Tambahkan Opacity Mask Menggunakan ImageBrush
Kami memuat gambar TIFF, mendefinisikan persegi sumber dan tujuan, serta mengatur kuas ke mode tile sehingga mask diulang bila diperlukan.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Langkah 5: Simpan Dokumen XPS Hasil
Akhirnya, simpan dokumen ke disk. File output akan berisi persegi panjang dengan opacity mask yang diterapkan.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Ikuti langkah-langkah ini dengan cermat untuk mengintegrasikan fungsionalitas **add opacity mask** ke dalam dokumen Java XPS Anda menggunakan Aspose.Page.

## Masalah Umum & Pemecahan Masalah
- **Image not found** – Verifikasi bahwa `dataDir` mengarah ke folder yang benar dan bahwa `R08SY_NN.tif` ada.  
- **Mask appears solid** – Pastikan gambar sumber memang mengandung nilai alpha yang bervariasi; gambar yang sepenuhnya tidak tembus tidak akan menunjukkan transparansi.  
- **Tile mode not respected** – Persegi tujuan harus lebih kecil daripada persegi sumber agar tiling terlihat.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page kompatibel dengan semua lingkungan pengembangan Java?**  
A: Ya, Aspose.Page dirancang untuk bekerja mulus dengan berbagai IDE Java dan alat build.

**Q: Bisakah saya menggunakan Aspose.Page tanpa lisensi?**  
A: Meskipun Anda dapat mengevaluasi perpustakaan dengan lisensi sementara, lisensi penuh diperlukan untuk penggunaan produksi.

**Q: Apakah ada batasan pada versi percobaan?**  
A: Versi percobaan mungkin memberlakukan batasan ukuran atau fitur; lihat dokumentasi resmi untuk detailnya.

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Page?**  
A: Kunjungi **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** untuk bantuan komunitas atau beli lisensi untuk bantuan premium.

**Q: Apakah ada jaminan uang kembali untuk Aspose.Page?**  
A: Lihat **[purchase page](https://purchase.aspose.com/buy)** untuk informasi tentang kebijakan pengembalian dana.

---

**Terakhir Diperbarui:** 2026-04-30  
**Diuji Dengan:** Aspose.Page Java 24.11 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
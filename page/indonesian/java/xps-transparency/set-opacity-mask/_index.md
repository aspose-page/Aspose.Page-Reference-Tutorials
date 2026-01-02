---
date: 2026-01-02
description: Pelajari cara menambahkan opacity mask ke dokumen XPS dengan Aspose.Page
  Java. Panduan langkah demi langkah untuk membuat persegi panjang opacity mask dan
  meningkatkan kualitas visual.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Setel Masker Opasitas di Java XPS menggunakan Aspose.Page Java
url: /id/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Opacity Mask di Java XPS menggunakan Aspose.Page Java

## Pendahuluan
Selamat datang di panduan lengkap kami tentang **aspose page java** opacity masks. Pada tutorial ini Anda akan belajar cara membuat dokumen XPS, menambahkan kanvas, dan menerapkan opacity mask pada sebuah persegi panjang—semua dengan API kuat Aspose.Page Java. Pada akhirnya Anda akan dapat menambahkan persegi panjang dengan opacity mask yang memberikan tampilan XPS Anda menjadi halus dan semi‑transparan.

## Jawaban Cepat
- **Apa yang dilakukan opacity mask?** Ia menentukan tingkat transparansi yang berbeda‑beda untuk sebuah bentuk, memungkinkan konten di bawahnya terlihat.
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page untuk Java (aspose page java).
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.
- **Berapa banyak baris kode?** Sekitar 20 baris Java ditambah beberapa pernyataan setup.
- **Bisakah saya menggunakan kembali mask pada beberapa bentuk?** Ya, Anda dapat menetapkan ImageBrush yang sama ke beberapa path.

## Apa itu Opacity Mask di XPS?
Opacity mask adalah bitmap atau vektor yang mengontrol nilai alpha (transparansi) setiap piksel dalam sebuah bentuk. Ketika diterapkan pada persegi panjang, bagian‑bagian persegi panjang menjadi sepenuhnya opak, sebagian transparan, atau sepenuhnya transparan, menciptakan efek visual yang canggih.

## Mengapa Menggunakan Aspose.Page Java untuk Opacity Masks?
- **API .NET‑style lengkap di Java** – model objek yang intuitif.  
- **Tanpa ketergantungan eksternal** – bekerja dengan Java murni.  
- **Rendering fidelitas tinggi** – mask dirender persis seperti dalam spesifikasi XPS.  
- **Cross‑platform** – dapat dijalankan di Windows, Linux, atau macOS tanpa perubahan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:
- Pemahaman dasar tentang pemrograman Java.  
- Perpustakaan Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- Lisensi yang valid untuk Aspose.Page. Jika belum memilikinya, dapatkan lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.  
- Lingkungan pengembangan yang mampu mengompilasi dan menjalankan aplikasi Java (misalnya IntelliJ IDEA, Eclipse, atau VS Code).

## Impor Paket
Mulailah dengan mengimpor kelas‑kelas yang diperlukan dari perpustakaan Aspose.Page. Ini memastikan API tersedia untuk proyek Anda.

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
Pertama, buat instance dokumen XPS baru yang akan menampung semua grafik kita.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Langkah 2: Tambahkan Kanvas
Kanvas berfungsi sebagai permukaan gambar di dalam halaman XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Langkah 3: Tambahkan Persegi Panjang dan Terapkan Isian Solid
Di sini kita membuat path persegi panjang dan memberinya isian merah solid. Persegi panjang ini nantinya akan menerima opacity mask.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Langkah 4: Tambahkan Opacity Mask Menggunakan ImageBrush
Kita memuat gambar TIFF, mendefinisikan persegi sumber dan tujuan, serta mengatur brush ke mode tile sehingga mask diulang bila diperlukan.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Langkah 5: Simpan Dokumen XPS yang Dihasilkan
Akhirnya, simpan dokumen ke disk. File output akan berisi persegi panjang dengan opacity mask yang telah diterapkan.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Ikuti langkah‑langkah ini dengan cermat untuk memasukkan fungsionalitas **add opacity mask** ke dalam dokumen Java XPS Anda menggunakan Aspose.Page.

## Masalah Umum & Pemecahan Masalah
- **Gambar tidak ditemukan** – Pastikan `dataDir` mengarah ke folder yang tepat dan bahwa `R08SY_NN.tif` ada.  
- **Mask muncul solid** – Pastikan gambar sumber memang mengandung nilai alpha yang bervariasi; gambar yang sepenuhnya opak tidak akan menampilkan transparansi.  
- **Mode tile tidak berfungsi** – Persegi tujuan harus lebih kecil dari persegi sumber agar tiling terlihat.

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Page kompatibel dengan semua lingkungan pengembangan Java?**  
J: Ya, Aspose.Page dirancang untuk bekerja mulus dengan berbagai IDE Java dan alat build.

**T: Bisakah saya menggunakan Aspose.Page tanpa lisensi?**  
J: Anda dapat mengevaluasi perpustakaan dengan lisensi sementara, tetapi lisensi penuh diperlukan untuk penggunaan produksi.

**T: Apakah ada batasan pada versi percobaan?**  
J: Versi percobaan mungkin memberlakukan batasan ukuran atau fitur; lihat dokumentasi resmi untuk detailnya.

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.Page?**  
J: Kunjungi **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk bantuan komunitas atau beli lisensi untuk dukungan premium.

**T: Apakah ada jaminan uang kembali untuk Aspose.Page?**  
J: Lihat **[halaman pembelian](https://purchase.aspose.com/buy)** untuk informasi kebijakan pengembalian dana.

---

**Terakhir Diperbarui:** 2026-01-02  
**Diuji Dengan:** Aspose.Page Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-03
description: Pelajari cara menggunakan Aspose.Page untuk .NET untuk menata gambar
  dalam pola ubin pada dokumen XPS. Panduan langkah demi langkah ini menunjukkan cara
  menata gambar secara efisien dan meningkatkan daya tarik visual.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Cara Menggunakan Aspose.Page untuk Menambahkan Gambar Ubin ke Dokumen XPS
url: /id/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Aspose.Page untuk Menambahkan Gambar Berulang ke Dokumen XPS

## Pendahuluan

Jika Anda bertanya-tanya **cara menggunakan Aspose** untuk memberikan file XPS Anda gaya visual yang lebih kaya, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk **menyusun gambar berulang** di dalam dokumen XPS menggunakan Aspose.Page untuk .NET. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke proyek .NET apa pun untuk membuat grafik gambar berulang secara langsung.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page for .NET  
- **Metode mana yang membuat kuas berulang?** `CreateImageBrush` dengan `TileMode = XpsTileMode.Tile`  
- **Apakah saya dapat mengontrol opasitas?** Ya – atur `path.Fill.Opacity` (misalnya 0.5f)  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara berfungsi untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Apa itu Aspose.Page dan Mengapa Mengulang Gambar?

Aspose.Page adalah API kuat yang memungkinkan pengembang menghasilkan, mengedit, dan merender XPS, PDF, serta format berbasis halaman lainnya tanpa bergantung pada Microsoft Office. Mengulang gambar—menyebarkan bitmap secara berulang di atas sebuah bentuk—membantu Anda mengisi area besar dengan pola, watermark, atau tekstur latar belakang sambil menjaga ukuran file tetap kecil.

## Cara Menggunakan Aspose.Page untuk Mengulang Gambar dalam Dokumen XPS

Di bawah ini Anda akan menemukan contoh lengkap yang siap dijalankan. Setiap langkah dijelaskan dengan bahasa sederhana sebelum blok kode yang bersangkutan, sehingga Anda dapat memahami **mengapa** setiap baris penting.

### Prasyarat

- **Aspose.Page for .NET** – unduh dan referensikan perpustakaan dari situs resmi [di sini](https://reference.aspose.com/page/net/).  
- **Lingkungan pengembangan** – Visual Studio (edisi apa pun) atau IDE .NET lain yang Anda sukai.

### Impor Namespace

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup sehingga kompiler mengetahui di mana menemukan kelas‑kelas XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Langkah 1: Tentukan Direktori Dokumen

Tentukan di mana file XPS yang dihasilkan dan gambar sumber akan disimpan. Ganti placeholder dengan folder sebenarnya di mesin Anda.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Langkah 2: Buat Dokumen XPS Baru

Instansiasi dokumen XPS kosong yang akan menampung grafik berulang.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Langkah 3: Tambahkan Gambar Berulang

Di sini kami membuat jalur persegi panjang, mengisinya dengan `ImageBrush`, dan mengatur kuas ke mode berulang. Properti `TileMode` memberi tahu mesin untuk mengulang gambar secara horizontal dan vertikal. Sesuaikan koordinat persegi panjang atau gambar sumber sesuai kebutuhan skenario Anda.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Langkah 4: Simpan Dokumen XPS Hasil

Akhirnya, tulis dokumen ke disk. File output dapat dibuka dengan viewer XPS apa pun atau diproses lebih lanjut dengan Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Masalah Umum & Tips

- **Kesalahan jalur** – Pastikan `dataDir` diakhiri dengan garis miring atau gunakan `Path.Combine` untuk menghindari masalah pemisah yang hilang.  
- **Ketidaksesuaian ukuran gambar** – Gambar sumber harus cukup besar untuk area pengulangan; jika tidak pola dapat tampak terdistorsi.  
- **Opasitas tidak terlihat** – Beberapa viewer mengabaikan opasitas pada XPS; uji dengan viewer yang sepenuhnya mendukung rendering XPS (misalnya, XPS Viewer di Windows).

## Pertanyaan yang Sering Diajukan

### Q1: Apakah Aspose.Page kompatibel dengan semua lingkungan pengembangan .NET?
A: Ya, Aspose.Page bekerja dengan Visual Studio, Rider, VS Code, dan IDE apa pun yang mendukung .NET.

### Q2: Apakah saya dapat mengatur opasitas gambar berulang?
A: Tentu saja. Contoh ini menetapkan `path.Fill.Opacity = 0.5f;`—Anda dapat mengubah nilai float antara 0 (transparan) dan 1 (opaque).

### Q3: Apakah ada mode pengulangan lain yang tersedia di Aspose.Page untuk .NET?
A: Ya. Selain `XpsTileMode.Tile`, Anda dapat menggunakan `FlipX`, `FlipY`, dan `FlipXY` untuk membuat pola cermin.

### Q4: Bagaimana cara menangani lisensi sementara untuk Aspose.Page?
A: Lihat halaman [lisensi sementara](https://purchase.aspose.com/temporary-license/) di situs Aspose untuk detail cara memperoleh dan menerapkan lisensi percobaan.

### Q5: Di mana saya dapat mencari bantuan atau terhubung dengan komunitas Aspose.Page?
A: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk mengajukan pertanyaan, berbagi potongan kode, dan belajar dari pengembang lain.

### Q6: Apakah saya dapat menggunakan pendekatan ini untuk membuat efek watermark?
A: Ya. Dengan menurunkan opasitas dan memilih gambar semi‑transparan, kuas berulang berfungsi sempurna sebagai watermark berulang.

## Kesimpulan

Anda kini mengetahui **cara menggunakan Aspose** untuk menambahkan gambar berulang ke dokumen XPS, mengontrol opasitasnya, dan menyimpan hasilnya untuk penggunaan lebih lanjut. Teknik ini ideal untuk pola latar belakang, watermark, atau situasi apa pun di mana grafik berulang menambah daya tarik visual tanpa memperbesar ukuran file. Jangan ragu bereksperimen dengan bentuk, gambar, dan mode pengulangan yang berbeda untuk menyesuaikan kebutuhan proyek Anda.

---

**Terakhir Diperbarui:** 2026-03-03  
**Diuji Dengan:** Aspose.Page for .NET (rilisan terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
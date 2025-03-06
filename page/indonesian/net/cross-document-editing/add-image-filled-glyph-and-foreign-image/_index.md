---
title: Tambahkan Gambar Berisi Glyph & Gambar Asing dengan Aspose.Page .NET
linktitle: Tambahkan Gambar Berisi Glyph & Gambar Asing
second_title: Aspose.Halaman .NET API
description: Buka kekuatan pemrosesan dokumen di .NET dengan Aspose.Page. Tambahkan mesin terbang berisi gambar dengan mudah. Sempurnakan visual dan sederhanakan alur kerja Anda.
weight: 11
url: /id/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gambar Berisi Glyph & Gambar Asing dengan Aspose.Page .NET

## Perkenalan

Dalam dunia pengembangan .NET, Aspose.Page menonjol sebagai perangkat canggih untuk menangani tugas pemrosesan dokumen. Tutorial ini akan memandu Anda melalui proses menambahkan mesin terbang berisi gambar dan menggabungkan gambar asing menggunakan Aspose.Page untuk .NET. Di akhir panduan ini, Anda akan memiliki pemahaman yang kuat tentang cara meningkatkan kemampuan pemrosesan dokumen Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET yang berfungsi dengan Visual Studio atau IDE pilihan lainnya.

- Direktori Dokumen: Buat direktori tempat Anda menyimpan dokumen Anda. Ini akan disebut sebagai "Direktori Dokumen Anda" dalam contoh kode.

## Impor Namespace

Di aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Buat Dokumen XPS Pertama

Mulailah dengan membuat dokumen XPS pertama menggunakan Aspose.Page. Dokumen ini akan berfungsi sebagai dasar untuk menambahkan mesin terbang berisi gambar.

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat Dokumen XPS pertama
XpsDocument doc1 = new XpsDocument();
```

## Langkah 2: Tambahkan Mesin Terbang ke Dokumen Pertama

Tambahkan mesin terbang ke dokumen pertama, tentukan font, ukuran, gaya, dan posisi.

```csharp
// Tambahkan mesin terbang ke dokumen pertama
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Langkah 3: Isi Glyph dengan Image Brush

Isi mesin terbang dengan kuas gambar, memanfaatkan gambar dari direktori data Anda.

```csharp
// Isi mesin terbang dengan kuas gambar
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Langkah 4: Buat Dokumen XPS Kedua

Sekarang, buat dokumen XPS kedua yang akan menggabungkan mesin terbang dari dokumen pertama.

```csharp
// Buat Dokumen XPS kedua
XpsDocument doc2 = new XpsDocument();
```

## Langkah 5: Tambahkan Glyph dengan Font dari Dokumen Pertama

Tambahkan mesin terbang ke dokumen kedua, menggunakan font dari dokumen pertama.

```csharp
// Tambahkan mesin terbang dengan font dari dokumen pertama ke dokumen kedua
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Langkah 6: Buat Kuas Gambar dari Isi Dokumen Pertama

Buat kuas gambar dari isi dokumen pertama dan gunakan itu untuk mengisi mesin terbang di dokumen kedua.

```csharp
// Buat kuas gambar dari isi dokumen pertama dan isi mesin terbang di dokumen kedua
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Langkah 7: Simpan Dokumen

Simpan dokumen XPS pertama dan kedua.

```csharp
// Simpan dokumen XPS pertama
doc1.Save(dataDir + "out1.xps");

// Simpan dokumen XPS kedua
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Kesimpulan

Selamat! Anda telah berhasil menambahkan mesin terbang berisi gambar dan memasukkan gambar asing menggunakan Aspose.Page untuk .NET. Tutorial ini memberikan landasan untuk meningkatkan kemampuan pemrosesan dokumen Anda, membuka kemungkinan baru untuk dokumen yang kreatif dan menarik secara visual.

## FAQ

### Q1: Dapatkah saya menggunakan format gambar yang berbeda untuk mengisi mesin terbang?

A1: Ya, Aspose.Page mendukung berbagai format gambar. Pastikan kompatibilitas dengan format gambar yang dipilih.

### Q2: Bagaimana cara menyesuaikan tampilan mesin terbang lebih lanjut?

A2: Jelajahi dokumentasi Aspose.Page untuk mengetahui properti dan metode tambahan untuk menyempurnakan tampilan mesin terbang.

### Q3: Apakah Aspose.Page cocok untuk menangani kumpulan dokumen besar?

A3: Aspose.Page dirancang untuk menangani kumpulan dokumen kecil dan besar secara efisien.

### Q4: Dapatkah saya menerapkan gaya yang berbeda pada masing-masing mesin terbang?

A4: Ya, Anda dapat menyesuaikan gaya untuk setiap mesin terbang secara mandiri, sehingga memberikan tingkat fleksibilitas yang tinggi.

### Q5: Apa keuntungan menggunakan Aspose.Page dibandingkan alat pemrosesan dokumen lainnya?

A5: Aspose.Page menawarkan serangkaian fitur lengkap, kinerja luar biasa, dan dokumentasi ekstensif, menjadikannya pilihan utama bagi banyak pengembang.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

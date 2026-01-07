---
date: 2026-01-07
description: Pelajari cara membuat dokumen XPS .NET menggunakan Aspose.Page. Panduan
  ini menunjukkan cara menambahkan glif yang diisi gambar dan gambar asing untuk visual
  dokumen yang lebih kaya.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Buat dokumen XPS .NET dengan Aspose.Page – Glyph Terisi Gambar & Gambar Asing
url: /id/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat XPS document .NET dengan Aspose.Page – Glyph Terisi Gambar & Gambar Asing

## Introduction

Jika Anda perlu **create XPS document .NET** aplikasi yang tampak halus dan profesional, Aspose.Page memberi Anda alat untuk menyematkan gambar langsung ke dalam glyph dan menggunakan kembali sumber daya grafis di seluruh dokumen. Dalam tutorial ini kami akan menunjukkan cara membuat dua file XPS, mengisi glyph dengan image brush, dan kemudian menggunakan kembali brush tersebut di dokumen kedua. Pada akhir tutorial Anda akan memahami mengapa pendekatan ini menghemat memori, menyederhanakan styling, dan membuka kemungkinan kreatif untuk laporan, faktur, atau konten yang dapat dicetak.

## Quick Answers
- **Apa yang dibahas dalam tutorial ini?** Menambahkan glyph terisi gambar dan menggunakan kembali glyph tersebut di seluruh dokumen XPS dengan Aspose.Page untuk .NET.  
- **Kata kunci utama apa yang ditargetkan?** `create xps document .net`.  
- **Prasyarat?** Lingkungan pengembangan .NET, Aspose.Page untuk .NET, dan folder untuk file XPS Anda.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk prototipe yang berfungsi.  
- **Bisakah saya menggunakan format gambar lain?** Ya – format apa pun yang didukung oleh `System.Drawing.Image` .NET.  

## Prerequisites

Sebelum menyelami kode, pastikan Anda memiliki hal-hal berikut siap:

- **Aspose.Page for .NET** – unduh perpustakaan terbaru dari [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio 2022 (atau IDE apa pun yang mendukung .NET 6+).  
- **Document Directory** – buat folder di mesin Anda yang akan menyimpan gambar input dan file XPS yang dihasilkan; kami akan menyebutnya **Your Document Directory** dalam potongan kode.

## Import Namespaces

Mulailah dengan mengimpor namespace yang diperlukan untuk bekerja dengan objek XPS dan utilitas menggambar.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step‑by‑Step Guide

### Step 1: Create the First XPS Document

Langkah 1: Buat Dokumen XPS Pertama

Kami memulai dengan membuat instansi dokumen XPS kosong yang akan menampung glyph terisi gambar.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Step 2: Add Glyphs to the First Document

Langkah 2: Tambahkan Glyph ke Dokumen Pertama

Selanjutnya, tambahkan sebuah glyph (karakter teks) yang nanti akan kami isi dengan image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 3: Fill Glyphs with an Image Brush

Langkah 3: Isi Glyph dengan Image Brush

Di sini kami membuat `ImageBrush` dari file TIFF yang terletak di direktori data kami dan menerapkannya ke glyph. Brush diatur ke tile mode sehingga gambar berulang jika area glyph melebihi ukuran gambar.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Step 4: Create the Second XPS Document

Langkah 4: Buat Dokumen XPS Kedua

Sekarang kami membuat dokumen XPS kedua yang akan menggunakan kembali gaya glyph dan image brush dari yang pertama.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Step 5: Add Glyphs with the Font from the First Document

Langkah 5: Tambahkan Glyph dengan Font dari Dokumen Pertama

Kami menambahkan glyph ke dokumen kedua, menggunakan kembali objek font yang sama persis dari dokumen pertama. Ini memastikan konsistensi visual di kedua file.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Step 6: Create an Image Brush from the Fill of the First Document

Langkah 6: Buat Image Brush dari Isi Dokumen Pertama

Alih-alih memuat gambar lagi, kami menggandakan brush dari `glyphs1` dan menetapkannya ke `glyphs2`. Ini menunjukkan bagaimana Anda dapat **create XPS document .NET** alur kerja yang berbagi sumber daya secara efisien.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Step 7: Save the Documents

Langkah 7: Simpan Dokumen

Akhirnya, simpan kedua file XPS ke disk. Anda sekarang dapat membukanya dengan viewer XPS apa pun untuk melihat efek glyph terisi gambar.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Why use image‑filled glyphs when you create XPS document .NET?

Mengapa menggunakan glyph terisi gambar saat Anda create XPS document .NET?

- **Visual Impact** – Mengubah teks biasa menjadi elemen kaya grafis tanpa meraster seluruh halaman.  
- **Resource Reuse** – Membagikan brush dan font di beberapa dokumen, mengurangi jejak memori.  
- **Flexibility** – Menyusun ubin, memperluas, atau memutar image brush untuk mencapai pola khusus atau branding.  

## Common Issues & Tips

Masalah Umum & Tips

- **File Path Errors** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`\` atau `/`) yang sesuai untuk OS Anda.  
- **Unsupported Image Formats** – Aspose.Page bekerja paling baik dengan TIFF, PNG, dan JPEG. Konversi format lain sebelum digunakan.  
- **TileMode Not Applied** – Pastikan Anda melakukan cast ke `XpsImageBrush` sebelum mengatur `TileMode`; jika tidak properti akan diabaikan.  

## Frequently Asked Questions

Pertanyaan yang Sering Diajukan

### Q1: Can I use different image formats for filling glyphs?

**A:** Ya, Aspose.Page mendukung TIFF, PNG, JPEG, BMP, dan GIF. Cukup berikan ekstensi file yang benar dalam pemanggilan `CreateImageBrush`.

### Q2: How can I customize the appearance of glyphs further?

**A:** Jelajahi properti tambahan pada `XpsGlyphs` seperti `Opacity`, `RenderTransform`, dan `Stroke` untuk menyempurnakan rendering.

### Q3: Is Aspose.Page suitable for handling large document sets?

**A:** Tentu saja. Perpustakaan ini dioptimalkan untuk skenario kinerja tinggi dan dapat memproses ribuan file XPS dalam pekerjaan batch.

### Q4: Can I apply different styles to individual glyphs?

**A:** Ya. Setiap instance `XpsGlyphs` dapat memiliki fill, stroke, dan transformasi masing‑masing, memberi Anda kontrol granular.

### Q5: What are the benefits of using Aspose.Page over other document processing tools?

**A:** Aspose.Page menawarkan API lengkap tanpa lisensi untuk pembuatan, manipulasi, dan konversi XPS, dengan dokumentasi yang luas serta dukungan 24/7.

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
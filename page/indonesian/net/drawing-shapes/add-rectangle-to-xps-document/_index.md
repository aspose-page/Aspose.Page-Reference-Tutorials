---
title: Tambahkan Rectangle ke Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Persegi Panjang ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Tingkatkan pembuatan dokumen dengan Aspose.Page untuk .NET. Pelajari cara menambahkan persegi panjang ke dokumen XPS dalam tutorial langkah demi langkah ini.
type: docs
weight: 13
url: /id/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Perkenalan

Aspose.Page untuk .NET adalah perpustakaan canggih yang menyediakan berbagai fitur untuk bekerja dengan dokumen XPS (Spesifikasi Kertas XML) dalam aplikasi .NET. Dalam tutorial ini, kita akan fokus menambahkan persegi panjang ke dokumen XPS menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah ini untuk menyempurnakan proses pembuatan dokumen Anda.

## Prasyarat

Sebelum memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Page for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/net/).

2. Direktori Dokumen: Siapkan direktori tempat Anda ingin menyimpan dokumen XPS Anda.

## Impor Namespace

Dalam aplikasi .NET Anda, sertakan namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Atur Direktori Dokumen

```csharp
// MantanMulai:3
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Langkah 2: Buat Dokumen XPS Baru

```csharp
// MantanMulai:4
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Langkah 3: Tambahkan Persegi Panjang

```csharp
// MantanMulai:5
// CMYK (biru) warna solid dengan guratan persegi panjang di kiri bawah
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## Langkah 4: Simpan Dokumen

```csharp
// MantanMulai:6
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Selamat! Anda telah berhasil menambahkan persegi panjang ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Aspose.Page untuk .NET menyederhanakan tugas manipulasi dokumen, memungkinkan pengembang membuat dan memodifikasi dokumen XPS dengan mudah. Panduan langkah demi langkah ini menunjukkan cara menambahkan persegi panjang ke dokumen XPS Anda, memberikan dasar yang kuat untuk eksplorasi lebih lanjut.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan semua aplikasi .NET?

A1: Ya, Aspose.Page dirancang untuk bekerja secara lancar dengan semua aplikasi .NET.

### Q2: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk .NET?

 A2: Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/net/).

### Q3: Dapatkah saya mencoba Aspose.Page untuk .NET secara gratis sebelum membeli?

 A3: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A4: Kunjungi[Link ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan izin sementara.

### Q5: Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan terkait Aspose.Page untuk .NET?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.
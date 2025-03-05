---
title: Tambahkan Teks ke Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Teks ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi panduan langkah demi langkah tentang menambahkan teks ke dokumen XPS menggunakan Aspose.Page untuk .NET. Tingkatkan proyek .NET Anda dengan mudah.
type: docs
weight: 13
url: /id/net/text-manipulation/add-text-to-xps-document/
---
## Perkenalan

Dalam dunia pengembangan .NET yang dinamis, Aspose.Page menonjol sebagai alat yang ampuh untuk bekerja dengan dokumen XPS. Menambahkan teks ke dokumen XPS adalah persyaratan umum, dan Aspose.Page menyederhanakan proses ini. Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Page untuk .NET untuk menambahkan teks ke dokumen XPS dengan lancar.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page. Anda dapat mengunduhnya dari[Aspose.Page untuk dokumentasi .NET](https://reference.aspose.com/page/net/).

-  Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET Anda. Jika Anda belum melakukannya, ikuti petunjuk instalasi yang disediakan di[dokumentasi](https://reference.aspose.com/page/net/).

- Direktori Dokumen: Buat direktori tempat Anda menyimpan dokumen Anda. Ganti "Direktori Dokumen Anda" di cuplikan kode yang disediakan dengan jalur sebenarnya.

Sekarang, mari beralih ke panduan langkah demi langkah.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk memulai proyek kita:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Buat Dokumen XPS Baru

Untuk mulai bekerja dengan Aspose.Page, buat dokumen XPS baru. Ini akan menjadi kanvas tempat kita menambahkan teks.

```csharp
// MantanMulai:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Langkah 2: Buat Kuas untuk Teks

Sekarang, mari buat kuas untuk menentukan warna teks. Dalam contoh ini, kita menggunakan kuas warna hitam.

```csharp
// MantanMulai:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Langkah 3: Tambahkan Mesin Terbang ke Dokumen

Mesin terbang mewakili teks dalam dokumen XPS. Tambahkan mesin terbang ke dokumen dengan font, ukuran, gaya, dan posisi yang diinginkan.

```csharp
// MantanMulai:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Langkah 4: Simpan Dokumen XPS yang Dihasilkan

Terakhir, simpan dokumen XPS dengan teks tambahan ke direktori yang Anda tentukan.

```csharp
// MantanMulai:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Dengan mengikuti langkah-langkah sederhana ini, Anda telah berhasil menambahkan teks ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Kesimpulannya, Aspose.Page untuk .NET memberikan solusi langsung untuk menambahkan teks ke dokumen XPS di proyek .NET Anda. Kesederhanaan perpustakaan, dipadukan dengan fitur-fiturnya yang canggih, menjadikannya alat yang sangat berharga untuk manipulasi dokumen.

## Pertanyaan yang Sering Diajukan

### Q1: Dapatkah saya menyesuaikan font dan ukuran teks yang ditambahkan?

 A1: Ya, Anda memiliki kendali penuh atas font dan ukurannya. Sesuaikan parameter di`AddGlyphs` metode yang sesuai.

### Q2: Apakah Aspose.Page kompatibel dengan .NET Core?

A2: Tentu saja! Aspose.Page mendukung .NET Core, memastikan kompatibilitas dengan teknologi .NET terbaru.

### Q3: Apakah ada persyaratan lisensi untuk menggunakan Aspose.Page?

 A3: Ya, Anda memerlukan lisensi yang valid. Jelajahi opsi lisensi[Di Sini](https://purchase.aspose.com/buy).

### Q4: Bagaimana saya bisa mendapatkan dukungan atau mencari bantuan?

 A4: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk berhubungan dengan masyarakat dan mendapatkan bantuan.

### Q5: Apakah tersedia uji coba gratis?

 A5: Tentu saja! Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
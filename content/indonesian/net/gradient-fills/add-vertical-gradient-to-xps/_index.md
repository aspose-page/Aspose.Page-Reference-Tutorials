---
title: Tambahkan Gradien Vertikal ke XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Gradien Vertikal ke XPS
second_title: Aspose.Halaman .NET API
description: Pelajari cara menyempurnakan dokumen XPS dengan gradien vertikal menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 15
url: /id/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Perkenalan

Selamat datang di tutorial langkah demi langkah tentang cara menambahkan gradien vertikal ke dokumen XPS menggunakan Aspose.Page untuk .NET. Aspose.Page adalah API canggih yang memungkinkan Anda bekerja dengan file XPS (Spesifikasi Kertas XML) di aplikasi .NET Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan dokumen XPS baru, menambahkan gradien vertikal ke jalur, dan menyimpan hasilnya.

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Page for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET dengan IDE pilihan Anda, seperti Visual Studio.

Sekarang, mari kita mulai menambahkan gradien vertikal ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Impor Namespace

Dalam aplikasi .NET Anda, sertakan namespace yang diperlukan untuk mengakses kelas dan metode Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Sebelum memulai, tetapkan jalur ke direktori dokumen tempat Anda ingin menyimpan dokumen XPS yang dihasilkan.

```csharp
// MantanMulai:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Langkah 2: Buat Dokumen XPS Baru

Inisialisasi dokumen XPS baru menggunakan kode berikut:

```csharp
// MantanMulai:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Langkah 3: Tentukan Perhentian Gradien

Buat daftar perhentian gradien, tentukan warna dan posisi untuk setiap perhentian. Dalam contoh ini, kita mendefinisikan gradien vertikal dengan lima perhentian.

```csharp
// MantanMulai:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Langkah 4: Buat Jalur dengan Gradien

Tentukan jalur dengan menentukan geometrinya dan terapkan kuas gradien linier padanya.

```csharp
// MantanMulai:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Langkah 5: Simpan Dokumen XPS yang Dihasilkan

Simpan dokumen XPS yang dimodifikasi ke direktori yang Anda tentukan.

```csharp
// MantanMulai:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Selamat! Anda telah berhasil menambahkan gradien vertikal ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara memanfaatkan Aspose.Page untuk .NET guna menyempurnakan dokumen XPS dengan gradien vertikal. Aspose.Page menyederhanakan tugas-tugas kompleks, memberikan pengembang cara yang mulus untuk memanipulasi file XPS dalam aplikasi .NET mereka.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan Visual Studio 2019?

A1: Ya, Aspose.Page kompatibel dengan Visual Studio 2019. Pastikan Anda menginstal versi perpustakaan yang benar.

### Q2: Dapatkah saya menggunakan Aspose.Page untuk proyek komersial?

 A2: Ya, Aspose.Page dapat digunakan untuk proyek komersial. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk mengeksplorasi opsi lisensi.

### Q3: Apakah tersedia uji coba gratis?

 A3: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Page[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya dapat menemukan dokumentasi Aspose.Page?

 A4: Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/net/).

### Q5: Bagaimana saya bisa mendapatkan dukungan atau mengajukan pertanyaan?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.
---
title: Tambahkan Circle Ellipse ke Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Lingkaran Ellipse ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Sempurnakan dokumen XPS dengan gradien radial yang dinamis menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk efek visual yang menakjubkan.
type: docs
weight: 11
url: /id/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Perkenalan

Membuat dokumen XPS yang menarik secara visual merupakan persyaratan umum dalam berbagai aplikasi. Aspose.Page untuk .NET menyediakan serangkaian fitur canggih untuk memanipulasi dokumen XPS secara efisien. Dalam tutorial ini, kita akan fokus menambahkan elips lingkaran ke dokumen XPS menggunakan Aspose.Page untuk .NET. Ikuti langkah-langkah di bawah ini untuk menyempurnakan dokumen XPS Anda dengan gradien radial yang cerah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Menginstal Aspose.Page untuk perpustakaan .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).
- Lingkungan pengembangan, sebaiknya Visual Studio atau alat pengembangan .NET lainnya.
- Pengetahuan dasar tentang pemrograman C#.

## Impor Namespace

Untuk memulai, sertakan namespace yang diperlukan dalam kode C# Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah:

## Langkah 1: Siapkan Dokumen

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```

Di sini, kami menginisialisasi dokumen XPS baru menggunakan Aspose.Page untuk .NET.

## Langkah 2: Tentukan Elips Gradien Radial

```csharp
// Gradien radial membelai elips di kiri bawah
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Langkah ini melibatkan pendefinisian elips gradien radial dengan berbagai penghentian warna.

## Langkah 3: Atur Kuas Gradien Radial

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Di sini, kita mengatur goresan elips menjadi kuas gradien radial, menyediakan parameter yang diperlukan.

## Langkah 4: Sesuaikan Ketebalan Stroke

```csharp
path.StrokeThickness = 12f;
```

Langkah ini melibatkan penyesuaian ketebalan goresan untuk visualisasi yang lebih baik.

## Langkah 5: Simpan Dokumen XPS yang Dihasilkan

```csharp
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Terakhir, simpan dokumen XPS yang dimodifikasi ke lokasi yang diinginkan.

## Kesimpulan

Selamat! Anda telah berhasil menambahkan elips lingkaran dengan gradien radial ke dokumen XPS Anda menggunakan Aspose.Page untuk .NET. Bereksperimenlah dengan berbagai parameter dan warna untuk mendapatkan efek visual yang diinginkan dalam dokumen Anda.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

A1: Aspose.Page untuk .NET secara khusus berhubungan dengan manipulasi dokumen XPS. Untuk format lain, pertimbangkan untuk menggunakan pustaka Aspose terkait.

### Q2: Apakah lisensi sementara tersedia untuk tujuan pengujian?

 A2: Ya, Anda bisa mendapatkan lisensi sementara untuk pengujian dengan mengunjungi[Link ini](https://purchase.aspose.com/temporary-license/).

### Q3: Di mana saya dapat menemukan bantuan dan diskusi tambahan?

 A3: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.

### Q4: Apakah ada contoh dokumen yang tersedia untuk referensi?

 A4: Jelajahi[dokumentasi](https://reference.aspose.com/page/net/) untuk contoh dan pedoman yang komprehensif.

### Q5: Bisakah saya membeli Aspose.Page untuk .NET?

 A5: Ya, Anda dapat membeli perpustakaannya[Di Sini](https://purchase.aspose.com/buy).
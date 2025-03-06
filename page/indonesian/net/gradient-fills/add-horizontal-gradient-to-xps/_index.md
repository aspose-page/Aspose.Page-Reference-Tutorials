---
title: Tambahkan Gradien Horizontal ke XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Gradien Horisontal ke XPS
second_title: Aspose.Halaman .NET API
description: Pelajari cara menambahkan gradien horizontal yang menakjubkan ke dokumen XPS Anda menggunakan Aspose.Page untuk .NET. Tingkatkan daya tarik visual dengan mudah.
weight: 13
url: /id/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Horizontal ke XPS dengan Aspose.Page untuk .NET

## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara menyempurnakan dokumen XPS dengan menambahkan gradien horizontal menggunakan Aspose.Page untuk .NET. Aspose.Page untuk .NET adalah perpustakaan canggih yang menyediakan penanganan dokumen XPS (Spesifikasi Kertas XML) dengan lancar dalam aplikasi .NET. Menambahkan gradien dapat memberikan daya tarik visual pada dokumen Anda, dan panduan ini akan memandu Anda melalui proses langkah demi langkah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Page for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[Aspose.Page untuk Dokumentasi .NET](https://reference.aspose.com/page/net/).

2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai, termasuk editor kode seperti Visual Studio.

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek Anda. Namespace berikut penting untuk bekerja dengan Aspose.Page untuk .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah.

## Langkah 1: Tetapkan Jalur Direktori Dokumen

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

## Langkah 3: Inisialisasi Gradient Stop

```csharp
// MantanMulai:5
// Inisialisasi Daftar XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Langkah 4: Buat Jalur Baru

```csharp
// MantanMulai:6
//Buat jalur baru dengan mendefinisikan geometri dalam bentuk singkatan
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Langkah 5: Simpan Dokumen XPS yang Dihasilkan

```csharp
// MantanMulai:7
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Sekarang, Anda telah berhasil menambahkan gradien horizontal ke dokumen XPS Anda menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Menyempurnakan dokumen XPS Anda dengan gradien tidak hanya meningkatkan daya tarik visualnya tetapi juga memberikan pengalaman pengguna yang lebih menarik. Aspose.Page untuk .NET menyederhanakan proses ini, memungkinkan Anda mencapai hasil profesional dengan mudah.

## FAQ

### Q1: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk .NET?

 A1: Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/page/net/).

### Q2: Bagaimana cara mengunduh Aspose.Page untuk .NET?

 A2: Anda dapat mengunduh perpustakaan dari[Aspose.Page untuk halaman unduh .NET](https://releases.aspose.com/page/net/).

### Q3: Di mana saya dapat membeli Aspose.Page untuk .NET?

 A3: Anda dapat membeli Aspose.Page untuk .NET dari[halaman pembelian](https://purchase.aspose.com/buy).

### Q4: Apakah tersedia uji coba gratis?

 A4: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A5: Anda dapat memperoleh lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

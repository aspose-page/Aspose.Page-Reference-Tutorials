---
title: Terapkan Grid Visual Brush dengan Aspose.Page untuk .NET
linktitle: Terapkan Kuas Visual Kotak
second_title: Aspose.Halaman .NET API
description: Jelajahi dunia pemrosesan dokumen yang dinamis di .NET dengan Aspose.Page. Pelajari cara menerapkan Grid Visual Brush untuk dokumen visual yang menakjubkan.
weight: 10
url: /id/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Terapkan Grid Visual Brush dengan Aspose.Page untuk .NET

## Perkenalan

Dalam dunia pengembangan .NET, Aspose.Page menonjol sebagai alat yang ampuh untuk menangani tugas pemrosesan dokumen. Salah satu fitur menarik yang ditawarkannya adalah kemampuan untuk menerapkan Grid Visual Brush, menghadirkan dimensi baru pada dokumen Anda. Tutorial ini akan memandu Anda melalui proses penerapan Kuas Visual Magenta Grid langkah demi langkah menggunakan Aspose.Page untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET: Pastikan Anda telah menginstal dan mengatur perpustakaan di lingkungan .NET Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET yang berfungsi, dan pemahaman dasar tentang pemrograman C#.

- Direktori Dokumen: Buat direktori untuk dokumen Anda tempat file yang diproses akan disimpan.

## Impor Namespace

Dalam kode C#, Anda perlu mengimpor namespace yang diperlukan untuk memanfaatkan fitur Aspose.Page secara efektif:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah.

## Langkah 1: Inisialisasi XpsDocument

```csharp
// MantanMulai:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

 Di sini, kita membuat sebuah instance dari`XpsDocument` untuk bekerja dengan dokumen XPS.

## Langkah 2: Buat Geometri Grid Magenta

```csharp
// MantanMulai:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Langkah ini melibatkan pembuatan geometri jalur untuk grid magenta.

## Langkah 3: Desain VisualBrush Kotak Magenta

```csharp
// MantanMulai:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Di sini, kami mendesain aspek visual grid magenta menggunakan grafik vektor.

## Langkah 4: Terapkan VisualBrush ke Grid

```csharp
// MantanMulai:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Terapkan kuas visual ke jalur kisi, pastikan ubinnya tepat.

## Langkah 5: Tambahkan Grid ke Kanvas

```csharp
// MantanMulai:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Tambahkan kisi ke kanvas, tentukan transformasi apa pun yang diperlukan.

## Langkah 6: Tingkatkan dengan Red Rectangle

```csharp
// MantanMulai:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// ExEnd:8
```

Tingkatkan daya tarik visual dengan menambahkan persegi panjang transparan berwarna merah.

## Langkah 7: Simpan Dokumen

```csharp
// MantanMulai:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Simpan dokumen XPS yang dihasilkan di direktori yang Anda tentukan.

## Kesimpulan

Selamat! Anda telah berhasil menerapkan Grid Visual Brush ke dokumen Anda menggunakan Aspose.Page untuk .NET. Teknik ini dapat menyempurnakan elemen visual dokumen Anda secara signifikan, memberikan pengalaman pengguna yang dinamis dan menarik.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET di aplikasi web dan desktop?

A1: Ya, Aspose.Page untuk .NET serbaguna dan dapat digunakan dalam berbagai jenis aplikasi.

### Q2: Apakah ada versi uji coba yang tersedia sebelum membeli?

 A2: Tentu saja, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dukungan tambahan atau diskusi komunitas?

 A3: Kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk diskusi dan dukungan.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A4: Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Dokumentasi lain apa yang tersedia untuk Aspose.Page untuk .NET?

 A5: Jelajahi dokumentasi yang komprehensif[Di Sini](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

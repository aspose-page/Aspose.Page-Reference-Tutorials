---
title: Memotong XPS dengan Aspose.Page untuk .NET
linktitle: Memotong XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi kekuatan Aspose.Page untuk .NET dalam panduan langkah demi langkah tentang pemotongan dokumen XPS. Buat, manipulasi, dan simpan file XPS dengan mudah.
weight: 11
url: /id/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Memotong XPS dengan Aspose.Page untuk .NET

## Perkenalan

Selamat datang di tutorial komprehensif tentang Clipping XPS menggunakan Aspose.Page untuk .NET! Dalam panduan ini, kami akan memandu Anda melalui proses membuat, memanipulasi, dan menyimpan dokumen XPS menggunakan Aspose.Page untuk .NET. XPS, atau Spesifikasi Kertas XML, adalah format dokumen terstandarisasi dan terbuka, dan Aspose.Page untuk .NET menyediakan alat canggih untuk bekerja dengan dokumen XPS di aplikasi .NET Anda.

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:

- Visual Studio diinstal pada mesin Anda.
-  Aspose.Page untuk perpustakaan .NET ditambahkan ke proyek Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/net/).
- Pengetahuan dasar bahasa pemrograman C#.

## Impor Namespace

Untuk menggunakan Aspose.Page untuk fungsionalitas .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah ini:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang, mari kita uraikan kode contoh yang Anda berikan menjadi beberapa langkah.

## Langkah 1: Tetapkan jalur direktori dokumen.

```csharp
string dataDir = "Your Document Directory";
```

Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Buat Dokumen XPS baru.

```csharp
XpsDocument doc = new XpsDocument();
```

Ini akan membuat dokumen XPS baru yang akan Anda kerjakan.

## Langkah 3: Buat kanvas utama.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Langkah ini membuat kanvas utama, yang umum untuk semua elemen halaman.

## Langkah 4: Atur offset kiri dan atas di kanvas utama.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Sesuaikan offset kiri dan atas sesuai kebutuhan Anda.

## Langkah 5: Buat geometri jalur persegi panjang.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Ini menciptakan geometri jalur untuk persegi panjang.

## Langkah 6: Buat isian untuk persegi panjang.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Tentukan warna isian untuk persegi panjang.

## Langkah 7: Tambahkan kanvas lain dengan klip ke kanvas utama.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Langkah ini menambahkan kanvas lain ke kanvas utama.

## Langkah 8: Buat geometri lingkaran untuk klip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Ini menciptakan geometri klip melingkar dan menerapkannya pada kanvas kedua.

## Langkah 9: Buat persegi panjang di kanvas kedua dan isi.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Langkah ini membuat persegi panjang di kanvas kedua dan mengisinya.

## Langkah 10: Tambahkan kanvas kedua dengan persegi panjang yang digores ke kanvas utama.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Ini menambahkan kanvas lain ke kanvas utama.

## Langkah 11: Buat persegi panjang di kanvas ketiga dan coretlah.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Ini menciptakan sebuah persegi panjang di kanvas ketiga dan menerapkan stroke padanya.

## Langkah 12: Simpan dokumen XPS yang dihasilkan.

```csharp
doc.Save(dataDir + "output2.xps");
```

Ini menyimpan dokumen XPS ke direktori yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara membuat klip XPS menggunakan Aspose.Page untuk .NET. Panduan ini memberikan panduan rinci tentang langkah-langkah yang terlibat dalam proses tersebut.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

A1: Aspose.Page untuk .NET terutama berfokus pada dokumen XPS, namun Aspose menyediakan pustaka lain untuk berbagai format dokumen.

### Q2: Apakah Aspose.Page untuk .NET cocok untuk pemula?

A2: Ya, Aspose.Page untuk .NET dirancang agar mudah digunakan, dan pemula dapat dengan cepat memahami fungsinya dengan dokumentasi yang tepat.

### Q3: Di mana saya dapat menemukan lebih banyak contoh dan sumber daya?

 A3: Kunjungi[dokumentasi](https://reference.aspose.com/page/net/) Dan[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk sumber daya dan contoh yang luas.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A4: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk .NET?

 A5: Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

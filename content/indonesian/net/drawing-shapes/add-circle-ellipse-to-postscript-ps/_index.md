---
title: Tambahkan Circle Ellipse ke PostScript (PS) dengan Aspose.Page
linktitle: Tambahkan Lingkaran Ellipse ke PostScript (PS)
second_title: Aspose.Halaman .NET API
description: Pelajari cara menambahkan elips lingkaran dengan mudah ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 10
url: /id/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Perkenalan

Selamat datang di tutorial komprehensif tentang menambahkan elips lingkaran ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Aspose.Page adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan PostScript dan format dokumen lainnya dengan lancar. Dalam panduan ini, kami akan memandu Anda melalui proses memasukkan elips lingkaran ke dalam dokumen PS Anda dengan mudah.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page untuk .NET Library: Unduh dan instal perpustakaan Aspose.Page untuk .NET dari[Di Sini](https://releases.aspose.com/page/net/).

2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi di mesin Anda.

Sekarang, mari kita mulai dengan panduan langkah demi langkah.

## Impor Namespace

Pada langkah pertama, Anda perlu mengimpor namespace yang diperlukan untuk membuat fungsionalitas Aspose.Page tersedia dalam kode Anda.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memandu Anda melalui proses menambahkan elips lingkaran ke dokumen PostScript.

## Langkah 1: Atur Direktori Dokumen

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
```

Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Buat Aliran Output untuk Dokumen PostScript

```csharp
//Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Di sini, FileStream dibuat untuk menulis dokumen PostScript, dan mode file diatur untuk membuat file baru.

## Langkah 3: Buat Opsi Simpan dan Dokumen PS

```csharp
//Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();

// Buat Dokumen PS 1 halaman baru
PsDocument document = new PsDocument(outPsStream, options, false);
```

Langkah ini melibatkan pembuatan opsi penyimpanan dengan ukuran A4 dan menginisialisasi Dokumen PS 1 halaman baru.

## Langkah 4: Buat Jalur Grafik untuk Ellipse Pertama

```csharp
//Buat jalur grafis dari elips pertama
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Jalur grafis dibuat untuk elips pertama, menentukan posisi dan dimensinya.

## Langkah 5: Atur Cat dan Isi Ellipse

```csharp
//Atur cat
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Isi elips
document.Fill(path);
```

Di sini, cat diatur, dan elips pertama diisi dengan warna yang ditentukan.

## Langkah 6: Buat Jalur Grafik untuk Ellipse Kedua

```csharp
//Buat jalur grafis dari elips kedua
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Demikian pula, jalur grafis dibuat untuk elips kedua, yang menentukan posisi dan dimensinya.

## Langkah 7: Atur Stroke dan Gambar Ellipse

```csharp
//Atur pukulan
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Goresan (garis besar) elips
document.Draw(path);
```

Pada langkah ini, goresan diatur, dan elips kedua digariskan dengan warna dan ketebalan garis yang ditentukan.

## Langkah 8: Tutup Halaman Saat Ini dan Simpan Dokumen

```csharp
//Tutup halaman saat ini
document.ClosePage();

//Simpan dokumennya
document.Save();
```

Akhirnya, halaman saat ini ditutup, dan seluruh dokumen disimpan, menyelesaikan prosesnya.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menambahkan elips lingkaran ke dokumen PostScript menggunakan Aspose.Page untuk .NET. Tutorial ini memberikan panduan langkah demi langkah yang mendetail untuk membantu Anda mengintegrasikan fungsi ini ke dalam proyek Anda dengan lancar.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

 A1: Aspose.Page terutama berfokus pada PostScript, tetapi Aspose menyediakan perpustakaan lain untuk berbagai format dokumen. Periksalah[Asumsikan dokumentasi](https://reference.aspose.com/page/net/) untuk lebih jelasnya.

### Q2: Di mana saya bisa mendapatkan dukungan tambahan dan diskusi komunitas?

 A2: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk diskusi dan dukungan komunitas.

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk .NET?

 A3: Ya, Anda dapat mengakses[uji coba gratis](https://releases.aspose.com/)untuk menjelajahi fitur Aspose.Page untuk .NET.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?

 A4: Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

### Q5: Di mana saya dapat membeli Aspose.Page untuk .NET?

 A5: Beli Aspose.Page untuk .NET dari[halaman beli](https://purchase.aspose.com/buy).
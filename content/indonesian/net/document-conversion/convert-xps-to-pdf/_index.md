---
title: Konversi XPS ke PDF dengan Aspose.Page untuk .NET
linktitle: Konversi XPS ke PDF
second_title: Aspose.Halaman .NET API
description: Konversi XPS ke PDF dengan mudah di .NET dengan Aspose.Page. Unduh perpustakaan, jelajahi dokumentasi, dan dapatkan uji coba gratis.
type: docs
weight: 11
url: /id/net/document-conversion/convert-xps-to-pdf/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari proses mengonversi dokumen XPS (Spesifikasi Kertas XML) ke PDF (Portable Document Format) menggunakan perpustakaan Aspose.Page untuk .NET yang kuat. Aspose.Page untuk .NET menyediakan serangkaian fitur canggih untuk bekerja dengan file XPS, memungkinkan pengembang mengonversinya dengan mulus ke format PDF dengan berbagai opsi penyesuaian.

## Prasyarat

Sebelum kita memulai perjalanan konversi ini, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Page for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[Aspose.Dokumentasi halaman](https://reference.aspose.com/page/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET dengan Visual Studio atau IDE lain yang kompatibel.

- Dokumen XPS: Siapkan dokumen XPS yang ingin Anda konversi ke PDF. Ini bisa berupa contoh file XPS Anda yang disimpan di direktori yang ditentukan.

## Impor Namespace

Sebelum mendalami kodenya, mari impor namespace yang diperlukan agar fungsi Aspose.Page for .NET dapat diakses dalam kode kita:

```csharp
using Aspose.Page.XPS;
```

## Langkah 1: Inisialisasi Direktori Dokumen

```csharp
string dataDir = "Your Document Directory";
```

Ganti "Direktori Dokumen Anda" dengan jalur ke direktori yang berisi dokumen XPS Anda.

## Langkah 2: Inisialisasi Aliran PDF dan XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Buka aliran untuk file PDF keluaran dan file XPS masukan. Pastikan Anda telah menetapkan jalur file yang sesuai.

## Langkah 3: Muat Dokumen XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Muat dokumen XPS menggunakan perpustakaan Aspose.Page untuk .NET.

## Langkah 4: Inisialisasi Opsi Penyimpanan PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Siapkan opsi penyimpanan PDF, termasuk parameter seperti tingkat kualitas JPEG, kompresi gambar, kompresi teks, dan nomor halaman tertentu untuk disertakan.

## Langkah 5: Buat Perangkat Rendering PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Buat perangkat rendering untuk format PDF menggunakan perpustakaan Aspose.Page untuk .NET.

## Langkah 6: Simpan Dokumen ke PDF

```csharp
document.Save(device, options);
```

Simpan dokumen XPS ke PDF menggunakan perangkat dan opsi rendering yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mengonversi dokumen XPS ke PDF menggunakan Aspose.Page untuk .NET. Pustaka serbaguna ini memberi pengembang seperangkat alat canggih untuk menangani berbagai format dokumen dengan mudah.

## FAQ

### Q1: Bisakah saya mengonversi beberapa file XPS menjadi satu PDF menggunakan Aspose.Page untuk .NET?

A1: Ya, Anda dapat mengulang beberapa file XPS dan mengikuti langkah yang sama untuk menggabungkannya menjadi satu PDF.

### Q2: Apakah ada format output lain yang didukung oleh Aspose.Page untuk .NET?

A2: Ya, Aspose.Page untuk .NET mendukung berbagai format output, termasuk TIFF, JPEG, PNG, dan banyak lagi.

### Q3: Bagaimana cara menyesuaikan tampilan dokumen PDF yang dikonversi?

A3: Anda dapat mengubah parameter objek opsi, seperti kompresi gambar dan kompresi teks, untuk mencapai tampilan yang diinginkan.

### Q4: Apakah ada versi uji coba yang tersedia untuk Aspose.Page untuk .NET?

 A4: Ya, Anda dapat menjelajahi kemampuan Aspose.Page untuk .NET dengan mendapatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Q5: Di mana saya bisa mendapatkan dukungan komunitas untuk Aspose.Page untuk .NET?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk diskusi dan dukungan komunitas.
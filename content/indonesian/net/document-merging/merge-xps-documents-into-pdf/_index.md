---
title: Gabungkan Dokumen XPS ke PDF dengan Aspose.Page untuk .NET
linktitle: Gabungkan Dokumen XPS ke dalam PDF
second_title: Aspose.Halaman .NET API
description: Gabungkan dokumen XPS dengan mudah menjadi PDF berkualitas tinggi menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk pengalaman konversi dokumen yang lancar.
type: docs
weight: 11
url: /id/net/document-merging/merge-xps-documents-into-pdf/
---
## Perkenalan

Dalam lanskap pemrosesan dokumen yang terus berkembang, Aspose.Page untuk .NET muncul sebagai alat canggih untuk menggabungkan dokumen XPS ke dalam format PDF dengan lancar. Tutorial ini akan memandu Anda melalui prosesnya, menguraikan setiap langkah untuk memastikan eksekusi yang lancar dan efektif.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).

- File Dokumen: Miliki dokumen XPS (`input.xps`) siap di direktori yang Anda tentukan.

## Impor Namespace

Dalam proyek .NET Anda, sertakan namespace yang diperlukan untuk bekerja dengan Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan metode yang diperlukan untuk konversi dokumen.

## Langkah 1: Inisialisasi Aliran

```csharp
// MantanMulai:3
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Inisialisasi aliran keluaran PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Inisialisasi aliran input XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Langkah ini melibatkan pengaturan aliran input dan output untuk file XPS dan PDF. Pastikan jalur dan nama file yang digunakan benar.

## Langkah 2: Muat Dokumen XPS

```csharp
// MantanMulai:4
// Muat dokumen XPS dari aliran
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// atau memuat dokumen XPS langsung dari file. Tidak diperlukan xpsStream.
//Dokumen XpsDocument = XpsDocument baru (inputFileName, XpsLoadOptions baru ());
// ExEnd:4
```

 Di sini, kami memuat dokumen XPS ke dalam`XpsDocument` objek, mempersiapkannya untuk diproses lebih lanjut.

## Langkah 3: Inisialisasi Opsi Simpan

```csharp
// MantanMulai:5
// Inisialisasi objek opsi dengan parameter yang diperlukan.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

 Sesuaikan`PdfSaveOptions` objek berdasarkan preferensi Anda, menentukan parameter seperti kompresi gambar, kompresi teks, dan nomor halaman.

## Langkah 4: Buat Perangkat Rendering

```csharp
// MantanMulai:6
// Buat perangkat rendering untuk format PDF
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

 Itu`PdfDevice` adalah alat yang bertanggung jawab untuk merender dokumen XPS ke dalam format PDF.

## Langkah 5: Simpan Dokumen

```csharp
// MantanMulai:7
document.Save(device, options);
// ExEnd:7
```

Terakhir, simpan dokumen menggunakan perangkat rendering dan opsi yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil menggabungkan dokumen XPS ke PDF menggunakan Aspose.Page untuk .NET. Proses yang mulus ini memastikan pelestarian kualitas dan format dokumen.

## FAQ

### Q1: Bisakah saya menggabungkan beberapa file XPS menjadi satu PDF?

 A1: Ya, Anda bisa. Cukup sesuaikan`PageNumbers` parameter di`PdfSaveOptions` untuk memasukkan halaman yang diinginkan dari file XPS yang berbeda.

### Q2: Apakah lisensi sementara tersedia untuk Aspose.Page untuk .NET?

 A2: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.

### Q3: Apakah ada batasan ukuran file saat menggunakan Aspose.Page untuk konversi dokumen?

A3: Aspose.Page untuk .NET tidak menerapkan batasan ketat pada ukuran file, namun performa optimal dicapai dengan ukuran file yang wajar.

### Q4: Dapatkah saya menyesuaikan output PDF lebih lanjut, seperti menambahkan tanda air atau anotasi?

A4: Ya, Aspose.Page untuk .NET menyediakan fitur ekstensif untuk manipulasi PDF. Periksa dokumentasi untuk opsi penyesuaian lanjutan.

### Q5: Apakah Aspose.Page untuk .NET mendukung pengembangan lintas platform?

A5: Ya, Aspose.Page untuk .NET dirancang untuk bekerja dengan lancar di berbagai platform.
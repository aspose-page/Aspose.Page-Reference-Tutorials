---
title: Tambahkan Gambar ke Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Gambar ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi integrasi gambar yang lancar ke dalam dokumen XPS dengan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk pengalaman pengembangan yang lancar.
weight: 11
url: /id/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gambar ke Dokumen XPS dengan Aspose.Page untuk .NET

## Perkenalan

Dalam dunia pengembangan .NET, memasukkan gambar ke dalam dokumen XPS adalah persyaratan umum. Aspose.Page untuk .NET menyederhanakan proses ini, menawarkan perangkat canggih untuk memanipulasi dan menyempurnakan dokumen XPS dengan mudah. Tutorial ini akan memandu Anda melalui langkah-langkah menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page untuk .NET Library: Unduh dan instal perpustakaan dari[Dokumentasi Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio.

3. Contoh Gambar: Miliki contoh file gambar (misalnya, "QL_logo_color.tif") yang ingin Anda tambahkan ke dokumen XPS.

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan ke proyek .NET Anda. Namespace ini sangat penting untuk memanfaatkan fitur yang disediakan oleh Aspose.Page untuk .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Atur Direktori Dokumen

Mulailah dengan menentukan jalur ke direktori dokumen Anda. Langkah ini memastikan bahwa proyek Anda mengetahui di mana menemukan dan menyimpan file.

```csharp
// MantanMulai:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

## Langkah 2: Buat Dokumen XPS

Buat dokumen XPS baru menggunakan Aspose.Page untuk .NET.

```csharp
// MantanMulai:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

## Langkah 3: Tambahkan Gambar ke Dokumen XPS

Sekarang, mari tambahkan gambar ke dokumen XPS. Dalam contoh ini, kita akan menggunakan contoh gambar bernama "QL_logo_color.tif".

```csharp
// MantanMulai:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

## Langkah 4: Simpan Dokumen XPS yang Dihasilkan

Simpan dokumen XPS dengan gambar yang ditambahkan.

```csharp
// MantanMulai:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Sekarang Anda telah berhasil menambahkan gambar ke dokumen XPS menggunakan Aspose.Page untuk .NET!

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memanfaatkan Aspose.Page untuk .NET untuk menggabungkan gambar ke dalam dokumen XPS dengan lancar. Panduan langkah demi langkah ini memastikan proses integrasi yang lancar, meningkatkan kemampuan pengembangan .NET Anda.

## FAQ

### Q1: Apakah Aspose.Page untuk .NET kompatibel dengan versi kerangka .NET terbaru?

 A1: Aspose.Page untuk .NET dirancang agar kompatibel dengan berbagai versi kerangka .NET, termasuk rilis terbaru. Mengacu kepada[dokumentasi](https://reference.aspose.com/page/net/) untuk rincian spesifik.

### Q2: Bisakah saya menggunakan Aspose.Page untuk .NET di lingkungan Windows dan Linux?

A2: Ya, Aspose.Page untuk .NET tidak bergantung pada platform, sehingga cocok untuk digunakan di lingkungan Windows dan Linux.

### Q3: Apakah ada opsi lisensi untuk Aspose.Page untuk .NET?

 A3: Ya, Anda dapat menjelajahi opsi lisensi dan melakukan pembelian[Di Sini](https://purchase.aspose.com/buy).

### Q4: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk .NET?

 A4: Ya, Anda dapat mencoba Aspose.Page untuk .NET secara gratis dengan mengakses[uji coba gratis](https://releases.aspose.com/).

### Q5: Di mana saya dapat mencari bantuan atau terlibat dengan komunitas Aspose.Page untuk .NET?

 A5: Kunjungi[Aspose.Page untuk forum .NET](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan dukungan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

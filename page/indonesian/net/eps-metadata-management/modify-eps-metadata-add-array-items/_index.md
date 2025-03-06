---
title: Tambahkan Item Array dengan Aspose.Page
linktitle: Tambahkan Item Array
second_title: Aspose.Halaman .NET API
description: Jelajahi cara menambahkan item array dalam file EPS menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk manipulasi dokumen yang lancar.
weight: 11
url: /id/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Item Array dengan Aspose.Page

## Perkenalan

Dalam bidang manipulasi dan pemrosesan dokumen di .NET, Aspose.Page menonjol sebagai alat yang ampuh. Di antara banyak kemampuannya, menangani item array dalam file EPS adalah persyaratan umum. Dalam tutorial ini, kita akan menjelajahi proses langkah demi langkah menambahkan item array menggunakan Aspose.Page di lingkungan .NET. Baik Anda seorang pengembang berpengalaman atau pendatang baru, panduan ini akan memandu Anda melalui proses dengan jelas dan tepat.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar tentang pemrograman .NET.
-  Aspose.Page untuk .NET diinstal. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).
- Editor kode, seperti Visual Studio, untuk mengikuti contohnya.

## Impor Namespace

Dalam proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Tambahkan baris berikut di awal kode Anda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Namespace ini menyediakan akses ke kelas dan metode penting yang diperlukan untuk manipulasi file EPS.

## Langkah 1: Inisialisasi aliran input file EPS

```csharp
// MantanMulai:3
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Inisialisasi aliran input file EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Buat instance PsDocument dari aliran
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

 Di sini, kami menyiapkan aliran input awal untuk file EPS dan membuat a`PsDocument` contoh.

## Langkah 2: Dapatkan metadata XMP

```csharp
// MantanMulai:4
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, kami mendapatkan file baru yang berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

Ambil metadata XMP dari file EPS. Jika file EPS tidak memiliki metadata XMP, file baru akan dibuat dengan nilai dari komentar metadata PS.

## Langkah 3: Ubah nilai metadata XMP

```csharp
// MantanMulai:5
// Ubah nilai metadata XMP

// Tambahkan satu judul lagi. Ini akan ditambahkan di akhir array secara default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Tambahkan satu pencipta lagi. Itu akan ditambahkan ke array dengan indeks (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

Ubah metadata XMP dengan menambahkan judul dan pembuat baru ke dalam array.

## Langkah 4: Simpan file EPS dengan metadata XMP yang diubah

```csharp
// MantanMulai:6
// Simpan file EPS dengan metadata XMP yang diubah

// Buat aliran keluaran
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Simpan berkas EPS
    document.Save(outPsStream);
}
// ExEnd:6
```

Terakhir, simpan file EPS dengan metadata XMP yang diperbarui. Perubahan yang dilakukan pada item array akan tercermin dalam file output.

## Kesimpulan

Menambahkan item array dengan Aspose.Page di .NET adalah proses yang mudah, seperti yang ditunjukkan dalam tutorial ini. Dengan prasyarat yang tepat dan panduan langkah demi langkah, pengembang dapat memanipulasi file EPS dengan lancar, memastikan dokumen mereka memenuhi persyaratan metadata tertentu.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan semua lingkungan .NET?

A1: Ya, Aspose.Page dirancang untuk bekerja secara lancar dengan semua lingkungan .NET, menyediakan fungsionalitas yang konsisten di seluruh platform.

### Q2: Bisakah saya menggunakan Aspose.Page secara gratis?

 A2: Aspose.Page menawarkan versi uji coba gratis, memungkinkan pengguna menjelajahi fitur-fiturnya. Untuk penggunaan berkelanjutan, lisensi harus dibeli dari[Di Sini](https://purchase.aspose.com/buy).

### Q3: Apakah lisensi sementara tersedia untuk Aspose.Page?

 A3: Ya, izin sementara dapat diperoleh dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk kebutuhan proyek jangka pendek.

### Q4: Di mana saya dapat menemukan dukungan komunitas untuk Aspose.Page?

A4: Untuk diskusi dan dukungan komunitas, kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39).

### Q5: Apa versi terbaru Aspose.Page untuk .NET?

 A5: Untuk mengakses versi terbaru Aspose.Page untuk .NET, lihat[dokumentasi](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

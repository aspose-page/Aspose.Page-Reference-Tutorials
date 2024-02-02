---
title: Tambahkan Nilai Bernama dengan Aspose.Page
linktitle: Tambahkan Nilai Bernama
second_title: Aspose.Halaman .NET API
description: Pelajari cara menambahkan nilai bernama ke file EPS di .NET menggunakan Aspose.Page. Tutorial komprehensif ini memandu Anda melalui proses langkah demi langkah.
type: docs
weight: 12
url: /id/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## Perkenalan

Di bidang pemrosesan dokumen dengan .NET, Aspose.Page menonjol sebagai alat yang ampuh untuk menangani file EPS. Aspose.Page memberdayakan pengembang untuk memanipulasi metadata XMP, memfasilitasi tugas seperti menambahkan nilai bernama. Tutorial ini akan memandu Anda melalui proses menambahkan nilai bernama ke file EPS menggunakan Aspose.Page secara langkah demi langkah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio diinstal.
-  Aspose.Page untuk perpustakaan .NET. Jika belum diinstal, Anda dapat mendownloadnya dari[Di Sini](https://releases.aspose.com/page/net/).

## Impor Namespace

Pertama, mari impor namespace yang diperlukan ke dalam kode C# Anda. Namespace ini sangat penting untuk mengakses fungsionalitas yang disediakan oleh Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Langkah 1: Inisialisasi Aliran Input File EPS

 Langkah awal melibatkan inisialisasi aliran input untuk file EPS. Mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen Anda:

```csharp
// MantanMulai:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Langkah 2: Dapatkan Metadata XMP

Ambil metadata XMP dari file EPS. Jika file EPS tidak memiliki metadata XMP, file baru akan dibuat, diisi dengan nilai dari komentar metadata PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Langkah 3: Ubah Nilai Metadata XMP

Sekarang, mari kita buat perubahan pada metadata XMP. Dalam contoh ini, kita akan menambahkan nilai bernama ke struktur "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Langkah 4: Simpan File EPS dengan Metadata XMP yang Diubah

Simpan file EPS dengan metadata XMP yang diperbarui. Buat aliran keluaran dan simpan file EPS yang dimodifikasi:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Kesimpulan

Selamat! Anda telah berhasil menambahkan nilai bernama ke file EPS menggunakan Aspose.Page di .NET. Tutorial ini telah memandu Anda melalui langkah-langkah penting, menampilkan kesederhanaan dan efektivitas Aspose.Page dalam manipulasi dokumen.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan versi file EPS yang berbeda?

A1: Aspose.Page mendukung berbagai versi file EPS, memastikan kompatibilitas dengan berbagai macam dokumen.

### Q2: Dapatkah saya menggunakan Aspose.Page untuk proyek komersial?

 A2: Ya, Aspose.Page dilengkapi dengan lisensi komersial, dan Anda dapat membelinya[Di Sini](https://purchase.aspose.com/buy).

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page?

 A3: Ya, Anda dapat menjelajahi Aspose.Page dengan uji coba gratis yang tersedia[Di Sini](https://releases.aspose.com/).

### Q4: Bagaimana saya bisa mendapatkan dukungan atau terhubung dengan komunitas Aspose?

 A4: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk mendapatkan dukungan dan terhubung dengan komunitas.

### Q5: Apa itu lisensi sementara, dan bagaimana cara mendapatkannya?

 A5: Jika Anda memerlukan lisensi sementara untuk tujuan pengujian atau evaluasi, Anda dapat memperolehnya[Di Sini](https://purchase.aspose.com/temporary-license/).
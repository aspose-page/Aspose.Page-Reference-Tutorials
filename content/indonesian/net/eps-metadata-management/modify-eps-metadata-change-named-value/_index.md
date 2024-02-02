---
title: Ubah Nilai Bernama dengan Aspose.Page untuk .NET
linktitle: Ubah Nilai Bernama
second_title: Aspose.Halaman .NET API
description: Pelajari cara mengubah nilai bernama dalam file EPS menggunakan Aspose.Page untuk .NET. Sesuaikan metadata XMP dengan mudah untuk pemrosesan dokumen yang disesuaikan.
type: docs
weight: 16
url: /id/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Perkenalan

Dalam dunia pemrosesan dokumen, Aspose.Page untuk .NET menonjol sebagai alat yang ampuh untuk memanipulasi file EPS. Salah satu fungsi utama yang ditawarkannya adalah kemampuan untuk mengubah nilai bernama dalam metadata XMP. Tutorial ini akan memandu Anda melalui proses mengubah nilai bernama menggunakan Aspose.Page untuk .NET, memberdayakan Anda untuk menyesuaikan file EPS sesuai dengan kebutuhan spesifik Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page for .NET. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/page/net/).

- Direktori Dokumen: Miliki direktori khusus untuk file EPS tempat Anda dapat melakukan perubahan nilai bernama.

## Impor Namespace

Dalam proyek .NET Anda, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh Aspose.Page. Tambahkan namespace berikut ke kode Anda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang, mari kita bagi kode menjadi beberapa langkah untuk pemahaman yang komprehensif:

## Langkah 1: Inisialisasi Aliran Input File EPS

```csharp
// MantanMulai:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

Pada langkah ini, kami menyiapkan aliran input untuk file EPS yang ingin Anda modifikasi. Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Dapatkan Metadata XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Ambil metadata XMP yang ada dari file EPS. Jika file EPS tidak berisi metadata XMP, file baru akan dibuat dengan nilai dari komentar metadata PS.

## Langkah 3: Ubah Nilai Metadata XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Di sini, kami mendemonstrasikan perubahan dua nilai bernama dalam struktur "xmpTPg:MaxPageSize". Anda dapat menyesuaikannya sesuai dengan kebutuhan spesifik Anda.

## Langkah 4: Simpan File EPS dengan Metadata XMP yang Diubah

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Simpan file EPS yang dimodifikasi ke aliran keluaran. File tersebut sekarang akan mencerminkan perubahan yang dilakukan pada metadata XMP.

## Kesimpulan

Dengan tutorial ini, Anda telah mempelajari cara memanfaatkan Aspose.Page untuk .NET guna mengubah nilai bernama dalam metadata XMP di file EPS. Fungsionalitas ini membuka banyak kemungkinan untuk menyesuaikan dan menyesuaikan dokumen Anda untuk memenuhi kebutuhan spesifik.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

A1: Ya, Aspose.Page mendukung berbagai format dokumen, termasuk EPS, XPS, dan PDF.

### Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.Page untuk .NET?

 A2: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi selengkapnya tentang Aspose.Page untuk .NET?

 A3: Lihat dokumentasi[Di Sini](https://reference.aspose.com/page/net/).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A4: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Opsi dukungan apa yang tersedia untuk Aspose.Page untuk pengguna .NET?

 A5: Kunjungi forum komunitas[Di Sini](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi.
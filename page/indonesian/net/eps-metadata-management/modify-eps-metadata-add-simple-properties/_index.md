---
title: Tambahkan Properti Sederhana dengan Aspose.Page untuk .NET
linktitle: Tambahkan Properti Sederhana
second_title: Aspose.Halaman .NET API
description: Sempurnakan file EPS dengan Aspose.Page untuk .NET. Tambahkan properti sederhana dengan mudah untuk metadata dokumen yang disesuaikan.
weight: 14
url: /id/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Properti Sederhana dengan Aspose.Page untuk .NET

## Perkenalan

Dalam bidang manipulasi dan penyempurnaan dokumen, Aspose.Page untuk .NET muncul sebagai alat yang ampuh, memberikan pengembang kemampuan untuk menambahkan dan memodifikasi metadata XMP dalam file EPS dengan mulus. Tutorial ini akan memandu Anda melalui proses menambahkan properti sederhana ke file EPS menggunakan Aspose.Page untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page for .NET: Pastikan Anda telah menginstal Aspose.Page for .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/page/net/).

2.  Direktori Dokumen: Siapkan direktori untuk menyimpan file EPS Anda. Perbarui`dataDir` variabel dalam cuplikan kode yang disediakan dengan jalur ke direktori dokumen Anda.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan untuk mengaktifkan komunikasi dengan Aspose.Page untuk .NET. Tambahkan baris berikut di awal file kode Anda:

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

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Inisialisasi aliran input file EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Buat instance PsDocument dari aliran
PsDocument document = new PsDocument(psStream);
```

## Langkah 2: Dapatkan Metadata XMP

```csharp
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, kami mendapatkan file baru yang berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Langkah 3: Ubah Nilai Metadata XMP

```csharp
// Ubah nilai metadata XMP
DateTime now = DateTime.UtcNow;

// Tambahkan properti Integer
xmp.Add("xmp:Intg1", new XmpValue(111));

// Tambahkan properti DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Tambahkan properti Ganda
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Tambahkan properti String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Langkah 4: Simpan File EPS dengan Metadata XMP yang Diubah

```csharp
// Simpan file EPS dengan metadata XMP yang diubah

// Buat aliran keluaran
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Simpan berkas EPS
    document.Save(outPsStream);
}
```

## Langkah 5: Tutup FileStream

```csharp
finally
{
    psStream.Close();
}
```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah memasukkan properti sederhana ke dalam file EPS Anda menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Kesimpulannya, Aspose.Page untuk .NET terbukti menjadi aset yang sangat berharga bagi pengembang yang ingin menyempurnakan file EPS dengan metadata XMP khusus. Dengan menambahkan properti sederhana, Anda dapat menyesuaikan dan memperkaya dokumen Anda untuk memenuhi persyaratan tertentu, membuka banyak kemungkinan untuk manipulasi dokumen.

## FAQ

### Q1: Apakah Aspose.Page untuk .NET kompatibel dengan semua file EPS?

A1: Aspose.Page untuk .NET mendukung berbagai file EPS. Namun, kompatibilitas dapat bervariasi berdasarkan kompleksitas dan struktur masing-masing file.

### Q2: Bisakah saya mengubah metadata XMP yang ada dengan Aspose.Page untuk .NET?

A2: Tentu saja! Seperti yang ditunjukkan dalam tutorial ini, Anda dapat dengan mudah mengubah nilai metadata XMP yang ada atau menambahkan nilai baru sesuai kebutuhan Anda.

### Q3: Apakah ada batasan pada jenis properti yang dapat saya tambahkan?

A3: Aspose.Page untuk .NET mendukung berbagai tipe data untuk properti, termasuk bilangan bulat, tanggal, ganda, dan string. Anda memiliki fleksibilitas dalam memilih jenis yang sesuai untuk metadata Anda.

### Q4: Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Page untuk .NET?

 A4: Untuk bantuan teknis, kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) atau jelajahi[dokumentasi](https://reference.aspose.com/page/net/) untuk panduan komprehensif.

### Q5: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk .NET?

 A5: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

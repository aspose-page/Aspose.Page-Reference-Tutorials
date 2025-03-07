---
title: Ubah Nilai dengan Aspose.Page untuk .NET
linktitle: Ubah Nilai
second_title: Aspose.Halaman .NET API
description: Manipulasi file EPS master dengan Aspose.Page untuk .NET. Ubah nilai metadata XMP dengan mudah.
weight: 17
url: /id/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah Nilai dengan Aspose.Page untuk .NET

## Perkenalan

Dalam dunia pemrosesan dokumen yang dinamis, Aspose.Page untuk .NET menonjol sebagai alat yang ampuh, menawarkan kepada pengembang kemampuan untuk memanipulasi file EPS dengan mudah. Dalam tutorial ini, kita akan mempelajari proses mengubah nilai dalam file EPS menggunakan Aspose.Page untuk .NET. Baik Anda seorang pengembang berpengalaman atau pemula yang penasaran, panduan langkah demi langkah ini akan membekali Anda dengan keterampilan yang diperlukan untuk memodifikasi metadata XMP di file EPS Anda secara efisien.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

### 1. Aspose.Page untuk Perpustakaan .NET

Pastikan Anda telah menginstal pustaka Aspose.Page untuk .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/page/net/).

### 2. Direktori Dokumen

Siapkan direktori untuk dokumen Anda. Ini akan menjadi lokasi penyimpanan file EPS Anda.

Sekarang setelah prasyarat kita beres, mari beralih ke langkah penting berikutnya.

## Impor Namespace

Dalam proyek .NET apa pun, penting untuk mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Inilah cara Anda melakukannya:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Langkah 1: Inisialisasi aliran input file EPS

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Inisialisasi aliran input file EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Langkah 2: Buat instance PsDocument dari aliran

```csharp
//Buat instance PsDocument dari aliran
PsDocument document = new PsDocument(psStream);
```

Sekarang kita telah menyiapkan tahapannya, mari lanjutkan ke inti tutorial kita - mengubah nilai metadata XMP dalam file EPS.

## Langkah 3: Dapatkan metadata XMP

```csharp
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, kami mendapatkan file baru yang berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Langkah 4: Ubah nilai metadata XMP

Sekarang, mari kita ubah beberapa nilai kunci dalam metadata XMP:

### Langkah 4.1: Ubah nilai ModifyDate

```csharp
// Ubah nilai ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Langkah 4.2: Ubah nilai Pencipta

```csharp
// Ubah nilai Pencipta
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Langkah 4.3: Ubah nilai Judul

```csharp
// Ubah nilai Judul
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Setelah perubahan ini dilakukan, mari beralih ke langkah terakhir - menyimpan file EPS yang dimodifikasi.

## Langkah 5: Simpan file EPS dengan metadata XMP yang diubah

### Langkah 5.1: Buat aliran keluaran

```csharp
// Buat aliran keluaran
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Langkah 5.2: Simpan file EPS

```csharp
// Simpan berkas EPS
document.Save(outPsStream);
```

Terakhir, tutup aliran input:

```csharp
finally
{
    psStream.Close();
}
```

Selamat! Anda telah berhasil mengubah nilai metadata XMP dalam file EPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi proses perubahan nilai yang mulus dalam file EPS menggunakan Aspose.Page untuk .NET. Sebagai pengembang, kini Anda memiliki alat canggih untuk manipulasi dokumen secara efisien.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format file lain?

A1: Aspose.Page terutama berfokus pada manipulasi file EPS. Untuk format lainnya, jelajahi beragam produk Aspose.

### Q2: Apakah ada versi uji coba yang tersedia?

 A2: Ya, Anda dapat mencoba Aspose.Page untuk .NET dengan uji coba gratis yang tersedia[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi terperinci?

 A3: Dokumentasi lengkap dapat ditemukan[Di Sini](https://reference.aspose.com/page/net/).

### Q4: Bagaimana cara mendapatkan lisensi sementara?

 A4: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Bisakah saya membeli Aspose.Page untuk .NET?

 A5: Tentu saja! Kunjungi halaman pembelian[Di Sini](https://purchase.aspose.com/buy) untuk opsi lisensi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

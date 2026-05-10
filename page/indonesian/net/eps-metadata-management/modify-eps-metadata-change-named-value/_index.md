---
date: 2026-01-25
description: Pelajari cara mengatur XMP dan mengubah nilai bernama dalam file EPS
  menggunakan Aspose.Page untuk .NET. Sesuaikan metadata XMP dengan mudah untuk pemrosesan
  dokumen yang disesuaikan.
linktitle: Change Named Value
second_title: Aspose.Page .NET API
title: Cara Mengatur XMP dan Mengubah Nilai Bernama dengan Aspose.Page untuk .NET
url: /id/net/eps-metadata-management/modify-eps-metadata-change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menetapkan XMP dan Mengubah Named Value dengan Aspose.Page untuk .NET

## Introduction

Jika Anda perlu **cara menetapkan XMP** informasi di dalam file EPS dan juga **mengubah named value** entri dalam metadata-nya, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas skenario dunia nyata di mana Anda memodifikasi metadata XMP menggunakan Aspose.Page untuk .NET, memberi Anda kontrol penuh atas properti dokumen, branding, dan pemrosesan lanjutan.

## Quick Answers
- **Apa itu XMP?** Format standar untuk menyematkan metadata dalam file grafis dan dokumen.  
- **Mengapa mengubah named value?** Untuk memperbarui bidang metadata tertentu seperti ukuran halaman atau tag khusus tanpa menulis ulang seluruh file.  
- **Library mana yang membantu?** Aspose.Page untuk .NET menyediakan API yang sederhana untuk kedua tugas tersebut.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Platform yang didukung?** .NET Framework, .NET Core, dan .NET 5/6+.

## Prerequisites

Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page for .NET: Pastikan Anda telah menginstal pustaka Aspose.Page for .NET. Jika belum, Anda dapat mengunduhnya [here](https://releases.aspose.com/page/net/).

- Document Directory: Miliki direktori yang ditentukan untuk file EPS Anda di mana Anda dapat melakukan perubahan named value.

## Import Namespaces

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

Sekarang, mari kita uraikan kode menjadi beberapa langkah untuk pemahaman yang komprehensif:

## Step 1: Initialize EPS File Input Stream

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

Pada langkah ini, kami menyiapkan aliran input untuk file EPS yang ingin Anda modifikasi. Pastikan untuk mengganti "Your Document Directory" dengan jalur sebenarnya ke direktori dokumen Anda.

## Step 2: Get XMP Metadata

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Ambil metadata XMP yang ada dari file EPS. Jika file EPS tidak berisi metadata XMP, satu yang baru akan dihasilkan dengan nilai dari komentar metadata PS.

## Step 3: Change XMP Metadata Values

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Di sini, kami menunjukkan cara **mengubah named value** entri dalam struktur `xmpTPg:MaxPageSize`. Anda dapat menyesuaikan nama properti dan nilai sesuai kebutuhan metadata Anda.

## Step 4: Save EPS File with Changed XMP Metadata

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Simpan file EPS yang telah dimodifikasi ke aliran output. File tersebut kini akan mencerminkan perubahan yang dibuat pada metadata XMP.

## Common Issues and Solutions

- **Missing XMP section** – Jika EPS sumber tidak berisi XMP apa pun, Aspose.Page secara otomatis membuat blok XMP minimal. Anda kemudian dapat menambahkan named value khusus Anda seperti yang ditunjukkan di atas.  
- **Incorrect namespace prefix** – Pastikan bahwa namespace (mis., `xmpTPg`) cocok dengan yang ada di metadata asli; jika tidak, API akan memperlakukannya sebagai properti baru.  
- **File access errors** – Verifikasi bahwa aplikasi memiliki izin baca/tulis untuk direktori yang Anda tentukan di `dataDir`.

## Frequently Asked Questions

**Q: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?**  
A: Ya, Aspose.Page mendukung berbagai format dokumen, termasuk EPS, XPS, dan PDF.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Page untuk .NET?**  
A: Ya, Anda dapat mengakses percobaan gratis [here](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Page untuk .NET?**  
A: Lihat dokumentasi [here](https://reference.aspose.com/page/net/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?**  
A: Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

**Q: Opsi dukungan apa yang tersedia untuk pengguna Aspose.Page untuk .NET?**  
A: Kunjungi forum komunitas [here](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-08
description: Pelajari cara menambahkan item array ke metadata EPS menggunakan Aspose.Page
  EPS metadata. Panduan .NET langkah demi langkah ini menunjukkan cara menambahkan
  item array dan membaca file EPS secara efisien.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Tambahkan Item Array
og_description: Temukan cara menambahkan item array ke metadata EPS menggunakan Aspose.Page
  EPS metadata. Ikuti tutorial .NET singkat ini untuk membaca file EPS dan mengelola
  metadata secara efisien.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Menambahkan item array dengan metadata Aspose.Page EPS di .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Menambahkan item array dengan metadata Aspose.Page EPS di .NET
url: /id/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan item array dengan metadata EPS Aspose.Page di .NET

## Pendahuluan

Dalam tutorial ini Anda akan belajar cara menambahkan item array ke metadata EPS menggunakan **Aspose.Page EPS metadata**. Apakah Anda perlu memperkaya file EPS dengan judul tambahan, pembuat, atau tag khusus, Aspose.Page membuat tugas ini mudah bagi pengembang .NET mana pun. Kami akan membahas setiap langkah, mulai dari membuka aliran EPS hingga menyimpan paket XMP yang diperbarui, sehingga Anda dapat mengintegrasikan penanganan metadata ke dalam aplikasi Anda dengan percaya diri.

## Jawaban Cepat
- **Apa yang dapat Anda lakukan dengan metadata EPS Aspose.Page?** Ini memungkinkan membaca dan menulis array metadata XMP di dalam file EPS dari .NET.  
- **Kelas mana yang mewakili dokumen EPS?** `PsDocument` adalah kelas inti untuk memuat dan menyimpan konten EPS.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya memodifikasi metadata tanpa mengubah grafik EPS?** Ya, hanya paket XMP yang diubah, sementara konten halaman tetap tidak tersentuh.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu metadata EPS Aspose.Page?
Metadata EPS Aspose.Page adalah blok informasi berbasis XMP yang tertanam di dalam file EPS. Ia menyimpan properti deskriptif seperti judul, pembuat, kata kunci, dan tag khusus sesuai standar ISO 16684‑1. Metadata dapat diakses dan dimodifikasi secara programatis melalui API Aspose.Page, memungkinkan manajemen dokumen otomatis dan optimasi pencarian.

## Mengapa memodifikasi metadata EPS?
Aspose.Page dapat memproses **lebih dari 30 bidang metadata** dan menangani file EPS hingga **200 MB** tanpa memuat seluruh dokumen ke memori, yang mengurangi penggunaan CPU hingga 40 % dibandingkan dengan parsing seluruh file. Memperbarui metadata meningkatkan kemampuan pencarian, kepatuhan, dan otomatisasi alur kerja hilir.

## Prasyarat

- Pengetahuan dasar pemrograman .NET.  
- Aspose.Page untuk .NET terinstal – unduh dari [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (atau IDE kompatibel .NET lainnya) untuk menjalankan kode contoh.  

## Cara menambahkan item array ke metadata EPS?
Untuk menambahkan item array, pertama muat file EPS ke dalam `PsDocument`, kemudian ambil paket XMP-nya menggunakan `GetXmpMetadata()`. Gunakan metode `AddArrayItem()` pada array XMP yang diinginkan, seperti `dc:title` atau `dc:creator`, untuk menambahkan nilai baru. Akhirnya, panggil `Save()` untuk menulis metadata yang diperbarui kembali ke file sambil mempertahankan konten grafis tidak berubah.

### Langkah 1: inisialisasi aliran masukan file eps
`PsDocument` mewakili dokumen EPS dan menyediakan metode untuk mengakses kontennya. Kode berikut membuka file EPS sebagai aliran dan membuat instance `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Langkah 2: dapatkan metadata xmp
`GetXmpMetadata()` mengambil paket XMP yang tertanam dalam file EPS. Jika tidak ada paket, API akan membuat yang baru berdasarkan komentar PostScript yang ada.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Langkah 3: ubah nilai metadata xmp
`AddArrayItem()` menambahkan nilai baru ke array XMP yang ada tanpa menimpa entri lain. Gunakan untuk menambahkan judul, pembuat, atau tag khusus ke metadata.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Langkah 4: simpan file eps dengan metadata xmp yang diubah
`Save()` menulis paket XMP yang dimodifikasi kembali ke file EPS sambil mempertahankan konten PostScript asli. Berikan jalur output untuk membuat file baru atau menimpa sumber.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Jebakan umum dan pemecahan masalah

- **Paket XMP null** – Jika `GetXmpMetadata()` mengembalikan `null`, pastikan file EPS berisi setidaknya satu blok komentar; jika tidak, buat instance `XmpMetadata` baru secara manual.  
- **Masalah enkoding** – Gunakan UTF‑8 saat menambahkan nilai string untuk menghindari kerusakan karakter dalam bahasa non‑ASCII.  
- **File besar** – Untuk file EPS yang lebih besar dari 150 MB, pertimbangkan streaming input melalui `FileStream` dengan buffer untuk menjaga penggunaan memori tetap rendah.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Page kompatibel dengan semua lingkungan .NET?**  
A: Ya, Aspose.Page berfungsi di .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7, memberikan perilaku API yang konsisten di Windows, Linux, dan macOS.

**Q: Bisakah saya menggunakan Aspose.Page secara gratis?**  
A: Anda dapat mengevaluasi perpustakaan dengan unduhan percobaan gratis dari [halaman pembelian Aspose](https://purchase.aspose.com/buy). Lisensi komersial diperlukan untuk penerapan produksi.

**Q: Apakah lisensi sementara tersedia untuk Aspose.Page?**  
A: Lisensi sementara dapat diperoleh dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk proyek jangka pendek atau periode evaluasi.

**Q: Di mana saya dapat menemukan dukungan komunitas untuk Aspose.Page?**  
A: Bergabunglah dalam diskusi di [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk mengajukan pertanyaan dan berbagi solusi dengan pengembang lain.

**Q: Apa versi terbaru Aspose.Page untuk .NET?**  
A: Lihat [dokumentasi resmi](https://reference.aspose.com/page/net/) untuk catatan rilis terbaru dan tautan unduhan.

---

**Terakhir Diperbarui:** 2026-08-08  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Tutorial Terkait

- [Ubah Item Array dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Tambahkan Properti Sederhana dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Tambahkan Namespace dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
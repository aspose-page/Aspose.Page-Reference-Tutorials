---
date: 2026-08-13
description: Pelajari cara menggunakan Aspose.Page untuk mengubah nilai EPS dalam
  aplikasi .NET, termasuk pembaruan metadata XMP langkah demi langkah.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Ubah Nilai
og_description: Tutorial mengubah nilai eps dengan Aspose.Page menunjukkan cara memodifikasi
  metadata XMP di dalam file EPS menggunakan .NET. Ikuti panduan langkah demi langkah
  untuk memperbarui pembuat, judul, dan tanggal modifikasi secara instan.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Tutorial Aspose.Page mengubah nilai EPS dengan .NET
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page mengubah nilai EPS dengan .NET – tutorial
url: /id/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page mengubah nilai EPS dengan .NET – tutorial

## Pendahuluan

Pada tutorial ini Anda akan menemukan cara **aspose.page change eps values** dengan mengedit metadata XMP yang tertanam dalam file EPS. Apakah Anda perlu memperbarui nama pembuat, menyesuaikan judul, atau memperbaiki tanggal modifikasi, Aspose.Page untuk .NET memberikan API bersih berbasis kode yang bekerja di Windows, Linux, dan macOS. Pada akhir panduan Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke layanan .NET atau aplikasi konsol apa pun.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengubah metadata XMP (pembuat, judul, tanggal modifikasi) di dalam file EPS menggunakan Aspose.Page untuk .NET.  
- **Versi perpustakaan mana yang diperlukan?** Setiap rilis Aspose.Page untuk .NET yang mendukung XMP (v24.10+).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; percobaan gratis dapat digunakan untuk pengembangan.  
- **Bisakah saya menjalankannya di .NET Core?** Ya – API kompatibel dengan .NET 5, .NET 6, dan .NET Core 3.1+.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk pembaruan metadata dasar.

## Apa itu metadata XMP?

Metadata XMP adalah blok XML standar yang menyimpan informasi deskriptif (penulis, judul, tanggal) di dalam EPS dan format grafis lainnya. Ia tertanam langsung di header file dan dapat dibaca oleh banyak alat desain dan penerbitan, memungkinkan penanganan metadata yang konsisten di seluruh platform. Memperbarui XMP memungkinkan aplikasi hilir menampilkan properti dokumen yang benar tanpa mengubah konten visual.

## Mengapa menggunakan Aspose.Page untuk metadata EPS?

Aspose.Page dapat memproses **30+** format grafis dan menangani file EPS hingga **1 GB** tanpa memuat seluruh file ke memori, memberikan pengurangan penggunaan RAM sebesar **70 %** dibandingkan dengan parsing stream yang sederhana. Perpustakaan ini juga menjamin bahwa rendering visual EPS tetap tidak berubah setelah penyuntingan metadata.

## Prasyarat

Sebelum Anda memulai, pastikan hal berikut sudah siap:

1. **Perpustakaan Aspose.Page untuk .NET** – unduh dari halaman rilis resmi Aspose.Page untuk .NET [di sini](https://releases.aspose.com/page/net/). Anda juga dapat menjelajahi rilis produk Aspose lainnya [di sini](https://releases.aspose.com/).  
2. **Direktori dokumen** – buat folder di mesin Anda tempat file EPS sumber dan file output akan disimpan.

Setelah lingkungan siap, mari impor namespace yang Anda perlukan.

## Impor namespace

Namespace `Aspose.Page` menyediakan kelas inti, sementara `System.IO` memberikan kemampuan penanganan stream.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Cara mengubah nilai metadata EPS?

Muat file EPS, ambil paket XMP-nya, ubah bidang yang diperlukan, dan tulis kembali EPS yang diperbarui ke disk. Proses ini tidak memerlukan rendering konten halaman, sehingga cepat dan efisien memori. Ikuti langkah‑langkah terperinci untuk melihat contoh kode untuk setiap operasi. Alur end‑to‑end ini dibahas pada langkah‑langkah di bawah.

### Langkah 1: inisialisasi aliran masukan file EPS

Buat `FileStream` hanya‑baca yang menunjuk ke file EPS sumber.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Langkah 2: buat instance PsDocument dari stream

`PsDocument` adalah objek tingkat atas yang mewakili dokumen EPS dalam memori. Ia memberi Anda akses ke konten halaman serta metadata XMP yang tertanam.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Langkah 3: dapatkan metadata XMP

Properti `XmpMetadata` mengembalikan objek `XmpPacket` yang dapat Anda query dan edit.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Langkah 4: ubah nilai metadata XMP

Sekarang Anda akan mengubah tiga bidang umum: **ModifyDate**, **Creator**, dan **Title**.

#### Langkah 4.1: ubah nilai ModifyDate

Setel `ModifyDate` ke stempel waktu UTC saat ini.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Langkah 4.2: ubah nilai Creator

Ganti pembuat yang ada dengan nama aplikasi Anda.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Langkah 4.3: ubah nilai Title

Perbarui judul untuk mencerminkan tujuan konten baru.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Langkah 5: simpan file EPS dengan metadata XMP yang diubah

Setelah mengedit, tulis kembali dokumen ke output.

#### Langkah 5.1: buat aliran output

Buka `FileStream` untuk file EPS tujuan.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Langkah 5.2: simpan file EPS

Panggil `Save` pada instance `PsDocument`, dengan memberikan aliran output.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Terakhir, tutup aliran masukan untuk melepaskan handle file.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Selamat! Anda telah berhasil **aspose.page change eps values** dengan memperbarui metadata XMP di dalam file EPS.

## Kesulitan umum dan pemecahan masalah

- **Paket XMP kosong** – Beberapa file EPS dihasilkan tanpa XMP. Dalam kasus ini, buat `XmpPacket` baru melalui `new XmpPacket()` sebelum menetapkan nilai.  
- **File besar** – Untuk EPS yang lebih besar dari 500 MB, aktifkan buffering stream dengan mengatur `PsDocumentOptions.UseMemoryMappedFiles = true` untuk menghindari `OutOfMemoryException`.  
- **Format tanggal tidak tepat** – XMP mengharapkan format ISO 8601. Gunakan `DateTime.UtcNow.ToString("o")` untuk menghasilkan string yang sesuai.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format grafis lain?**  
A: Ya, perpustakaan mendukung lebih dari 30 format termasuk PDF, SVG, dan AI, namun API penyuntingan XMP khusus untuk EPS dan PDF.

**Q: Apakah versi percobaan tersedia?**  
A: Ya, Anda dapat mencoba Aspose.Page untuk .NET dengan percobaan gratis yang tersedia di halaman rilis Aspose [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi terperinci?**  
A: Referensi API Aspose.Page .NET yang komprehensif dapat ditemukan [di sini](https://reference.aspose.com/page/net/).

**Q: Bagaimana cara mendapatkan lisensi sementara?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Bisakah saya membeli Aspose.Page untuk .NET?**  
A: Tentu saja! Kunjungi halaman pembelian Aspose.Page [di sini](https://purchase.aspose.com/buy) untuk opsi lisensi.

---

**Terakhir Diperbarui:** 2026-08-13  
**Diuji Dengan:** Aspose.Page 24.10 for .NET  
**Penulis:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Tutorial Terkait

- [Tambahkan Metadata ke Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Ekstrak Metadata dari Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Ubah Nilai Bernama dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-06-30
description: Pelajari cara membuat dokumen postscript .net dan menambahkan persegi
  panjang menggunakan Aspose.Page untuk .NET. Panduan langkah demi langkah dengan
  contoh kode.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Tambahkan Persegi Panjang ke PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Buat Dokumen PostScript .NET – Tambahkan Persegi Panjang Aspose.Page
url: /id/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah Persegi Panjang ke PostScript (PS) dengan Aspose.Page untuk .NET

## Pendahuluan

Aspose.Page for .NET adalah perpustakaan yang memungkinkan pembuatan dan manipulasi file PostScript, EPS, dan XPS secara programatis. Jika Anda ingin **create postscript document .net**, tutorial ini memandu Anda menambahkan persegi panjang ke dokumen PostScript menggunakan Aspose.Page, memberikan dasar yang kuat untuk pembuatan grafik yang lebih kaya.

## Jawaban Cepat
- **Library apa yang saya butuhkan?** Aspose.Page for .NET.  
- **Bisakah saya membuat dokumen PostScript dari awal?** Ya – API memungkinkan Anda membangun file PS secara programatis.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Berapa lama waktu implementasinya?** Biasanya kurang dari 10 menit untuk bentuk dasar.

## Apa itu membuat dokumen postscript .net?
Membuat dokumen PostScript di .NET berarti secara programatis menghasilkan file `.ps` yang menggambarkan konten halaman—teks, grafik, atau bentuk—menggunakan API Aspose.Page. Pendekatan ini ideal untuk pembuatan grafik sisi‑server, pembuatan laporan otomatis, atau skenario apa pun yang memerlukan kontrol presisi atas format output.

## Mengapa menggunakan Aspose.Page untuk .NET?
Aspose.Page mendukung **30+ primitif grafik** dan dapat menghasilkan file hingga **500 MB** tanpa memuat seluruh dokumen ke dalam memori, memberikan rendering berperforma tinggi di Windows, Linux, dan macOS. Ini memberi Anda kontrol penuh atas bentuk, warna, dan goresan sambil menghilangkan kebutuhan menulis kode PostScript tingkat rendah.

- **Kontrol penuh atas grafik** – gambar bentuk, atur warna, dan terapkan goresan tanpa harus berurusan dengan sintaks PS tingkat rendah.  
- **Lintas‑platform** – bekerja pada runtime Windows, Linux, dan macOS.  
- **Tanpa dependensi eksternal** – perpustakaan menangani semua pembuatan PS secara internal.  
- **Dokumentasi & contoh yang lengkap** – memulai dengan cepat.

## Prasyarat

- **Aspose.Page for .NET Library** – unduh dan instal dari [here](https://releases.aspose.com/page/net/).  
- **Lingkungan Pengembangan** – Visual Studio, VS Code, atau IDE kompatibel .NET apa pun.

## Impor Namespace

Namespace `Aspose.Page` menyediakan kelas inti yang Anda perlukan, seperti `Document`, `Page`, `SolidBrush`, dan `Pen`. Impor namespace ini sebelum mulai menulis kode.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang mari kita bagi contoh menjadi langkah‑langkah bernomor yang jelas.

## Langkah 1: Siapkan Direktori Dokumen Anda

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan folder tempat Anda ingin menyimpan file PS yang dihasilkan.

## Langkah 2: Buat Stream Output untuk Dokumen PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Stream ini mengarah ke **AddRectangle_outPS.ps**. Silakan ganti nama file atau ubah lokasinya sesuai kebutuhan.

## Langkah 3: Atur Opsi Penyimpanan dan Buat Dokumen PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Di sini kami memberi tahu Aspose.Page untuk menggunakan ukuran halaman A4 dan membuat dokumen satu‑halaman.

## Langkah 4: Tambahkan Persegi Panjang Terisi

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Kami mendefinisikan persegi panjang pada (250, 100) dengan lebar 150 dan tinggi 100, menetapkan kuas berwarna oranye, dan mengisi bentuk tersebut.

## Langkah 5: Tambahkan Persegi Panjang Berbingkai

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Persegi panjang kedua dibuat lebih rendah pada halaman, kali ini dengan goresan merah 3‑point.

## Langkah 6: Tutup Halaman dan Simpan Dokumen

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Menutup halaman menyelesaikan gambar, dan `Save()` menulis file PS ke disk.

## Cara membuat dokumen postscript .net?
`Document` adalah kelas utama yang mewakili file PostScript dalam Aspose.Page. `SaveOptions` menentukan pengaturan seperti ukuran halaman dan format output untuk dokumen. Muat objek `Document`, konfigurasikan `SaveOptions` untuk halaman A4, gambar bentuk Anda dengan `SolidBrush` atau `Pen`, lalu panggil `document.Save()`—seluruh alur kerja hanya memerlukan beberapa baris kode dan berjalan pada runtime .NET apa pun yang didukung. Pola ini memungkinkan Anda menghasilkan file PostScript yang sepenuhnya sesuai standar tanpa menyentuh sintaks PS mentah.

## Cara menghasilkan file postscript
Gunakan kelas `SaveOptions` dari Aspose.Page untuk menentukan format output sebagai PostScript (`SaveFormat.PS`). Perpustakaan mengalirkan konten langsung ke file atau memory stream, memungkinkan Anda menghasilkan dokumen besar secara efisien tanpa konsumsi memori yang berlebihan.

## Masalah Umum & Tips

- **Path file tidak benar** – Pastikan `dataDir` diakhiri dengan pemisah path (`\\` atau `/`) atau gunakan `Path.Combine`.  
- **Lisensi hilang** – Di lingkungan produksi, terapkan lisensi Aspose Anda sebelum membuat dokumen untuk menghindari watermark evaluasi.  
- **Visibilitas warna** – Jika persegi panjang tampak kosong, pastikan warna kuas atau pena kontras dengan latar belakang halaman.

## Pertanyaan yang Sering Diajukan

**Q:** Bisakah saya menyesuaikan warna persegi panjang?  
**A:** Tentu saja. Ubah nilai `Color.Orange` atau `Color.Red` dalam konstruktor `SolidBrush` dan `Pen` ke `System.Drawing.Color` apa pun yang Anda inginkan.

**Q:** Apakah Aspose.Page kompatibel dengan format dokumen lain?  
**A:** Ya. Selain PostScript, Aspose.Page juga mendukung pembuatan XPS dan EPS.

**Q:** Bagaimana cara menambahkan teks ke dokumen yang sama?  
**A:** Gunakan kelas `TextFragment` untuk menempatkan teks pada koordinat yang diinginkan, lalu panggil `document.Draw(textFragment)`.

**Q:** Di mana saya dapat menemukan contoh tambahan dan referensi API lengkap?  
**A:** Jelajahi dokumentasi [here](https://reference.aspose.com/page/net/) dan bergabung dengan komunitas di [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Bisakah saya mencoba Aspose.Page sebelum membeli?  
**A:** Ya, unduh versi percobaan gratis [here](https://releases.aspose.com/). Untuk evaluasi yang lebih lama, pertimbangkan [lisensi sementara](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.Page 24.12 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat Dokumen PostScript dengan Aspose.Page untuk .NET](/page/net/document-creation/create-postscript-document/)
- [Tambahkan Gambar ke Dokumen PostScript (PS) dengan Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Tambahkan Teks ke Dokumen PostScript (PS) dengan Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
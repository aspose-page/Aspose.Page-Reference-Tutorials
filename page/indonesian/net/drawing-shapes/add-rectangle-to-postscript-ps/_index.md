---
date: 2026-01-18
description: Pelajari cara membuat dokumen PostScript .NET dan menambahkan persegi
  panjang menggunakan Aspose.Page untuk .NET. Panduan langkah demi langkah dengan
  contoh kode.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Buat dokumen PostScript .NET – Tambahkan Persegi Panjang dengan Aspose.Page
url: /id/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Persegi Panjang ke PostScript (PS) dengan Aspose.Page untuk .NET

## Pendahuluan

Jika Anda ingin **create postscript document .net**, Aspose.Page menyediakan solusi kuat untuk menangani file PostScript. Dalam tutorial ini, kami akan memandu Anda menambahkan persegi panjang ke dokumen PostScript menggunakan Aspose.Page untuk .NET, memberi Anda dasar yang kuat untuk pembuatan grafik yang lebih kaya.

## Jawaban Cepat
- **Library apa yang saya butuhkan?** Aspose.Page for .NET.
- **Bisakah saya membuat dokumen PostScript dari awal?** Ya – API memungkinkan Anda membangun file PS secara programatis.
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.
- **Berapa lama waktu implementasinya?** Biasanya kurang dari 10 menit untuk bentuk dasar.

## Apa itu membuat dokumen postscript .net?
Membuat dokumen PostScript di .NET berarti secara programatis menghasilkan file .ps yang menggambarkan konten halaman—teks, grafik, atau bentuk—menggunakan API Aspose.Page. Pendekatan ini ideal untuk pembuatan grafik sisi‑server, pembuatan laporan otomatis, atau skenario apa pun yang memerlukan kontrol presisi atas format output.

## Mengapa menggunakan Aspose.Page untuk .NET?
- **Kontrol penuh atas grafik** – menggambar bentuk, mengatur warna, dan menerapkan goresan tanpa harus berurusan dengan sintaks PS tingkat rendah.
- **Cross‑platform** – berfungsi pada runtime Windows, Linux, dan macOS.
- **Tanpa dependensi eksternal** – perpustakaan menangani semua generasi PS secara internal.
- **Dokumentasi & contoh yang kaya** – memulai dengan cepat.

## Prasyarat

- **Aspose.Page for .NET Library** – unduh dan instal dari [here](https://releases.aspose.com/page/net/).
- **Lingkungan Pengembangan** – Visual Studio, VS Code, atau IDE kompatibel .NET apa pun.

## Impor Namespace

Sebelum Anda mulai menulis kode, impor namespace yang menyediakan kelas yang diperlukan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang mari kita bagi contoh menjadi langkah‑langkah yang jelas dan bernomor.

## Langkah 1: Siapkan Direktori Dokumen Anda

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan folder tempat Anda ingin menyimpan file PS yang dihasilkan.

## Langkah 2: Buat Output Stream untuk Dokumen PostScript

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

## Langkah 4: Tambahkan Persegi Panjang Berisi

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

## Masalah Umum & Tips

- **Path file tidak benar** – Pastikan `dataDir` diakhiri dengan pemisah path (`\\` atau `/`) atau gunakan `Path.Combine`.
- **Lisensi hilang** – Pada lingkungan produksi, terapkan lisensi Aspose Anda sebelum membuat dokumen untuk menghindari watermark evaluasi.
- **Keterlihatan warna** – Jika persegi panjang muncul kosong, pastikan warna kuas atau pena kontras dengan latar belakang halaman.

## Pertanyaan yang Sering Diajukan

**Q:** Can I customize the colors of the rectangles?  
**A:** Absolutely. Change the `Color.Orange` or `Color.Red` values in the `SolidBrush` and `Pen` constructors to any `System.Drawing.Color` you prefer.

**Q:** Is Aspose.Page compatible with other document formats?  
**A:** Yes. Besides PostScript, Aspose.Page also supports XPS and EPS generation.

**Q:** How can I add text to the same document?  
**A:** Use the `TextFragment` class to place text at desired coordinates, then call `document.Draw(textFragment)`.

**Q:** Where can I find additional examples and full API reference?  
**A:** Explore the documentation [here](https://reference.aspose.com/page/net/) and join the community at the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Can I try Aspose.Page before buying?  
**A:** Yes, download a free trial [here](https://releases.aspose.com/). For extended evaluation, consider a [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-01-18  
**Diuji Dengan:** Aspose.Page 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
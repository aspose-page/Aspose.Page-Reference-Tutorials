---
date: 2026-01-23
description: Pelajari cara menghasilkan file PostScript dan menambahkan elips lingkaran
  menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah ini untuk
  menggambar elips dengan kode C# secara cepat.
linktitle: Add Circle Ellipse to PostScript (PS)
second_title: Aspose.Page .NET API
title: Buat File PostScript & Tambahkan Lingkaran Elips – Aspose.Page
url: /id/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan File PostScript & Menambahkan Lingkaran Elips – Aspose.Page

## Pendahuluan

Dalam tutorial ini Anda akan mempelajari **cara menghasilkan file PostScript** dan menyisipkan elips lingkaran yang sempurna menggunakan Aspose.Page .NET API. Baik Anda sedang membangun mesin pelaporan, membuat grafik vektor, atau perlu menggambar elips secara programatis di C#, panduan ini akan memandu Anda melalui setiap langkah—dari menyiapkan lingkungan hingga menyimpan dokumen PS akhir.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan dua elips (terisi dan bergaris) ke file PostScript dengan Aspose.Page untuk .NET.  
- **Kata kunci utama apa yang ditargetkan?** *generate postscript file*.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh elips dasar.

## Apa itu “generate postscript file”?

Menghasilkan file PostScript berarti secara programatis membuat dokumen .ps yang mendeskripsikan isi halaman menggunakan bahasa PostScript. Format ini banyak dipakai untuk pencetakan, desain grafis, dan alur konversi ke PDF.

## Mengapa menambahkan elips lingkaran dengan Aspose.Page?

- **Presisi** – Gambar berbasis vektor memastikan skala tanpa kehilangan kualitas.  
- **Lintas platform** – File PS yang sama dapat dirender pada printer mana pun yang kompatibel dengan PostScript.  
- **C# friendly** – API menyederhanakan perintah PS tingkat rendah, memungkinkan Anda *draw ellipse* dengan tipe .NET yang familiar.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **Aspose.Page untuk .NET** – Unduh dan instal pustaka dari [sini](https://releases.aspose.com/page/net/).  
2. **Lingkungan pengembangan .NET** – Visual Studio, Rider, atau .NET CLI terpasang di mesin Anda.

Setelah semuanya siap, mari mulai menulis kode.

## Mengimpor Namespace

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup agar kelas Aspose.Page tersedia.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Menetapkan Direktori Dokumen

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

> **Tip profesional:** Ganti `"Your Document Directory"` dengan jalur absolut atau relatif yang dapat ditulisi oleh aplikasi Anda.

### Langkah 2: Membuat Stream Output untuk Dokumen PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

`FileStream` membuka (atau membuat) *AddEllipse_outPS.ps* di mana konten PS yang dihasilkan akan disimpan.

### Langkah 3: Membuat Opsi Penyimpanan dan Dokumen PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Di sini kita menentukan ukuran halaman A4 dan menginstansiasi `PsDocument` satu‑halaman.

### Langkah 4: Membuat Graphics Path untuk Elips Pertama

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

`GraphicsPath` menyimpan definisi geometris elips yang diposisikan pada (250, 100) dengan lebar 150 pt dan tinggi 100 pt.

### Langkah 5: Menetapkan Paint dan Mengisi Elips

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

Kita mengisi elips pertama dengan warna oranye yang cerah.

### Langkah 6: Membuat Graphics Path untuk Elips Kedua

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Elips kedua didefinisikan lebih rendah pada halaman (koordinat y 300).

### Langkah 7: Menetapkan Stroke dan Menggambar Elips

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

Kali ini kita *draw ellipse* menggunakan pena merah dengan ketebalan 3 pt, menghasilkan outline bergaris.

### Langkah 8: Menutup Halaman Saat Ini dan Menyimpan Dokumen

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Menutup halaman menyelesaikan konten, dan `Save()` menulis output PostScript ke stream yang telah dibuat sebelumnya.

## Masalah Umum & Solusinya

| Masalah | Alasan | Solusi |
|---------|--------|--------|
| **File tidak dibuat** | `dataDir` mengarah ke folder yang tidak ada. | Pastikan direktori ada atau gunakan `Directory.CreateDirectory(dataDir);` sebelum membuka stream. |
| **Elips tampak terdistorsi** | Dimensi persegi panjang tidak tepat (lebar ≠ tinggi). | Gunakan lebar & tinggi yang sama untuk lingkaran sempurna; sesuaikan nilai `RectangleF` yang bersangkutan. |
| **License exception** | Menjalankan tanpa lisensi Aspose.Page yang valid di produksi. | Terapkan lisensi sementara atau permanen seperti dijelaskan dalam dokumentasi Aspose. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?**  
J: Aspose.Page fokus pada PostScript, tetapi Aspose menyediakan pustaka tambahan untuk PDF, DOCX, dan format lainnya. Lihat [dokumentasi Aspose](https://reference.aspose.com/page/net/) untuk daftar lengkap.

**T: Di mana saya dapat menemukan dukungan tambahan dan diskusi komunitas?**  
J: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk mengajukan pertanyaan, berbagi contoh, dan mendapatkan bantuan dari pengembang lain.

**T: Apakah ada versi percobaan gratis untuk Aspose.Page?**  
J: Ya, Anda dapat mengunduh versi percobaan gratis dari halaman [free trial](https://releases.aspose.com/) untuk mengevaluasi pustaka sebelum membeli.

**T: Bagaimana cara mendapatkan lisensi sementara untuk pengujian?**  
J: Lisensi sementara dapat diminta [di sini](https://purchase.aspose.com/temporary-license/) dan berlaku selama 30 hari.

**T: Di mana saya dapat membeli lisensi penuh untuk Aspose.Page?**  
J: Opsi pembelian tercantum pada halaman resmi [buy page](https://purchase.aspose.com/buy).

## Kesimpulan

Anda kini mengetahui cara **menghasilkan file PostScript** dan **menggambar bentuk elips** menggunakan Aspose.Page untuk .NET. Dengan mengikuti langkah‑langkah di atas, Anda dapat dengan mudah mengintegrasikan grafik vektor ke dalam alur kerja pencetakan atau rendering apa pun. Bereksperimenlah dengan warna, lebar garis, dan posisi yang berbeda untuk menciptakan ilustrasi yang lebih kompleks.

---

**Terakhir Diperbarui:** 2026-01-23  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
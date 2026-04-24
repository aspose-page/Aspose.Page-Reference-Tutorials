---
date: 2026-01-05
description: Pelajari cara menambahkan clipping path pada PostScript menggunakan Aspose.Page
  untuk .NET – panduan langkah demi langkah dengan teknik mengatur kuas cat dan menggambar
  persegi panjang bergaris putus‑putus.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Tambahkan Jalur Pemotongan ke PS dengan Aspose.Page untuk .NET
url: /id/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Clipping Path ke PS dengan Aspose.Page untuk .NET

## Introduction

Dalam tutorial komprehensif ini Anda akan menemukan cara **menambahkan clipping path** ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Kami akan memandu Anda melalui setiap langkah, menunjukkan cara **mengatur kuas cat**, dan mendemonstrasikan cara **menggambar persegi panjang putus‑putus** di sekitar konten yang dipotong. Pada akhir tutorial, Anda akan memiliki file PS yang berfungsi penuh yang menggambarkan clipping berdasarkan bentuk, membuat grafik Anda lebih dinamis dan profesional.

## Quick Answers
- **Apa yang dilakukan “add clipping path”?** Itu membatasi operasi menggambar ke bentuk yang ditentukan, menyembunyikan segala sesuatu di luar bentuk tersebut.  
- **Library mana yang menangani clipping di .NET?** Aspose.Page untuk .NET menyediakan API yang kaya untuk manipulasi PS/EPS.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah warna kuas?** Ya, gunakan `SetPaint` dengan `SolidBrush` atau gradien apa pun yang Anda inginkan.  
- **Apakah menggambar persegi panjang putus‑putus memungkinkan?** Tentu – buat `Pen` dengan `DashStyle.Dash` dan gunakan `Draw`.  

## What is a clipping path in PostScript?
Clipping path mendefinisikan wilayah yang terlihat dari perintah menggambar berikutnya. Apa pun yang digambar di luar path akan diabaikan, memungkinkan Anda membuat grafik bertopeng yang kompleks tanpa mengubah konten asli.

## Why use Aspose.Page for clipping?
- **Tidak ada dependensi eksternal** – perpustakaan .NET murni.  
- **Kontrol penuh** atas status grafik (save/restore, translate, rotate).  
- **Primitif menggambar yang kaya** seperti `SetPaint`, `Clip`, dan `Draw` dengan pena serta kuas yang dapat disesuaikan.  

## Prerequisites

- Pengetahuan dasar pemrograman C#.  
- Perpustakaan Aspose.Page untuk .NET terinstal – Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- Visual Studio atau IDE .NET pilihan Anda.  

## Import Namespaces

Pertama, impor namespace yang diperlukan untuk manipulasi grafik:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang mari kita uraikan contoh menjadi langkah‑langkah yang jelas dan bernomor.

### Step 1: Set Document Directory

Tentukan folder tempat file sumber dan output Anda berada.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document

Buat stream yang dapat ditulis untuk menampung file PS yang dihasilkan.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Step 3: Create Save Options

Instansiasi `PsSaveOptions` dengan pengaturan default. Anda dapat menyesuaikannya nanti jika diperlukan.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New 1‑Paged PS Document

Inisialisasi objek `PsDocument` yang mewakili file PS Anda.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create Graphics Path from the Rectangle

Kita akan menggunakan persegi panjang sebagai bentuk dasar yang kemudian akan dipotong.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Step 6: Clipping by Shape

Di sini kita **menambahkan clipping path** menggunakan lingkaran, **mengatur kuas cat** menjadi biru, dan mengisi persegi panjang dalam wilayah yang dipotong.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Step 7: Displace Upper Level Graphics State & Draw Dashed Rectangle

Setelah mengembalikan status sebelumnya, kami memindahkan kursor grafik lagi, **menggambar persegi panjang putus‑putus**, dan menerapkan garis biru.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Step 8: Close and Save Document

Selesaikan halaman dan tulis file PS ke disk.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Anda kini telah berhasil **menambahkan clipping path**, mengatur kuas cat khusus, dan menggambar persegi panjang putus‑putus di sekitar grafik Anda menggunakan Aspose.Page untuk .NET.

## Common Issues and Solutions

- **Clipping tidak terlihat:** Pastikan Anda memanggil `WriteGraphicsSave()` sebelum melakukan translate dan `WriteGraphicsRestore()` setelah mengisi.  
- **Warna tidak tepat:** Verifikasi bahwa `SetPaint` dipanggil setelah `Clip` dan sebelum `Fill`.  
- **Garis putus‑putus muncul solid:** Pastikan `DashStyle` pada `Pen` diatur ke `DashStyle.Dash` sebelum `SetStroke`.  

## Frequently Asked Questions

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan bahasa pemrograman lain?
A: Aspose.Page terutama dirancang untuk aplikasi .NET. Namun, Aspose menyediakan perpustakaan serupa untuk bahasa pemrograman lain.

### Q2: Di mana saya dapat menemukan contoh tambahan dan dokumentasi untuk Aspose.Page untuk .NET?
A: Anda dapat menjelajahi lebih banyak contoh dan dokumentasi detail pada [dokumentasi Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Apakah tersedia percobaan gratis untuk Aspose.Page untuk .NET?
A: Ya, Anda dapat mengakses percobaan gratis Aspose.Page untuk .NET [di sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat mendapatkan dukungan atau mendiskusikan pertanyaan terkait Aspose.Page?
A: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

---

**Terakhir Diperbarui:** 2026-01-05  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
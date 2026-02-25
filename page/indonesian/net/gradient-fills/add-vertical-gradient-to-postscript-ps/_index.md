---
date: 2026-02-25
description: Pelajari cara menggunakan kuas gradien linier C# untuk menambahkan gradien
  ke file PS dan mengisi persegi panjang dengan gradien menggunakan Aspose.Page untuk
  .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linear Gradient Brush – Tambahkan Gradien Vertikal ke PostScript (PS) dengan
  Aspose.Page
url: /id/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 Simpan Dokumen".

Conclusion paragraph.

Common Issues and Solutions table: translate Issue, Why it Happens, How to Fix, and rows.

FAQ: translate Q1 etc.

Last Updated etc: keep same.

Now produce final content with same shortcodes.

Let's craft.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Tambahkan Gradien Vertikal ke PostScript (PS) dengan Aspose.Page

## Introduction

Dalam dunia manipulasi dan pembuatan dokumen, **Aspose.Page for .NET** menonjol sebagai alat yang kuat bagi para pengembang. Dalam panduan ini Anda akan menemukan cara **menambahkan gradien ke file PS** dengan menggunakan **brush gradien linear C#** untuk **mengisi persegi panjang dengan gradien**. Pada akhir tutorial, Anda akan memiliki pemahaman langkah‑demi‑langkah yang jelas tentang kode yang diperlukan dan mengapa teknik ini menghasilkan gradien vertikal yang halus dalam output PostScript Anda.

## Quick Answers
- **Apa yang dilakukan brush gradien linear C#?** Brush ini membuat transisi halus antara beberapa warna di seluruh bentuk.
- **Apakah saya dapat menggunakan ini dengan versi .NET apa pun?** Ya, Aspose.Page mendukung .NET Framework 4.5+ dan .NET Core/5+.
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk build non‑evaluasi.
- **Apakah gradien benar‑benar vertikal?** Brush diputar 90°, memastikan aliran vertikal.
- **Di mana output disimpan?** Ke jalur yang Anda tentukan di `dataDir` (misalnya `VerticalGradient_outPS.ps`).

## What is a C# Linear Gradient Brush?
**C# linear gradient brush** adalah objek GDI+ (`LinearGradientBrush`) yang melukis transisi warna linear antara titik‑titik yang ditentukan. Ketika digabungkan dengan API gambar Aspose.Page, ia memungkinkan Anda merender gradien canggih langsung ke dalam dokumen PostScript (PS).

## Why Use a Linear Gradient Brush for PostScript?
- **Output berkualitas tinggi:** Gradien dirender pada level printer, mempertahankan fidelitas.
- **Kontrol penuh:** Anda dapat mengatur titik warna khusus, rotasi, dan skala.
- **Kode dapat digunakan kembali:** Logika brush yang sama bekerja untuk PDF, SVG, dan format lain yang didukung oleh Aspose.Page.

## Prerequisites

Sebelum memulai tutorial, pastikan hal‑hal berikut sudah tersedia:

- Aspose.Page for .NET: Pastikan Anda telah menginstal pustaka Aspose.Page. Anda dapat menemukan sumber daya dan dokumentasi yang diperlukan [di sini](https://reference.aspose.com/page/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai, termasuk Integrated Development Environment (IDE) untuk pengembangan .NET.
- Pemahaman Dasar: Kenali dasar‑dasar pengembangan .NET, termasuk bekerja dengan stream, graphics path, dan manipulasi warna.

## Import Namespaces

Di proyek C# Anda, sertakan namespace yang diperlukan di awal file kode Anda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up the Document Directory

Mulailah dengan menentukan jalur ke direktori dokumen Anda. Ini adalah lokasi di mana dokumen PS Anda akan disimpan.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

Buat output stream untuk dokumen PostScript menggunakan kelas `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Step 3: Create Save Options and PS Document

Buat save options dengan ukuran A4 dan inisialisasi dokumen PS baru dengan 1 halaman.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Dimensions

Tentukan dimensi dan posisi persegi panjang tempat gradien vertikal akan diterapkan.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Step 5: Create Graphics Path

Bangun graphics path dari persegi panjang yang telah ditentukan.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Define Interpolation Colors

Tetapkan array warna interpolasi dan posisi untuk gradien.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Step 7: Create Linear Gradient Brush

Buat linear gradient brush dengan persegi panjang sebagai batas, warna mulai dan akhir.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Step 8: Set Brush Transform

Atur transform untuk brush, memastikan komponen skala X dan Y cocok dengan lebar dan tinggi persegi panjang.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Step 9: Set Paint and Fill the Rectangle

Atur paint untuk dokumen, dan **isi persegi panjang dengan gradien** menggunakan path yang telah didefinisikan sebelumnya.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Step 10: Close the Current Page and Save the Document

Tutup halaman saat ini dan simpan dokumen PostScript.

```csharp
document.ClosePage();
document.Save();
```

Selamat! Anda telah berhasil **menambahkan gradien vertikal ke dokumen PostScript** menggunakan **brush gradien linear C#** dengan Aspose.Page for .NET. Bereksperimenlah dengan parameter dan warna yang berbeda untuk mencapai berbagai efek visual dalam dokumen Anda.

## Common Issues and Solutions

| Issue | Why it Happens | How to Fix |
|-------|----------------|------------|
| Gradien muncul horizontal | Rotasi brush tidak diterapkan | Pastikan `brushTransform.Rotate(90);` dipanggil sebelum menetapkan ke `brush.Transform`. |
| Warna tampak pudar | Output stream beresolusi rendah | Gunakan `PsSaveOptions` dengan resolusi lebih tinggi atau tingkatkan ukuran dokumen. |
| File output kosong | Stream tidak di‑flush | Verifikasi bahwa `document.Save();` dipanggil di luar blok `using`. |

## Frequently Asked Questions

**Q1: Apakah saya dapat menerapkan beberapa gradien ke wilayah yang berbeda dalam dokumen yang sama?**  
A: Ya, Anda dapat. Cukup ulangi langkah‑langkah untuk setiap wilayah dengan dimensi dan skema warna masing‑masing.

**Q2: Bagaimana cara mengintegrasikan kode ini ke dalam proyek .NET saya yang sudah ada?**  
A: Salin dan tempel kode ke file proyek Anda dan pastikan pustaka Aspose.Page sudah direferensikan.

**Q3: Apakah ada tipe gradien lain yang tersedia di Aspose.Page untuk .NET?**  
A: Aspose.Page mendukung berbagai tipe gradien, termasuk radial dan path gradients. Lihat dokumentasi untuk detail lebih lanjut.

**Q4: Bisakah saya menggunakan Aspose.Page untuk proyek komersial?**  
A: Ya, Anda dapat. Kunjungi [di sini](https://purchase.aspose.com/buy) untuk menjelajahi opsi lisensi.

**Q5: Apakah ada forum komunitas untuk Aspose.Page tempat saya dapat meminta bantuan?**  
A: Tentu! Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk terhubung dengan pengembang lain dan mendapatkan bantuan.

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
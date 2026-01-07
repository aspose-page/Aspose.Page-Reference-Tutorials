---
date: 2026-01-07
description: Pelajari cara membuat dokumen XPS, menambahkan klon glif, menggunakan
  kuas warna solid, dan menyimpan file XPS dengan Aspose.Page untuk .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Buat Dokumen XPS – Tambahkan Klon Glyph & Ubah Warna dengan Aspose.Page untuk
  .NET
url: /id/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS – Tambahkan Klon Glyph & Ubah Warna dengan Aspose.Page untuk .NET

## Introduction

Selamat datang di panduan langkah‑demi‑langkah ini yang menunjukkan **cara membuat file dokumen XPS**, mengkloning glyph, dan mengubah warnanya menggunakan Aspose.Page untuk .NET. Baik Anda membuat laporan dinamis, faktur, atau grafik khusus, menguasai teknik ini memungkinkan Anda menghasilkan output XPS yang kaya visual tanpa meninggalkan ekosistem .NET.

## Quick Answers
- **Apa tujuan utama?** Membuat dokumen XPS, menambahkan klon glyph, dan mengubah warnanya.  
- **Perpustakaan mana yang digunakan?** Aspose.Page untuk .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara tersedia untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Bagaimana cara menyimpan hasil?** Gunakan metode `Save` untuk menulis file XPS ke disk.

## Prerequisites

- Pemahaman dasar tentang bahasa pemrograman C#.  
- Visual Studio atau lingkungan pengembangan C# lain yang Anda sukai telah terpasang.  
- Aspose.Page untuk .NET. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- Keterbiasaan dengan format dokumen XPS.

## Import Namespaces

Untuk memulai, sertakan namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

Mulailah dengan menyiapkan direktori tempat dokumen Anda akan disimpan:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

Sekarang, buat dokumen XPS pertama:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

Tambahkan glyph ke dokumen pertama menggunakan parameter yang ditentukan:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

Isi glyph di dokumen pertama dengan **kuas warna solid**, misalnya hijau:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

Sekarang, buat dokumen XPS kedua:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

Klon glyph dari dokumen pertama dan tambahkan ke dokumen kedua:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

Ubah warna glyph yang diklon di dokumen kedua, misalnya menjadi merah. Ini menunjukkan **cara mengubah warna** glyph setelah diklon:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

Simpan dokumen XPS pertama ke folder yang Anda tentukan sebelumnya:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

Simpan dokumen XPS kedua:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Selamat! Anda telah berhasil **membuat file dokumen XPS**, menambahkan klon glyph, dan mengubah warnanya menggunakan Aspose.Page untuk .NET.

## Why Use Glyph Cloning and Color Changes?

- **Dapat Digunakan Kembali:** Mengklon glyph yang ada untuk menggunakan kembali bentuk vektor kompleks tanpa harus mendefinisikannya kembali.  
- **Kinerja:** Mengurangi waktu pemrosesan dibandingkan membuat ulang glyph dari awal.  
- **Fleksibilitas Desain:** Terapkan instance `SolidColorBrush` yang berbeda pada glyph yang sama untuk mencapai tema visual yang beragam.  
- **Pengeditan Lintas Dokumen:** Mengklon glyph di beberapa file XPS, memungkinkan branding yang konsisten di seluruh laporan.

## Common Issues & Troubleshooting

| Masalah | Solusi |
|-------|----------|
| **Klon mengembalikan null** | Pastikan glyph sumber (`glyphs`) telah ditambahkan ke dokumen pertama sebelum diklon. |
| **Warna tidak berubah** | Lakukan cast `glyphs.Fill` ke `XpsSolidColorBrush` sebelum mengatur properti `Color` (seperti yang ditunjukkan pada Langkah 7). |
| **File tidak tersimpan** | Verifikasi bahwa `dataDir` mengarah ke folder yang valid dan dapat ditulisi serta Anda memiliki izin sistem file yang sesuai. |
| **Ukuran glyph tidak terduga** | Sesuaikan parameter ukuran font (argumen kedua dalam `AddGlyphs`) untuk menskalakan glyph secara tepat. |

## Frequently Asked Questions

**Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?**  
A1: Aspose.Page untuk .NET dirancang khusus untuk bekerja dengan dokumen XPS. Jika Anda perlu memanipulasi format lain, Anda dapat menjelajahi perpustakaan Aspose lain yang disesuaikan untuk format tersebut.

**Q2: Apakah lisensi sementara tersedia untuk Aspose.Page untuk .NET?**  
A2: Ya, Anda dapat memperoleh lisensi sementara untuk tujuan pengujian. Kunjungi [di sini](https://purchase.aspose.com/temporary-license/) untuk informasi lebih lanjut.

**Q3: Bagaimana saya dapat mendapatkan dukungan atau bantuan untuk masalah apa pun?**  
A3: Silakan kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mencari bantuan.

**Q4: Apakah ada batasan pada versi percobaan gratis?**  
A4: Versi percobaan gratis memiliki beberapa batasan, dan disarankan untuk meninjau dokumentasi untuk detailnya sebelum penggunaan.

**Q5: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Page untuk .NET?**  
A5: Anda dapat merujuk ke dokumentasi [di sini](https://reference.aspose.com/page/net/) untuk informasi detail dan contoh.

**Q6: Bagaimana cara mengubah warna garis (stroke) glyph alih-alih isian?**  
A6: Gunakan `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` untuk mengatur kuas stroke.

**Q7: Bisakah saya menambahkan beberapa klon glyph ke dokumen yang sama?**  
A7: Ya, panggil `doc2.Add(glyphs.Clone());` berulang kali, sesuaikan posisi sesuai kebutuhan.

**Terakhir Diperbarui:** 2026-01-07  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
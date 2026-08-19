---
date: 2026-02-25
description: Pelajari cara membuat gradien XPS dengan isian horizontal menggunakan
  Aspose.Page untuk .NET. Tingkatkan daya tarik visual dengan mudah dalam dokumen
  Anda.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Buat Gradien XPS: Isi Horizontal dengan Aspose.Page untuk .NET'
url: /id/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Gradient XPS – Menambahkan Gradient Horizontal ke XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan **membuat isian gradient XPS** yang berjalan secara horizontal di seluruh halaman Anda. Menambahkan gradient horizontal dapat langsung membuat dokumen XPS terlihat lebih halus dan menarik, terutama untuk laporan, brosur, atau output visual‑rich apa pun. Kami akan memandu Anda melalui proses lengkap menggunakan Aspose.Page untuk .NET, mulai dari menyiapkan lingkungan hingga menyimpan file XPS akhir.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan gradient horizontal ke dokumen XPS dengan Aspose.Page untuk .NET.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk .NET (versi terbaru apa pun).  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Sekitar 5–10 menit untuk gradient dasar.  
- **Bisakah saya mengubah arah gradient?** Ya – ubah titik mulai/akhir dari `LinearGradientBrush`.

## Cara membuat gradient XPS dengan Aspose.Page untuk .NET

Di bawah ini Anda akan menemukan panduan langkah‑demi‑langkah yang menjelaskan **mengapa** setiap baris kode ada, bukan hanya **apa** yang dilakukannya. Silakan ikuti di Visual Studio atau editor .NET pilihan Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.Page untuk .NET Library:** Pastikan Anda telah menginstal perpustakaan Aspose.Page untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. **Lingkungan Pengembangan:** Siapkan lingkungan pengembangan yang sesuai, termasuk editor kode seperti Visual Studio.

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek Anda. Namespace ini penting untuk bekerja dengan Aspose.Page untuk .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah.

## Langkah 1: Atur Path Direktori Dokumen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Langkah 2: Buat Dokumen XPS Baru

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Langkah 3: Inisialisasi Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Langkah 4: Buat Path Baru

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Langkah 5: Simpan Dokumen XPS yang Dihasilkan

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Sekarang, Anda telah berhasil menambahkan gradient horizontal ke dokumen XPS Anda menggunakan Aspose.Page untuk .NET.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| Gradient muncul sebagai warna solid | Gradient stops tidak ditambahkan dengan benar | Pastikan `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` dijalankan setelah mengatur brush. |
| File yang disimpan kosong | `dataDir` mengarah ke folder yang tidak ada | Verifikasi folder tersebut ada atau gunakan path absolut. |
| Error kompilasi pada `PointF` | Referensi `System.Drawing` hilang | Tambahkan referensi ke `System.Drawing.Common` (untuk .NET Core/5+). |

## FAQ

### Q1: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk .NET?

A1: Dokumentasinya dapat Anda temukan [di sini](https://reference.aspose.com/page/net/).

### Q2: Bagaimana cara mengunduh Aspose.Page untuk .NET?

A2: Anda dapat mengunduh perpustakaan tersebut dari [halaman unduhan Aspose.Page untuk .NET](https://releases.aspose.com/page/net/).

### Q3: Di mana saya dapat membeli Aspose.Page untuk .NET?

A3: Anda dapat membeli Aspose.Page untuk .NET melalui [halaman pembelian](https://purchase.aspose.com/buy).

### Q4: Apakah tersedia trial gratis?

A4: Ya, Anda dapat memperoleh trial gratis [di sini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

A5: Anda dapat memperoleh lisensi sementara dari [tautan ini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan teknik gradient ini pada dokumen XPS yang sudah berisi gambar?**  
J: Tentu saja. Gradient diterapkan pada lapisan path, sehingga gambar yang ada tetap tidak terpengaruh.

**T: Apakah memungkinkan membuat gradient vertikal sebagai gantinya?**  
J: Ya. Ubah titik mulai dan akhir `LinearGradientBrush` sehingga memiliki koordinat Y yang berbeda sementara X tetap konstan.

**T: Apakah Aspose.Page mendukung .NET Core?**  
J: Perpustakaan ini sepenuhnya kompatibel dengan .NET Core, .NET 5, dan versi selanjutnya.

**T: Bagaimana cara menggunakan gradient yang sama pada beberapa halaman?**  
J: Buat `XpsLinearGradientBrush` sekali, simpan dalam variabel, dan tetapkan ke path pada setiap halaman.

## Kesimpulan

Meningkatkan dokumen XPS Anda dengan gradient tidak hanya memperbaiki daya tarik visual tetapi juga memberikan pengalaman pengguna yang lebih menarik. Dengan Aspose.Page untuk .NET, Anda dapat **membuat isian gradient XPS** dengan cepat dan andal, memberikan laporan, brosur, atau e‑book Anda sentuhan profesional.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-02-25  
**Diuji Dengan:** Aspose.Page untuk .NET 24.11  
**Penulis:** Aspose  

---
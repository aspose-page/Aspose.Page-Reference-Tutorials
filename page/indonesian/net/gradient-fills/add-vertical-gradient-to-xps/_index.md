---
date: 2026-02-25
description: Pelajari cara membuat dokumen XPS dan menerapkan gradien linier dengan
  Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk menyimpan
  file XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Buat Dokumen XPS dengan Gradien Vertikal menggunakan Aspose.Page
url: /id/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Gradien Vertikal ke XPS dengan Aspose.Page untuk .NET

## Introduction

Dalam tutorial ini Anda akan **membuat dokumen XPS** yang menampilkan gradien vertikal yang halus. Menambahkan gradien adalah cara umum untuk membuat file XPS terlihat lebih profesional—sempurna untuk laporan, brosur, atau grafik yang dapat dicetak. Kami akan memandu Anda melalui setiap langkah, mulai dari menyiapkan proyek hingga menyimpan file XPS akhir, sehingga Anda dapat dengan cepat menerapkan gradien linear pada jalur apa pun.

## Quick Answers
- **Apa yang dibahas dalam tutorial ini?** Menambahkan gradien linear vertikal ke sebuah jalur dalam dokumen XPS.  
- **Perpustakaan mana yang diperlukan?** Aspose.Page untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.  
- **Bisakah saya menyimpan hasilnya sebagai file XPS?** Ya, metode `Save` menulis file ke disk.

## What is a vertical gradient in XPS?

Gradien vertikal adalah transisi warna yang berjalan dari bagian atas sebuah bentuk ke bagian bawah. Di XPS, hal ini dicapai dengan **kuas gradien linear** yang mendefinisikan titik awal dan akhir, serta kumpulan gradient stop yang mengontrol warna pada posisi tertentu.

## Why use Aspose.Page to create XPS document with gradients?

- **Integrasi .NET penuh** – bekerja dengan .NET Framework, .NET Core, dan .NET 5/6+.  
- **Tanpa ketergantungan eksternal** – semua proses rendering ditangani oleh perpustakaan.  
- **Fidelity tinggi** – gradien dirender persis seperti yang didefinisikan, sesuai spesifikasi XPS.  
- **Mudah dipelihara** – model objek yang jelas untuk jalur, kuas, dan warna.

## Prerequisites

- **Aspose.Page untuk .NET Library:** Pastikan Anda telah menginstal perpustakaan Aspose.Page untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- **Lingkungan Pengembangan:** Siapkan lingkungan pengembangan .NET dengan IDE pilihan Anda, seperti Visual Studio.

Sekarang semua sudah siap, mari kita masuk ke kode.

## Import Namespaces

Dalam aplikasi .NET Anda, sertakan namespace yang diperlukan untuk mengakses kelas dan metode Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

Tentukan folder tempat file XPS yang dihasilkan akan disimpan.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

Buat dokumen XPS baru yang nantinya akan diisi dengan jalur berisi gradien.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

Gradient stop menentukan warna dan posisinya sepanjang garis gradien. Di sini kami membuat lima stop untuk menghasilkan transisi vertikal yang halus.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

Kami menggambar jalur berbentuk persegi panjang dan menerapkan **kuas gradien linear** yang berjalan vertikal dari titik (10, 110) ke titik (10, 200). Kuas tersebut menerima gradient stop yang telah didefinisikan sebelumnya.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

Akhirnya, tulis dokumen XPS ke disk. Langkah **save XPS file** ini menghasilkan `AddVerticalGradient_outXPS.xps` di folder yang Anda tentukan.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** Verifikasi output dengan membuka file XPS di Windows XPS Viewer atau penampil pihak ketiga lainnya untuk memastikan gradien muncul seperti yang diharapkan.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Gradien muncul sebagai warna solid | Gradient stop tidak ditambahkan ke kuas | Pastikan `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` dijalankan. |
| File tidak ditemukan saat menyimpan | `dataDir` mengarah ke folder yang tidak ada | Buat direktori terlebih dahulu atau gunakan path absolut. |
| Warna terlihat berbeda | Nilai warna menggunakan urutan ARGB; periksa urutan kanal | Gunakan `CreateColor(alpha, red, green, blue)` dengan benar. |

## Frequently Asked Questions

**Q: Apakah Aspose.Page kompatibel dengan Visual Studio 2019?**  
A: Ya, Aspose.Page kompatibel dengan Visual Studio 2019. Pastikan Anda memiliki versi perpustakaan yang tepat terinstal.

**Q: Bisakah saya menggunakan Aspose.Page untuk proyek komersial?**  
A: Ya, Aspose.Page dapat digunakan untuk proyek komersial. Kunjungi [di sini](https://purchase.aspose.com/buy) untuk menjelajahi opsi lisensi.

**Q: Apakah tersedia versi percobaan gratis?**  
A: Ya, Anda dapat mendapatkan versi percobaan gratis Aspose.Page [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi Aspose.Page?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/page/net/).

**Q: Bagaimana cara mendapatkan dukungan atau mengajukan pertanyaan?**  
A: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

## Conclusion

Anda kini tahu cara **membuat dokumen XPS**, **menerapkan gradien linear**, dan **menyimpan file XPS** menggunakan Aspose.Page untuk .NET. Pendekatan ini memberi Anda kontrol penuh atas gaya visual dalam output XPS, membuat dokumen cetak Anda lebih menonjol.

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page untuk .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
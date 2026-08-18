---
date: 2026-02-23
description: Pelajari cara membuat dokumen XPS dengan gradien diagonal menggunakan
  Aspose.Page untuk .NET dan tingkatkan presentasi visual Anda dengan mudah.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Buat XPS Gradien Diagonal dengan Aspose.Page untuk .NET
url: /id/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat XPS Gradien Diagonal dengan Aspose.Page untuk .NET

## Pendahuluan

Jika Anda perlu **membuat XPS gradien diagonal** yang menarik perhatian, Aspose.Page untuk .NET mempermudah prosesnya. Dalam tutorial ini Anda akan belajar cara menambahkan gradien diagonal ke dokumen XPS, langkah demi langkah, menggunakan API Aspose.Page. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali dan dapat disesuaikan dengan bentuk atau skema warna apa pun.

## Jawaban Cepat
- **Apa yang dilakukan metode API?** Membuat kuas gradien linear yang melintasi secara diagonal sebuah path.  
- **Kelas mana yang mewakili dokumen XPS?** `XpsDocument`.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi.  
- **Bisakah saya mengubah arah gradien?** Ya—sesuaikan nilai `PointF` awal dan akhir.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu **create diagonal gradient xps**?
Gradien diagonal adalah transisi warna yang halus yang berjalan dari satu sudut bentuk ke sudut berlawanan. Dalam XPS, efek ini dicapai dengan menerapkan `LinearGradientBrush` pada properti isi (fill) sebuah path. Library Aspose.Page mengabstraksi markup XPS tingkat rendah, memungkinkan Anda fokus pada warna dan geometri.

## Mengapa menggunakan Aspose.Page untuk gradien diagonal?
- **Rendering berpresisi tinggi** – output sesuai dengan spesifikasi XPS secara tepat.  
- **Integrasi .NET penuh** – bekerja dengan C#, VB.NET, dan bahasa .NET apa pun.  
- **Tanpa ketergantungan eksternal** – semua ditangani dalam proses, tidak memerlukan COM atau Office.  
- **Dapat diskalakan untuk dokumen kompleks** – Anda dapat menggabungkan banyak gradien, gambar, dan teks pada halaman yang sama.

## Prasyarat

1. **Aspose.Page for .NET Library** – unduh di [sini](https://releases.aspose.com/page/net/).  
2. **Lingkungan Pengembangan** – Visual Studio, Rider, atau editor apa pun yang mendukung proyek .NET.  

Sekarang, mari kita selami kode.

## Impor Namespace

Dalam proyek .NET Anda, sertakan namespace yang diperlukan dari library Aspose.Page untuk mengakses kelas dan metode yang dibutuhkan. Tambahkan namespace berikut di awal kode Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Langkah 1: Atur Direktori Dokumen

Mulailah dengan menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen XPS hasil dengan gradien diagonal akan disimpan.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Langkah 2: Buat Dokumen XPS Baru

Inisialisasi `XpsDocument` baru menggunakan library Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Tentukan Warna Gradien

Buat daftar objek `XpsGradientStop`, masing‑masing mewakili warna dalam gradien diagonal.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Langkah 4: Tambahkan Gradien Diagonal ke Path

Buat path baru dengan geometri yang ditentukan, dan terapkan gradien diagonal padanya. Sesuaikan transformasi rendering dan properti isi (fill) sesuai kebutuhan.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Langkah 5: Simpan Dokumen XPS Hasil

Akhirnya, simpan dokumen XPS yang telah dimodifikasi ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Anda kini telah berhasil **membuat file XPS gradien diagonal**. Silakan bereksperimen dengan berbagai titik warna, string geometri, atau matriks transformasi untuk menghasilkan berbagai efek visual.

## Masalah Umum dan Solusinya
- **Gradien tidak terlihat** – Pastikan geometri path tertutup dan titik awal/akhir kuas berada dalam batas path.  
- **Warna tidak tepat** – Pastikan Anda menggunakan `CreateColor` dengan nilai ARGB yang benar; metode ini mengharapkan nilai dalam rentang 0‑255.  
- **File tidak tersimpan** – Periksa bahwa `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menerapkan beberapa gradien pada bagian berbeda dari dokumen?**  
A: Ya, Anda dapat membuat beberapa path dan menerapkan gradien yang berbeda pada masing‑masing.

**Q: Apakah ada gaya gradien bawaan yang tersedia?**  
A: Aspose.Page memungkinkan gradien kustom, memberi Anda kontrol penuh atas transisi warna.

**Q: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?**  
A: Aspose.Page terutama berfokus pada manipulasi dokumen XPS.

**Q: Bagaimana cara menangani kesalahan yang terkait dengan pemrosesan dokumen?**  
A: Lihat [dokumentasi](https://reference.aspose.com/page/net/) untuk praktik terbaik penanganan kesalahan.

**Q: Apakah ada versi percobaan yang tersedia sebelum membeli?**  
A: Ya, Anda dapat menjelajahi [versi percobaan gratis](https://releases.aspose.com/) untuk mencoba Aspose.Page untuk .NET.

**Q: Bagaimana cara mengubah arah gradien menjadi vertikal atau horizontal?**  
A: Modifikasi argumen `PointF` dalam `CreateLinearGradientBrush` untuk menetapkan titik awal dan akhir yang baru.

**Q: Apakah library mendukung transparansi dalam gradien?**  
A: Ya—sertakan nilai alfa saat membuat warna dengan `CreateColor`.

## Kesimpulan

Aspose.Page untuk .NET menyederhanakan proses meningkatkan dokumen XPS dengan gradien diagonal. Panduan ini membawa Anda melalui semua langkah mulai dari menyiapkan prasyarat hingga menyimpan file akhir. Terus bereksperimen dengan berbagai bentuk dan palet warna untuk membuat laporan, brosur, atau faktur XPS Anda benar‑benar menonjol.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose
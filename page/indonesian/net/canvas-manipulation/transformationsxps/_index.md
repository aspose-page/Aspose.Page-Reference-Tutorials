---
date: 2026-01-05
description: Pelajari cara mengubah dokumen XPS dengan mudah menggunakan Aspose.Page
  untuk .NET. Ikuti panduan langkah demi langkah kami untuk transformasi yang mulus.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Cara Mengubah XPS dengan Aspose.Page untuk .NET
url: /id/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Selamat datang di dunia Aspose.Page untuk .NET, sebuah perpustakaan kuat yang memungkinkan Anda melakukan berbagai transformasi pada dokumen XPS dengan mudah. **Dalam tutorial ini, Anda akan menemukan cara mengubah dokumen XPS menggunakan Aspose.Page untuk .NET**, baik Anda seorang pengembang berpengalaman maupun yang baru memulai. Kami akan membimbing Anda melalui setiap langkah, menjelaskan alasan di balik setiap transformasi, dan memberikan tip praktis yang dapat Anda terapkan dalam proyek nyata.

## Jawaban Cepat
- **Apa yang dapat Anda capai?** Buat, terjemahkan, skala, dan putar elemen kanvas XPS secara programatis.  
- **Perpustakaan mana yang diperlukan?** Aspose.Page untuk .NET (versi terbaru).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Platform yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk transformasi dasar yang ditunjukkan di sini.

## Apa itu “cara mengubah xps”?
Frasa *how to transform xps* mengacu pada modifikasi programatis tata letak, ukuran, dan orientasi elemen di dalam dokumen XPS (XML Paper Specification). Dengan menggunakan Aspose.Page, Anda dapat menerapkan transformasi berbasis matriks pada kanvas, memberikan kontrol detail atas posisi, skala, dan rotasi tanpa harus mengedit XML XPS secara manual.

## Mengapa menggunakan Aspose.Page untuk transformasi XPS?
- **Integrasi .NET penuh** – bekerja mulus dengan Visual Studio, Rider, dan IDE lainnya.  
- **Tanpa dependensi eksternal** – API menangani semua detail XPS tingkat rendah untuk Anda.  
- **Dukungan transformasi lengkap** – terjemahkan, skala, putar, dan gabungkan beberapa transformasi dalam satu panggilan.  
- **Dioptimalkan untuk performa** – cocok untuk menghasilkan laporan, faktur, atau grafik cetak apa pun secara dinamis.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- **Aspose.Page untuk .NET Library** – unduh dan instal dari dokumentasi resmi: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Lingkungan Pengembangan** – Visual Studio, Visual Studio Code, atau IDE lain yang kompatibel dengan .NET.  
- **Direktori Dokumen** – folder di mesin Anda tempat Anda akan membaca/menulis file XPS. Ganti placeholder dalam kode dengan path yang sebenarnya.

Sekarang semua sudah siap, mari kita selami kode.

## Impor Namespace

Pertama, impor namespace yang menyediakan kelas Aspose.Page yang Anda perlukan:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Cara Mengubah XPS – Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Dokumen XPS Baru

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Penjelasan*: Kami memulai dengan mendefinisikan folder yang berisi file sumber dan output kami, kemudian membuat instance `XpsDocument` kosong. Objek ini akan menjadi kanvas untuk semua transformasi selanjutnya.

### Langkah 2: Buat Kanvas Utama

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Mengapa ini penting*: Kanvas utama berfungsi sebagai kontainer untuk semua kanvas lainnya. Dengan menerapkan offset kecil, kami memastikan konten tidak terpotong di tepi halaman.

### Langkah 3: Buat Geometri Jalur Persegi Panjang

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: String jalur mengikuti sintaks jalur XPS standar (`M` untuk move, `L` untuk line, `Z` untuk close). Sesuaikan koordinat untuk mengubah ukuran persegi panjang.

### Langkah 4: Tambahkan Isi untuk Persegi Panjang

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Gunakan `CreateColor` dengan nilai RGB untuk menyesuaikan palet merek Anda.

### Langkah 5: Tambahkan Kanvas Baru Tanpa Transformasi

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Di sini kami cukup menempatkan persegi panjang pada halaman tanpa transformasi tambahan—berguna sebagai elemen dasar.

### Langkah 6: Tambahkan Kanvas Baru dengan Transformasi Translasi

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Apa yang terjadi?* Matriks pertama memindahkan persegi panjang ke bawah sebesar 200 unit. Panggilan `Translate` berikutnya menggesernya 500 unit ke kanan, menunjukkan bagaimana beberapa translasi dapat dirangkai.

### Langkah 7: Tambahkan Kanvas Baru dengan Transformasi Skala Ganda

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Mengapa skala?* Skala 2 menggandakan lebar dan tinggi persegi panjang, memungkinkan Anda membuat grafik lebih besar tanpa mendefinisikan ulang geometri.

### Langkah 8: Tambahkan Kanvas Baru dengan Transformasi Rotasi di Sekitar Titik

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Wawasan utama*: `RotateAround` memutar kanvas di sekitar titik khusus (di sini (100, 50)), memberi Anda kontrol detail atas titik pivot rotasi.

### Langkah 9: Simpan Dokumen XPS Hasil

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Setelah semua transformasi diterapkan, dokumen disimpan ke `output1.xps`. Buka file tersebut di penampil XPS apa pun untuk melihat persegi panjang berlapis dengan translasi, skala, dan rotasi masing‑masing.

## Masalah Umum & Pemecahan Masalah

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| File output kosong | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau gunakan path absolut |
| Persegi panjang tidak berada pada posisi yang diharapkan | Nilai matriks tidak tepat | Periksa kembali urutan pemanggilan `Translate`, `Scale`, dan `RotateAround` |
| Warna muncul salah | Nilai RGB di luar rentang 0‑255 | Gunakan nilai byte yang valid untuk setiap kanal |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Page untuk .NET kompatibel dengan semua lingkungan pengembangan .NET?**  
J: Ya, ia bekerja mulus dengan Visual Studio, Visual Studio Code, Rider, dan IDE apa pun yang mendukung .NET.

**T: Di mana saya dapat menemukan contoh tambahan dan dokumentasi API detail?**  
J: Kunjungi dokumentasi resmi di [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**T: Bisakah saya mencoba Aspose.Page sebelum membeli lisensi?**  
J: Tentu saja. Versi percobaan gratis tersedia di sini: [Aspose.Page Free Trial](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk pengujian?**  
J: Anda dapat memintanya melalui halaman lisensi sementara: [Temporary License](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat membeli lisensi penuh?**  
J: Beli langsung dari toko Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Terakhir Diperbarui:** 2026-01-05  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
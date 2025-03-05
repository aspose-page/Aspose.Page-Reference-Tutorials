---
title: Transformasi XPS dengan Aspose.Page untuk .NET
linktitle: Transformasi XPS
second_title: Aspose.Halaman .NET API
description: Ubah dokumen XPS dengan mudah dengan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk transformasi yang lancar.
type: docs
weight: 13
url: /id/net/canvas-manipulation/transformationsxps/
---
## Perkenalan

Selamat datang di dunia Aspose.Page untuk .NET, perpustakaan canggih yang memungkinkan Anda melakukan berbagai transformasi pada dokumen XPS dengan mudah. Dalam tutorial ini, kita akan mendalami proses transformasi dokumen XPS menggunakan Aspose.Page untuk .NET. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui setiap langkah, memastikan Anda memahami konsepnya dengan mudah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

-  Aspose.Page untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Page untuk Dokumentasi .NET](https://reference.aspose.com/page/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang kompatibel, seperti Visual Studio atau alat pengembangan .NET lainnya.

- Direktori Dokumen Anda: Ganti placeholder dalam kode dengan jalur sebenarnya ke direktori dokumen Anda.

Sekarang, mari masuk ke tutorialnya!

## Impor Namespace

Pertama, pastikan Anda mengimpor namespace yang diperlukan untuk membuat fungsionalitas Aspose.Page untuk .NET tersedia dalam kode Anda. Tambahkan namespace berikut di awal skrip Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Buat Dokumen XPS Baru

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```

## Langkah 2: Buat Kanvas Utama

```csharp
// Buat kanvas utama, umum untuk semua elemen halaman
XpsCanvas canvas1 = doc.AddCanvas();

// Buat offset kiri dan atas di kanvas utama
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Langkah 3: Buat Geometri Jalur Persegi Panjang

```csharp
// Buat geometri jalur persegi panjang
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Langkah 4: Tambahkan Isian untuk Persegi Panjang

```csharp
// Buat isian untuk persegi panjang
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Langkah 5: Tambahkan Kanvas Baru Tanpa Transformasi

```csharp
// Tambahkan kanvas baru tanpa transformasi apa pun ke kanvas utama
XpsCanvas canvas2 = canvas1.AddCanvas();

// Buat persegi panjang di kanvas ini dan isi
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Langkah 6: Tambahkan Kanvas Baru dengan Transformasi Terjemahan

```csharp
// Tambahkan kanvas baru dengan transformasi terjemahan ke kanvas utama
XpsCanvas canvas3 = canvas1.AddCanvas();

// Terjemahkan kanvas ini untuk memposisikan persegi panjang baru di bawah persegi panjang sebelumnya
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Terjemahkan kanvas ini ke sisi kanan halaman
canvas3.RenderTransform.Translate(500, 0);

// Buat persegi panjang di kanvas ini dan isi
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Langkah 7: Tambahkan Kanvas Baru dengan Transformasi Skala Ganda

```csharp
//Tambahkan kanvas baru dengan transformasi skala ganda ke kanvas utama
XpsCanvas canvas4 = canvas1.AddCanvas();

// Terjemahkan kanvas ini untuk memposisikan persegi panjang baru di bawah persegi panjang sebelumnya
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Skala kanvas ini
canvas4.RenderTransform.Scale(2, 2);

// Buat persegi panjang di kanvas ini dan isi
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Langkah 8: Tambahkan Kanvas Baru dengan Transformasi Rotasi Di Sekitar Titik

```csharp
// Tambahkan kanvas baru dengan rotasi di sekitar transformasi titik ke kanvas utama
XpsCanvas canvas5 = canvas1.AddCanvas();

// Terjemahkan kanvas ini untuk memposisikan persegi panjang baru di bawah persegi panjang sebelumnya
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Putar kanvas ini di sekitar titik sebesar 45 derajat
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Buat persegi panjang di kanvas ini dan isi
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Langkah 9: Simpan Dokumen XPS yang Dihasilkan

```csharp
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Kesimpulan

Selamat! Anda telah berhasil mengubah dokumen XPS menggunakan Aspose.Page untuk .NET. Panduan ini mencakup langkah-langkah penting, mulai dari menyiapkan prasyarat hingga melakukan berbagai transformasi. Bereksperimenlah dengan teknik ini dan buka potensi penuh Aspose.Page untuk .NET dalam proyek Anda.

## FAQ

### Q1: Apakah Aspose.Page untuk .NET kompatibel dengan semua lingkungan pengembangan .NET?

A1: Ya, Aspose.Page untuk .NET dirancang untuk bekerja secara lancar dengan berbagai lingkungan pengembangan .NET, termasuk Visual Studio.

### Q2: Di mana saya dapat menemukan contoh dan dokumentasi tambahan untuk Aspose.Page untuk .NET?

 A2: Kunjungi[Aspose.Page untuk Dokumentasi .NET](https://reference.aspose.com/page/net/) untuk dokumentasi dan contoh yang komprehensif.

### Q3: Dapatkah saya mencoba Aspose.Page untuk .NET sebelum membeli?

 A3: Ya, Anda dapat menjelajahi versi uji coba gratis dengan mengunjungi[Uji Coba Gratis Aspose.Halaman](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A4: Dapatkan lisensi sementara dengan mengunjungi[Lisensi Sementara](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat membeli Aspose.Page untuk .NET?

 A5: Beli Aspose.Page untuk .NET di[Aspose. Pembelian Halaman](https://purchase.aspose.com/buy).
---
title: Pangkas Gambar EPS dengan Aspose.Page untuk .NET
linktitle: Pangkas Gambar EPS
second_title: Aspose.Halaman .NET API
description: Jelajahi dunia manipulasi gambar EPS yang mulus di .NET dengan Aspose.Page. Pangkas dan ubah ukuran gambar dengan mudah untuk hasil yang menakjubkan.
weight: 10
url: /id/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pangkas Gambar EPS dengan Aspose.Page untuk .NET

## Perkenalan

Apakah Anda kesulitan memanipulasi gambar EPS di aplikasi .NET Anda? Tidak perlu mencari lagi! Dalam tutorial ini, kami akan memandu Anda melalui proses memotong gambar EPS menggunakan pustaka Aspose.Page untuk .NET yang canggih. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan langkah demi langkah ini akan membantu Anda mencapai pemotongan gambar yang tepat dengan mudah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan kerja tentang pengembangan .NET.
-  Aspose.Page untuk perpustakaan .NET diinstal. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/page/net/).
- Contoh gambar EPS (ganti "input.eps" dalam kode dengan file Anda yang sebenarnya).

## Impor Namespace

Mari kita mulai dengan mengimpor namespace yang diperlukan agar kode kita dapat berjalan dengan lancar. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Sekarang, mari kita bagi tutorialnya menjadi beberapa langkah.

## Langkah 1: Inisialisasi PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Inisialisasi a`PsDocument` objek dengan aliran input EPS.

## Langkah 2: Ekstrak Kotak Pembatas

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Ambil kotak pembatas awal gambar EPS.

## Langkah 3: Buat Aliran Keluaran

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Buat aliran keluaran untuk gambar EPS yang dipotong.

## Langkah 4: Tentukan Kotak Batas Baru

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Tentukan kotak pembatas baru untuk dipotong. Pastikan nilai baru berada dalam kotak pembatas awal.

## Langkah 5: Pangkas dan Simpan

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Pangkas gambar EPS menggunakan kotak pembatas baru dan simpan ke aliran keluaran.

Ulangi langkah-langkah ini untuk skenario pengubahan ukuran yang berbeda.

## Mengubah ukuran Gambar EPS

### Ubah ukuran dalam Inci

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Ubah ukuran gambar EPS dan simpan dengan dimensi yang ditentukan dalam inci.

### Ubah ukuran dalam Milimeter

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Ubah ukuran gambar EPS dan simpan dengan dimensi yang ditentukan dalam milimeter.

### Ubah ukuran dalam Persen

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Ubah ukuran gambar EPS dan simpan dengan dimensi yang ditentukan dalam persentase.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara memotong dan mengubah ukuran gambar EPS menggunakan Aspose.Page untuk .NET. Sekarang, tingkatkan kemampuan manipulasi gambar Anda dan bawa aplikasi .NET Anda ke level berikutnya.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format gambar lain?

A1: Aspose.Page terutama berfokus pada gambar EPS, tetapi Aspose menyediakan berbagai perpustakaan untuk format berbeda. Periksa dokumentasinya untuk format tertentu.

### Q2: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A2: Kunjungi[Link ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan izin sementara untuk pengujian.

### Q3: Apakah ada batasan ukuran gambar yang dapat saya proses dengan Aspose.Page untuk .NET?

A3: Aspose.Page dirancang untuk menangani gambar dengan berbagai ukuran. Namun, performa dapat bervariasi berdasarkan kompleksitas gambar.

### Q4: Apakah ada forum komunitas untuk diskusi Aspose.Page?

 A4: Ya, Anda dapat terlibat dengan komunitas Aspose.Page[Di Sini](https://forum.aspose.com/c/page/39).

### Q5: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Page untuk .NET?

 A5: Lihat dokumentasi[Di Sini](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

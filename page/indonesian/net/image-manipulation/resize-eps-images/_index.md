---
title: Ubah ukuran Gambar EPS dengan Aspose.Page untuk .NET
linktitle: Ubah ukuran Gambar EPS
second_title: Aspose.Halaman .NET API
description: Jelajahi proses yang mulus dalam mengubah ukuran gambar EPS di .NET menggunakan Aspose.Page. Mencapai presisi dalam poin, inci, milimeter, dan persentase dengan mudah.
type: docs
weight: 11
url: /id/net/image-manipulation/resize-eps-images/
---
## Perkenalan

Apakah Anda ingin mengubah ukuran gambar EPS dengan lancar menggunakan Aspose.Page untuk .NET? Tutorial ini adalah panduan komprehensif Anda untuk dengan mudah memanipulasi ukuran gambar EPS dalam berbagai satuan seperti titik, inci, milimeter, dan persentase. Aspose.Page untuk .NET menyediakan seperangkat alat canggih, dan dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah.

## Prasyarat

Sebelum mempelajari keajaiban pengubahan ukuran, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Page untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).

- Direktori Dokumen: Buat direktori tempat Anda menyimpan file input EPS dan file output yang diubah ukurannya.

Sekarang setelah semuanya siap, mari lanjutkan mengimpor namespace yang diperlukan dan mempelajari panduan langkah demi langkah.

## Impor Namespace

Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Page. Tambahkan kode berikut di awal file Anda:

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

## Langkah 1: Mengubah Ukuran Poin

Mari kita mulai dengan mengubah ukuran gambar EPS dalam poin. Poin adalah satuan pengukuran standar dalam industri percetakan.

```csharp
public static void ResizeInPoints()
{
    // Direktori Dokumen Anda
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Langkah 2: Mengubah Ukuran dalam Inci

Sekarang, mari kita ubah ukuran gambar EPS dalam inci, satuan umum yang digunakan dalam desain grafis.

```csharp
public static void ResizeInInches()
{
    // Direktori Dokumen Anda
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Langkah 3: Mengubah Ukuran dalam Milimeter

Sekarang, mari kita ubah ukuran gambar EPS dalam milimeter, satuan lain yang banyak digunakan dalam desain dan pencetakan.

```csharp
public static void ResizeInMillimeters()
{
    // Direktori Dokumen Anda
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Langkah 4: Mengubah Ukuran dalam Persen

Terakhir, mari kita ubah ukuran gambar EPS menggunakan persentase, yang memberikan pendekatan fleksibel untuk menyesuaikan ukuran gambar.

```csharp
public static void ResizeInPercents()
{
    // Direktori Dokumen Anda
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Jangan ragu untuk mengintegrasikan metode ini ke dalam proyek Anda, dan Anda akan mengubah ukuran gambar EPS dengan mudah. Bereksperimenlah dengan unit yang berbeda untuk mencapai dimensi yang diinginkan.

## Kesimpulan

Selamat! Anda telah menguasai seni mengubah ukuran gambar EPS dengan Aspose.Page untuk .NET. Perpustakaan yang kuat ini membuka banyak kemungkinan untuk memanipulasi grafik vektor. Baik Anda mendesain untuk media cetak atau digital, Aspose.Page memberdayakan Anda untuk mencapai hasil yang tepat dan disesuaikan.

## FAQ

### Q1: Dapatkah saya mengubah ukuran beberapa gambar EPS secara bersamaan?

A1: Ya, Anda dapat menelusuri kumpulan file EPS, menerapkan metode pengubahan ukuran yang sesuai.

### Q2: Apakah Aspose.Page kompatibel dengan format gambar lainnya?

A2: Aspose.Page terutama berfokus pada format PostScript dan EPS. Untuk format gambar lainnya, pertimbangkan untuk menggunakan Aspose.Imaging.

### Q3: Apakah ada pertimbangan perizinan untuk proyek komersial?

 A3: Ya, pastikan Anda memiliki lisensi yang valid. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk rincian perizinan.

### Q4: Dapatkah saya mencoba Aspose.Page sebelum membeli?

 A4: Tentu saja! Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Q5: Di mana saya dapat mencari bantuan tambahan atau mendiskusikan masalah?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk berhubungan dengan masyarakat dan mendapatkan bantuan.
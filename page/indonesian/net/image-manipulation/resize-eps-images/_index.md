---
date: 2026-03-03
description: Pelajari cara mengubah ukuran gambar EPS di .NET dengan Aspose.Page –
  panduan langkah demi langkah tentang cara mengubah ukuran EPS menggunakan poin,
  inci, milimeter, atau persentase.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Cara Mengubah Ukuran Gambar EPS dengan Aspose.Page untuk .NET
url: /id/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah Ukuran Gambar EPS dengan Aspose.Page untuk .NET

## Pendahuluan

Apakah Anda mencari **cara mengubah ukuran EPS** secara mulus menggunakan Aspose.Page untuk .NET? Tutorial ini adalah panduan komprehensif Anda untuk dengan mudah memanipulasi ukuran gambar EPS dalam berbagai satuan seperti poin, inci, milimeter, dan persentase. Aspose.Page untuk .NET menyediakan rangkaian alat yang kuat, dan dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pengubahan ukuran EPS?** Aspose.Page for .NET  
- **Satuan apa yang didukung?** Points, Inches, Millimeters, and Percents  
- **Apakah saya memerlukan lisensi untuk produksi?** Yes – a commercial license is required  
- **Bisakah saya mengubah ukuran beberapa file sekaligus?** Absolutely – just loop through the files  
- **Apakah .NET Core didukung?** Yes, the API works with .NET Framework and .NET Core  

## Apa itu Pengubahan Ukuran EPS?
Encapsulated PostScript (EPS) adalah format grafik berbasis vektor yang umum digunakan dalam alur kerja cetak dan desain. Mengubah ukuran file EPS mengubah bounding box-nya tanpa merasterkan karya seni, sehingga mempertahankan ketajaman pada skala apa pun.

## Mengapa Mengubah Ukuran Gambar EPS?
- **Mempertahankan Kualitas Cetak:** Skala vektor menjaga tepi tetap tajam.  
- **Menyesuaikan Persyaratan Tata Letak:** Sesuaikan dimensi agar cocok dengan ukuran halaman atau kanvas.  
- **Mengotomatiskan Pekerjaan Batch:** Mengubah ukuran secara programatik puluhan file dalam hitungan detik.  

## Prasyarat

Sebelum menyelami proses pengubahan ukuran, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page for .NET Library: Pastikan Anda telah menginstal pustaka Aspose.Page untuk .NET. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/page/net/).

- Document Directory: Buat sebuah direktori tempat Anda akan menyimpan file EPS input dan file hasil ubah ukuran.

Setelah semuanya siap, mari lanjutkan dengan mengimpor namespace yang diperlukan dan menyelami panduan langkah demi langkah.

## Impor Namespace

Dalam proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Page. Tambahkan kode berikut di awal file Anda:

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

## Cara Mengubah Ukuran EPS dalam Poin

Poin adalah satuan ukuran standar dalam industri percetakan. Contoh di bawah menggandakan lebar dan tinggi asli.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## Cara Mengubah Ukuran EPS dalam Inci

Inci sering digunakan oleh desainer grafis saat menyiapkan aset untuk cetak.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## Cara Mengubah Ukuran EPS dalam Milimeter

Milimeter umum digunakan di wilayah yang memakai sistem metrik.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## Cara Mengubah Ukuran EPS Menggunakan Persentase

Pengubahan ukuran berbasis persentase memungkinkan Anda menskalakan gambar relatif terhadap ukuran aslinya.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Silakan integrasikan metode ini ke dalam proyek Anda, dan Anda akan mengubah ukuran gambar EPS dengan mudah. Bereksperimenlah dengan berbagai satuan untuk mencapai dimensi yang diinginkan.

## Masalah Umum dan Solusinya
- **File not found:** Verifikasi bahwa `dataDir` mengarah ke folder yang benar dan bahwa `input.eps` ada.  
- **Unexpected size:** Ingat bahwa `Units.Percents` mengharapkan nilai seperti 150 untuk 150 % dari ukuran asli.  
- **License exception:** Jika Anda melihat kesalahan lisensi, pastikan file lisensi Aspose.Page yang valid dimuat sebelum membuat `PsDocument`.  

## Kesimpulan

Selamat! Anda telah menguasai **cara mengubah ukuran EPS** dengan Aspose.Page untuk .NET. Pustaka yang kuat ini membuka dunia kemungkinan untuk memanipulasi grafik vektor. Baik Anda merancang untuk cetak maupun media digital, Aspose.Page memberi Anda kemampuan untuk mencapai hasil yang tepat dan disesuaikan.

## FAQ

### Q1: Bisakah saya mengubah ukuran beberapa gambar EPS secara bersamaan?

A1: Ya, Anda dapat melakukan loop melalui koleksi file EPS, menerapkan metode pengubahan ukuran secara sesuai.

### Q2: Apakah Aspose.Page kompatibel dengan format gambar lain?

A2: Aspose.Page terutama berfokus pada format PostScript dan EPS. Untuk format gambar lain, pertimbangkan menggunakan Aspose.Imaging.

### Q3: Apakah ada pertimbangan lisensi untuk proyek komersial?

A3: Ya, pastikan Anda memiliki lisensi yang valid. Kunjungi [here](https://purchase.aspose.com/buy) untuk detail lisensi.

### Q4: Bisakah saya mencoba Aspose.Page sebelum membeli?

A4: Tentu saja! Anda dapat mendapatkan percobaan gratis [here](https://releases.aspose.com/).

### Q5: Di mana saya dapat mencari bantuan tambahan atau mendiskusikan masalah?

A5: Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan bantuan.

## Pertanyaan yang Sering Diajukan

**Q: Apakah kode ini bekerja dengan .NET Core 6?**  
A: Ya. API kompatibel dengan .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, dan .NET 6+.

**Q: Bagaimana saya dapat mempertahankan profil warna asli?**  
A: Metode `ResizeEps` tidak mengubah data warna; hanya mengubah bounding box.

**Q: Apakah memungkinkan mengubah ukuran EPS tanpa memuat seluruh file ke memori?**  
A: Menggunakan stream seperti yang ditunjukkan menjaga penggunaan memori tetap rendah; dokumen diproses secara langsung.

**Q: Bisakah saya menumpuk beberapa operasi pengubahan ukuran?**  
A: Tentu saja. Panggil `ResizeEps` secara berurutan pada instance `PsDocument` yang sama.

**Q: Apa yang terjadi pada gambar yang tersemat di dalam EPS?**  
A: Mereka diskalakan secara proporsional dengan konten vektor, mempertahankan kualitas.

---

**Terakhir Diperbarui:** 2026-03-03  
**Diuji Dengan:** Aspose.Page 24.12 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
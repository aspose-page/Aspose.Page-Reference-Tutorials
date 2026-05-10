---
date: 2026-03-16
description: Pelajari cara memotong gambar EPS dan mengubah ukuran file gambar EPS
  di .NET menggunakan Aspose.Page. Ikuti panduan langkah demi langkah ini untuk memotong
  EPS dan mengubah ukuran gambar EPS dengan mudah.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Cara Memotong Gambar EPS dengan Aspose.Page untuk .NET
url: /id/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Memotong Gambar EPS dengan Aspose.Page untuk .NET

## Pendahuluan

Jika Anda perlu mengetahui **cara memotong gambar EPS** dalam aplikasi .NET, Anda berada di tempat yang tepat. Pada tutorial ini kami akan memandu Anda melalui proses memotong dan mengubah ukuran file EPS menggunakan pustaka Aspose.Page untuk .NET yang kuat. Baik Anda sedang menyempurnakan alat pelaporan atau menyiapkan grafik untuk layanan web, menguasai teknik ini akan menghemat waktu dan memberikan hasil yang pixel‑perfect.

## Jawaban Cepat
- **Pustaka apa yang menangani pemotongan EPS?** Aspose.Page untuk .NET  
- **Metode utama?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Bisakah saya juga mengubah ukuran EPS?** Ya – gunakan `ResizeEps` dengan inci, milimeter, atau persen.  
- **Prasyarat?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page terpasang, sebuah file EPS.  
- **Waktu implementasi tipikal?** Sekitar 10 menit untuk alur kerja potong‑dan‑ubah‑ukuran dasar.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

- Pengetahuan dasar tentang pengembangan .NET.  
- Pustaka Aspose.Page untuk .NET terinstal. Jika belum, Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- Contoh gambar EPS (ganti `"input.eps"` dalam kode dengan file Anda yang sebenarnya).

## Impor Namespace

Mari mulai dengan mengimpor namespace yang memberi kita akses ke kelas penanganan EPS.

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

## Cara Memotong Gambar EPS – Panduan Langkah‑per‑Langkah

### Langkah 1: Inisialisasi `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Kami membuat instance `PsDocument` dari aliran EPS input. Objek ini mewakili file EPS dalam memori dan memberi kami akses ke metode pemotongan serta pengubahan ukuran.

### Langkah 2: Ekstrak Bounding Box Asli

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Bounding box memberi tahu Anda dimensi kanvas EPS saat ini. Mengetahui nilai‑nilai ini membantu Anda menentukan persegi pemotongan yang aman.

### Langkah 3: Buat Aliran Output

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Kami membuka aliran yang dapat ditulis di mana EPS yang dipotong akan disimpan. Menggunakan blok `using` menjamin aliran ditutup dengan benar.

### Langkah 4: Definisikan Bounding Box Baru

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Ganti angka‑angka dengan koordinat yang ingin Anda pertahankan. Pastikan nilai baru tetap berada di dalam bounding box asli; jika tidak operasi akan gagal.

### Langkah 5: Potong dan Simpan EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Baris tunggal ini melakukan pemotongan dan menulis hasilnya ke `output_crop.eps`. Metode ini memodifikasi dokumen dalam memori, sehingga Anda dapat menambahkan operasi lain jika diperlukan.

## Ubah Ukuran Gambar EPS

Setelah memotong, Anda sering ingin mengubah ukuran EPS untuk tampilan atau pencetakan. Aspose.Page mendukung tiga satuan ukuran.

### Ubah Ukuran dalam Inci

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Ubah Ukuran dalam Milimeter

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Ubah Ukuran dalam Persen

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Setiap pemanggilan menimpa output sebelumnya, jadi pastikan membuat aliran baru jika Anda memerlukan file terpisah untuk setiap ukuran.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| **Nilai bounding box di luar jangkauan** | Kotak baru melebihi dimensi asli | Verifikasi nilai `initialBoundingBox` dan pilih koordinat di dalam rentang tersebut. |
| **File output kosong** | Aliran output tidak di‑flush atau tidak ditutup | Pastikan blok `using` selesai sebelum mengakses file, atau panggil `outputEpsStream.Flush()`. |
| **Skala tidak terduga** | Campur satuan (mis., inci vs. milimeter) | Selalu tentukan enum `Units` yang tepat sesuai nilai ukuran Anda. |

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format gambar lain?

A1: Aspose.Page terutama berfokus pada gambar EPS, tetapi Aspose menyediakan berbagai pustaka untuk format yang berbeda. Periksa dokumentasi mereka untuk format spesifik.

### Q2: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

A2: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan lisensi sementara untuk pengujian.

### Q3: Apakah ada batasan ukuran gambar yang dapat saya proses dengan Aspose.Page untuk .NET?

A3: Aspose.Page dirancang untuk menangani gambar dengan berbagai ukuran. Namun, kinerja dapat bervariasi tergantung pada kompleksitas gambar.

### Q4: Apakah ada forum komunitas untuk diskusi Aspose.Page?

A5: Ya, Anda dapat berinteraksi dengan komunitas Aspose.Page [di sini](https://forum.aspose.com/c/page/39).

### Q5: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Page untuk .NET?

A5: Lihat dokumentasi [di sini](https://reference.aspose.com/page/net/).

---

**Terakhir Diperbarui:** 2026-03-16  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
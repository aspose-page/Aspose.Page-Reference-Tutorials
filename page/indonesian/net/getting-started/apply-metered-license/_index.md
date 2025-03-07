---
title: Terapkan Lisensi Terukur dengan Aspose.Page untuk .NET
linktitle: Terapkan Lisensi Terukur
second_title: Aspose.Halaman .NET API
description: Jelajahi integrasi Aspose.Page untuk .NET yang lancar dengan panduan langkah demi langkah dalam menerapkan lisensi terukur. Optimalkan pemrosesan dokumen dengan mudah.
weight: 10
url: /id/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Terapkan Lisensi Terukur dengan Aspose.Page untuk .NET

## Perkenalan

Buka potensi penuh Aspose.Page untuk .NET dengan menerapkan lisensi terukur. Tutorial ini akan memandu Anda melalui proses pengaturan dan penerapan lisensi terukur, memastikan penggunaan perpustakaan .NET yang canggih ini lancar dan optimal.

## Prasyarat

Sebelum mendalami langkah-langkahnya, pastikan Anda memiliki prasyarat berikut:

-  Lisensi Aspose.Page untuk .NET yang valid: Anda dapat memperolehnya dari[pembelian.aspose.com](https://purchase.aspose.com/buy).
-  Pustaka Aspose.Page terinstal: Lihat[dokumentasi](https://reference.aspose.com/page/net/) untuk petunjuk pemasangan.
- Lingkungan pengembangan .NET: Pastikan Anda memiliki lingkungan .NET yang berfungsi di mesin Anda.

## Impor Namespace

Di proyek .NET Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Langkah 1: Tetapkan Kunci Publik dan Pribadi Terukur

 Inisialisasi`Aspose.Page.Metered` kelas dan mengatur kunci publik dan pribadi terukur. Mengganti`<type public key here>` Dan`<type private key here>` dengan kunci Anda yang sebenarnya.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Langkah 2: Muat File EPS dan Buat Dokumen

 Tentukan jalur ke file EPS Anda dan buat aliran untuk membaca kontennya. Kemudian, buat sebuah instance dari`PsDocument` kelas dari sungai.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Langkah 3: Konversi Gambar EPS ke PNG

 Buat sebuah`ImageDevice` untuk mengonversi file EPS menjadi gambar PNG. Simpan file EPS sebagai gambar menggunakan`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Langkah 4: Ambil Byte Gambar

Dapatkan byte gambar, di mana setiap array byte mewakili satu halaman. Dalam hal ini, kami memiliki satu halaman.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Langkah 5: Simpan Byte Gambar ke File

Simpan byte gambar ke file, pastikan konversi sukses dari EPS ke PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Langkah 6: Verifikasi Lisensi Terukur

Periksa secara visual apakah izin terukur berhasil diterapkan. Jika gambar yang dihasilkan tidak berisi pesan evaluasi berwarna merah, ini menunjukkan bahwa lisensi terukur diterapkan tanpa masalah apa pun.

Sekarang Anda siap memanfaatkan kemampuan penuh Aspose.Page untuk .NET dengan lisensi terukur!

## Kesimpulan

Panduan langkah demi langkah ini telah membekali Anda dengan pengetahuan untuk menerapkan lisensi terukur dengan lancar menggunakan Aspose.Page untuk .NET. Tingkatkan kemampuan pemrosesan dokumen Anda dan jelajahi fitur luas yang ditawarkan oleh perpustakaan canggih ini.

## FAQ

### Q1: Bagaimana cara mendapatkan lisensi terukur untuk Aspose.Page untuk .NET?

 A1: Kunjungi[pembelian.aspose.com](https://purchase.aspose.com/buy) untuk memperoleh lisensi yang sah.

### Q2: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk .NET?

 A2: Lihat[Aspose.Halaman .NET](https://reference.aspose.com/page/net/) untuk dokumentasi yang komprehensif.

### Q3: Apakah ada forum untuk diskusi dan dukungan Aspose.Page?

 A3: Ya, kunjungi[forum](https://forum.aspose.com/c/page/39) untuk terlibat dengan masyarakat dan mencari bantuan.

### Q4: Dapatkah saya mencoba Aspose.Page untuk .NET sebelum membeli?

 A4: Tentu saja! Akses uji coba gratis di[Di Sini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?

 A5: Kunjungi[izin sementara/](https://purchase.aspose.com/temporary-license/) untuk mendapatkan izin sementara.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

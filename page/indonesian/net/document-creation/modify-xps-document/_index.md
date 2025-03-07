---
title: Ubah Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Ubah Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi kekuatan Aspose.Page untuk .NET untuk memodifikasi dokumen XPS dengan mudah. Ikuti panduan langkah demi langkah kami, tingkatkan pemrosesan dokumen Anda, dan tambahkan teks tanda tangan yang dipersonalisasi.
weight: 12
url: /id/net/document-creation/modify-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah Dokumen XPS dengan Aspose.Page untuk .NET

## Perkenalan

Selamat datang di panduan langkah demi langkah kami tentang cara memodifikasi dokumen XPS menggunakan Aspose.Page untuk .NET. Aspose.Page adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file XPS dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan teks tanda tangan, "Dikonfirmasi," ke halaman tertentu dalam dokumen XPS.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page. Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/page/net/).

-  Unduh File yang Diperlukan: Unduh file yang diperlukan, termasuk dokumen input XPS, dari[Halaman rilis Aspose](https://releases.aspose.com/page/net/).

-  Direktori Dokumen: Siapkan direktori untuk dokumen Anda dan perbarui`dir` variabel dalam kode dengan jalur yang sesuai.

Sekarang setelah semuanya siap, mari selami panduan langkah demi langkah.

## Impor Namespace

Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Langkah 1: Buka Aliran Dokumen XPS

```csharp
// MantanMulai:3
// Jalur ke direktori dokumen.
string dir = "Your Document Directory";
// Buka aliran file XPS
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Buat dokumen PS dari aliran
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Lanjutkan ke langkah berikutnya...
}
// ExEnd:3
```

## Langkah 2: Buat Teks Tanda Tangan

```csharp
// MantanMulai:4
// Buat isi teks tanda tangan
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Lanjutkan ke langkah berikutnya...
// ExEnd:4
```

## Langkah 3: Tentukan Halaman dan Tambahkan Tanda Tangan

```csharp
// MantanMulai:5
// Tentukan halaman di mana tanda tangan akan ditetapkan
int[] pageNumbers = new int[] {1, 2, 3};

//Untuk setiap halaman yang ditentukan, setel tanda tangan "Dikonfirmasi" pada koordinat x=650 dan y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Tentukan halaman aktif
    document.SelectActivePage(pageNumbers[i]);

    // Buat objek mesin terbang
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Tentukan isian untuk mesin terbang
    glyphs.Fill = textFill;
}
// Lanjutkan ke langkah berikutnya...
// ExEnd:5
```

## Langkah 4: Simpan Perubahan pada Dokumen XPS

```csharp
// MantanMulai:6
// Simpan dokumen XPS yang diubah
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Selamat! Anda telah berhasil memodifikasi dokumen XPS menggunakan Aspose.Page untuk .NET. Jangan ragu untuk menjelajahi fitur dan fungsi tambahan yang ditawarkan oleh Aspose.Page untuk meningkatkan pemrosesan dokumen Anda.

## Kesimpulan

Dalam tutorial ini, kami membahas langkah-langkah penting untuk memodifikasi dokumen XPS menggunakan Aspose.Page untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan teks tanda tangan ke halaman tertentu, menambahkan sentuhan personal pada dokumen Anda.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan kerangka .NET terbaru?

A1: Ya, Aspose.Page diperbarui secara berkala untuk mendukung kerangka .NET terbaru.

### Q2: Dapatkah saya menyesuaikan font dan gaya teks yang ditambahkan?

A2: Tentu saja! Anda dapat mengubah font, gaya, dan atribut lainnya sesuai kebutuhan Anda.

### Q3: Apakah ada batasan ukuran dokumen yang dapat ditangani Aspose.Page?

A3: Aspose.Page dirancang untuk menangani dokumen dengan berbagai ukuran, namun selalu disarankan untuk memeriksa dokumentasi untuk detail spesifik.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?

 A4: Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat mencari bantuan atau terhubung dengan komunitas Aspose?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk bertanya dan terlibat dengan komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

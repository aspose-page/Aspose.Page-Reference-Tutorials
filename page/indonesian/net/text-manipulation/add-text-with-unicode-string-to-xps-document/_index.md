---
title: Tambahkan Teks dengan String Unicode ke Dokumen XPS dengan Aspose.Page
linktitle: Tambahkan Teks dengan String Unicode ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi kekuatan Aspose.Page untuk .NET dengan panduan langkah demi langkah kami tentang menambahkan teks Unicode ke dokumen XPS.
type: docs
weight: 12
url: /id/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Perkenalan

Dalam lanskap pengembangan .NET yang terus berkembang, Aspose.Page menonjol sebagai alat yang ampuh untuk menangani dokumen XPS. Di antara banyak fiturnya, kemampuan untuk menambahkan teks dengan string Unicode ke dokumen XPS adalah fungsi yang berharga. Panduan langkah demi langkah ini akan memandu Anda melalui proses tersebut, memastikan Anda memanfaatkan kemampuan ini secara efektif.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar tentang pengembangan .NET.
- Visual Studio diinstal pada mesin Anda.
-  Aspose.Page untuk perpustakaan .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/net/).

## Impor Namespace

Untuk memulai, pastikan Anda mengimpor namespace yang diperlukan ke dalam proyek Anda. Ini akan menyediakan kelas dan fungsi yang diperlukan untuk bekerja dengan Aspose.Page. Berikut adalah namespace penting:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Siapkan Dokumen

Pertama, buat dokumen XPS baru di mana Anda akan menambahkan teks Unicode. Ikuti cuplikan kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```

## Langkah 2: Tambahkan Teks Unicode

Sekarang, mari tambahkan teks Unicode ke dokumen XPS. Contoh ini menggunakan font Arial, mengatur ukuran font menjadi 20, dan memposisikan teks pada koordinat (400f, 200f). String Unicode dalam hal ini adalah "TEN.rof SPX.esopsA". Lihat cuplikan kode di bawah ini:

```csharp
// Tambahkan teks
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Langkah 3: Simpan Dokumen

Setelah teks Unicode ditambahkan, simpan dokumen XPS yang dihasilkan. Inilah langkah terakhir:

```csharp
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Selamat! Anda telah berhasil menambahkan teks Unicode ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi proses menambahkan teks Unicode ke dokumen XPS menggunakan Aspose.Page untuk .NET. Fungsionalitas ini membuka pintu bagi pembuatan dokumen yang beragam dan dinamis dalam lingkungan .NET.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan kerangka .NET terbaru?

A1: Ya, Aspose.Page diperbarui secara berkala untuk memastikan kompatibilitas dengan kerangka .NET terbaru.

### Q2: Dapatkah saya menyesuaikan gaya dan ukuran font saat menambahkan teks?

A2: Tentu saja! Kode contoh yang diberikan memungkinkan Anda menyesuaikan gaya font, ukuran, dan atribut lainnya dengan mudah.

### Q3: Di mana saya dapat menemukan dokumentasi tambahan untuk Aspose.Page?

 A3: Anda dapat merujuk ke dokumentasi[Di Sini](https://reference.aspose.com/page/net/) untuk informasi lengkap dan contoh.

### Q4: Apakah ada sumber daya gratis untuk memulai Aspose.Page?

 A4: Ya, Anda dapat menjelajahinya[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.

### Q5: Apakah tersedia versi uji coba sebelum melakukan pembelian?

 A5: Tentu saja! Anda dapat mengakses versi uji coba gratis[Di Sini](https://releases.aspose.com/) sebelum melakukan pembelian.
---
title: Buat Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Buat Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi dunia pembuatan dokumen XPS dengan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk membuat dokumen elektronik dengan mudah.
type: docs
weight: 10
url: /id/net/document-creation/create-xps-document/
---
## Perkenalan

Selamat datang di panduan langkah demi langkah kami dalam membuat dokumen XPS menggunakan Aspose.Page untuk .NET. Dalam tutorial ini, kita akan mengeksplorasi proses pembuatan file XPS, format yang banyak digunakan untuk dokumen elektronik. Baik Anda seorang pengembang berpengalaman atau baru memulai Aspose.Page, panduan ini dirancang untuk membantu Anda membuat dokumen XPS dengan lancar dengan contoh jelas dan penjelasan mendetail.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Page untuk .NET Library: Unduh dan instal perpustakaan Aspose.Page dari[tautan unduhan](https://releases.aspose.com/page/net/).

2. Direktori Dokumen Anda: Pilih atau buat direktori di sistem Anda tempat Anda ingin menyimpan file XPS keluaran.

Sekarang, mari masuk ke tutorialnya!

## Impor Namespace

Untuk menggunakan Aspose.Page untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah ini:

### Langkah 1: Tambahkan Referensi ke Aspose.Page

Dalam proyek Anda, tambahkan referensi ke perpustakaan Aspose.Page untuk .NET. Anda dapat menemukan DLL yang diperlukan dalam paket yang diunduh.

### Langkah 2: Impor Namespace

Sertakan namespace berikut dalam file kode Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang kita telah menyiapkan prasyarat dan mengimpor namespace yang diperlukan, mari kita bagi proses pembuatan dokumen XPS menjadi beberapa langkah.

## Langkah 1: Atur Direktori Dokumen

```csharp
string dir = "Your Document Directory";
```

 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan file XPS keluaran.

## Langkah 2: Buat Dokumen XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

 Inisialisasi dokumen XPS baru menggunakan`XpsDocument` kelas.

## Langkah 3: Tambahkan Mesin Terbang ke Dokumen

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 Menggunakan`AddGlyphs` metode untuk menambahkan mesin terbang (teks) ke dokumen. Sesuaikan font, ukuran, gaya, dan posisi sesuai kebutuhan.

## Langkah 4: Atur Warna Isi Glyph

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Tentukan warna isian untuk mesin terbang yang ditambahkan. Dalam contoh ini, kami menggunakan warna hitam, tetapi Anda dapat memilih warna apa pun.

## Langkah 5: Simpan Hasilnya

```csharp
xDocs.Save(dir + "output.xps");
```

Terakhir, simpan dokumen XPS ke direktori yang ditentukan dengan nama file yang diinginkan. File XPS yang dihasilkan akan berisi pesan "Hello World!" teks.

Selamat! Anda telah berhasil membuat dokumen XPS menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita mempelajari proses pembuatan dokumen XPS menggunakan Aspose.Page untuk .NET. Perpustakaan canggih ini menyediakan cara mulus untuk menghasilkan dokumen elektronik dengan mudah. Bereksperimenlah dengan berbagai font, gaya, dan konten untuk menyesuaikan file XPS dengan kebutuhan spesifik Anda.

## FAQ

### Q1: Bisakah saya menggunakan font khusus di dokumen XPS saya?

A1: Ya, Anda dapat menentukan jenis dan ukuran font saat menambahkan mesin terbang ke dokumen XPS Anda.

### Q2: Apakah Aspose.Page kompatibel dengan .NET Core?

A2: Ya, Aspose.Page mendukung .NET Core, memungkinkan Anda menggunakannya dalam aplikasi lintas platform.

### Q3: Bagaimana cara menambahkan gambar ke dokumen XPS?

A3: Aspose.Page menyediakan metode untuk menambahkan gambar ke dokumen XPS Anda. Lihat dokumentasi untuk contoh detail.

### Q4: Dapatkah saya membuat dokumen XPS multi-halaman?

A4: Tentu saja! Anda dapat menambahkan beberapa halaman ke dokumen XPS Anda menggunakan perpustakaan Aspose.Page.

### Q5: Apakah ada versi uji coba yang tersedia?

 A5: Ya, Anda dapat menjelajahi fitur Aspose.Page dengan mengunduh[uji coba gratis](https://releases.aspose.com/).
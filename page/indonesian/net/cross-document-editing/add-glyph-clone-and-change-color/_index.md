---
title: Tambahkan Glyph Clone dan Ubah Warna dengan Aspose.Page untuk .NET
linktitle: Tambahkan Glyph Clone dan Ubah Warna
second_title: Aspose.Halaman .NET API
description: Jelajahi kekuatan Aspose.Page untuk .NET dalam tutorial komprehensif ini. Pelajari cara menambahkan klon mesin terbang dan mengubah warna dalam dokumen XPS dengan mudah.
weight: 10
url: /id/net/cross-document-editing/add-glyph-clone-and-change-color/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Glyph Clone dan Ubah Warna dengan Aspose.Page untuk .NET

## Perkenalan

Selamat datang di panduan langkah demi langkah tentang penggunaan Aspose.Page untuk .NET guna menambahkan klon mesin terbang dan mengubah warna di dokumen XPS Anda. Aspose.Page for .NET adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan file XPS dengan lancar. Dalam tutorial ini, kami akan fokus pada proses menambahkan klon mesin terbang dan mengubah warnanya, sehingga meningkatkan daya tarik visual dokumen Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar tentang bahasa pemrograman C#.
- Visual Studio atau lingkungan pengembangan C# pilihan lainnya diinstal.
-  Aspose.Page untuk perpustakaan .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/net/).
- Keakraban dengan format dokumen XPS.

## Impor Namespace

Untuk memulai, sertakan namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Mulailah dengan menyiapkan direktori tempat dokumen Anda akan disimpan:

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Buat Dokumen XPS Pertama

Sekarang, mari buat dokumen XPS pertama:

```csharp
XpsDocument doc1 = new XpsDocument();
```

## Langkah 3: Tambahkan Mesin Terbang ke Dokumen Pertama

Tambahkan mesin terbang ke dokumen pertama menggunakan parameter yang ditentukan:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Langkah 4: Isi Glyph di Dokumen Pertama dengan Warna

Isi mesin terbang di dokumen pertama dengan warna solid, misalnya hijau:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

## Langkah 5: Buat Dokumen XPS Kedua

Sekarang, buat dokumen XPS kedua:

```csharp
XpsDocument doc2 = new XpsDocument();
```

## Langkah 6: Tambahkan Mesin Terbang yang Diklon dari Dokumen Pertama

Kloning mesin terbang dari dokumen pertama dan tambahkan ke dokumen kedua:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

## Langkah 7: Isi Glyph di Dokumen Kedua dengan Warna Lain

Ubah warna mesin terbang yang dikloning di dokumen kedua, misalnya, menjadi merah:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

## Langkah 8: Simpan Dokumen XPS Pertama

Simpan dokumen XPS pertama:

```csharp
doc1.Save(dataDir + "out1.xps");
```

## Langkah 9: Simpan Dokumen XPS Kedua

Simpan dokumen XPS kedua:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Selamat! Anda telah berhasil menambahkan klon mesin terbang dan mengubah warna di dokumen XPS Anda menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi cara memanfaatkan Aspose.Page untuk .NET untuk menyempurnakan elemen visual dokumen XPS Anda. Dengan menambahkan klon mesin terbang dan menyesuaikan warna, Anda dapat membuat dokumen yang menarik secara visual dan dinamis yang disesuaikan dengan kebutuhan spesifik Anda.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

A1: Aspose.Page untuk .NET dirancang khusus untuk bekerja dengan dokumen XPS. Jika Anda perlu memanipulasi format lain, Anda dapat menjelajahi pustaka Aspose lain yang disesuaikan untuk format tersebut.

### Q2: Apakah lisensi sementara tersedia untuk Aspose.Page untuk .NET?

 A2: Ya, Anda bisa mendapatkan lisensi sementara untuk tujuan pengujian. Mengunjungi[Di Sini](https://purchase.aspose.com/temporary-license/) untuk informasi lebih lanjut.

### Q3: Bagaimana saya bisa mendapatkan dukungan atau mencari bantuan untuk masalah apa pun?

 A3: Jangan ragu untuk mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk berhubungan dengan masyarakat dan mencari bantuan.

### Q4: Apakah ada batasan pada versi uji coba gratis?

A4: Versi uji coba gratis memiliki beberapa keterbatasan, dan disarankan untuk meninjau dokumentasi untuk detailnya sebelum digunakan.

### Q5: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Page untuk .NET?

 A5: Anda dapat merujuk ke dokumentasi[Di Sini](https://reference.aspose.com/page/net/) untuk informasi rinci dan contoh.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

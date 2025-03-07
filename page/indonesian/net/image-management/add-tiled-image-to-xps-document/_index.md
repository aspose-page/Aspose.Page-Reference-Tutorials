---
title: Tambahkan Gambar Ubin ke Dokumen XPS dengan Aspose.Page untuk .NET
linktitle: Tambahkan Gambar Ubin ke Dokumen XPS
second_title: Aspose.Halaman .NET API
description: Jelajahi penambahan gambar ubin ke dokumen XPS dengan mudah menggunakan Aspose.Page untuk .NET. Tingkatkan daya tarik visual dan buat dokumen yang menakjubkan.
weight: 12
url: /id/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gambar Ubin ke Dokumen XPS dengan Aspose.Page untuk .NET

## Perkenalan

Apakah Anda ingin menyempurnakan dokumen XPS Anda dengan menambahkan gambar ubin yang menarik secara visual? Aspose.Page untuk .NET memberdayakan pengembang untuk mencapai hal ini dengan lancar. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menambahkan gambar ubin ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page. Anda dapat menemukan dokumentasi terperinci dan mengunduh perpustakaan[Di Sini](https://reference.aspose.com/page/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET pilihan Anda, seperti Visual Studio.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan ke dalam proyek Anda. Hal ini memastikan bahwa Anda memiliki akses ke kelas dan metode yang diperlukan untuk bekerja dengan Aspose.Page. Tambahkan namespace berikut di awal kode Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah.

## Langkah 1: Tentukan Direktori Dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
```

Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen XPS Anda.

## Langkah 2: Buat Dokumen XPS Baru

```csharp
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```

 Buat instance dokumen XPS baru menggunakan`XpsDocument` kelas.

## Langkah 3: Tambahkan Gambar Berubin

```csharp
// Gambar ubin
// Persegi panjang terisi ImageBrush di kanan atas bawah
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Langkah ini menambahkan gambar ubin ke dokumen XPS. Sesuaikan koordinat dan jalur file gambar sesuai kebutuhan Anda.

## Langkah 4: Simpan Dokumen XPS yang Dihasilkan

```csharp
// Simpan dokumen XPS yang dihasilkan
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Simpan dokumen XPS yang dimodifikasi ke direktori yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menambahkan gambar ubin ke dokumen XPS menggunakan Aspose.Page untuk .NET. Fitur sederhana namun kuat ini memungkinkan Anda meningkatkan daya tarik visual dokumen Anda dengan mudah.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan semua lingkungan pengembangan .NET?

A1: Ya, Aspose.Page dirancang untuk bekerja secara lancar dengan berbagai lingkungan pengembangan .NET, termasuk Visual Studio.

### Q2: Dapatkah saya menyesuaikan opasitas gambar ubin?

A2: Tentu saja, seperti yang ditunjukkan dalam contoh, Anda dapat mengatur opacity dari persegi panjang yang terisi menggunakan`Opacity` Properti.

### Q3: Apakah ada mode ubin lain yang tersedia di Aspose.Page untuk .NET?

 A3: Ya, Aspose.Page menyediakan mode ubin yang berbeda. Dalam tutorial ini, kami menggunakan`XpsTileMode.Tile`, namun Anda dapat menjelajahi opsi lain di dokumentasi.

### Q4: Bagaimana cara menangani lisensi sementara untuk Aspose.Page?

 A4: Lihat[izin sementara](https://purchase.aspose.com/temporary-license/) halaman di situs web Aspose untuk panduan dalam memperoleh dan menerapkan lisensi sementara.

### Q5: Di mana saya dapat mencari bantuan atau terhubung dengan komunitas Aspose.Page?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk terlibat dengan komunitas, mengajukan pertanyaan, dan menemukan solusi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

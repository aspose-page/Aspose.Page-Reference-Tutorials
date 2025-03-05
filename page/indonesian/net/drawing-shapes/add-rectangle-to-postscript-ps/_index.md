---
title: Tambahkan Rectangle ke PostScript (PS) dengan Aspose.Page untuk .NET
linktitle: Tambahkan Persegi Panjang ke PostScript (PS)
second_title: Aspose.Halaman .NET API
description: Tingkatkan pembuatan dokumen di .NET dengan Aspose.Page. Pelajari cara menambahkan persegi panjang ke file PostScript (PS) langkah demi langkah.
type: docs
weight: 12
url: /id/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Perkenalan

Jika Anda ingin meningkatkan kemampuan pembuatan dokumen di .NET, Aspose.Page memberikan solusi canggih untuk menangani dokumen PostScript. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan persegi panjang ke dokumen PostScript menggunakan Aspose.Page untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk .NET Library: Unduh dan instal perpustakaan Aspose.Page untuk .NET dari[Di Sini](https://releases.aspose.com/page/net/).

- Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET di mesin Anda.

## Impor Namespace

Sebelum Anda memulai coding, pastikan untuk mengimpor namespace yang diperlukan untuk mengakses kelas dan metode yang diperlukan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah:

## Langkah 1: Siapkan Direktori Dokumen Anda

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
```

Pada langkah ini, ganti "Direktori Dokumen Anda" dengan jalur tempat Anda ingin menyimpan dokumen PostScript Anda.

## Langkah 2: Buat Aliran Output untuk Dokumen PostScript

```csharp
//Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Di sini, kita membuat aliran keluaran untuk dokumen PostScript dan menentukan nama file ("AddRectangle_outPS.ps"). Sesuaikan nama file dan lokasinya sesuai preferensi Anda.

## Langkah 3: Tetapkan Opsi Simpan dan Buat Dokumen PS

```csharp
//Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();

// Buat Dokumen PS 1 halaman baru
PsDocument document = new PsDocument(outPsStream, options, false);
```

Atur opsi penyimpanan, tentukan ukuran halaman yang diinginkan (dalam hal ini A4). Kemudian, buat dokumen PostScript satu halaman baru.

## Langkah 4: Tambahkan Persegi Panjang dan Isi

```csharp
//Buat jalur grafis dari persegi panjang pertama
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Atur cat
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Isi persegi panjang
document.Fill(path);
```

Di sini, kita membuat jalur grafis yang mewakili persegi panjang pertama, mengatur warna cat (dalam hal ini, oranye), dan mengisi persegi panjang.

## Langkah 5: Tambahkan Persegi Panjang dan Goresan Lainnya

```csharp
//Buat jalur grafis dari persegi panjang kedua
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Atur pukulan
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Goresan (garis besar) persegi panjang
document.Draw(path);
```

Mirip dengan langkah sebelumnya, kita membuat jalur grafis untuk persegi panjang kedua, mengatur warna goresan (merah dengan ketebalan 3), dan menguraikan persegi panjang tersebut.

## Langkah 6: Tutup Halaman dan Simpan Dokumen

```csharp
//Tutup halaman saat ini
document.ClosePage();

//Simpan dokumennya
document.Save();
```

Terakhir, tutup halaman saat ini dan simpan seluruh dokumen.

## Kesimpulan

Selamat! Anda telah berhasil menambahkan persegi panjang ke dokumen PostScript menggunakan Aspose.Page untuk .NET. Tutorial ini mencakup langkah-langkah penting, mulai dari menyiapkan lingkungan pengembangan hingga menyimpan dokumen akhir.

## FAQ

### Q1: Dapatkah saya menyesuaikan warna persegi panjang?

A1: Ya, Anda dapat menyesuaikan warna dengan menyesuaikan parameter di`SolidBrush` Dan`Pen` kelas.

### Q2: Apakah Aspose.Page kompatibel dengan format dokumen lain?

A2: Ya, Aspose.Page mendukung berbagai format dokumen, termasuk XPS dan PostScript.

### Q3: Bagaimana cara menambahkan teks ke dokumen?

 A3: Anda dapat menggunakan`TextFragment` kelas di Aspose.Page untuk menambahkan teks ke dokumen Anda.

### Q4: Di mana saya dapat menemukan contoh dan dokumentasi tambahan?

 A4: Jelajahi dokumentasinya[Di Sini](https://reference.aspose.com/page/net/) dan kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.

### Q5: Dapatkah saya mencoba Aspose.Page sebelum membeli?

 A5: Ya, Anda bisa mendapatkan versi uji coba gratis[Di Sini](https://releases.aspose.com/) , dan untuk penggunaan jangka panjang, pertimbangkan a[izin sementara](https://purchase.aspose.com/temporary-license/).

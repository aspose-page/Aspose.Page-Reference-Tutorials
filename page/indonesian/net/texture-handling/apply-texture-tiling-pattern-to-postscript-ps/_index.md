---
title: Terapkan Pola Ubin Tekstur ke PostScript (PS) dengan Aspose.Page
linktitle: Terapkan Pola Ubin Tekstur ke PostScript (PS)
second_title: Aspose.Halaman .NET API
description: Sempurnakan dokumen PostScript (PS) Anda dengan pola ubin tekstur menggunakan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk sentuhan kreatif.
type: docs
weight: 10
url: /id/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## Perkenalan

Selamat datang di tutorial langkah demi langkah tentang cara menerapkan pola ubin tekstur ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Aspose.Page adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan berbagai format dokumen, dan dalam tutorial ini, kita akan menjelajahi cara menyempurnakan dokumen PS Anda dengan menambahkan pola ubin tekstur.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:

- [Studio visual](https://visualstudio.microsoft.com/) diinstal pada mesin Anda.
- Pengetahuan dasar tentang pemrograman C#.
-  Unduh dan instal[Aspose.Page untuk perpustakaan .NET](https://releases.aspose.com/page/net/).
- File gambar untuk pola tekstur (misalnya, "TestTexture.bmp").

## Impor Namespace

Dalam kode C# Anda, pastikan Anda mengimpor namespace yang diperlukan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memandu Anda melalui proses tersebut.

## Langkah 1: Siapkan Direktori Dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
```

Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur tempat Anda ingin menyimpan dokumen PS Anda.

## Langkah 2: Buat Aliran Output untuk Dokumen PS

```csharp
// Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Buat opsi penyimpanan dengan ukuran A4
    PsSaveOptions options = new PsSaveOptions();

    // Buat Dokumen PS 1 halaman baru
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Langkah ini mengatur aliran keluaran untuk dokumen PS, termasuk menentukan ukuran dokumen.

## Langkah 3: Terapkan Pola Ubin Tekstur

```csharp
// Buat objek Bitmap dari file gambar
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Buat kuas tekstur dari gambar
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Tambahkan penskalaan dalam arah X ke polanya
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Atur kuas tekstur ini sebagai cat saat ini
    document.SetPaint(brush);
}
```

Langkah ini melibatkan pembuatan kuas tekstur dari gambar dan mengaturnya sebagai cat saat ini untuk dokumen.

## Langkah 4: Buat Jalur Persegi Panjang dan Isi

```csharp
// Buat jalur persegi panjang
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Isi persegi panjang
document.Fill(path);
```

Di sini, kita menentukan jalur persegi panjang dan mengisinya dengan kuas tekstur yang telah ditetapkan sebelumnya.

## Langkah 5: Atur Stroke dan Gambar

```csharp
// Dapatkan cat terkini
Brush paint = document.GetPaint();

// Atur goresan merah
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Goreskan persegi panjang tersebut
document.Draw(path);
```

Langkah ini melibatkan pengaturan properti guratan dan menggambar persegi panjang yang digariskan.

## Langkah 6: Isi dan Garis Besar Teks dengan Pola Tekstur

```csharp
// Isi teks dengan pola tekstur
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Garis besar teks dengan pola tekstur
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Terakhir, kami mengisi dan menguraikan teks dengan pola tekstur, sehingga meningkatkan daya tarik visual dokumen Anda.

## Langkah 7: Simpan dan Tutup Dokumen

```csharp
// Tutup halaman saat ini
document.ClosePage();

// Simpan dokumennya
document.Save();
```

Pastikan untuk menutup halaman saat ini dan menyimpan dokumen untuk menerapkan perubahan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menerapkan pola ubin tekstur ke dokumen PostScript menggunakan Aspose.Page untuk .NET. Bereksperimenlah dengan berbagai gambar dan pola untuk menyesuaikan dokumen PS Anda lebih jauh.

## FAQ

### Q1: Dapatkah saya menggunakan format gambar lain untuk pola tekstur?

A1: Ya, Aspose.Page mendukung berbagai format gambar. Pastikan kompatibilitas dengan dokumentasi perpustakaan.

### Q2: Apakah Aspose.Page kompatibel dengan .NET Core?

A2: Ya, Aspose.Page kompatibel dengan .NET Framework dan .NET Core.

### Q3: Bagaimana cara menyesuaikan ukuran persegi panjang bertekstur?

 A3: Ubah dimensi di`RectangleF` parameter selama pembuatan jalur.

### Q4: Bisakah saya menambahkan beberapa pola tekstur ke satu dokumen?

A4: Ya, Anda dapat mengulangi proses tersebut dengan gambar dan jalur yang berbeda.

### Q5: Di mana saya dapat menemukan sumber daya dan dukungan tambahan?

 A5: Kunjungi[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan menjelajahi[dokumentasi](https://reference.aspose.com/page/net/).

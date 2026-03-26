---
date: 2026-03-26
description: Pelajari cara membuat dokumen PostScript .NET dengan pola ubin tekstur
  menggunakan Aspose.Page. Ikuti panduan langkah demi langkah kami untuk menambahkan
  tekstur kaya ke file PS Anda.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Buat dokumen PostScript .NET dengan penyusunan tekstur
url: /id/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen PostScript .NET dengan Pengulangan Tekstur

## Cara membuat dokumen PostScript .NET dengan pengulangan tekstur

## Jawaban Cepat
- **Library apa yang digunakan?** Aspose.Page for .NET  
- **Apakah saya dapat menggunakan .NET Core?** Ya, library mendukung .NET Core dan .NET 5/6  
- **Format gambar apa yang dapat digunakan untuk tekstur?** Format apa pun yang didukung oleh System.Drawing (BMP, PNG, JPEG, dll.)  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi  

## Prasyarat

- [Visual Studio](https://visualstudio.microsoft.com/) terpasang di mesin Anda.  
- Pengetahuan dasar tentang pemrograman C#.  
- Unduh dan instal [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- Sebuah file gambar untuk pola tekstur (misalnya **TestTexture.bmp**).

## Impor Namespace

Di file C# Anda, impor namespace yang diperlukan agar kompiler mengetahui di mana menemukan tipe yang akan kami gunakan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Siapkan Direktori Dokumen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ganti **Your Document Directory** dengan folder tempat Anda ingin menyimpan file PS yang dihasilkan.

## Langkah 2: Buat Stream Output untuk Dokumen PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Blok ini membuka file stream, mengatur ukuran halaman (A4 secara default), dan membuat instance **PsDocument** baru yang akan kita gambar.

## Langkah 3: Terapkan Pola Pengulangan Tekstur

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Di sini kami memuat bitmap, membungkusnya dalam **TextureBrush**, secara opsional memperluasnya secara horizontal, dan memberi tahu **PsDocument** untuk menggunakan kuas ini pada operasi menggambar berikutnya.

## Langkah 4: Buat Jalur Persegi Panjang dan Isi

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Sebuah persegi panjang sederhana didefinisikan dan diisi dengan kuas tekstur yang telah kami atur sebelumnya.

## Langkah 5: Atur Garis Luar dan Gambar

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Kami mengambil cat (paint) saat ini (kuas tekstur), membuat pena merah untuk garis luar, dan menggambar batas persegi panjang.

## Langkah 6: Isi dan Garis Luar Teks dengan Pola Tekstur

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Langkah ini menunjukkan kemampuan **fill and stroke text**: karakter “ABC” diisi dengan kuas tekstur dan kemudian digarisbawahi, menghasilkan efek visual yang mencolok.

## Langkah 7: Simpan dan Tutup Dokumen

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Menutup halaman menyelesaikan perintah menggambar, dan `Save()` menulis file PostScript ke disk.

## Masalah Umum dan Solusinya

- **Tekstur tampak terdistorsi** – Sesuaikan nilai `Matrix` untuk mengontrol skala pada arah X/Y.  
- **Gambar tidak ditemukan** – Pastikan `dataDir` mengarah ke folder yang tepat dan nama file cocok persis, termasuk huruf besar/kecil.  
- **Warna tampak tidak tepat** – Ingat bahwa PostScript menggunakan ruang warna yang tidak bergantung pada perangkat; pastikan Anda menggunakan objek `Color` yang dipetakan dengan benar.

## Pertanyaan yang Sering Diajukan

**T:** Apakah saya dapat menggunakan format gambar lain untuk pola tekstur?  
**J:** Ya, format apa pun yang didukung oleh `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, dll.) dapat digunakan.

**T:** Apakah Aspose.Page kompatibel dengan .NET Core?  
**J:** Tentu saja. Library berjalan di .NET Framework, .NET Core, dan .NET 5/6.

**T:** Bagaimana cara mengubah ukuran persegi panjang bertekstur?  
**J:** Modifikasi nilai `RectangleF` pada langkah pembuatan persegi panjang (misalnya, `new RectangleF(0, 0, 300, 150)`).

**T:** Dapatkah saya menerapkan beberapa pola tekstur dalam satu dokumen?  
**J:** Ya. Cukup buat `TextureBrush` baru dengan gambar berbeda dan panggil `SetPaint` lagi sebelum menggambar bentuk atau teks berikutnya.

**T:** Di mana saya dapat menemukan contoh lebih banyak dan referensi API?  
**J:** Kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39) untuk bantuan komunitas dan [dokumentasi resmi](https://reference.aspose.com/page/net/) untuk penggunaan API secara detail.

## Kesimpulan

Anda kini tahu cara **membuat dokumen PostScript .NET** dan menerapkan pola pengulangan tekstur, termasuk cara **mengisi dan menggarisbawahi teks** dengan tekstur tersebut. Bereksperimenlah dengan gambar berbeda, matriks skala, dan primitif menggambar untuk menghasilkan file PS bergaya khusus untuk laporan, selebaran, atau output grafis lainnya.

---

**Terakhir Diperbarui:** 2026-03-26  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
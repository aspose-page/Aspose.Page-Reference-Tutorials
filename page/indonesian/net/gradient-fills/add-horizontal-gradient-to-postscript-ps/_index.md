---
date: 2026-02-25
description: Tingkatkan dokumen PostScript dengan persegi panjang gradien linear menggunakan
  Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk mempelajari
  pengisian teks dengan gradien dan gradien pada outline teks.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Tambahkan Persegi Panjang Gradien Linear ke PostScript (PS) dengan Aspose.Page
url: /id/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 .NET  
**Author:** Aspose  

Translate labels: "Terakhir Diperbarui", "Diuji Dengan", "Penulis". Keep dates unchanged.

Then closing shortcodes.

Finally backtop button shortcode unchanged.

Make sure to keep markdown formatting.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Persegi Panjang Gradien Linear ke PostScript (PS) dengan Aspose.Page

## Pendahuluan

Selamat datang di tutorial komprehensif ini tentang menambahkan **linear gradient rectangle** ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Aspose.Page adalah perpustakaan kuat yang memungkinkan Anda membuat, memodifikasi, dan merender dokumen dalam berbagai format, dan hari ini kami akan fokus pada cara membawa gradien yang menarik ke file PS Anda.

### Jawaban Cepat
- **Apa yang dilakukan linear gradient rectangle?** Itu mengisi area persegi panjang dengan transisi warna halus dari satu sisi ke sisi lainnya.  
- **API mana yang menangani gradient fill text?** `LinearGradientBrush` dikombinasikan dengan `SetPaint` dan `FillAndStrokeText`.  
- **Bisakah saya memberi outline pada teks dengan gradien?** Ya—gunakan `SetStroke` dengan kuas gradien dan panggil `OutlineText`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial Aspose.Page diperlukan untuk penggunaan non‑evaluasi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- Aspose.Page for .NET Library: Pastikan perpustakaan direferensikan dalam proyek Anda. Anda dapat mengunduhnya dari [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Document Directory: Buat folder di disk tempat file PS yang dihasilkan akan disimpan dan ganti **“Your Document Directory”** dalam kode dengan path tersebut.

## Impor Namespace

Untuk memulai, impor namespace yang memberi Anda akses ke kelas menggambar dan kelas khusus PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Apa Itu Linear Gradient Rectangle?

Sebuah **linear gradient rectangle** hanyalah bentuk persegi panjang yang interiornya dilukis dengan gradien linear—warna bertransisi secara halus sepanjang garis lurus, biasanya dari kiri ke kanan (horizontal) atau atas ke bawah (vertikal). Di Aspose.Page Anda mencapai ini dengan menggabungkan `GraphicsPath` yang mendefinisikan persegi panjang dengan `LinearGradientBrush` yang menggambarkan transisi warna.

## Mengapa Menggunakan Gradient Fill Text dan Outline Text Gradient?

- **Daya Tarik Visual:** Teks yang diisi gradien menambah kedalaman dan gaya modern pada laporan, faktur, atau materi promosi.  
- **Konsistensi Merek:** Cocokkan warna korporat dengan nilai ARGB yang tepat.  
- **Fleksibilitas:** Kuas yang sama dapat digunakan kembali untuk mengisi bentuk, mengisi teks, dan gradien outline, mengurangi duplikasi kode.

## Langkah 1: Siapkan Dokumen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 2: Definisikan Gradient Rectangle dan Warna

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Langkah 3: Atur Transformasi untuk Kuas

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Langkah 4: Atur Paint dan Isi Persegi Panjang

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Cara Menerapkan Gradient Fill Text

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Menggunakan Outline Text Gradient

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Langkah 7: Tutup Halaman Saat Ini dan Simpan Dokumen

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Selamat! Anda telah berhasil menambahkan **linear gradient rectangle** ke dokumen PostScript dan menggunakan kuas yang sama untuk **gradient fill text** serta **outline text gradient**.

## Kasus Penggunaan Umum & Tips

- **Header Laporan:** Isi blok teks besar dengan gradien untuk menyorot judul bagian.  
- **Logo Merek:** Buat ulang bentuk logo dengan bentuk berisi gradien untuk konsistensi branding.  
- **Tip Pro:** Gunakan kembali instance `LinearGradientBrush` yang sama untuk beberapa panggilan menggambar agar warna tetap selaras sempurna di seluruh bentuk dan teks.

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menerapkan gradien pada bentuk lain selain persegi panjang?
**A:** Ya, Anda dapat menerapkan gradien pada bentuk apa pun yang didefinisikan oleh `GraphicsPath`. Cukup tambahkan lingkaran, poligon, atau jalur khusus sebelum memanggil `document.Fill(path)`.

### Q2: Bagaimana cara mengubah warna gradien?
**A:** Modifikasi nilai `Color.FromArgb` saat membuat `LinearGradientBrush`. Warna pertama adalah warna awal, warna kedua adalah warna akhir gradien.

### Q3: Apakah Aspose.Page kompatibel dengan format dokumen yang berbeda?
**A:** Tentu saja. Aspose.Page mendukung XPS, PS, PDF, dan beberapa format vektor lainnya. Periksa dokumentasi resmi untuk daftar lengkapnya.

### Q4: Bisakah saya menggunakan Aspose.Page untuk proyek komersial?
**A:** Ya, lisensi komersial tersedia. Lihat halaman pembelian untuk detailnya: [here](https://purchase.aspose.com/buy).

### Q5: Di mana saya dapat menemukan dukungan komunitas?
**A:** Bergabunglah dengan forum komunitas Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

**Terakhir Diperbarui:** 2026-02-25  
**Diuji Dengan:** Aspose.Page 24.10 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
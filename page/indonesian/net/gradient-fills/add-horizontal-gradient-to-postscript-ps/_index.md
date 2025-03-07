---
title: Tambahkan Gradien Horizontal ke PostScript (PS) dengan Aspose.Page
linktitle: Tambahkan Gradien Horisontal ke PostScript (PS)
second_title: Aspose.Halaman .NET API
description: Sempurnakan dokumen PostScript dengan gradien horizontal yang menakjubkan menggunakan Aspose.Page untuk .NET. Ikuti tutorial langkah demi langkah kami untuk penerapan yang lancar.
weight: 12
url: /id/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Horizontal ke PostScript (PS) dengan Aspose.Page

## Perkenalan

Selamat datang di tutorial komprehensif tentang menambahkan gradien horizontal ke dokumen PostScript (PS) menggunakan Aspose.Page untuk .NET. Aspose.Page adalah perpustakaan canggih yang memfasilitasi manipulasi dokumen dalam berbagai format, menyediakan alat yang dibutuhkan pengembang untuk membuat, memodifikasi, dan merender dokumen dengan lancar.

Dalam tutorial ini, kami akan fokus pada penyempurnaan dokumen PostScript Anda dengan menggabungkan gradien horizontal yang menarik. Kami akan memandu Anda melalui setiap langkah proses, memastikan bahwa Anda mendapatkan pemahaman yang kuat tentang penerapannya.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page for .NET Library: Pastikan Anda memiliki perpustakaan Aspose.Page for .NET yang terintegrasi ke dalam lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[Aspose.Page untuk dokumentasi .NET](https://reference.aspose.com/page/net/).

- Direktori Dokumen: Siapkan direktori untuk menyimpan dokumen Anda, dan ganti "Direktori Dokumen Anda" dalam kode yang diberikan dengan jalur sebenarnya.

Sekarang, mari kita jelajahi cara menambahkan gradien horizontal ke dokumen PostScript langkah demi langkah.

## Impor Namespace

Sebelum memulai, penting untuk mengimpor namespace yang diperlukan untuk mengakses fungsi yang disediakan oleh Aspose.Page. Tambahkan namespace berikut di awal kode Anda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Siapkan Dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Buat opsi penyimpanan dengan ukuran A4
    PsSaveOptions options = new PsSaveOptions();

    // Buat Dokumen PS 1 halaman baru
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 2: Tentukan Gradien Persegi Panjang dan Warna

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Buat jalur grafis dari persegi panjang pertama
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Buat kuas gradien linier dengan persegi panjang sebagai batas, warna awal, dan akhir
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Langkah 3: Atur Transform untuk Brush

```csharp
    // Buat transformasi untuk kuas. Komponen skala X dan Y harus sama dengan lebar dan tinggi persegi panjang.
    // Komponen terjemahan adalah offset dari persegi panjang
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Tetapkan transformasi
    brush.Transform = brushTransform;
```

## Langkah 4: Atur Cat dan Isi Persegi Panjang

```csharp
    // Atur cat
    document.SetPaint(brush);

    // Isi persegi panjang
    document.Fill(path);
```

## Langkah 5: Isi Teks dengan Gradien

```csharp
    // Isi teks dengan gradien
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Langkah 6: Atur Stroke dan Garis Besar Teks

```csharp
    // Atur pukulan saat ini
    document.SetStroke(new Pen(brush, 5));
    // Garis besar teks dengan gradien
    document.OutlineText("ABC", font, 200, 400);
```

## Langkah 7: Tutup Halaman Saat Ini dan Simpan Dokumen

```csharp
    // Tutup halaman saat ini
    document.ClosePage();

    // Simpan dokumennya
    document.Save();
}
```

Selamat! Anda telah berhasil menambahkan gradien horizontal ke dokumen PostScript menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami membahas proses menyempurnakan dokumen PostScript Anda dengan gradien horizontal menggunakan pustaka Aspose.Page untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda mendapatkan wawasan berharga dalam memanfaatkan alat canggih ini untuk manipulasi dokumen.

## FAQ

### Q1: Bisakah saya menerapkan gradien ke bentuk lain selain persegi panjang?

 A1: Ya, Anda dapat menerapkan gradien ke berbagai bentuk menggunakan Aspose.Page. Ubah`GraphicsPath` kreasi yang sesuai dengan bentuk spesifik Anda.

### Q2: Bagaimana cara mengubah warna gradien?

 A2: Sesuaikan`Color.FromArgb` nilai-nilai di`LinearGradientBrush` instantiasi untuk mencapai warna gradien yang diinginkan.

### Q3: Apakah Aspose.Page kompatibel dengan format dokumen yang berbeda?

A3: Aspose.Page mendukung berbagai format dokumen, termasuk XPS, PS, PDF, dan lainnya. Lihat dokumentasi untuk daftar lengkap.

### Q4: Dapatkah saya menggunakan Aspose.Page untuk proyek komersial?

 A4: Ya, Aspose.Page hadir dengan opsi lisensi komersial. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk detailnya.

### Q5: Apakah ada forum komunitas untuk pengguna Aspose.Page?

 A5: Ya, bergabunglah dengan komunitas Aspose.Page di[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan pengguna lain dan mencari bantuan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

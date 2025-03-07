---
title: Tampilkan Transparansi Semu di PostScript (PS) dengan Aspose.Page
linktitle: Tampilkan Transparansi Semu di PostScript (PS)
second_title: Aspose.Halaman .NET API
description: Jelajahi kekuatan transparansi semu di PostScript dengan Aspose.Page untuk .NET. Ikuti panduan langkah demi langkah kami untuk mendapatkan dokumen yang menakjubkan secara visual.
weight: 13
url: /id/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tampilkan Transparansi Semu di PostScript (PS) dengan Aspose.Page

## Perkenalan

Apakah Anda ingin meningkatkan daya tarik visual dokumen PostScript (PS) Anda dengan menerapkan transparansi semu? Aspose.Page untuk .NET memberikan solusi ampuh untuk mencapai efek ini dengan mudah. Dalam tutorial langkah demi langkah ini, kami akan memandu Anda melalui proses menampilkan transparansi semu di PostScript menggunakan Aspose.Page.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page untuk .NET. Anda dapat mengunduhnya dari[Aspose.Dokumentasi halaman](https://reference.aspose.com/page/net/).

- Direktori Dokumen: Siapkan direktori untuk menyimpan dokumen PostScript Anda.

Sekarang setelah Anda memiliki alat yang diperlukan, mari jelajahi cara menampilkan transparansi semu di PostScript menggunakan Aspose.Page.

## Impor Namespace

Sebelum mempelajari contoh ini, pastikan Anda mengimpor namespace yang diperlukan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Buat Aliran Output untuk Dokumen PostScript

```csharp
// MantanMulai:1
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
//Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Buat opsi penyimpanan dengan ukuran A4
	PsSaveOptions options = new PsSaveOptions();

	// Buat Dokumen PS 1 halaman baru
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 2: Buat Persegi Panjang dengan Isi Gradien Buram

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Langkah 3: Buat Persegi Panjang dengan Isi Gradien Tembus

```csharp
	offsetX = 350;

	//Buat jalur grafis dari persegi panjang pertama
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Buat warna kuas gradien linier yang transparansinya bukan 255, tapi 150 dan 50. Jadi tembus cahaya.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Langkah 4: Tutup Halaman Saat Ini dan Simpan Dokumen

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan transparansi semu ke dalam dokumen PostScript Anda menggunakan Aspose.Page untuk .NET.

## Kesimpulan

Kesimpulannya, Aspose.Page untuk .NET menawarkan cara yang mudah dan efisien untuk menyempurnakan elemen visual dokumen PostScript Anda. Langkah-langkah yang diuraikan di atas memberikan jalur yang jelas untuk menerapkan transparansi semu, memungkinkan Anda menghasilkan keluaran yang menakjubkan secara visual.

## FAQ

### Q1: Apakah Aspose.Page kompatibel dengan semua versi .NET?

A1: Aspose.Page untuk .NET kompatibel dengan berbagai versi kerangka .NET, memastikan fleksibilitas dan kemudahan integrasi.

### Q2: Dapatkah saya menerapkan transparansi semu pada bentuk lain selain persegi panjang?

A2: Ya, prinsip yang sama dapat diterapkan pada bentuk lain dengan menyesuaikan GraphicsPath.

### Q3: Di mana saya dapat menemukan contoh dan dokumentasi tambahan?

 A3: Jelajahi[Aspose.Dokumentasi halaman](https://reference.aspose.com/page/net/) untuk contoh komprehensif dan dokumentasi terperinci.

### Q4: Apakah ada uji coba gratis yang tersedia untuk Aspose.Page?

 A4: Ya, Anda dapat mengakses uji coba gratis Aspose.Page dari[Link ini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?

 A5: Kunjungi[Link ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan lisensi sementara untuk Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

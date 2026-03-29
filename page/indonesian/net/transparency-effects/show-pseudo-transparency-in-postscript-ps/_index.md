---
date: 2026-03-29
description: Pelajari cara menggunakan kuas gradien linear C# untuk membuat pseudo‑transparansi
  dalam PostScript dengan Aspose.Page untuk .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Kuas Gradien Linear C# untuk Pseudo‑Transparansi di PS
url: /id/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kuasa Sapu Gradien Linear C# untuk Pseudo-Transparansi dalam PostScript (PS)

## Pendahuluan

Jika Anda perlu menambahkan efek tembus pandang halus ke file PostScript (PS) Anda, **linear gradient brush C#** adalah alat yang sempurna. Aspose.Page untuk .NET memudahkan melukis persegi panjang dengan isian gradien yang opak maupun tembus pandang, memberikan dokumen Anda tampilan modern dan berlapis. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk membuat pseudo‑transparansi menggunakan linear gradient brush dalam C#.

## Jawaban Cepat
- **Apa perpustakaan yang menyediakan linear gradient brush?** Aspose.Page for .NET
- **Kelas grafis mana yang membuat gradien?** `LinearGradientBrush`
- **Bisakah saya mengontrol opasitas per warna?** Ya, menggunakan `Color.FromArgb(alpha, …)`
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Page yang valid diperlukan
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Apa itu linear gradient brush C#?

`LinearGradientBrush` adalah objek GDI+ yang melukis transisi halus antara dua warna sepanjang garis lurus. Ketika Anda menentukan saluran alfa (0‑255) untuk setiap warna, Anda dapat membuat gradien tembus pandang—tepat apa yang kita butuhkan untuk pseudo‑transparansi dalam PostScript.

## Mengapa menggunakan linear gradient brush C# untuk pseudo‑transparansi?

- **Kontrol opasitas yang halus:** Sesuaikan alfa setiap warna untuk mencapai tingkat tembus pandang yang diinginkan.  
- **Rendering independen perangkat:** Sapu ini bekerja sama pada layar, PDF, EPS, dan output PS.  
- **API sederhana:** Beberapa baris kode C# menghasilkan efek visual kelas profesional.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

- Aspose.Page untuk .NET terpasang. Anda dapat mengunduhnya dari [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- Folder yang dapat ditulisi tempat dokumen PostScript yang dihasilkan akan disimpan.

Setelah Anda memiliki alat yang diperlukan, mari mulai membangun persegi panjang pseudo‑transparan.

## Impor Namespace

Sebelum kita mulai, impor namespace yang berisi kelas yang akan kita gunakan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Buat aliran output untuk dokumen PostScript

Kita mulai dengan membuat aliran file yang akan menampung file PS yang dihasilkan, kemudian menginisialisasi `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 2: Buat persegi panjang dengan isian gradien **opaque**

Di sini kita membangun `LinearGradientBrush` yang warnanya sepenuhnya opak (alpha = 255). Persegi panjang ini akan berfungsi sebagai lapisan latar belakang.

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

## Langkah 3: Buat persegi panjang dengan isian gradien **translucent**

Sekarang kita menggunakan **linear gradient brush C#** di mana nilai alfa kurang dari 255 (misalnya 150 dan 50). Ini membuat persegi panjang sebagian tembus pandang, menghasilkan efek pseudo‑transparansi.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Langkah 4: Tutup halaman dan simpan dokumen

Akhirnya kita menyelesaikan halaman dan menulis file PS ke disk.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Dengan mengikuti empat langkah ini Anda dapat dengan mulus menggabungkan persegi panjang opak dan tembus pandang, menciptakan efek pseudo‑transparansi yang meyakinkan pada output PostScript apa pun.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| Warna muncul sepenuhnya opaque | Nilai alpha disetel ke 255 secara tidak sengaja | Gunakan `Color.FromArgb(alpha, …)` dengan `alpha` < 255 |
| Gradien terdistorsi secara tidak tepat | Matriks transformasi tidak tepat | Verifikasi parameter matriks sesuai dengan dimensi persegi panjang |
| File output kosong | Aliran tidak ditutup atau `Save()` tidak dipanggil | Pastikan `document.ClosePage()` dan `document.Save()` dijalankan di dalam blok `using` |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page kompatibel dengan semua versi .NET?**  
A: Aspose.Page untuk .NET kompatibel dengan berbagai versi kerangka kerja .NET, memastikan fleksibilitas dan kemudahan integrasi.

**Q: Bisakah saya menerapkan pseudo‑transparansi pada bentuk lain selain persegi panjang?**  
A: Ya, prinsip yang sama dapat diterapkan pada bentuk apa pun dengan menyesuaikan `GraphicsPath` yang bersangkutan.

**Q: Di mana saya dapat menemukan contoh tambahan dan dokumentasi?**  
A: Jelajahi [Aspose.Page documentation](https://reference.aspose.com/page/net/) untuk contoh komprehensif dan referensi API yang detail.

**Q: Apakah ada versi percobaan gratis untuk Aspose.Page?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.Page dari [tautan ini](https://releases.aspose.com/).

**Q: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page?**  
A: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara bagi Aspose.Page.

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
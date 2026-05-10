---
date: 2026-02-23
description: Pelajari cara menambahkan gradien ke file PostScript, menyimpan file
  PostScript dengan ukuran halaman A4, dan mengisi gradien persegi panjang menggunakan
  Aspose.Page untuk .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Cara Menambahkan Gradien – Gradien Diagonal di PostScript (PS) dengan Aspose.Page
  .NET
url: /id/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

 with all translations.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien: Gradien Diagonal ke PostScript (PS) dengan Aspose.Page .NET

## Pendahuluan

Menambahkan gradien diagonal ke dokumen PostScript (PS) dapat secara dramatis meningkatkan daya tarik visual, terutama ketika Anda perlu **cara menambahkan gradien** efek dalam laporan teknis, brosur, atau aplikasi yang intensif grafis. Dalam tutorial ini Anda akan melihat secara tepat cara menambahkan gradien ke file PostScript, mengatur ukuran halaman A4, dan mengisi sebuah persegi panjang dengan transisi warna yang halus menggunakan Aspose.Page untuk .NET.

## Jawaban Cepat
- **Library apa yang diperlukan?** Aspose.Page for .NET  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Bisakah saya mengubah arah gradien?** Ya – rotate the brush transform as shown in the code  
- **Bagaimana cara menyimpan hasilnya?** Use `PsDocument.Save()` which writes a PostScript file to disk  
- **Apakah lisensi diperlukan untuk produksi?** Ya, a commercial license unlocks full functionality  

## Apa itu gradien diagonal dalam PostScript?

Gradien diagonal adalah transisi warna linear yang berjalan pada sudut (biasanya 45°) melintasi sebuah bentuk. Dalam PostScript, ini dicapai dengan menerapkan `LinearGradientBrush` dengan matriks transformasi khusus yang memutar, memperbesar, dan mentranslasi gradien agar sesuai dengan persegi panjang yang diinginkan.

## Mengapa menggunakan Aspose.Page untuk pengisian gradien?

Aspose.Page mengabstraksi perintah PostScript tingkat rendah, memungkinkan Anda bekerja dengan objek grafik .NET yang familiar. Anda dapat membuat pengisian kompleks, mengatur dimensi halaman, dan mengekspor langsung ke **menyimpan file PostScript** tanpa harus berurusan dengan sintaks PS mentah.

## Prasyarat

- **Aspose.Page for .NET Library** – unduh di [sini](https://releases.aspose.com/page/net/).  
- **Document Directory** – folder tempat file `*.ps` yang dihasilkan akan ditulis.

Sekarang setelah kami mencakup dasar-dasarnya, mari kita jalani implementasinya langkah demi langkah.

## Impor Namespace

Pertama, impor namespace yang memberi Anda akses ke perangkat EPS, utilitas menggambar, dan kelas I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Buat Output Stream untuk Dokumen PostScript (Buat Dokumen PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Langkah 2: Atur Ukuran Halaman A4 (Opsi Penyimpanan)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Langkah 3: Buat Dokumen PS 1‑Halaman Baru

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 4: Definisikan Parameter Persegi Panjang

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Langkah 5: Buat Jalur Grafik

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Langkah 6: Buat Linear Gradient Brush (Isi Gradien Persegi Panjang)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Langkah 7: Buat Transformasi untuk Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Langkah 8: Terapkan Transformasi ke Brush (Putar, Skala, Translasi)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Langkah 9: Atur Transformasi ke Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Langkah 10: Atur Paint dan Isi Persegi Panjang

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Langkah 11: Tutup Halaman Saat Ini

```csharp
	//Close current page
	document.ClosePage();
```

## Langkah 12: Simpan Dokumen (Simpan File PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Cara Menyimpan File PostScript

Pemanggilan `PsDocument.Save()` menulis konten PostScript yang lengkap ke stream yang Anda buka pada **Langkah 1**. Setelah blok `using` selesai, file `DiagonaGradient_outPS.ps` akan tersedia di direktori yang Anda tentukan.

## Kasus Penggunaan Umum

- **Dokumentasi teknis** yang membutuhkan bayangan latar belakang halus.  
- **Brosur pemasaran** di mana gradien diagonal menambah tampilan modern.  
- **Generator laporan otomatis** yang menghasilkan file PS dapat dicetak secara langsung.

## Pemecahan Masalah & Tips

- **Warna tidak tepat** – periksa kembali nilai ARGB yang diberikan ke `LinearGradientBrush`.  
- **Gradien tidak terlihat** – pastikan matriks transformasi memutar dan menskalakan dengan benar; pemanggilan `Rotate(-45)` mengatur sudut diagonal.  
- **File tidak dibuat** – verifikasi bahwa `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page kompatibel dengan semua framework .NET?**  
A: Aspose.Page mendukung berbagai versi .NET, mulai dari .NET Framework 4.5+ hingga .NET 6+, memastikan kompatibilitas yang luas.

**Q: Bisakah saya menyesuaikan warna gradien di Aspose.Page?**  
A: Ya, Anda dapat menentukan warna ARGB apa pun saat membuat `LinearGradientBrush`, memberi Anda kontrol penuh atas warna awal dan akhir.

**Q: Apakah ada versi percobaan tersedia untuk Aspose.Page?**  
A: Ya, Anda dapat menjelajahi fitur Aspose.Page dengan mengunduh versi percobaan [di sini](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?**  
A: Dapatkan lisensi sementara untuk Aspose.Page [di sini](https://purchase.aspose.com/temporary-license/) untuk membuka kemampuan tambahan selama evaluasi.

**Q: Di mana saya dapat menemukan dukungan komunitas untuk Aspose.Page?**  
A: Bergabunglah dengan komunitas Aspose.Page di [forum](https://forum.aspose.com/c/page/39) untuk bantuan dan diskusi.

**Terakhir Diperbarui:** 2026-02-23  
**Diuji Dengan:** Aspose.Page for .NET (rilis stabil terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
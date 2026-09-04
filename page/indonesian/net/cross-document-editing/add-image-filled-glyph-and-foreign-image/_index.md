---
date: 2026-06-30
description: Pelajari cara membuat dokumen XPS .NET dan menambahkan glyph isi gambar
  atau gambar asing menggunakan Aspose.Page untuk .NET dalam beberapa langkah mudah.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Tambahkan Glyph Isi Gambar & Gambar Asing
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Buat Dokumen XPS .NET – Tambahkan Glyph Isi Gambar & Gambar Asing dengan Aspose.Page
url: /id/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS .NET – Tambahkan Glyph Terisi Gambar & Gambar Asing dengan Aspose.Page

## Pendahuluan

Dalam pengembangan .NET, **create XPS document .NET** tugas umum ketika Anda membutuhkan grafik berkualitas tinggi dan independen resolusi. Aspose.Page untuk .NET mempermudah hal ini dan memungkinkan Anda memperkaya file XPS dengan glyph yang terisi gambar atau mengambil gambar dari dokumen XPS lain. Pada akhir tutorial ini Anda akan mengetahui cara membuat dua dokumen XPS, mengisi glyph dengan gambar, dan menggunakan kembali gambar tersebut di seluruh dokumen—sempurna untuk menghasilkan faktur, sertifikat, atau output visual apa pun.

## Jawaban Cepat
- **Apa yang didukung oleh Aspose.Page?** Lebih dari 25 format gambar dan kemampuan memproses file XPS hingga 500 MB tanpa memuat seluruh memori.  
- **Berapa baris kode yang diperlukan untuk menambahkan glyph terisi gambar?** Hanya dua baris: buat `ImageBrush` dan tetapkan ke `Glyph`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial menghilangkan watermark evaluasi.  
- **Versi .NET mana yang kompatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya menggunakan kembali font dari XPS lain?** Tentu – Anda dapat mengimpor koleksi font dari dokumen pertama ke dokumen kedua.

## Bagaimana cara membuat dokumen XPS menggunakan Aspose.Page .NET?

Muat pustaka Aspose.Page, buat instance `XpsDocument`, tambahkan halaman, dan panggil `Save` – itu adalah alur kerja lengkap dalam tiga pernyataan singkat. API secara otomatis menangani ukuran halaman, DPI, dan manajemen sumber daya, sehingga Anda tidak perlu mengelola struktur XPS tingkat rendah secara manual. Pendekatan ini dapat diskalakan dari selebaran satu halaman hingga katalog beratus‑ratus halaman.

## Prasyarat

- **Aspose.Page for .NET** – unduh dari [here](https://releases.aspose.com/page/net/).  
- **IDE .NET** – Visual Studio, Rider, atau VS Code dengan ekstensi C#.  
- **Folder untuk dokumen Anda** – kami akan menyebutnya **Your Document Directory** dalam cuplikan kode.

## Impor Namespace

Namespace `Aspose.Page.XPS` menyediakan kelas inti dokumen XPS, sementara `Aspose.Page.XPS.XpsModel` berisi elemen model seperti glyph dan brush. Impor mereka di bagian atas file Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Apa itu Glyph Terisi Gambar?

Glyph adalah bentuk vektor yang dapat dirender dengan warna solid, gradien, atau image brush. Ketika Anda menerapkan `ImageBrush`, interior glyph diwarnai dengan gambar yang diberikan, memungkinkan efek visual kompleks tanpa meraster seluruh halaman.

## Langkah 1: Buat Dokumen XPS Pertama

`XpsDocument` mewakili paket XPS dan merupakan titik masuk untuk membuat serta menyimpan file XPS. Mulailah dengan membuat dokumen XPS pertama yang akan menampung glyph terisi gambar.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Langkah 2: Tambahkan Glyph ke Dokumen Pertama

`XpsGlyphs` mendefinisikan koleksi glyph (karakter teks) yang dapat ditempatkan pada halaman. Tambahkan glyph ke dokumen pertama, dengan menentukan font, ukuran, gaya, dan posisi.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Langkah 3: Isi Glyph dengan Image Brush

`ImageBrush` melukis area dengan gambar, memungkinkan pola atau foto mengisi bentuk. Isi glyph dengan image brush, menggunakan gambar dari direktori data Anda.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Langkah 4: Buat Dokumen XPS Kedua

`XpsDocument` digunakan untuk membuat file XPS baru yang dapat berisi halaman, sumber daya, dan konten. Sekarang, buat dokumen XPS kedua yang akan menggabungkan glyph dari dokumen pertama.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Langkah 5: Tambahkan Glyph dengan Font dari Dokumen Pertama

`Font` mewakili jenis huruf yang digunakan untuk merender teks dalam dokumen XPS. Tambahkan glyph ke dokumen kedua, menggunakan font yang diekstrak dari dokumen pertama. Dengan berbagi koleksi font, Anda menjaga ukuran file tetap kecil dan memastikan konsistensi visual.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Langkah 6: Buat Image Brush dari Isi Dokumen Pertama

`ImageBrush` dapat dibuat dari isi yang ada untuk menggunakan kembali gambar yang sama di seluruh dokumen. Buat image brush dari isi dokumen pertama dan gunakan untuk mengisi glyph di dokumen kedua. Teknik “gambar asing” ini memungkinkan Anda menggunakan kembali karya seni tanpa menggandakan file sumber.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Langkah 7: Simpan Dokumen

`Save` menulis paket XPS ke file, menyematkan semua sumber daya. Simpan kedua dokumen XPS pertama dan kedua ke folder output. Metode `Save` menulis paket XPS, menyematkan semua sumber daya dan mempertahankan glyph terisi gambar.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Gambar tidak muncul di dalam glyph** | `ImageBrush` dibuat dengan URI yang salah atau ukuran gambar melebihi batas glyph. | Verifikasi jalur gambar, dan opsional set `ImageBrush.Stretch = Stretch.Uniform`. |
| **Font tidak ada di dokumen kedua** | Sumber daya font tidak diekspor dari XPS pertama. | Gunakan `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` sebelum menambahkan glyph. |
| **Penurunan kinerja pada file besar** | Memuat gambar besar ke memori untuk setiap glyph. | Gunakan satu instance `ImageBrush` untuk semua glyph, atau turunkan resolusi gambar sebelum digunakan. |

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menggunakan format gambar yang berbeda untuk mengisi glyph?

A1: Ya, Aspose.Page mendukung PNG, JPEG, BMP, GIF, TIFF, dan lainnya—lebih dari 25 format secara total.

### Q2: Bagaimana saya dapat menyesuaikan tampilan glyph lebih lanjut?

A2: Jelajahi properti seperti `Glyph.Stroke`, `Glyph.FillOpacity`, dan `Glyph.Transform` untuk menyesuaikan garis tepi, transparansi, dan rotasi.

### Q3: Apakah Aspose.Page cocok untuk menangani set dokumen besar?

A3: Tentu. Perpustakaan ini memproses file XPS beratus‑ratus halaman menggunakan streaming, menjaga penggunaan memori di bawah 100 MB bahkan untuk dokumen 500 halaman.

### Q4: Bisakah saya menerapkan gaya berbeda pada masing‑masing glyph?

A4: Ya, setiap instance `Glyph` memiliki properti `Fill`, `Stroke`, dan `Transform` masing‑masing, memungkinkan penataan per‑glyph.

### Q5: Apa manfaat menggunakan Aspose.Page dibandingkan alat XPS lainnya?

A5: Aspose.Page mendukung lebih dari 25 format gambar, memproses file hingga 500 MB tanpa memuat seluruh memori, dan menyediakan API 100 % .NET‑native—menghilangkan kebutuhan akan interop COM atau alat eksternal.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat Dokumen XPS – Aspose.Page untuk .NET](/page/net/document-creation/)
- [Tambahkan Gambar ke Dokumen XPS dengan Aspose.Page untuk .NET](/page/net/image-management/add-image-to-xps-document/)
- [Tambahkan Salinan Glyph dan Ubah Warna dengan Aspose.Page untuk .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
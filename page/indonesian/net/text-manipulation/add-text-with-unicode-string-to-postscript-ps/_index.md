---
date: 2026-03-21
description: Pelajari cara membuat dokumen PostScript C# dengan teks Unicode menggunakan
  Aspose.Page untuk .NET – cara cepat untuk meningkatkan manipulasi dokumen.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Buat dokumen PostScript C# dengan teks Unicode – Aspose.Page
url: /id/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Teks dengan String Unicode ke PostScript (PS) menggunakan Aspose.Page

## Pendahuluan

Jika Anda perlu **membuat dokumen PostScript C#** dan menyisipkan karakter Unicode, Aspose.Page untuk .NET membuat prosesnya menjadi sederhana. Pada tutorial ini kami akan memandu Anda melalui contoh lengkap, langkah‑demi‑langkah yang menunjukkan cara menambahkan teks Jepang (atau string Unicode apa pun) ke file PS, memilih font khusus, dan menyimpan hasilnya. Pada akhir tutorial, Anda akan memiliki potongan kode yang dapat digunakan kembali dalam proyek C# mana pun.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan teks Unicode ke file PostScript menggunakan Aspose.Page dalam C#.
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk .NET (versi terbaru).
- **Apakah saya memerlukan font khusus?** Font TrueType/OpenType apa pun yang mendukung rentang Unicode yang diinginkan, misalnya *Arial Unicode MS*.
- **Berapa banyak baris kode?** Sekitar 30 baris, dibagi menjadi langkah‑langkah yang jelas.
- **Apakah diperlukan lisensi?** Lisensi sementara cukup untuk evaluasi; lisensi penuh diperlukan untuk produksi.

## Apa itu “create postscript document c#”?
Membuat dokumen PostScript dalam C# berarti menghasilkan file .ps secara programatik yang mengikuti spesifikasi bahasa PostScript. Aspose.Page menyembunyikan detail tingkat rendah, sehingga Anda dapat fokus pada konten seperti teks, grafik, dan font.

## Mengapa menggunakan Aspose.Page untuk teks Unicode?
- **Dukungan Unicode penuh** – menampilkan karakter dari bahasa apa pun tanpa harus mengatur encoding secara manual.
- **Tidak bergantung pada perangkat** – kode yang sama bekerja untuk output PS, EPS, dan PDF.
- **Tanpa ketergantungan eksternal** – perpustakaan menangani pemuatan font dan pemetaan glyph secara internal.

## Prasyarat

- Familiaritas dasar dengan C# dan pengembangan .NET.
- Perpustakaan Aspose.Page untuk .NET terpasang. Anda dapat mengunduhnya dari [dokumentasi Aspose.Page untuk .NET](https://reference.aspose.com/page/net/).
- Sebuah folder yang berisi font yang akan Anda gunakan (misalnya *Arial Unicode MS*).

## Impor Namespace

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Siapkan Direktori Dokumen dan Folder Font

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Langkah 2: Buat Stream Output untuk Dokumen PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Langkah 3: Tambahkan Teks Unicode dengan Font Kustom

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Langkah 4: Tutup Halaman Saat Ini

```csharp
document.ClosePage();
```

## Langkah 5: Finalisasi dan Simpan Dokumen

```csharp
document.Save();
```

## Masalah Umum dan Solusinya

- **Font tidak ditemukan** – Pastikan jalur `AdditionalFontsFolders` mengarah ke folder yang berisi file .ttf/.otf dan nama font cocok persis.
- **Karakter menjadi sampah** – Pastikan string sumber dienkode sebagai UTF‑8 dalam file sumber C# Anda (gunakan `#pragma warning disable 1591` bila diperlukan).
- **File tidak dibuat** – Periksa izin menulis pada `dataDir` dan pastikan stream dibuang dengan benar (blok `using` menangani ini).

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Page untuk .NET dengan bahasa pemrograman lain?**  
J: Aspose.Page terutama dirancang untuk .NET, tetapi ada setara Java yang tersedia.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk .NET?**  
J: Kunjungi [Temporary License](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara.

**T: Apakah ada forum komunitas untuk diskusi Aspose.Page?**  
J: Ya, kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

**T: Format apa saja yang dapat dikerjakan oleh Aspose.Page untuk .NET?**  
J: Aspose.Page mendukung berbagai format, termasuk XPS, PS, EPS, PDF, dan lainnya.

**T: Bisakah saya menyesuaikan tampilan teks yang ditambahkan?**  
J: Ya, Anda dapat menyesuaikan font, ukuran, warna, dan properti lain dari teks di Aspose.Page.

## Kesimpulan

Dalam tutorial ini kami menunjukkan cara **membuat dokumen PostScript C#** dan menyisipkan teks Unicode menggunakan Aspose.Page. Dengan mengikuti langkah‑langkah di atas, Anda dapat dengan cepat mengintegrasikan rendering teks multibahasa ke dalam aplikasi .NET apa pun, memberi Anda kontrol penuh atas pembuatan dan tata letak dokumen.

---

**Terakhir Diperbarui:** 2026-03-21  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-21
description: Pelajari cara mengisi teks dan menambahkan teks ke dokumen PS menggunakan
  Aspose.Page untuk .NET. Panduan langkah demi langkah dengan contoh kode.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Cara Mengisi Teks dalam Dokumen PostScript (PS) dengan Aspose.Page
url: /id/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengisi Teks dalam Dokumen PostScript (PS) dengan Aspose.Page

## Pendahuluan

Jika Anda perlu **cara mengisi teks** di dalam file PostScript (PS), Aspose.Page untuk .NET mempermudahnya. Baik Anda membuat laporan, faktur, atau grafik khusus, menambahkan dan menata teks adalah kebutuhan utama. Pada tutorial ini kami akan membimbing Anda melalui seluruh proses—dari menyiapkan lingkungan hingga menyimpan dokumen PS akhir—sehingga Anda dapat menambahkan teks ke file PS dengan percaya diri dalam aplikasi .NET Anda.

## Jawaban Cepat
- **Apa arti “fill text”?** Itu merender karakter menggunakan kuas solid, melukis glif langsung ke halaman.  
- **Apakah saya dapat menggunakan font kustom?** Ya—Aspose.Page mendukung font kustom melalui fitur `add custom font ps`.  
- **Bagaimana cara menyimpan dokumen PS?** Panggil `document.Save()` setelah menutup halaman; ini menulis file ke disk (`save ps document`).  
- **Apakah “fill and stroke text” didukung?** Tentu saja; gunakan `FillAndStrokeText` untuk menerapkan isi dan garis tepi sekaligus.  
- **Versi .NET apa yang dibutuhkan?** .NET Framework 4.5+ atau runtime .NET Core/5/6+.

## Apa itu “cara mengisi teks” dalam dokumen PS?

Mengisi teks berarti melukis karakter dengan warna (atau kuas) solid tanpa garis tepi. Di PostScript, ini analog dengan operator `fill`. Aspose.Page menyederhanakannya menjadi metode yang mudah digunakan seperti `FillText` dan `FillAndStrokeText`.

## Mengapa menggunakan Aspose.Page untuk menambahkan custom font ps?

- **Dukungan font lengkap** – font sistem dan font TrueType/OpenType eksternal berfungsi langsung.  
- **Posisi yang tepat** – Anda mengontrol koordinat X/Y, ukuran, dan gaya.  
- **Styling kaya** – gabungkan isi, garis tepi, dan pena untuk efek seperti “fill and stroke text”.  
- **Lintas‑platform** – bekerja di Windows, Linux, dan macOS dengan API yang sama.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Page untuk .NET** – unduh perpustakaan dari [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Direktori Dokumen** – folder di mesin Anda tempat file PS sumber dan output akan disimpan (disebut *Your Document Directory* dalam kode).  
- **Folder Font** – sub‑folder yang berisi semua font kustom yang akan Anda gunakan.

## Impor Namespace

Pertama, impor namespace yang diperlukan agar kompiler mengetahui lokasi kelas yang akan kita gunakan:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Output Stream untuk Dokumen PS  

Kami membuka `FileStream` yang akan menampung file PS yang dihasilkan, mengonfigurasi `PsSaveOptions` untuk menunjuk ke folder font kustom kami, dan menginstansiasi `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tip:** Pertahankan blok `using` untuk memastikan aliran ditutup secara otomatis, yang juga menyelesaikan file PS (`save ps document`).

### Langkah 2: Isi Teks dengan Font Sistem  

Di sini kami mendemonstrasikan operasi **cara mengisi teks** dasar menggunakan font *Times New Roman* bawaan.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Langkah 3: Isi Teks dengan Font Kustom  

Jika Anda memerlukan tampilan khusus, muat font kustom dari folder font menggunakan `ExternalFontCache.FetchDrFont`. Ini memenuhi persyaratan **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Langkah 4: Gariskan (Stroke) Teks dengan Font Sistem  

Menggariskan menggambar kontur glif. Gabungkan dengan isi untuk efek “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Mengapa ini penting:** Panggilan `FillAndStrokeText` menunjukkan cara **fill and stroke text** dalam satu langkah, memberi Anda kontrol tipografi yang lebih kaya.

### Langkah 5: Gariskan Teks dengan Font Kustom  

Teknik garisan yang sama bekerja dengan font kustom apa pun yang telah Anda muat.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Langkah 6: Tutup Halaman dan Simpan Dokumen  

Menyelesaikannya sangat mudah: tutup halaman saat ini dan panggil `Save()` untuk menulis file PS ke disk.

```csharp
document.ClosePage();
document.Save();
}
```

> **Hasil:** Anda akan menemukan `AddText_outPS.ps` di *Your Document Directory*, berisi teks yang diisi dan digariskan dengan font sistem serta font kustom.

## Masalah Umum dan Solusinya

| Masalah | Solusi |
|-------|----------|
| **Font kustom tidak ditemukan** | Pastikan file font (.ttf/.otf) ada di folder yang dirujuk oleh `AdditionalFontsFolders`. |
| **Teks muncul di posisi yang salah** | Sesuaikan koordinat X/Y yang diberikan ke `FillText`/`OutlineText`. Ingat bahwa PostScript menggunakan poin (1/72 inci). |
| **Warna terlihat berbeda** | Pastikan Anda menggunakan `SolidBrush` atau `Pen` dengan nilai `Color` yang tepat. |
| **Dokumen tidak tersimpan** | Pastikan blok `using` selesai tanpa pengecualian dan aplikasi memiliki izin menulis ke folder target. |

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat menggunakan Aspose.Page dengan perpustakaan .NET lainnya?**  
J: Ya, Aspose.Page terintegrasi mulus dengan komponen .NET lain, memungkinkan Anda menggabungkan perpustakaan PDF, gambar, atau chart dalam solusi yang sama.

**T: Apakah font kustom penting untuk proses ini?**  
J: Meskipun font sistem sudah cukup, font kustom memberi kebebasan desain penuh dan berguna ketika tipografi khusus merek diperlukan.

**T: Apakah Aspose.Page cocok untuk pemrosesan dokumen berskala besar?**  
J: Tentu. Perpustakaan ini dioptimalkan untuk skenario throughput tinggi dan dapat menangani ribuan file PS secara efisien.

**T: Bisakah saya mengubah posisi teks dalam dokumen PS?**  
J: Tentu—cukup ubah nilai numerik X/Y dalam pemanggilan `FillText` atau `OutlineText`.

**T: Di mana saya dapat mencari bantuan untuk pertanyaan terkait Aspose.Page?**  
J: Kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan bantuan ahli.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-03-21  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose
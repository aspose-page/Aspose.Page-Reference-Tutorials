---
date: 2026-03-21
description: Pelajari cara menambahkan teks Unicode ke dokumen XPS menggunakan Aspose.Page
  untuk .NET. Panduan ini menunjukkan cara membuat dokumen XPS dengan C# dan menambahkan
  teks dengan string Unicode menggunakan Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Cara Menambahkan Teks Unicode ke Dokumen XPS dengan Aspose.Page
url: /id/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Teks Unicode ke Dokumen XPS dengan Aspose.Page

## Pendahuluan

Jika Anda perlu **how to add unicode** karakter ke file XPS, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat yang diperlukan untuk **create XPS document C#**‑style menggunakan Aspose.Page untuk .NET dan mendemonstrasikan kemampuan **aspose page add text** dengan string Unicode. Pada akhir tutorial Anda akan memiliki dokumen XPS yang berfungsi penuh dan menampilkan teks Unicode right‑to‑left (RTL) dengan benar.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan teks Unicode ke dokumen XPS dengan Aspose.Page untuk .NET.  
- **Bahasa apa yang digunakan?** C# (kompatibel dengan .NET Framework dan .NET Core).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Apakah saya dapat mengubah font atau ukuran?** Ya – contoh menggunakan Arial 20 pt, tetapi font apa pun yang terpasang dapat digunakan.  
- **Apakah dukungan RTL termasuk?** Menetapkan `BidiLevel = 1` mengaktifkan rendering right‑to‑left untuk string Unicode.

## Apa itu “how to add unicode” dalam XPS?

Menambahkan teks Unicode berarti menyisipkan karakter dari bahasa apa pun—Arab, Ibrani, Cina, dll.—ke dalam dokumen XPS. Kelas `XpsGlyphs` milik Aspose.Page menangani penempatan glyph tingkat rendah, sementara properti `BidiLevel` mengontrol arah teks untuk skrip RTL.

## Mengapa menggunakan Aspose.Page untuk menambahkan teks?

- **Integrasi .NET penuh** – bekerja dengan .NET Framework, .NET Core, .NET 5/6+.  
- **Tanpa dependensi eksternal** – kode murni yang dikelola, tanpa interop COM.  
- **Dukungan tipografi lengkap** – font, gaya, warna, dan teks bidirectional.  
- **Kinerja tinggi** – membuat dan menyimpan file XPS dengan cepat, ideal untuk generasi sisi server.

## Prasyarat

- Pengetahuan dasar tentang C# dan pengembangan .NET.  
- Visual Studio (versi terbaru apa pun).  
- Perpustakaan Aspose.Page untuk .NET – unduh dari [here](https://releases.aspose.com/page/net/).

## Impor Namespace

Pertama, impor namespace yang memberi Anda akses ke model XPS dan utilitas menggambar.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Siapkan Dokumen – create XPS document C#

Buat dokumen XPS baru yang akan menampung teks Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Langkah 2: Tambahkan Teks Unicode – aspose page add text

Sekarang kita menambahkan string Unicode sebenarnya. Dalam contoh ini kami menggunakan font Arial, ukuran 20, dan menempatkan teks pada (400 f, 200 f). `BidiLevel` sebesar 1 memberi tahu renderer untuk memperlakukan string sebagai right‑to‑left.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Langkah 3: Simpan Dokumen

Akhirnya, simpan file XPS ke disk.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Selamat! Anda telah berhasil menambahkan teks **how to add unicode** ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Teks muncul berantakan | Font tidak mendukung rentang Unicode | Gunakan font yang berisi glyph yang diperlukan (mis., Arial Unicode MS). |
| Teks RTL masih left‑to‑right | `BidiLevel` tidak disetel atau disetel ke 0 | Pastikan `glyphs.BidiLevel = 1;` untuk skrip RTL. |
| File tidak tersimpan | Path `dataDir` tidak valid | Pastikan direktori ada dan aplikasi memiliki izin menulis. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page kompatibel dengan .NET framework terbaru?**  
A: Ya, Aspose.Page secara rutin diperbarui untuk mendukung .NET Framework, .NET Core, dan .NET 5/6+.

**Q: Bisakah saya menyesuaikan gaya dan ukuran font saat menambahkan teks?**  
A: Tentu saja! Metode `AddGlyphs` memungkinkan Anda menentukan keluarga font, ukuran, dan `FontStyle` apa pun yang Anda butuhkan.

**Q: Di mana saya dapat menemukan dokumentasi tambahan untuk Aspose.Page?**  
A: Anda dapat merujuk ke dokumentasi [here](https://reference.aspose.com/page/net/) untuk detail API yang komprehensif.

**Q: Apakah ada sumber daya gratis untuk memulai dengan Aspose.Page?**  
A: Ya, jelajahi forum komunitas di [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk tip, contoh, dan dukungan sesama pengguna.

**Q: Apakah ada versi percobaan yang tersedia sebelum membeli?**  
A: Tentu! Unduh versi percobaan gratis dari [here](https://releases.aspose.com/) untuk mengevaluasi perpustakaan.

**Terakhir Diperbarui:** 2026-03-21  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
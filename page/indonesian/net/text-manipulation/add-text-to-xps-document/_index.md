---
date: 2026-03-21
description: Pelajari cara membuat dokumen XPS .NET dan menambahkan teks menggunakan
  Aspose.Page untuk .NET. Panduan langkah demi langkah untuk pengembang .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Buat dokumen XPS .NET dan tambahkan teks dengan Aspose.Page
url: /id/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat dokumen XPS .NET dan tambahkan teks dengan Aspose.Page

Dalam pengembangan .NET modern, kemampuan untuk **create XPS document .NET** file secara programatis adalah keterampilan yang berharga, terutama ketika Anda perlu menghasilkan laporan yang dapat dicetak, faktur, atau grafik khusus. Tutorial ini memandu Anda menggunakan Aspose.Page untuk **aspose.page add text** ke dokumen XPS, memberi Anda kontrol penuh atas tata letak dan gaya—semua dari dalam aplikasi .NET Anda.

## Jawaban Cepat
- **What does this tutorial cover?** Menambahkan teks ke dokumen XPS yang baru dibuat menggunakan Aspose.Page untuk .NET.  
- **How long does it take?** Sekitar 5‑10 menit untuk implementasi dasar.  
- **What are the prerequisites?** Lingkungan pengembangan .NET dan pustaka Aspose.Page.  
- **Is a license required?** Ya, lisensi Aspose.Page yang valid diperlukan untuk penggunaan produksi.  
- **Can it run on .NET Core / .NET 6+?** Tentu – Aspose.Page mendukung semua versi .NET terbaru.

## Apa itu create xps document .net?

Membuat dokumen XPS di .NET berarti menghasilkan file tata letak tetap yang mempertahankan tampilan tepat dari konten Anda di berbagai perangkat dan printer. XPS (XML Paper Specification) adalah standar terbuka Microsoft untuk deskripsi halaman, mirip dengan PDF tetapi sepenuhnya berbasis XML.

## Mengapa menggunakan Aspose.Page untuk menambahkan teks?

Aspose.Page menawarkan API tingkat tinggi yang berorientasi objek yang mengabstraksi markup XPS tingkat rendah. Anda dapat menambahkan teks, grafik, dan bentuk tanpa harus berurusan dengan XML mentah, membuat proses pengembangan lebih cepat dan kurang rawan kesalahan.

## Prasyarat

- Aspose.Page untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Page. Anda dapat mengunduhnya dari [dokumentasi Aspose.Page untuk .NET](https://reference.aspose.com/page/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET Anda. Jika belum melakukannya, ikuti petunjuk instalasi yang disediakan dalam [dokumentasi](https://reference.aspose.com/page/net/).
- Direktori Dokumen: Buat direktori tempat Anda akan menyimpan dokumen. Ganti "Your Document Directory" dalam potongan kode yang disediakan dengan jalur yang sebenarnya.

Sekarang setelah kami membahas dasar-dasarnya, mari selami kode.

## Impor Namespace

Pertama, impor namespace yang diperlukan untuk memulai proyek:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Buat dokumen XPS .NET

Buat dokumen XPS baru yang akan menjadi kanvas untuk teks kami.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Langkah 2: Buat kuas untuk teks

Tentukan kuas berwarna solid yang menentukan warna teks. Di sini kami menggunakan hitam.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Langkah 3: Tambahkan glyphs (aspose.page add text)

Glyphs adalah representasi tingkat rendah dari karakter dalam dokumen XPS. Panggilan ini menambahkan teks “Hello World!” pada koordinat yang ditentukan.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Langkah 4: Simpan dokumen XPS hasil

Simpan dokumen ke disk sehingga Anda dapat melihat atau mencetaknya nanti.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Dengan mengikuti langkah-langkah ini, Anda telah berhasil **create XPS document .NET** dan menambahkan teks khusus menggunakan Aspose.Page.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File not found** when saving | `dataDir` points to a non‑existent folder | Pastikan direktori ada atau gunakan `Directory.CreateDirectory(dataDir)` sebelum menyimpan. |
| **Text not visible** | Brush color matches background | Ubah `Color.Black` ke warna kontras lainnya. |
| **Unsupported font** | Font not installed on the machine | Gunakan font yang dijamin ada, atau sematkan font menggunakan fitur font‑embedding Aspose.Page. |

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menyesuaikan font dan ukuran teks yang ditambahkan?

A1: Ya, Anda memiliki kontrol penuh atas font dan ukuran. Sesuaikan parameter dalam metode `AddGlyphs` sesuai kebutuhan.

### Q2: Apakah Aspose.Page kompatibel dengan .NET Core?

A2: Tentu! Aspose.Page mendukung .NET Core, memastikan kompatibilitas dengan teknologi .NET terbaru.

### Q3: Apakah ada persyaratan lisensi untuk menggunakan Aspose.Page?

A3: Ya, Anda memerlukan lisensi yang valid. Jelajahi opsi lisensi [di sini](https://purchase.aspose.com/buy).

### Q4: Bagaimana saya dapat mendapatkan dukungan atau bantuan?

A4: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan bantuan.

### Q5: Apakah tersedia percobaan gratis?

A5: Tentu! Anda dapat mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

**Pertanyaan Tambahan**

**Q: Bisakah saya menambahkan beberapa blok teks pada halaman yang sama?**  
A: Ya, cukup panggil `doc.AddGlyphs` beberapa kali dengan koordinat yang berbeda.

**Q: Apakah Aspose.Page memungkinkan rotasi teks?**  
A: Anda dapat menerapkan matriks transformasi ke objek `XpsGlyphs` untuk memutar atau memiringkan teks.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Terakhir Diperbarui:** 2026-03-21  
**Diuji dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

---
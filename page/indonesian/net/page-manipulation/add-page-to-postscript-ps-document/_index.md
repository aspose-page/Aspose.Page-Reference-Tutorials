---
date: 2026-03-03
description: Pelajari cara mengatur ukuran halaman khusus dan menambahkan halaman
  PS kedua ke dokumen PostScript menggunakan Aspose.Page untuk .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Atur Ukuran Halaman Kustom dalam Dokumen PS dengan Aspose.Page
url: /id/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Halaman ke Dokumen PostScript (PS) dengan Aspose.Page

## Introduction

Dalam pengembangan .NET, kemampuan untuk **set custom page size** dan **add second PS page** ke dokumen PostScript (PS) memberi Anda kontrol yang sangat detail atas tata letak cetakan, laporan, atau grafik yang dihasilkan. Aspose.Page untuk .NET membuat tugas ini sederhana dengan API yang bersih dan berorientasi objek. Pada tutorial ini Anda akan belajar cara membuat file PS multi‑halaman, menentukan ukuran khusus untuk setiap halaman, dan menyimpan hasilnya—semua dengan hanya beberapa baris kode C#.

## Jawaban Cepat
- **Apakah saya dapat mengatur ukuran halaman khusus?** Ya – cukup berikan lebar dan tinggi saat membuka halaman.  
- **Bagaimana cara menambahkan halaman PS kedua?** Panggil `document.OpenPage(width, height)` untuk kedua kalinya.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Di mana saya dapat mengunduh Aspose.Page?** Dari halaman unduhan resmi yang ditautkan di bawah.

## Prasyarat

Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan yang baik tentang pengembangan .NET.  
- Visual Studio terinstal di mesin Anda.  
- Pustaka Aspose.Page untuk .NET, yang dapat Anda unduh [di sini](https://releases.aspose.com/page/net/).  
- Direktori dokumen pilihan Anda untuk pengujian.

## Impor Namespace

Pastikan Anda menyertakan namespace yang diperlukan dalam proyek Anda untuk mengakses fungsionalitas yang disediakan oleh Aspose.Page. Pada contoh yang diberikan, namespace disertakan secara implisit, tetapi penting untuk memeriksa kembali dan melakukan penyesuaian berdasarkan struktur proyek Anda.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Langkah 1: Siapkan Proyek Anda

Buat proyek .NET baru di Visual Studio dan atur konfigurasi yang diperlukan. Pastikan untuk menambahkan referensi ke pustaka Aspose.Page dalam proyek Anda.

## Atur Ukuran Halaman Kustom dan Tambahkan Halaman PS Kedua

Bagian ini menunjukkan secara tepat cara **set custom page size** untuk setiap halaman dan cara **add second ps page** ke dokumen yang sama.

### Langkah 2: Inisialisasi Dokumen

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Langkah 3: Tambahkan Halaman Pertama (ukuran default)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Langkah 4: Tambahkan Halaman Kedua dengan Ukuran Berbeda (Kustom)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Langkah 5: Simpan Dokumen

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Ikuti langkah-langkah ini dengan cermat, dan Anda akan berhasil **set custom page size** dan menambahkan **second PS page** ke dokumen PostScript menggunakan Aspose.Page untuk .NET.

## Mengapa Ini Penting

- **Precision Layout** – Ukuran halaman kustom memungkinkan Anda menyesuaikan spesifikasi printer atau membuat format brosur yang unik.  
- **Multiple Pages** – Menambahkan halaman kedua (atau lebih) memungkinkan laporan multi‑halaman tanpa alat penggabungan eksternal.  
- **Cross‑Platform** – File PS yang dihasilkan dapat ditampilkan pada perangkat yang kompatibel dengan PostScript apa pun atau dikonversi ke PDF nanti.

## Kesalahan Umum & Pemecahan Masalah

- **Incorrect Path** – Pastikan `dataDir` diakhiri dengan pemisah jalur atau gunakan `Path.Combine`.  
- **License Issues** – Tanpa lisensi yang valid, pustaka dapat menambahkan watermark atau membatasi jumlah halaman.  
- **Unit Confusion** – Lebar dan tinggi diukur dalam point (1 point = 1/72 inci). Sesuaikan sesuai kebutuhan.

## Pertanyaan yang Sering Diajukan

**Q1: Apakah Aspose.Page kompatibel dengan format dokumen yang berbeda?**  
A1: Aspose.Page terutama berfokus pada manipulasi dokumen PostScript. Untuk format lain, Anda dapat menjelajahi pustaka Aspose yang disesuaikan dengan kebutuhan spesifik.

**Q2: Bisakah saya menyesuaikan ukuran halaman di Aspose.Page?**  
A2: Tentu saja! Seperti yang ditunjukkan dalam tutorial, Anda dapat menentukan ukuran yang berbeda untuk setiap halaman sesuai kebutuhan Anda.

**Q3: Di mana saya dapat menemukan contoh dan dokumentasi lebih lanjut?**  
A3: Kunjungi [documentation](https://reference.aspose.com/page/net/) untuk informasi lengkap dan berbagai contoh.

**Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?**  
A4: Arahkan ke [this link](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara untuk keperluan pengujian.

**Q5: Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan?**  
A5: Bergabunglah dengan [Aspose.Page community forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan pengembang lain, berbagi pengalaman, dan mencari bantuan.

---

**Terakhir Diperbarui:** 2026-03-03  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
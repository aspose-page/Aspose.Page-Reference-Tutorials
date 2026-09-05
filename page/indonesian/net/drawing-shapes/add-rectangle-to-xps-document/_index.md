---
date: 2026-07-19
description: Pelajari cara membuat dokumen XPS .NET dan menambahkan persegi panjang
  menggunakan Aspose.Page untuk .NET dalam panduan singkat langkah demi langkah.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Tambahkan Persegi Panjang ke Dokumen XPS
og_description: Buat dokumen XPS .NET dengan cepat. Tutorial ini menunjukkan cara
  menambahkan persegi panjang ke file XPS menggunakan Aspose.Page untuk .NET, dengan
  kode yang jelas dan tip.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Buat Dokumen XPS .NET – Tambahkan Persegi Panjang dengan Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Buat Dokumen XPS .NET – Tambahkan Persegi Panjang dengan Aspose.Page
url: /id/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS .NET – Tambahkan Persegi Panjang dengan Aspose.Page

## Pendahuluan

Dalam tutorial ini Anda akan belajar cara **create XPS document .NET** dan menggambar sebuah persegi panjang di dalamnya menggunakan Aspose.Page untuk .NET. Baik Anda sedang membangun mesin pelaporan, faktur yang dapat dicetak, atau lapisan grafis khusus, kemampuan untuk menghasilkan file XPS secara programatik memberi Anda kontrol penuh atas tata letak dan kesetiaan. Ikuti langkah‑langkah di bawah ini dan Anda akan memiliki file XPS siap pakai dalam hitungan menit.

## Jawaban Cepat
- **Apa tujuan utama?** Membuat dokumen XPS .NET dan menambahkan bentuk persegi panjang.  
- **Perpustakaan mana yang diperlukan?** Aspose.Page untuk .NET (dapat diunduh dari situs resmi).  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa lama waktu implementasinya?** Sekitar 5‑10 menit untuk persegi panjang dasar.

## Apa itu Aspose.Page untuk .NET?
Aspose.Page untuk .NET adalah API berperforma tinggi, sepenuhnya dikelola yang memungkinkan pengembang untuk secara programatik membuat, mengedit, dan merender dokumen XPS (XML Paper Specification) tanpa bergantung pada komponen eksternal. Ia menawarkan model objek yang kaya untuk menggambar bentuk, teks, dan gambar, serta mendukung fitur lanjutan seperti manajemen warna, kompresi, dan konversi PDF, menjadikannya cocok untuk berbagai skenario pembuatan dokumen.

## Mengapa menggunakan Aspose.Page untuk membuat dokumen XPS .NET?
Aspose.Page mendukung **30+ fitur XPS**—termasuk grafik vektor, tata letak teks, dan manajemen warna—dan dapat menghasilkan file hingga **500 MB** tanpa memuat seluruh dokumen ke dalam memori. Kemampuan terukur ini memastikan kinerja yang lancar bahkan untuk pekerjaan pencetakan berskala besar.

## Prasyarat

Sebelum Anda memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:

1. Perpustakaan Aspose.Page untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Page untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).
2. Direktori Dokumen: Siapkan direktori tempat Anda ingin menyimpan dokumen XPS Anda.

## Impor Namespace

Dalam aplikasi .NET Anda, sertakan namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bagaimana cara menambahkan persegi panjang ke dokumen XPS di .NET?

Muat dokumen XPS, buat objek `Graphics`, tentukan `RectangleF` dengan ukuran yang diinginkan, dan panggil `DrawRectangle`. Urutan ini menggambar persegi panjang dalam satu baris kode dan secara otomatis menangani skala DPI. Untuk halaman berukuran A4 standar, persegi panjang 200 × 100 pt muncul di tengah tanpa perhitungan tambahan.

### Langkah 1: Atur Direktori Dokumen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Langkah 2: Buat Dokumen XPS Baru

Kelas `XpsDocument` mewakili file XPS yang sedang Anda bangun dan menyediakan metode untuk menambahkan halaman, grafik, dan sumber daya lainnya.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Langkah 3: Tambahkan Persegi Panjang

`XpsPath` mendefinisikan objek jalur yang dapat digambar dalam dokumen XPS, memungkinkan Anda mengatur geometri, garis tepi, isi, dan properti visual lainnya.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Langkah 4: Simpan Dokumen

Metode `Save` menulis dokumen XPS yang telah dibangun ke jalur file yang ditentukan di disk.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Selamat! Anda telah berhasil menambahkan persegi panjang ke dokumen XPS menggunakan Aspose.Page untuk .NET.

## Masalah Umum dan Tips

- **Font yang hilang:** Pastikan font yang Anda referensikan terpasang di server; jika tidak, Aspose.Page akan menggantinya dengan font default, yang dapat mengubah tata letak.  
- **Dokumen besar:** Saat menghasilkan file lebih besar dari 200 MB, pertimbangkan memanggil `document.SaveOptions.Compress = true` untuk mengurangi penggunaan memori.  
- **Sistem koordinat:** XPS menggunakan poin (1/72 inci). Ingat untuk mengonversi piksel ke poin jika Anda bekerja dengan dimensi berbasis layar.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page kompatibel dengan semua aplikasi .NET?**  
A: Ya, Aspose.Page bekerja mulus dengan aplikasi .NET desktop, web, dan cloud.

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk .NET?**  
A: Referensi API lengkap tersedia [di sini](https://reference.aspose.com/page/net/).

**Q: Bisakah saya mencoba Aspose.Page untuk .NET secara gratis sebelum membeli?**  
A: Ya, Anda dapat mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page untuk .NET?**  
A: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara.

**Q: Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan terkait Aspose.Page untuk .NET?**  
A: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

---

**Terakhir Diperbarui:** 2026-07-19  
**Diuji Dengan:** Aspose.Page for .NET 24.9  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Dokumen XPS dengan Aspose.Page untuk .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Menggambar Bentuk](/page/net/drawing-shapes/)
- [Tambahkan Teks ke Dokumen XPS dengan Aspose.Page untuk .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
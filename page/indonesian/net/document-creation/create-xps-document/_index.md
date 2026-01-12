---
date: 2026-01-12
description: Pelajari cara membuat dokumen XPS dengan Aspose.Page untuk .NET – panduan
  langkah demi langkah untuk menghasilkan dokumen elektronik berkualitas tinggi.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Buat Dokumen XPS dengan Aspose.Page untuk .NET
url: /id/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Selamat datang di panduan langkah‑demi‑langkah kami tentang **cara membuat dokumen XPS** menggunakan Aspose.Page untuk .NET. Dalam tutorial ini, kami akan menjelajahi proses menghasilkan file XPS, format yang banyak digunakan untuk dokumen elektronik. Baik Anda seorang pengembang berpengalaman maupun baru memulai dengan Aspose.Page, panduan ini dirancang untuk membantu Anda membuat dokumen XPS dengan mulus melalui contoh yang jelas dan penjelasan terperinci.

## Jawaban Cepat
- **Apa perpustakaan yang saya butuhkan?** Aspose.Page for .NET  
- **Apakah saya dapat menjalankannya di .NET Core?** Yes, the library fully supports .NET Core and .NET 5/6  
- **Berapa baris kode?** Less than 20 lines to produce a basic XPS file  
- **Apakah saya memerlukan lisensi untuk pengujian?** A free trial is available; a license is required for production  
- **Format apa yang dihasilkan?** XPS (XML Paper Specification)  

## Cara membuat dokumen XPS menggunakan Aspose.Page untuk .NET

Di bawah ini Anda akan menemukan semua yang Anda perlukan sebelum mulai menulis kode, diikuti dengan langkah‑langkah singkat berurutan.

## Prasyarat

Sebelum kita memulai tutorial, pastikan Anda memiliki prasyarat berikut:

1. **Perpustakaan Aspose.Page untuk .NET:** Unduh dan instal perpustakaan Aspose.Page dari [tautan unduhan](https://releases.aspose.com/page/net/).
2. **Direktori Dokumen Anda:** Pilih atau buat direktori di sistem Anda tempat Anda ingin menyimpan file XPS hasil.

Sekarang, mari kita mulai tutorial!

## Impor Namespace

Untuk menggunakan Aspose.Page untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah‑langkah berikut:

### Langkah 1: Tambahkan Referensi ke Aspose.Page

Di proyek Anda, tambahkan referensi ke perpustakaan Aspose.Page untuk .NET. Anda dapat menemukan DLL yang diperlukan dalam paket yang diunduh.

### Langkah 2: Impor Namespace

Sertakan namespace berikut dalam file kode Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Setelah kami menyiapkan prasyarat dan mengimpor namespace yang diperlukan, mari kita uraikan proses pembuatan dokumen XPS menjadi beberapa langkah.

## Langkah 1: Atur Direktori Dokumen

```csharp
string dir = "Your Document Directory";
```

Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan file XPS hasil.

## Langkah 2: Buat Dokumen XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inisialisasi dokumen XPS baru menggunakan kelas `XpsDocument`.

## Langkah 3: Tambahkan Glyph ke Dokumen

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Gunakan metode `AddGlyphs` untuk menambahkan glyph (teks) ke dokumen. Sesuaikan font, ukuran, gaya, dan posisi sesuai kebutuhan.

## Langkah 4: Atur Warna Isi Glyph

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Tentukan warna isi untuk glyph yang ditambahkan. Dalam contoh ini, kami menggunakan warna hitam, tetapi Anda dapat memilih warna apa saja.

## Langkah 5: Simpan Hasil

```csharp
xDocs.Save(dir + "output.xps");
```

Akhirnya, simpan dokumen XPS ke direktori yang ditentukan dengan nama file yang diinginkan. File XPS yang dihasilkan akan berisi teks "Hello World!".

Selamat! Anda telah berhasil membuat dokumen XPS menggunakan Aspose.Page untuk .NET.

## Tips & Gotchas Umum

- **Path Direktori** – Gunakan `Path.Combine(dir, "output.xps")` untuk menghindari kehilangan pemisah path pada OS yang berbeda.  
- **Ketersediaan Font** – Font yang Anda tentukan harus terpasang di mesin tempat kode dijalankan; jika tidak, Aspose akan menggantinya dengan font default.  
- **Multiple Pages** – Untuk membuat file XPS multi‑halaman, buat objek `XpsPage` tambahan dan tambahkan konten ke setiap halaman sebelum menyimpan.

## Kesimpulan

Dalam tutorial ini, kami menjelaskan proses pembuatan dokumen XPS menggunakan Aspose.Page untuk .NET. Perpustakaan yang kuat ini menyediakan cara yang mulus untuk menghasilkan dokumen elektronik dengan mudah. Bereksperimenlah dengan berbagai font, gaya, dan konten untuk menyesuaikan file XPS Anda dengan kebutuhan spesifik.

## FAQ's

### Q1: Can I use custom fonts in my XPS document?

A1: Ya, Anda dapat menentukan keluarga font dan ukuran saat menambahkan glyph ke dokumen XPS Anda.

### Q2: Is Aspose.Page compatible with .NET Core?

A2: Ya, Aspose.Page mendukung .NET Core, memungkinkan Anda menggunakannya dalam aplikasi lintas‑platform.

### Q3: How can I add images to an XPS document?

A3: Aspose.Page menyediakan metode untuk menambahkan gambar ke dokumen XPS Anda. Lihat dokumentasi untuk contoh terperinci.

### Q4: Can I create multi‑page XPS documents?

A4: Tentu saja! Anda dapat menambahkan beberapa halaman ke dokumen XPS menggunakan perpustakaan Aspose.Page.

### Q5: Is there a trial version available?

A5: Ya, Anda dapat menjelajahi fitur Aspose.Page dengan mengunduh [free trial](https://releases.aspose.com/).

---

**Terakhir Diperbarui:** 2026-01-12  
**Diuji Dengan:** Aspose.Page 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
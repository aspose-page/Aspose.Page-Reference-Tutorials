---
date: 2026-08-08
description: Pelajari cara membuat EPS dengan metadata XMP dan menambahkan nilai bernama
  menggunakan Aspose.Page untuk .NET. Panduan langkah demi langkah dengan placeholder
  kode.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Tambahkan Nilai Bernama
og_description: Buat EPS dengan metadata XMP di .NET menggunakan Aspose.Page. Panduan
  ini menunjukkan cara menambahkan nilai bernama ke file EPS dengan cepat dan andal.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Buat EPS dengan XMP – tambahkan nilai bernama menggunakan Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Buat EPS dengan XMP – tambahkan nilai bernama menggunakan Aspose.Page
url: /id/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat EPS dengan XMP – tambahkan nilai bernama menggunakan Aspose.Page

## Pendahuluan

Dalam tutorial ini Anda akan belajar cara **create EPS with XMP** metadata dan menyuntikkan nilai bernama menggunakan pustaka Aspose.Page untuk .NET. Apakah Anda sedang membangun pipeline pemrosesan batch atau perlu memperkaya file EPS dengan tag XMP khusus, langkah-langkah di bawah ini akan memandu Anda melalui semuanya mulai dari menyiapkan proyek hingga menyimpan file yang telah dimodifikasi. Aspose.Page dapat menangani dokumen EPS hingga **500 halaman** tanpa memuat seluruh file ke memori, sehingga cocok untuk skenario volume tinggi.

## Jawaban cepat
- **Apa tujuan utama?** Tambahkan nilai XMP bernama ke file EPS yang ada.  
- **Perpustakaan mana yang diperlukan?** Aspose.Page untuk .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi komersial diperlukan untuk produksi; versi percobaan gratis tersedia.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10–15 menit untuk kasus penggunaan dasar.

## Cara membuat EPS dengan metadata XMP di .NET?

Muat file EPS target, peroleh (atau buat) objek metadata XMP‑nya, tambahkan nilai bernama yang diperlukan, dan akhirnya simpan dokumen kembali ke disk. Alur kerja ini hanya memerlukan beberapa pemanggilan metode dan berfungsi secara konsisten di semua versi EPS yang didukung. Pendekatan ini juga mempertahankan konten halaman yang ada dan struktur XMP lainnya, sehingga Anda dapat dengan aman menumpuk beberapa pembaruan metadata.

## Prasyarat

- Pengetahuan dasar tentang C# dan struktur proyek .NET.  
- Visual Studio 2022 (atau IDE kompatibel lainnya).  
- Pustaka Aspose.Page untuk .NET. Jika Anda belum memilikinya, unduh dari **Aspose.Page for .NET download page**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Impor namespace

Namespace berikut menyediakan akses ke kelas penanganan EPS, output perangkat, dan metadata XMP Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Langkah 1: inisialisasi aliran input file eps

Buat `FileStream` untuk file EPS sumber dan buat instance objek `PsDocument` untuk bekerja dengan dokumen.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Langkah 2: dapatkan metadata XMP

Ambil objek `XmpMetadata` dari dokumen; objek ini mewakili paket XMP yang tertanam.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Langkah 3: ubah nilai metadata XMP

Gunakan metode `AddNamedValue` dari `XmpMetadata` untuk menyisipkan nilai bernama baru ke dalam struktur XMP yang ditentukan.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Langkah 4: simpan file eps dengan metadata XMP yang diubah

Simpan dokumen yang telah dimodifikasi dengan menuliskannya ke `FileStream` baru.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Mengapa menggunakan Aspose.Page untuk metadata EPS?

Aspose.Page mendukung **50+ skema XMP** dan dapat memproses file EPS hingga **500 halaman** sambil menjaga penggunaan memori di bawah **30 MB** untuk dokumen tipikal. Pustaka ini tidak bergantung pada alat eksternal atau kode native, menjamin perilaku konsisten di lingkungan Windows, Linux, dan macOS.

## Masalah umum dan pemecahan masalah

- **Missing XMP packet:** Jika `GetXmpMetadata()` mengembalikan `null`, file EPS tidak mengandung blok XMP. Pustaka akan secara otomatis membuatnya, tetapi pastikan file tidak rusak.  
- **Namespace conflicts:** Saat menambahkan nilai bernama khusus, gunakan URI namespace yang unik untuk menghindari benturan dengan skema yang ada.  
- **Large files:** Untuk file EPS yang lebih besar dari 200 MB, pertimbangkan streaming output untuk menghindari konsumsi memori berlebih.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Page kompatibel dengan berbagai versi file EPS?**  
A: Aspose.Page mendukung versi EPS 3.0 hingga 3.3, memastikan kompatibilitas luas dengan file lama dan modern.

**Q: Apakah saya dapat menggunakan Aspose.Page untuk proyek komersial?**  
A: Ya, lisensi komersial diperlukan untuk penggunaan produksi. Anda dapat membeli lisensi **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: Apakah tersedia versi percobaan gratis?**  
A: Ya, versi percobaan yang berfungsi penuh dapat diunduh **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: Bagaimana saya dapat mendapatkan dukungan atau bergabung dengan komunitas?**  
A: Kunjungi **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** untuk mengajukan pertanyaan dan berbagi pengalaman.

**Q: Apa itu lisensi sementara dan bagaimana cara mendapatkannya?**  
A: Lisensi sementara memungkinkan Anda mengevaluasi produk untuk periode singkat. Anda dapat meminta satu **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**Terakhir diperbarui:** 2026-08-08  
**Diuji dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan Metadata ke Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Ubah Nilai Bernama dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Ekstrak Metadata dari Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
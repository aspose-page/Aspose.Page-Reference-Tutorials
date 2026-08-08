---
date: 2026-08-08
description: Pelajari cara menginisialisasi dokumen Aspose.Page, menambahkan namespace
  XML, dan memodifikasi metadata XMP pada file EPS menggunakan Aspose.Page untuk .NET.
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: Tambahkan Namespace
og_description: Inisialisasi dokumen Aspose.Page, tambahkan namespace XML, dan edit
  metadata XMP pada file EPS dengan Aspose.Page untuk .NET. Ikuti langkah singkat
  dan potongan kode.
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: Inisialisasi dokumen Aspose.Page dan tambahkan namespace di .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: Inisialisasi dokumen Aspose.Page dan tambahkan namespace di .NET
url: /id/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Inisialisasi dokumen Aspose.Page dan tambahkan namespace di .NET

## Pendahuluan

Dalam pengembangan .NET modern, **initialize aspose page document** sering menjadi langkah pertama ketika Anda perlu bekerja dengan file EPS secara programatik. Aspose.Page untuk .NET memberikan kontrol penuh atas metadata XMP, memungkinkan Anda menambahkan namespace XML khusus, mengedit properti yang ada, dan menyimpan perubahan kembali ke file. Tutorial ini membimbing Anda melalui setiap detail—dari mengimpor namespace yang tepat hingga menyimpan file EPS yang telah dimodifikasi—sehingga Anda dapat mengintegrasikan manajemen metadata ke dalam alur kerja dengan percaya diri.

## Jawaban Cepat
- **Apa baris kode pertama?** Buat `new Document("yourfile.eps")` untuk memuat file EPS.  
- **Metode mana yang menambahkan namespace?** Gunakan `XmpMetadata.AddNamespace(prefix, uri)`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Bisakah saya streaming file EPS besar?** Ya—gunakan `FileStream` untuk membuka file tanpa memuat seluruhnya ke memori.  
- **Apakah ini kompatibel dengan .NET 6+?** Tentu; Aspose.Page mendukung .NET Framework 4.5+, .NET Core 3.1+, dan .NET 6+.  

## Apa itu inisialisasi dokumen Aspose.Page?

Kelas `Document` mewakili file EPS yang dimuat ke memori. Memuat file dengan `new Document("file.eps")` memberi Anda akses langsung ke halaman, grafik, dan metadata XMP-nya, memungkinkan Anda membaca atau memodifikasi bagian mana pun dari dokumen. Kelas ini juga menyediakan metode untuk bekerja dengan metadata XMP dan konten halaman.

## Mengapa menambahkan namespace XML ke metadata EPS?

Menambahkan namespace XML khusus memperluas skema metadata, memungkinkan Anda menyimpan informasi proprietari bersama bidang XMP standar. Aspose.Page mendukung **50+** properti XMP dan dapat menangani file dengan **200+ halaman** tanpa memerlukan seluruh dokumen berada di RAM, yang berarti pemrosesan lebih cepat dan konsumsi memori lebih rendah.

## Prasyarat

1. **Pustaka Aspose.Page untuk .NET** – unduh dari [dokumentasi Aspose.Page](https://reference.aspose.com/page/net/).  
2. **Lingkungan pengembangan .NET** – Visual Studio 2022, Rider, atau IDE apa pun yang mendukung .NET 6+.

Pastikan pustaka tersebut direferensikan dalam proyek Anda (melalui NuGet atau referensi DLL langsung) sebelum melanjutkan.

## Impor namespace

Untuk bekerja dengan Aspose.Page Anda harus mengimpor namespace inti yang mengekspos kelas `Document` dan XMP.

Anda akan membutuhkan:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

Impor ini memberi Anda akses ke kelas `Document`, `XmpMetadata`, dan kelas penanganan aliran yang diperlukan untuk langkah-langkah berikutnya.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Langkah 1: inisialisasi proyek Anda

Buka file sumber tempat Anda ingin menempatkan kode. Mulailah dengan membuat instance dari kelas `Document`, yang **initialize aspose page document** untuk manipulasi lebih lanjut. Kelas `Document` mewakili dokumen EPS dan menyediakan akses ke konten serta metadata-nya.

```csharp
var epsDocument = new Document("sample.eps");
```

Baris ini memuat file EPS ke dalam objek `epsDocument`, membuat semua panggilan API selanjutnya menjadi memungkinkan.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Langkah 2: buka aliran file eps

Kelas `FileStream` menyediakan aliran untuk membaca dan menulis file, yang membantu menghindari pemuatan seluruh file EPS ke memori.

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

Pola `open eps file stream` direkomendasikan untuk beban kerja **produksi**.

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Langkah 3: dapatkan metadata xmp

Kelas `XmpMetadata` mengenkapsulasi metadata XMP dari dokumen EPS.

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

Sekarang Anda memiliki objek `xmp` yang dapat dimanipulasi dan berisi semua entri metadata saat ini.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Langkah 4: ubah metadata xmp

Metode `AddNamespace` mendaftarkan namespace XML baru dengan prefix dan URI, dan metode `SetProperty` menetapkan nilai ke properti metadata.

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

Pemanggilan `AddNamespace` mendaftarkan prefix, dan `SetProperty` menyimpan nilai menggunakan prefix tersebut.

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## Langkah 5: simpan file eps

Metode `Save` menulis dokumen dan metadata-nya kembali ke sistem file.

```csharp
epsDocument.Save("sample-updated.eps");
```

Setelah langkah ini, file EPS berisi namespace dan properti yang baru ditambahkan.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## Masalah umum dan pemecahan masalah

- **Namespace sudah ada** – Jika `AddNamespace` menghasilkan error, prefix sudah terdaftar. Gunakan prefix lain atau ambil URI yang ada dengan `xmp.GetNamespaceUri(prefix)`.  
- **File terkunci oleh proses lain** – Pastikan `FileStream` dibuang (`using` block) sebelum memanggil `Save`.  
- **Metadata tidak tersimpan** – Verifikasi bahwa file EPS memang mendukung XMP (sebagian besar file EPS modern melakukannya). File lama mungkin perlu dibuat ulang.  

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Page kompatibel dengan semua versi .NET?**  
J: Ya, Aspose.Page untuk .NET bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.

**T: Bisakah saya mengekstrak metadata tanpa memodifikasinya?**  
J: Tentu. Dapatkan objek `XmpMetadata` dan baca propertinya tanpa memanggil `SetProperty` atau `AddNamespace`.

**T: Di mana saya dapat menemukan dukungan atau bantuan tambahan?**  
J: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

**T: Apakah ada percobaan gratis untuk Aspose.Page?**  
J: Ya, Anda dapat menjelajahi percobaan gratis Aspose.Page di halaman [Aspose.Page free trial](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?**  
J: Dapatkan lisensi sementara di halaman [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.

---

**Terakhir diperbarui:** 2026-08-08  
**Diuji dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Tambahkan Metadata ke Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Tambahkan Properti Sederhana dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Ekstrak Metadata dari Dokumen EPS dengan Aspose.Page untuk .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
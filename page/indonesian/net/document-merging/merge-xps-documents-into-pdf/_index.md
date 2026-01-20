---
date: 2026-01-20
description: Tambahkan nomor halaman pada PDF dengan mudah saat menggabungkan dokumen
  XPS menjadi PDF berkualitas tinggi menggunakan Aspose.Page untuk .NET. Ikuti panduan
  langkah demi langkah kami untuk mengonversi XPS ke PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Tambahkan Nomor Halaman PDF – Gabungkan XPS ke PDF menggunakan Aspose.Page
url: /id/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Nomor Halaman PDF – Gabungkan XPS ke PDF menggunakan Aspose.Page

## Pendahuluan

Jika Anda perlu **menambahkan nomor halaman PDF** saat menggabungkan file XPS, Aspose.Page untuk .NET membuat prosesnya menjadi mudah. Pada tutorial ini kami akan membahas contoh lengkap yang siap produksi, yang mengonversi dokumen XPS ke PDF berkualitas tinggi, memungkinkan Anda mengontrol kompresi gambar, dan secara otomatis menyisipkan nomor halaman ke PDF akhir. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat dipakai ulang dalam proyek C# mana pun.

## Jawaban Cepat
- **Apakah saya dapat menambahkan nomor halaman saat menggabungkan XPS ke PDF?** Ya – properti `PdfSaveOptions.PageNumbers` melakukannya.  
- **Perpustakaan mana yang menangani konversi?** Aspose.Page untuk .NET.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Page yang valid diperlukan; lisensi sementara tersedia untuk pengujian.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Apakah output gambar berkualitas tinggi memungkinkan?** Tentu – atur `JpegQualityLevel` ke 100 dan pilih `PdfImageCompression.Jpeg`.

## Prasyarat

Sebelum memulai tutorial, pastikan Anda telah menyiapkan hal‑hal berikut:

- Aspose.Page untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Page. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/page/net/).

- File Dokumen: Siapkan dokumen XPS (`input.xps`) di direktori yang Anda tentukan.

## Impor Namespace

Di proyek .NET Anda, sertakan namespace yang diperlukan untuk bekerja dengan Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Langkah ini memastikan Anda memiliki akses ke kelas dan metode yang dibutuhkan untuk konversi dokumen.

## Cara menambahkan nomor halaman PDF saat menggabungkan dokumen XPS

Koleksi `PdfSaveOptions.PageNumbers` memungkinkan Anda menentukan halaman (atau rentang halaman) mana yang harus muncul di PDF output. Dengan mengisinya dengan nomor halaman yang diinginkan, Aspose.Page secara otomatis menyisipkan penomoran yang tepat.

### Langkah 1: Inisialisasi Stream

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Langkah ini melibatkan penyiapan stream input dan output untuk file XPS dan PDF. Pastikan jalur dan nama file yang digunakan sudah benar.

### Langkah 2: Muat Dokumen XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Di sini, kami memuat dokumen XPS ke dalam objek `XpsDocument`, menyiapkannya untuk proses selanjutnya.

### Langkah 3: Inisialisasi Opsi Penyimpanan (gabungkan xps ke pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Sesuaikan objek `PdfSaveOptions` sesuai preferensi Anda, termasuk parameter seperti kompresi gambar, kompresi teks, dan **nomor halaman** yang ingin ditampilkan di PDF akhir. Menetapkan `JpegQualityLevel` ke 100 memastikan **gambar PDF berkualitas tinggi**.

### Langkah 4: Buat Perangkat Rendering

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` adalah alat yang bertanggung jawab merender dokumen XPS ke format PDF.

### Langkah 5: Simpan Dokumen (c# xps ke pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Akhirnya, simpan dokumen menggunakan perangkat rendering dan opsi yang telah ditentukan. PDF output akan berisi halaman yang dipilih dengan nomor halaman yang ditambahkan secara otomatis.

## Mengapa menggunakan Aspose.Page untuk konversi ini?

- **Keandalan** – Menangani fitur XPS yang kompleks tanpa kehilangan kualitas.  
- **Kinerja** – Pemrosesan berbasis stream menghindari pemuatan seluruh file ke memori.  
- **Fleksibilitas** – Kontrol detail atas kualitas gambar, kompresi, dan penomoran halaman.  
- **Lintas‑platform** – Berfungsi di Windows, Linux, dan macOS dengan .NET Core.

## Masalah Umum dan Solusinya

| Masalah | Solusi |
|-------|----------|
| **PDF output kosong** | Pastikan jalur file XPS benar dan file tidak rusak. |
| **Nomor halaman tidak muncul** | Pastikan `PageNumbers` diatur ke indeks halaman berbasis nol yang tepat (misalnya, `new int[] {1,2,6}`). |
| **Gambar ber‑kualitas rendah** | Tingkatkan `JpegQualityLevel` dan pilih `PdfImageCompression.Jpeg`. |
| **File XPS besar menyebabkan tekanan memori** | Proses XPS dalam potongan lebih kecil atau tingkatkan batas memori aplikasi. |

## Pertanyaan yang Sering Diajukan

### Q1: Apakah saya dapat menggabungkan beberapa file XPS menjadi satu PDF?

A1: Ya, Anda dapat. Cukup sesuaikan parameter `PageNumbers` dalam `PdfSaveOptions` untuk menyertakan halaman yang diinginkan dari berbagai file XPS, atau muat tiap XPS secara berurutan dan panggil `document.Save` pada `PdfDevice` yang sama.

### Q2: Apakah ada lisensi sementara untuk Aspose.Page untuk .NET?

A2: Ya, Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/) untuk keperluan pengujian.

### Q3: Apakah ada batasan ukuran file saat menggunakan Aspose.Page untuk konversi dokumen?

A3: Aspose.Page untuk .NET tidak memberlakukan batasan ketat pada ukuran file, namun kinerja optimal dicapai dengan file berukuran wajar. Untuk dokumen XPS yang sangat besar, pertimbangkan memprosesnya dalam stream untuk mengurangi konsumsi memori.

### Q4: Bisakah saya menyesuaikan PDF output lebih lanjut, seperti menambahkan watermark atau anotasi?

A4: Ya, Aspose.Page untuk .NET menyediakan fitur lengkap untuk manipulasi PDF. Setelah konversi, Anda dapat menggunakan pustaka Aspose.PDF untuk menambahkan watermark, anotasi, atau peningkatan lainnya.

### Q5: Apakah Aspose.Page untuk .NET mendukung pengembangan lintas‑platform?

A5: Ya, Aspose.Page untuk .NET dirancang agar bekerja mulus di berbagai platform, termasuk Windows, Linux, dan macOS, ketika digunakan dengan .NET Core atau .NET 5/6.

---

**Terakhir Diperbarui:** 2026-01-20  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
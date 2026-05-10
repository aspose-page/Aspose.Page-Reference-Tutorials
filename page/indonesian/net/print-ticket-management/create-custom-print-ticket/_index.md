---
date: 2026-03-19
description: Pelajari cara menambahkan tiket dengan membuat tiket cetak khusus menggunakan
  Aspose.Page untuk .NET. Sesuaikan pengalaman pencetakan Anda dengan kontrol yang
  sangat detail.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Cara Menambahkan Tiket: Membuat Tiket Cetak Kustom dengan Aspose.Page untuk
  .NET'
url: /id/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Ticket: Membuat Custom Print Ticket dengan Aspose.Page untuk .NET

## Introduction

Jika Anda membutuhkan fungsionalitas **how to add ticket** dalam aplikasi .NET, Aspose.Page memberi Anda kemampuan untuk menghasilkan custom print tickets langsung dari kode. Dalam tutorial ini kami akan membahas seluruh proses—menyiapkan lingkungan, membuat dokumen XPS, melampirkan custom job print ticket, dan menyimpan hasilnya. Pada akhir tutorial, Anda akan dapat menambahkan dukungan ticket ke alur kerja pencetakan apa pun dengan percaya diri.

## Quick Answers
- **Apa arti “add ticket”?** Itu merujuk pada penyematan custom print ticket (metadata XPS) yang mengontrol pengaturan printer.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menggunakan ini dengan .NET Core?** Ya, Aspose.Page mendukung .NET Framework dan .NET Core.  
- **Berapa lama implementasinya?** Biasanya kurang dari 15 menit untuk ticket dasar.

## What is a Custom Print Ticket?
Custom print ticket adalah deskripsi berbasis XML tentang preferensi printer (seperti collate, copies, manajemen warna, dll.) yang menyertai dokumen XPS. Ini memungkinkan pengembang untuk secara programatis menentukan bagaimana dokumen harus dicetak, menghilangkan konfigurasi manual di sisi klien.

## Why add ticket support with Aspose.Page?
- **Kontrol halus:** Atur collate, jumlah salinan, tipe media, dan lainnya melalui kode.  
- **Konsistensi lintas platform:** Ticket yang sama berfungsi pada printer apa pun yang memahami metadata XPS.  
- **Integrasi mulus:** Bekerja langsung dengan proyek .NET Anda yang ada tanpa layanan tambahan.

## Prerequisites

Before kita mulai, pastikan Anda memiliki:

- Kemampuan dasar dalam pengembangan C# dan .NET.  
- Visual Studio (versi terbaru apa pun) terpasang.  
- Perpustakaan Aspose.Page untuk .NET ditambahkan ke proyek Anda.  

Jika Anda belum menambahkan perpustakaan tersebut, Anda dapat mengunduhnya dari [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/). Untuk bantuan komunitas, kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Import Namespaces

Mulailah dengan mengimpor namespace yang menyediakan kelas XPS dan metadata.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Sekarang mari kita uraikan implementasinya langkah demi langkah.

## Step 1: Set up Document Directory

Tentukan lokasi di mana file XPS yang dihasilkan akan disimpan.

```csharp
string dir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Buat instance dokumen XPS baru yang akan menampung halaman dan ticket.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Step 3: Add Custom Job Print Ticket

Lampirkan custom job print ticket ke dokumen. Ini adalah inti dari fungsionalitas **how to add ticket**—di sini Anda menentukan collate, copies, rendering intent, manajemen warna, dan pengaturan lain yang diperlukan.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Pro tip:** Ganti string snapshot placeholder dengan struktur DEVMODE yang di‑encode Base64 yang sesuai dengan kemampuan printer Anda.

## Step 4: Save the Document

Simpan dokumen XPS (dengan ticket tersemat) ke disk.

```csharp
xDocs.Save(dir + "output1.xps");
```

Saat Anda membuka *output1.xps* di penampil yang menghormati metadata XPS, printer akan secara otomatis menerapkan pengaturan yang didefinisikan dalam ticket.

## Common Issues and Solutions

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Ticket tidak diterapkan | Penampil mengabaikan metadata XPS | Gunakan driver printer yang mendukung XPS print tickets atau penampil seperti Microsoft XPS Viewer. |
| Snapshot Base64 tidak valid | Data DEVMODE rusak | Buat ulang snapshot dari driver printer menggunakan API `GetPrinter`. |
| Izin hilang | Akses menulis ke `dir` ditolak | Pastikan aplikasi dijalankan dengan hak akses sistem file yang cukup. |

## Frequently Asked Questions

**Q: Bisakah saya menggunakan Aspose.Page untuk .NET dengan kerangka .NET lainnya?**  
A: Ya, Aspose.Page bekerja dengan .NET Framework, .NET Core, .NET 5/6, dan versi selanjutnya.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?**  
A: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara untuk Aspose.Page.

**Q: Apakah ada forum komunitas untuk dukungan Aspose.Page?**  
A: Tentu saja, Anda dapat menemukan diskusi dan dukungan yang membantu di [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q: Jenis media apa yang didukung dalam custom print ticket?**  
A: Aspose.Page mendukung berbagai jenis media, termasuk kertas biasa, glossy, dan definisi media khusus.

**Q: Apakah ada contoh proyek yang tersedia untuk Aspose.Page untuk .NET?**  
A: Jelajahi [dokumentasi](https://reference.aspose.com/page/net/) untuk contoh proyek dan potongan kode guna memulai pengembangan Anda.

## Conclusion

Kami telah membahas dukungan **how to add ticket** pada dokumen XPS menggunakan Aspose.Page untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat menyematkan instruksi pencetakan yang kaya langsung ke dalam file Anda, memberi Anda kontrol penuh atas alur kerja pencetakan dari dalam aplikasi .NET Anda. Jangan ragu untuk bereksperimen dengan pengaturan ticket tambahan agar sesuai dengan lingkungan pencetakan spesifik Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Page for .NET (latest stable version)  
**Author:** Aspose
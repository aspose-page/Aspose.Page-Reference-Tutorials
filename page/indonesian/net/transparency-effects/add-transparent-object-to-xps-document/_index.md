---
date: 2026-03-29
description: Pelajari cara menambahkan objek transparan ke dokumen XPS dan kemudian
  mengekspor XPS ke PDF menggunakan Aspose.Page untuk .NET. Panduan langkah demi langkah
  dengan tips praktis.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Ekspor XPS ke PDF – Tambahkan Objek Transparan dengan Aspose.Page
url: /id/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor XPS ke PDF – Tambahkan Objek Transparan dengan Aspose.Page

## Pendahuluan

Dalam tutorial ini Anda akan belajar cara menambahkan objek transparan ke dokumen XPS dan kemudian **mengekspor XPS ke PDF** dengan Aspose.Page untuk .NET. Transparansi dapat membuat dokumen Anda terlihat lebih modern dan membantu menyoroti informasi penting. Kami akan membimbing Anda melalui setiap langkah, menjelaskan alasan di balik kode, dan menunjukkan cara menyelesaikan alur kerja dengan mengonversi file XPS ke PDF untuk memudahkan berbagi.

## Jawaban Cepat
- **Apa arti “mengekspor XPS ke PDF”?** Mengonversi file XPS menjadi file PDF sambil mempertahankan tata letak, warna, dan transparansi.  
- **Mengapa menambahkan transparansi terlebih dahulu?** Objek transparan memungkinkan Anda membuat grafik berlapis yang terlihat bagus dalam PDF akhir.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Page yang valid diperlukan untuk penggunaan produksi.  
- **Apakah ini dapat dijalankan di .NET Core?** Tentu – Aspose.Page mendukung .NET Core, .NET 5/6, dan .NET Framework lengkap.  
- **Di mana saya dapat menemukan contoh lain?** Lihat dokumentasi Aspose.Page dan forum komunitas yang ditautkan di bawah.

## Prasyarat

Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Page for .NET: Pastikan Anda telah menginstal pustaka Aspose.Page untuk .NET. Anda dapat mengunduhnya dari [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Impor Namespace

Untuk memulai, sertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang, mari lanjutkan dengan panduan langkah demi langkah.

## Langkah 1: Buat Dokumen XPS Baru

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Kode ini menginisialisasi dokumen XPS baru menggunakan Aspose.Page untuk .NET.

## Langkah 2: Demonstrasikan Transparansi

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Baris-baris ini membuat dua jalur abu-abu yang akan berfungsi sebagai latar belakang untuk bentuk transparan yang akan kami tambahkan nanti.

## Langkah 3: Buat Path dengan Geometri Persegi Panjang Tertutup

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Di sini kami membuat persegi panjang biru. Karena nanti kami akan mengubah opasitasnya, persegi panjang tersebut akan tampak semi‑transparan dalam PDF akhir.

## Langkah 4: Manipulasi Path dan Warna

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Kami menggandakan persegi panjang pertama, menambahkannya ke halaman, dan mengubah warna isinya menjadi hijau. Ini menunjukkan betapa mudahnya menggunakan kembali geometri yang ada.

## Langkah 5: Kloning dan Transformasi Path

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Path yang digandakan dipindahkan ke bawah sebesar 300 unit dan diwarnai merah, memberikan efek lapisan bertumpuk.

## Langkah 6: Ulangi dan Modifikasi Path

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Kami menggunakan kembali data geometri dari `path2`, memindahkannya ke kanan, dan menerapkan isian biru lagi.

## Langkah 7: Kelola Opasitas

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Menetapkan properti `Opacity` menjadi 0.8 membuat persegi panjang ini 80 % opak, menggambarkan cara Anda dapat menyesuaikan transparansi untuk setiap elemen.

## Langkah 8: Simpan Dokumen XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

File XPS kini disimpan dengan semua objek transparan yang diterapkan.  

**Ekspor ke PDF:** Untuk **mengekspor XPS ke PDF**, cukup panggil `doc.Save` lagi dengan ekstensi `.pdf`, misalnya, `doc.Save(dataDir + "TransparentDocument.pdf");`. Kesetiaan visual yang sama, termasuk pengaturan opasitas, dipertahankan dalam PDF yang dihasilkan.

## Mengapa mengekspor XPS ke PDF setelah menambahkan transparansi?

- **Kompatibilitas universal:** PDF didukung secara luas di berbagai platform, sementara XPS lebih bersifat niche.  
- **Efek visual yang dipertahankan:** Aspose.Page menjaga transparansi, gradien, dan transformasi matriks tetap utuh selama konversi.  
- **Berbagi mudah:** PDF dapat dibuka di browser, perangkat seluler, dan banyak pembaca pihak ketiga tanpa plugin tambahan.

## Kasus Penggunaan Umum

- **Brosur pemasaran** di mana grafik berlapis memberikan kesan premium.  
- **Diagram teknis** yang memerlukan bagian yang disorot tanpa mengacaukan tata letak.  
- **Pembuatan laporan** di mana Anda ingin menambahkan watermark atau logo dengan opasitas parsial.

## Tips & Hal yang Perlu Diperhatikan

- **Pro tip:** Selalu tetapkan nilai `Opacity` antara 0 dan 1. Nilai di luar rentang ini akan dipotong dan dapat menghasilkan hasil yang tidak terduga.  
- **Performance tip:** Menggunakan kembali geometri (`path2.Data`) mengurangi penggunaan memori ketika Anda memerlukan banyak bentuk serupa.  
- **Pitfall:** Menyimpan langsung ke PDF setelah menambahkan transparansi berfungsi langsung, tetapi jika Anda kemudian mengedit PDF dengan alat lain, beberapa penampil lama mungkin tidak menampilkan opasitas dengan benar.

## Kesimpulan

Menambahkan objek transparan ke dokumen XPS menggunakan Aspose.Page untuk .NET memberikan cara yang fleksibel untuk meningkatkan presentasi visual. Setelah file XPS Anda terlihat seperti yang diinginkan, Anda dapat **mengekspor XPS ke PDF** dalam satu baris kode, mempertahankan semua efek transparansi untuk distribusi luas.

## Pertanyaan Umum

### Q1: Bisakah saya menerapkan transparansi pada objek apa pun dalam dokumen XPS?

A1: Ya, transparansi dapat diterapkan pada berbagai objek seperti jalur, bentuk, dan gambar dalam dokumen XPS.

### Q2: Bagaimana cara menyesuaikan opasitas elemen tertentu?

A2: Anda dapat mengatur properti opasitas pada Fill atau Stroke untuk menyesuaikan transparansi elemen tertentu.

### Q3: Apakah Aspose.Page kompatibel dengan .NET Core?

A3: Ya, Aspose.Page mendukung .NET Core, memungkinkan pengembangan lintas platform.

### Q4: Bisakah saya mengekspor dokumen XPS ke format lain menggunakan Aspose.Page?

A4: Aspose.Page menyediakan fungsionalitas untuk mengekspor dokumen XPS ke berbagai format, termasuk PDF dan gambar.

### Q5: Di mana saya dapat menemukan dukungan tambahan dan diskusi komunitas?

A5: Untuk dukungan tambahan dan diskusi komunitas, kunjungi [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: Apakah konversi PDF mempertahankan pengaturan transparansi saya?

A6: Tentu saja. Saat Anda mengekspor XPS ke PDF dengan Aspose.Page, semua pengaturan opasitas dan pencampuran tetap dipertahankan.

### Q7: Bisakah saya memproses batch banyak file XPS ke PDF?

A7: Ya, Anda dapat melakukan loop melalui koleksi file XPS dan memanggil `doc.Save(...".pdf")` untuk masing‑masing, mengotomatiskan konversi massal.

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.Page 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
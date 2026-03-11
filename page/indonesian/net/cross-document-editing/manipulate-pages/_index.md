---
date: 2026-01-10
description: Pelajari cara menggabungkan dokumen XPS dengan Aspose.Page untuk .NET.
  Panduan langkah demi langkah ini menunjukkan teknik manipulasi halaman untuk hasil
  yang efisien.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Gabungkan Dokumen XPS dengan Aspose.Page untuk .NET
url: /id/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menggabungkan Dokumen XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan menemukan cara **menggabungkan dokumen XPS** dan memanipulasi halaman mereka menggunakan pustaka Aspose.Page dalam lingkungan .NET. Apakah Anda perlu menggabungkan beberapa laporan menjadi satu file XPS atau menyusun ulang halaman untuk output yang rapi, panduan ini akan memandu Anda melalui proses langkah demi langkah, dengan penjelasan yang jelas dan kode siap‑jalankan.

## Jawaban Cepat
- **Apa yang dapat saya lakukan dengan Aspose.Page?** Menggabungkan dokumen XPS, menyisipkan, menambah, atau menghapus halaman, dan menyimpan hasilnya.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara tersedia untuk evaluasi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah Visual Studio diperlukan?** Tidak, IDE apa pun yang mendukung C# dapat digunakan, tetapi Visual Studio disarankan.  
- **Berapa lama proses penggabungan?** Biasanya beberapa detik untuk file XPS berukuran standar.

## Apa itu menggabungkan dokumen XPS?
Menggabungkan dokumen XPS berarti mengambil halaman dari dua atau lebih file XPS yang ada dan menggabungkannya menjadi satu dokumen XPS. Ini berguna untuk membuat laporan terintegrasi, menyusun manual multi‑halaman, atau menyiapkan paket siap cetak tanpa mengonversi ke format lain.

## Mengapa menggunakan Aspose.Page untuk .NET?
Aspose.Page menawarkan **API .NET murni** yang bekerja langsung dengan file XPS—tanpa memerlukan alat eksternal atau komponen pihak ketiga. Ini memberi Anda kontrol detail atas urutan halaman, titik penyisipan, dan pelestarian konten, menjadikan proses penggabungan dapat diandalkan dan cepat.

## Prasyarat

- **Aspose.Page untuk .NET** – unduh dari [dokumentasi Aspose.Page untuk .NET](https://reference.aspose.com/page/net/).  
- **Lingkungan Pengembangan** – Visual Studio, Rider, atau IDE apa pun yang mendukung C#.  
- **File XPS Input** – tiga file contoh (`input1.xps`, `input2.xps`, `input3.xps`) ditempatkan di folder yang diketahui.

## Impor Namespace

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Namespace ini memberi Anda akses ke kelas dokumen XPS inti, model halaman, dan utilitas gambar dasar.

## Langkah 1: Atur Direktori Dokumen

```csharp
string dataDir = "Your Document Directory";
```

Ganti **Your Document Directory** dengan jalur lengkap tempat file XPS Anda disimpan, misalnya `C:\\Docs\\XpsFiles\\`.

## Lang 2: Buat Instance Dokumen XPS

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2`, dan `doc3` mewakili dokumen sumber yang ingin Anda gabungkan.  
- `doc4` adalah dokumen XPS kosong yang akan menampung hasil penggabungan.

## Langkah 3: Sisipkan, Tambah, dan Hapus Halaman

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Berikut penjelasan setiap baris:

1. **InsertPage(1, doc2.Page, false)** – menempatkan halaman pertama `doc2` pada posisi 1 di `doc4`.  
2. **AddPage(doc3.Page, false)** – menambahkan halaman pertama `doc3` ke akhir `doc4`.  
3. **RemovePageAt(2)** – menghapus halaman yang berada pada indeks 2 (berguna untuk menghilangkan halaman yang tidak diinginkan).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – menyisipkan halaman ketiga `doc1` ke posisi 2, menyelesaikan penggabungan.

Operasi ini menggambarkan cara Anda dapat **menggabungkan dokumen XPS** sambil menyusun ulang atau membuang halaman sesuai kebutuhan.

## Langkah 4: Simpan Dokumen yang Digabungkan

```csharp
doc4.Save(dataDir + "out.xps");
```

File XPS yang telah digabungkan akhir (`out.xps`) ditulis ke direktori yang sama. Anda sekarang dapat membukanya di penampil XPS apa pun atau memprosesnya lebih lanjut dengan Aspose.Page.

## Masalah Umum dan Solusinya
- **File tidak ditemukan** – periksa kembali jalur `dataDir` dan pastikan file input ada.  
- **Indeks halaman tidak valid** – indeks halaman dimulai dari 1; mencoba menyisipkan halaman yang tidak ada akan menghasilkan pengecualian.  
- **Kesalahan lisensi** – gunakan lisensi sementara atau penuh sebelum menerapkan ke produksi.

## FAQ

### Q1: Bisakah saya memanipulasi halaman dari dokumen XPS yang berbeda?
A1: Ya, seperti yang ditunjukkan dalam tutorial, Anda dapat menyisipkan halaman dari beberapa dokumen XPS ke dalam dokumen baru.

### Q2: Bagaimana cara menghapus halaman tertentu dari dokumen?
A2: Gunakan metode `RemovePageAt`, dengan menentukan indeks halaman yang ingin Anda hapus.

### Q3: Apakah Aspose.Page kompatibel dengan Visual Studio?
A3: Ya, Aspose.Page sepenuhnya kompatibel dengan Visual Studio, memudahkan integrasi ke dalam proyek .NET Anda.

### Q4: Apakah ada opsi lisensi yang tersedia?
A4: Ya, Anda dapat menjelajahi opsi lisensi dan memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat mendapatkan dukungan atau mengajukan pertanyaan?
A5: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk mendapatkan dukungan dan berinteraksi dengan komunitas.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggabungkan lebih dari tiga file XPS?**  
A: Tentu saja. Buat instance `XpsDocument` tambahan dan gunakan `InsertPage` atau `AddPage` berulang kali untuk membangun dokumen gabungan yang lebih besar.

**Q: Apakah penggabungan mempertahankan format dan grafik asli?**  
A: Ya. Aspose.Page menyalin konten halaman byte‑per‑byte, sehingga teks, gambar, dan grafik vektor tetap tidak berubah.

**Q: Bagaimana cara menyisipkan halaman di akhir tanpa menentukan indeks?**  
A: Gunakan `AddPage(sourcePage, false)` yang menambahkan halaman ke akhir dokumen.

**Q: Apakah memungkinkan menggabungkan dokumen XPS di server tanpa UI?**  
A: API ini sepenuhnya headless; Anda dapat menjalankan kode yang sama di ASP.NET, Azure Functions, atau lingkungan .NET sisi server mana pun.

**Q: Bagaimana jika file XPS saya dilindungi kata sandi?**  
A: Aspose.Page saat ini tidak mendukung file XPS terenkripsi; Anda harus mendekripsi mereka sebelum menggabungkan.

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.Page for .NET 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
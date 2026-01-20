---
date: 2026-01-20
description: Pelajari cara membuat dokumen XPS, menambahkan persegi panjang, dan menyimpan
  file XPS menggunakan Aspose.Page untuk .NET dalam panduan langkah demi langkah ini.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Buat Dokumen XPS: Tambahkan Persegi Panjang dengan Aspose.Page untuk .NET'
url: /id/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Dokumen XPS: Menambahkan Persegi Panjang dengan Aspose.Page untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan **membuat dokumen XPS** dan menggambar sebuah persegi panjang di dalamnya menggunakan pustaka Aspose.Page untuk .NET. Menambahkan bentuk seperti persegi panjang merupakan kebutuhan umum ketika Anda harus menghasilkan faktur, laporan, atau grafik khusus secara programatik. Ikuti langkah‑langkah di bawah ini dan Anda akan memiliki file XPS siap pakai dalam hitungan menit.

## Jawaban Cepat
- **Apa yang dapat saya hasilkan?** Dokumen XPS dengan grafik vektor dan teks.  
- **Pustaka mana?** Aspose.Page untuk .NET (tersedia versi percobaan gratis).  
- **Berapa lama waktu yang dibutuhkan?** Sekitar 5‑10 menit untuk mengimplementasikan dan menjalankannya.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyimpan hasilnya sebagai file XPS?** Ya – metode `Save` menulis **file XPS yang disimpan** ke disk.

## Apa itu “membuat dokumen XPS”?

Membuat dokumen XPS berarti membangun deskripsi halaman secara programatik dalam format XML Paper Specification. File yang dihasilkan bersifat independen resolusi, ideal untuk pencetakan dan tampilan berkualitas tinggi di berbagai platform.

## Mengapa menggunakan Aspose.Page untuk membuat dokumen XPS?

- **Dukungan .NET penuh** – bekerja dengan .NET Framework, .NET Core, dan .NET 5/6+.  
- **API menggambar yang kaya** – mencakup geometri jalur, kuas, pena, dan penanganan teks.  
- **Tanpa ketergantungan eksternal** – semuanya berjalan dalam proses tanpa memerlukan Office atau Acrobat.  

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Aspose.Page untuk .NET** – unduh [di sini](https://releases.aspose.com/page/net/).  
2. **Folder yang dapat ditulisi** tempat file XPS yang dihasilkan akan disimpan.

## Mengimpor Namespace

Di proyek .NET Anda, impor namespace yang diperlukan:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 1: Menetapkan Direktori Dokumen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Tips pro:** Gunakan jalur absolut atau `Path.Combine` untuk menghindari masalah pemisah jalur pada sistem operasi yang berbeda.

## Langkah 2: Membuat Dokumen XPS Baru

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

Pada titik ini Anda telah **membuat objek dokumen XPS** yang akan menampung semua elemen gambar.

## Langkah 3: Menambahkan Persegi Panjang (menggunakan create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

Pemanggilan `CreatePathGeometry` **membuat geometri jalur** yang mendefinisikan kontur persegi panjang. Anda dapat memodifikasi string perintah mirip SVG untuk menggambar bentuk lain.

## Langkah 4: Menyimpan Dokumen (menyimpan file XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Pemanggilan `Save` menulis **file XPS yang disimpan** ke lokasi yang Anda tentukan.

Selamat! Anda telah berhasil **membuat dokumen XPS**, menambahkan persegi panjang, dan menyimpan file tersebut.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `FileNotFoundException` pada `doc.Save` | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau buat dengan `Directory.CreateDirectory(dataDir)`. |
| Persegi panjang tidak terlihat | Profil warna stroke tidak ada atau geometri jalur rusak | Verifikasi jalur file ICC dan string geometri (`M … Z`). |
| Penurunan kinerja pada dokumen besar | Terlalu banyak pemanggilan `AddPath` individual | Gabungkan operasi menggambar atau gunakan kembali objek kuas/pena. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Page kompatibel dengan semua aplikasi .NET?**  
J: Ya, Aspose.Page dirancang untuk bekerja mulus dengan semua aplikasi .NET.

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page untuk .NET?**  
J: Dokumentasi tersedia [di sini](https://reference.aspose.com/page/net/).

**T: Bisakah saya mencoba Aspose.Page untuk .NET secara gratis sebelum membeli?**  
J: Ya, Anda dapat memperoleh percobaan gratis [di sini](https://releases.aspose.com/).

**T: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page untuk .NET?**  
J: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan lisensi sementara.

**T: Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan terkait Aspose.Page untuk .NET?**  
J: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas.

---

**Terakhir Diperbarui:** 2026-01-20  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
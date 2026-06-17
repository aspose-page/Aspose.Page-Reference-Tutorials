---
date: 2026-01-28
description: Pelajari cara mengonversi EPS ke PNG menggunakan Aspose.Page untuk .NET
  dan menerapkan lisensi metered untuk pemrosesan dokumen yang mulus.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Konversi EPS ke PNG dan Terapkan Lisensi Metered dengan Aspose.Page untuk .NET
url: /id/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi EPS ke PNG dan Terapkan Lisensi Metered dengan Aspose.Page untuk .NET

## Perkenalan

Buka potensi penuh Aspose.Page untuk .NET dengan **mengonversi EPS ke PNG** dan menerapkan lisensi metered. Tutorial ini memandu Anda melalui setiap langkah—dari mengunggah file EPS hingga menyimpannya sebagai gambar PNG—sehingga Anda dapat memproses dokumen secara efisien dan tanpa evaluasi watermark.

## Jawaban Cepat
- **Apa saja yang tercakup dalam tutorial ini?** Mengonversi file EPS ke gambar PNG dan menerapkan lisensi terukur dengan Aspose.Page untuk .NET.
- **Apakah saya memerlukan lisensi?** Ya, lisensi bermeter diperlukan untuk penggunaan produksi.
- **Versi .NET manakah yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Berapa lama waktu penerapannya?** Sekitar 10–15 menit untuk konversi dasar.
- **Bisakah saya menjalankan ini di Linux/macOS?** Tentu saja—Aspose.Page bersifat lintas platform.

## Apa itu “konversi EPS ke PNG”?
Mengonversi EPS ke PNG berarti merasterkan file Encapsulated PostScript (EPS) berbasis vektor menjadi gambar bitmap PNG. Ini berguna ketika Anda perlu menampilkan atau menyematkan grafik di halaman web, laporan, atau komponen UI yang tidak mendukung EPS.

## Mengapa menggunakan lisensi terukur untuk konversi EPS ke gambar?
Lisensi meteran memungkinkan Anda membayar hanya untuk halaman yang diproses, yang ideal untuk beban kerja dengan variabel volume. Lisensi ini juga menghilangkan banner evaluasi merah yang muncul saat menggunakan versi percobaan, memastikan output bersih untuk pengguna akhir Anda.

## Prasyarat

Sebelum menyelami langkah‑langkahnya, pastikan Anda memiliki prasyarat berikut:

- Lisensi Aspose.Page untuk .NET yang valid: Anda dapat memperolehnya dari [purchase.aspose.com](https://purchase.aspose.com/buy).
- Library Aspose.Page terpasang: Lihat [dokumentasi](https://reference.aspose.com/page/net/) untuk proses instalasi.
- Lingkungan pengembangan .NET: Pastikan Anda memiliki lingkungan .NET yang berfungsi di mesin Anda.

## Impor Namespace

Di proyek .NET Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Cara Mengonversi EPS ke PNG dengan Lisensi Meteran?

Berikut adalah panduan langkah-demi-langkah yang mencakup semua yang perlu Anda ketahui.

### Langkah 1: Atur Kunci Publik dan Privat Meteran

Inisialisasi kelas `Aspose.Page.Metered` dan atur kunci publik serta privat metered. Ganti `<type public key here>` dan `<type private key here>` dengan kunci Anda yang sebenarnya.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Langkah 2: Muat File EPS dan Buat Dokumen

Tentukan jalur ke file EPS Anda dan buat stream untuk membaca isinya. Kemudian, buat instance kelas `PsDocument` dari stream tersebut.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Langkah 3: Konversi EPS ke Gambar PNG

Buat `ImageDevice` untuk mengonversi file EPS menjadi gambar PNG. Simpan file EPS sebagai gambar menggunakan `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Langkah 4: Ambil Byte Gambar

Dapatkan byte gambar, di mana setiap array byte mewakili satu halaman. Dalam kasus ini, kita memiliki satu halaman.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Langkah 5: Simpan Byte Gambar ke File

Simpan byte gambar ke file, memastikan konversi dari EPS ke PNG berhasil.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Langkah 6: Verifikasi Lisensi Meteran

Periksa secara visual apakah lisensi metered telah diterapkan dengan sukses. Jika gambar yang dihasilkan tidak mengandung pesan evaluasi merah, itu menandakan lisensi metered telah diterapkan tanpa masalah.

Sekarang Anda siap memanfaatkan kemampuan penuh Aspose.Page untuk .NET dengan lisensi metered!

## Masalah dan Solusi Umum

| Masalah | Penyebab | Perbaikan |

|-------|-------|-----|

| Banner evaluasi merah masih muncul | Lisensi belum diatur atau kunci salah | Periksa kembali kunci publik/pribadi dan pastikan `SetMeteredKey` dipanggil sebelum pemrosesan dokumen apa pun |

| Tidak ada file output yang dibuat | Jalur `dataDir` atau izin file salah | Verifikasi direktori ada dan aplikasi memiliki izin tulis |

| Beberapa halaman tidak tersimpan | Hanya halaman pertama yang ditulis | Lakukan perulangan melalui `imagesBytes` dan tulis setiap array ke file PNG terpisah |

## Pertanyaan yang Sering Diajukan

**T: Dapatkah saya menggunakan lisensi terukur dalam pipeline CI/CD?**
J: Ya, Anda dapat menyimpan kunci dengan aman (misalnya, dalam variabel lingkungan) dan memanggil `SetMeteredKey` selama proses build.

**T: Apakah Aspose.Page mendukung pelestarian profil warna saat mengkonversi ke PNG?**
J: Output PNG mempertahankan informasi warna asli, tetapi Anda dapat menyesuaikannya lebih lanjut melalui `ImageSaveOptions`.

**T: Apakah mungkin untuk mengkonversi EPS ke format raster lain (JPEG, BMP)?**
J: Tentu saja—cukup ubah `ImageSaveOptions` ke format yang diinginkan.

**T: Berapa ukuran file EPS maksimum yang didukung?**
J: Aspose.Page menangani file besar, tetapi konsumsi memori meningkat seiring dengan resolusi gambar. Pertimbangkan untuk memproses halaman secara individual untuk dokumen yang sangat besar.

**T: Bagaimana cara saya mengambil jumlah halaman dalam file EPS secara terprogram?**
J: Gunakan `document.PagesCount` setelah memuat `PsDocument`.

---

**Terakhir Diperbarui:** 28 Januari 2026
**Diuji Dengan:** Aspose.Page 24.12 untuk .NET
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
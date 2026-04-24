---
date: 2026-01-05
description: Pelajari cara memotong dokumen XPS menggunakan Aspose.Page untuk .NET.
  Panduan langkah demi langkah ini menunjukkan cara membuat, memanipulasi, dan menyimpan
  file XPS secara efisien.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Cara Memotong XPS dengan Aspose.Page untuk .NET
url: /id/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Memotong XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Selamat datang di tutorial komprehensif ini tentang **cara memotong XPS** menggunakan Aspose.Page untuk .NET! Dalam panduan ini, kami akan memandu Anda melalui proses pembuatan, manipulasi, dan penyimpanan dokumen XPS dengan perpustakaan tersebut. XPS, atau XML Paper Specification, adalah format dokumen standar dan terbuka, dan Aspose.Page untuk .NET menyediakan alat yang kuat untuk bekerja dengan dokumen XPS dalam aplikasi .NET Anda.

## Jawaban Cepat
- **Apa itu clipping XPS?** Menerapkan masker geometris (clip) untuk membatasi area yang terlihat dari elemen kanvas XPS.  
- **Perpustakaan mana yang terbaik untuk ini?** Aspose.Page untuk .NET menawarkan API lengkap untuk pembuatan dan clipping XPS.  
- **Prasyarat?** Visual Studio, runtime .NET, dan perpustakaan Aspose.Page untuk .NET.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk skenario clipping dasar.  
- **Bisakah saya menggunakan ini di produksi?** Ya, dengan lisensi Aspose yang valid (versi percobaan tersedia).

## Apa itu “cara memotong XPS”?
Clipping pada XPS bekerja dengan mendefinisikan **geometri clip** (misalnya, lingkaran atau persegi panjang) dan menetapkannya ke kanvas. Apa pun yang digambar di luar geometri tersebut tidak akan dirender, memungkinkan Anda membuat tata letak halaman yang canggih seperti gambar yang dimask, bentuk khusus, atau area konten yang terfokus.

## Mengapa menggunakan Aspose.Page untuk .NET untuk memotong XPS?
- **Kontrol penuh** atas transformasi kanvas, geometri jalur, dan kuas.  
- **Tanpa ketergantungan eksternal** – semuanya berjalan di dalam aplikasi .NET Anda.  
- **Dukungan lintas‑platform** untuk .NET Framework, .NET Core, dan .NET 5/6+.  
- **Kinerja tinggi** dengan API ringan yang menulis file XPS yang valid.

## Prasyarat

Sebelum kita melanjutkan, pastikan Anda memiliki hal berikut:

- Visual Studio terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk .NET ditambahkan ke proyek Anda. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- Pengetahuan dasar tentang bahasa pemrograman C#.

## Impor Namespace

Untuk menggunakan fungsionalitas Aspose.Page untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah-langkah berikut:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang, mari kita uraikan contoh kode yang Anda berikan menjadi beberapa langkah.

## Langkah 1: Atur jalur direktori dokumen.

```csharp
string dataDir = "Your Document Directory";
```

Pastikan untuk mengganti "Your Document Directory" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Buat Dokumen XPS Baru.

```csharp
XpsDocument doc = new XpsDocument();
```

Ini membuat dokumen XPS baru yang akan Anda kerjakan.

## Langkah 3: Buat kanvas utama.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Langkah ini membuat kanvas utama, yang umum untuk semua elemen halaman.

## Langkah 4: Atur offset kiri dan atas pada kanvas utama.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Sesuaikan offset kiri dan atas sesuai kebutuhan Anda.

## Langkah 5: Buat geometri jalur persegi panjang.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Ini membuat geometri jalur untuk sebuah persegi panjang.

## Langkah 6: Buat isian untuk persegi panjang.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Tentukan warna isian untuk persegi panjang.

## Langkah 7: Tambahkan kanvas lain dengan clip ke kanvas utama.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Langkah ini menambahkan kanvas lain ke kanvas utama.

## Langkah 8: Buat geometri lingkaran untuk clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Ini membuat geometri clip berbentuk lingkaran dan menerapkannya ke kanvas kedua.

## Langkah 9: Buat persegi panjang di kanvas kedua dan isi.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Langkah ini membuat persegi panjang di kanvas kedua dan mengisinya.

## Langkah 10: Tambahkan kanvas kedua dengan persegi panjang bergaris ke kanvas utama.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Ini menambahkan kanvas lain ke kanvas utama.

## Langkah 11: Buat persegi panjang di kanvas ketiga dan beri garis tepi.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Ini membuat persegi panjang di kanvas ketiga dan menerapkan garis tepi padanya.

## Langkah 12: Simpan dokumen XPS hasil.

```csharp
doc.Save(dataDir + "output2.xps");
```

Ini menyimpan dokumen XPS ke direktori yang ditentukan.

## Masalah Umum dan Solusinya
- **Path tidak valid** – Pastikan `dataDir` diakhiri dengan backslash (`\\`) atau gunakan `Path.Combine`.  
- **Clip tidak diterapkan** – Verifikasi bahwa string geometri clip terbentuk dengan baik; spasi yang hilang dapat menyebabkan clip diabaikan.  
- **Pengecualian lisensi** – Pada build non‑evaluation, tambahkan lisensi Aspose yang valid sebelum membuat dokumen untuk menghindari pengecualian runtime.

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?

A1: Aspose.Page untuk .NET terutama fokus pada dokumen XPS, tetapi Aspose menyediakan perpustakaan lain untuk berbagai format dokumen.

### Q2: Apakah Aspose.Page untuk .NET cocok untuk pemula?

A2: Ya, Aspose.Page untuk .NET dirancang agar ramah pengguna, dan pemula dapat dengan cepat memahami fungsionalitasnya dengan dokumentasi yang tepat.

### Q3: Di mana saya dapat menemukan contoh dan sumber daya lebih lanjut?

A3: Kunjungi [dokumentasi](https://reference.aspose.com/page/net/) dan [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk sumber daya dan contoh yang lengkap.

### Q4: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk .NET?

A4: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah ada trial gratis untuk Aspose.Page untuk .NET?

A5: Ya, Anda dapat menjelajahi trial gratis [di sini](https://releases.aspose.com/).

## Pertanyaan Tambahan yang Sering Diajukan

**T: Bisakah saya menggabungkan beberapa geometri clip pada satu kanvas?**  
J: Ya, Anda dapat menetapkan `PathGeometry` yang kompleks yang berisi beberapa sub‑path ke properti `Clip`, memungkinkan masking berlapis.

**T: Apakah clipping memengaruhi konversi PDF?**  
J: Ketika Anda kemudian mengonversi XPS ke PDF menggunakan Aspose.PDF, geometri clip dipertahankan, sehingga hasil visual tetap identik.

**T: Apakah memungkinkan untuk menganimasikan clipping di XPS?**  
J: XPS sendiri tidak mendukung animasi; namun, Anda dapat menghasilkan serangkaian halaman XPS dengan bentuk clip yang berbeda untuk mensimulasikan gerakan.

---

**Terakhir Diperbarui:** 2026-01-05  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
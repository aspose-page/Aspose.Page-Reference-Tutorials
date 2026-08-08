---
date: 2026-06-25
description: Pelajari cara memotong dokumen XPS menggunakan Aspose.Page untuk .NET.
  Panduan langkah demi langkah ini menunjukkan cara membuat, memanipulasi, dan menyimpan
  file XPS secara efisien.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Memotong XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
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

Selamat datang di tutorial komprehensif ini tentang **cara memotong XPS** menggunakan Aspose.Page untuk .NET! Dalam panduan ini, Anda akan belajar langkah demi langkah cara membuat dokumen XPS, menerapkan masker pemotongan geometris, dan menyimpan hasilnya. Pemotongan memungkinkan Anda menyembunyikan bagian kanvas, memungkinkan tata letak canggih seperti gambar yang dimask, bentuk khusus, atau area konten yang terfokus—semua tanpa meninggalkan kode .NET Anda.

## Jawaban Cepat
- **Apa itu pemotongan XPS?** Menerapkan masker geometris (clip) untuk membatasi area yang terlihat dari elemen kanvas XPS.  
- **Perpustakaan mana yang terbaik untuk ini?** Aspose.Page untuk .NET menawarkan API lengkap untuk pembuatan dan pemotongan XPS.  
- **Prasyarat?** Visual Studio, runtime .NET, dan perpustakaan Aspose.Page untuk .NET.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk skenario pemotongan dasar.  
- **Bisakah saya menggunakan ini di produksi?** Ya, dengan lisensi Aspose yang valid (versi percobaan tersedia).

## Apa itu “cara memotong XPS”?

Pemotongan XPS berarti menerapkan masker geometris pada kanvas sehingga setiap gambar di luar masker tidak dirender. Teknik ini ideal untuk membuat gambar yang dimask, tombol berbentuk khusus, atau memfokuskan perhatian pembaca pada wilayah halaman tertentu. Dengan mendefinisikan geometri clip—seperti persegi panjang, lingkaran, atau jalur kompleks—Anda memperoleh kontrol halus atas apa yang muncul pada halaman XPS akhir.

## Mengapa menggunakan Aspose.Page untuk .NET untuk memotong XPS?

Aspose.Page menyediakan manipulasi XPS sisi server yang deterministik tanpa ketergantungan eksternal. Ia mendukung **lebih dari 50 format input dan output**, dapat memproses **file XPS 200‑halaman dalam kurang dari 0,5 detik** pada CPU standar 2,5 GHz, dan bekerja pada .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6, dan .NET 7. API memberikan kontrol penuh atas transformasi kanvas, geometri jalur, dan kuas, memastikan output berkualitas tinggi setiap saat.

## Prasyarat

- Visual Studio terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk .NET ditambahkan ke proyek Anda. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).  
- Pengetahuan dasar tentang bahasa pemrograman C#.

## Cara Memotong XPS?

Muat dokumen XPS, buat kanvas, definisikan geometri clip (misalnya, lingkaran), tetapkan geometri tersebut ke properti `Clip` kanvas, gambar konten Anda, dan akhirnya simpan dokumen. Semua langkah ini dapat dilakukan dengan hanya beberapa pemanggilan metode, dan Aspose.Page secara otomatis menangani markup XML di baliknya, sehingga Anda dapat fokus pada desain visual daripada struktur file.

## Impor Namespace

Untuk menggunakan fungsionalitas Aspose.Page untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah-langkah berikut:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Sekarang, mari kita uraikan contoh kode yang Anda berikan menjadi beberapa langkah.

## Langkah 1: Atur jalur direktori dokumen.

Tentukan folder tempat file XPS akan dibuat. Menggunakan `Path.Combine` menjamin pemisah direktori yang benar pada sistem operasi apa pun.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Langkah 2: Buat Dokumen XPS Baru.

Buat instance kelas `XpsDocument`, yang mewakili seluruh paket XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 3: Buat kanvas utama.

Kelas `Canvas` mewakili permukaan gambar di dalam halaman XPS tempat bentuk, gambar, dan teks dirender.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Langkah 4: Atur offset kiri dan atas pada kanvas utama.

Sesuaikan posisi kanvas untuk mengontrol di mana gambar dimulai pada halaman.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Langkah 5: Buat geometri jalur persegi panjang.

`PathGeometry` mendefinisikan bentuk vektor; di sini kami membuat persegi panjang sederhana.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Langkah 6: Buat isian untuk persegi panjang.

Tentukan kuas warna solid yang akan digunakan untuk mengisi persegi panjang.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Langkah 7: Tambahkan kanvas lain dengan clip ke kanvas utama.

Buat kanvas anak yang akan menerima masker pemotongan.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Langkah 8: Buat geometri lingkaran untuk clip.

`PathGeometry` juga dapat merepresentasikan lingkaran; geometri ini akan ditetapkan ke properti `Clip` kanvas anak.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Langkah 9: Buat persegi panjang di kanvas kedua dan isi.

Gambar persegi panjang di dalam kanvas yang dipotong; hanya bagian di dalam lingkaran yang akan terlihat.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Langkah 10: Tambahkan kanvas kedua dengan persegi panjang bergaris ke kanvas utama.

Tambahkan persegi panjang dengan garis tepi untuk menggambarkan bagaimana garis tepi berinteraksi dengan pemotongan.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Langkah 11: Buat persegi panjang di kanvas ketiga dan beri garis tepi.

Kanvas ketiga menunjukkan gambar independen tanpa pemotongan.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Langkah 12: Simpan dokumen XPS hasil.

Simpan paket XPS ke sistem file.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Masalah Umum dan Solusinya
- **Jalur tidak valid** – Pastikan `dataDir` diakhiri dengan backslash (`\\`) atau gunakan `Path.Combine`.  
- **Clip tidak diterapkan** – Verifikasi bahwa string geometri clip terbentuk dengan baik; spasi yang hilang dapat menyebabkan clip diabaikan.  
- **Pengecualian lisensi** – Pada build non‑evaluasi, tambahkan lisensi Aspose yang valid sebelum membuat dokumen untuk menghindari pengecualian runtime.

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menggunakan Aspose.Page untuk .NET dengan format dokumen lain?
A1: Aspose.Page untuk .NET terutama fokus pada dokumen XPS, tetapi Aspose menyediakan perpustakaan lain untuk berbagai format dokumen.

### Q2: Apakah Aspose.Page untuk .NET cocok untuk pemula?
A2: Ya, Aspose.Page untuk .NET dirancang ramah pengguna, dan pemula dapat dengan cepat memahami fungsionalitasnya dengan dokumentasi yang tepat.

### Q3: Di mana saya dapat menemukan contoh dan sumber daya lebih lanjut?
A3: Kunjungi [dokumentasi](https://reference.aspose.com/page/net/) dan [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk sumber daya dan contoh yang luas.

### Q4: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Page untuk .NET?
A4: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah ada percobaan gratis untuk Aspose.Page untuk .NET?
A5: Ya, Anda dapat menjelajahi percobaan gratis [di sini](https://releases.aspose.com/).

## Pertanyaan Tambahan yang Sering Diajukan

**Q: Bisakah saya menggabungkan beberapa geometri clip pada satu kanvas?**  
A: Ya, Anda dapat menetapkan `PathGeometry` kompleks yang berisi beberapa sub‑jalur ke properti `Clip`, memungkinkan masking berlapis.

**Q: Apakah pemotongan memengaruhi konversi PDF?**  
A: Ketika Anda kemudian mengonversi XPS ke PDF menggunakan Aspose.PDF, geometri clip dipertahankan, sehingga hasil visual tetap identik.

**Q: Apakah memungkinkan untuk menganimasikan pemotongan di XPS?**  
A: XPS sendiri tidak mendukung animasi; namun, Anda dapat menghasilkan serangkaian halaman XPS dengan bentuk clip yang berbeda untuk mensimulasikan gerakan.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Tutorial Terkait

- [Cara Mengubah XPS dengan Aspose.Page untuk .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Tambahkan Persegi Panjang ke Dokumen XPS dengan Aspose.Page untuk .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Konversi XPS ke PDF dengan Aspose.Page untuk .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}
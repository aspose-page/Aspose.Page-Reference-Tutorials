---
title: Transformasi PS dengan Aspose.Page untuk .NET
linktitle: Transformasi PS
second_title: Aspose.Halaman .NET API
description: Buka potensi Aspose.Page untuk .NET dengan panduan komprehensif tentang transformasi PostScript ini. Buat grafik dinamis dengan mudah.
weight: 12
url: /id/net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformasi PS dengan Aspose.Page untuk .NET

## Perkenalan

Selamat datang di dunia Aspose.Page untuk .NET, tempat Anda dapat memanfaatkan kekuatan transformasi dalam dokumen PostScript. Tutorial ini akan memandu Anda melalui berbagai transformasi seperti terjemahan, penskalaan, rotasi, geser, dan transformasi kompleks, memungkinkan Anda membuat grafik visual yang menakjubkan dan dinamis.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page for .NET Library: Pastikan Anda memiliki perpustakaan Aspose.Page for .NET yang terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari[tautan unduhan](https://releases.aspose.com/page/net/).

- Direktori Dokumen: Siapkan direktori untuk dokumen Anda dan ganti placeholder dalam kode dengan jalur sebenarnya.

## Impor Namespace

Di proyek .NET Anda, impor namespace yang diperlukan untuk bekerja dengan Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah.


## Tidak Ada Transformasi

### Langkah 1: Buat Aliran Keluaran

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat aliran keluaran untuk dokumen PostScript
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Buat opsi penyimpanan dengan nilai default
    PsSaveOptions options = new PsSaveOptions();

    // Buat Dokumen PS 1 halaman baru
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Buat jalur grafis dari persegi panjang
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Atur cat dalam kondisi grafis di tingkat atas
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Isi persegi panjang pertama yang berada pada status grafis tingkat atas dan tanpa transformasi apa pun
    document.Fill(path);

    // Tutup halaman saat ini
    document.ClosePage();

    // Simpan dokumennya
    document.Save();
}
```

Kode ini membuat dokumen PostScript tanpa transformasi, mengisi persegi panjang dengan warna oranye.

## Terjemahan

### Langkah 1: Simpan Status Grafik

```csharp
// Simpan status grafis untuk kembali ke status ini setelah transformasi
document.WriteGraphicsSave();
```

Langkah ini menyimpan status grafis saat ini, memungkinkan kita untuk kembali ke sana setelah transformasi.

### Langkah 2: Terjemahkan Status Grafik

```csharp
// Pindahkan status grafis saat ini 250 ke kanan
document.Translate(250, 0);
```

Terjemahkan keadaan grafik saat ini dengan menambahkan komponen terjemahan, lalu atur cat pada keadaan grafik saat ini menjadi warna biru.

### Langkah 3: Isi Rectangle dengan Transformasi Terjemahan

```csharp
// Atur cat pada kondisi grafis saat ini
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Isi persegi panjang kedua dalam kondisi grafik saat ini (memiliki transformasi terjemahan)
document.Fill(path);
```

Langkah ini mengisi persegi panjang kedua dalam kondisi grafis saat ini, yang sekarang mencakup transformasi terjemahan.

### Langkah 4: Kembalikan Status Grafik

```csharp
// Kembalikan status grafis ke level sebelumnya (atas).
document.WriteGraphicsRestore();
```

Setelah mengisi persegi panjang, kembalikan status grafik ke level sebelumnya.

Lanjutkan panduan langkah demi langkah ini untuk setiap jenis transformasi, termasuk Penskalaan, Rotasi, Geser, dan Transformasi Kompleks.

## Kesimpulan

Selamat! Anda telah berhasil menjelajahi kemampuan transformatif Aspose.Page untuk .NET. Sekarang, bereksperimenlah dengan berbagai kombinasi dan keluarkan kreativitas Anda dalam transformasi dokumen PostScript.

## FAQ

### Q1: Bagaimana cara menerapkan beberapa transformasi ke satu objek?

A1: Untuk menerapkan beberapa transformasi, gunakan`Transform` metode dengan matriks transformasi khusus.

### Q2: Dapatkah saya melihat pratinjau transformasi sebelum menyimpan dokumen?

A2: Ya, Anda dapat memvisualisasikan transformasi dengan merender dokumen dan mempratinjaunya di penampil yang sesuai.

### Q3: Apakah mungkin untuk menerapkan transformasi pada elemen tertentu dalam dokumen?

A3: Ya, Anda dapat mengisolasi transformasi ke elemen grafis tertentu dalam dokumen.

### Q4: Apakah ada pertimbangan kinerja saat menangani transformasi yang kompleks?

J4: Transformasi yang rumit dapat memengaruhi kinerja, jadi optimalkan kode Anda untuk efisiensi.

### Q5: Bagaimana saya bisa mendapatkan dukungan atau mencari bantuan untuk pertanyaan terkait Aspose.Page?

 A5: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-01-12
description: Pelajari cara menyimpan file PostScript dan membuat dokumen PostScript
  menggunakan Aspose.Page untuk .NET, serta menerapkan beberapa transformasi untuk
  grafik dinamis.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Simpan file PostScript dengan Transformasi Aspose.Page (.NET)
url: /id/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan file PostScript dengan Transformasi Aspose.Page (.NET)

## Pendahuluan

Dalam tutorial ini Anda akan mempelajari cara **menyimpan file PostScript** saat bekerja dengan Aspose.Page untuk .NET. Kami akan memandu Anda membuat dokumen PostScript, menerapkan beberapa transformasi seperti translasi, skala, rotasi, dan shearing, serta akhirnya menyimpan hasilnya. Pada akhir tutorial Anda akan nyaman membuat grafik dinamis secara programatis dan tahu persis di mana menempatkan setiap transformasi dalam state grafik.

## Jawaban Cepat
- **Apa yang dapat saya buat?** Dokumen PostScript lengkap dengan grafik yang telah ditransformasi.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk .NET (dapat diunduh dari situs resmi).  
- **Bagaimana cara menyimpan file?** Gunakan `PsDocument.Save()` setelah mengonfigurasi state grafik.  
- **Apakah saya dapat menerapkan beberapa transformasi?** Ya – gabungkan mereka dengan `Transform` atau panggilan berurutan.  
- **Apakah lisensi diperlukan?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.

## Apa itu operasi “save postscript file”?

Menyimpan file PostScript berarti menyimpan perintah gambar yang telah Anda bangun di memori ke file `.ps` di disk. File tersebut kemudian dapat dirender oleh interpreter PostScript, printer, atau penampil apa pun.

## Mengapa menggunakan Aspose.Page untuk .NET dalam membuat dokumen postscript?

Aspose.Page menyediakan API tingkat tinggi yang independen perangkat yang mengabstraksi sintaks PostScript tingkat rendah. Anda mendapatkan:

- Objek C# yang bertipe kuat untuk path, brush, dan transformasi.  
- Penanganan otomatis stack state grafik (save/restore).  
- Dukungan penuh untuk matriks transformasi kompleks tanpa perhitungan manual.  

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Perpustakaan **Aspose.Page untuk .NET** yang terintegrasi ke dalam proyek Anda. Dapatkan dari [tautan unduhan](https://releases.aspose.com/page/net/).  
- Folder yang dapat ditulisi tempat file `.ps` yang dihasilkan akan disimpan. Ganti jalur placeholder dalam kode dengan direktori Anda yang sebenarnya.

## Impor Namespace

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Sekarang mari kita jelajahi setiap langkah transformasi satu per satu.

## Tanpa Transformasi

### Langkah 1: Buat Output Stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Potongan kode ini membuat **dokumen PostScript** dengan satu persegi panjang oranye dan **menyimpan file PostScript** tanpa menerapkan transformasi apa pun.

## Translasi

### Langkah 1: Simpan State Grafik

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Menyimpan state grafik memungkinkan Anda kembali setelah memindahkan objek.

### Langkah 2: Translasi State Grafik

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Translasi memindahkan semua yang digambar setelah pemanggilan ini 250 unit ke kanan.

### Langkah 3: Isi Persegi Panjang dengan Transformasi Translasi

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Sekarang sebuah persegi panjang biru muncul 250 poin ke kanan dari persegi panjang oranye.

### Langkah 4: Pulihkan State Grafik

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Pemulihan mengembalikan sistem koordinat ke posisi semula, sehingga gambar berikutnya tidak terpengaruh oleh translasi.

## Skala

> *Anda dapat mengikuti pola yang sama—simpan state, terapkan `Scale`, gambar, lalu pulihkan.*  
> **Tips pro:** Gunakan skala tidak seragam (`Scale(sx, sy)`) untuk meregangkan objek hanya pada satu arah.

## Rotasi

> *Rotasi sekitar asal atau titik pivot khusus menggunakan `Rotate(angle)`.*
> **Tips pro:** Gabungkan `Translate` sebelum rotasi untuk memutar sekitar titik tertentu.

## Shearing

> *Transformasi shear (`Shear(shx, shy)`) memiringkan bentuk, berguna untuk efek miring.*  

## Transformasi Kompleks

> *Untuk skenario lanjutan, bangun `Matrix` khusus dan berikan ke `Transform(matrix)`.*
> Di sinilah Anda **menerapkan beberapa transformasi** dalam satu langkah.

## Kesimpulan

Anda telah mempelajari cara **menyimpan file PostScript**, **membuat dokumen PostScript**, dan **menerapkan beberapa transformasi** menggunakan Aspose.Page untuk .NET. Bereksperimenlah dengan urutan transformasi yang berbeda, gabungkan mereka, dan saksikan bagaimana grafik berkembang.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara menerapkan beberapa transformasi pada satu objek?**  
J: Gunakan metode `Transform` dengan `Matrix` khusus yang menggabungkan translasi, skala, rotasi, atau shearing sesuai urutan yang Anda butuhkan.

**T: Bisakah saya melihat pratinjau transformasi sebelum menyimpan dokumen?**  
J: Ya—render `PsDocument` ke gambar atau gunakan penampil PostScript untuk memeriksa output sebelum memanggil `Save()`.

**T: Apakah memungkinkan menerapkan transformasi pada elemen tertentu dalam dokumen?**  
J: Tentu saja. Simpan state grafik sebelum menggambar elemen, terapkan transformasi yang diinginkan, gambar, lalu pulihkan state.

**T: Apakah ada pertimbangan kinerja saat menangani transformasi kompleks?**  
J: Matriks kompleks meningkatkan beban CPU. Jaga transformasi sesederhana mungkin dan gunakan kembali state yang disimpan saat menggambar banyak objek serupa.

**T: Bagaimana cara mendapatkan dukungan atau bantuan terkait pertanyaan Aspose.Page?**  
J: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk bantuan komunitas, atau hubungi dukungan Aspose secara langsung.

---

**Terakhir Diperbarui:** 2026-01-12  
**Diuji Dengan:** Aspose.Page 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
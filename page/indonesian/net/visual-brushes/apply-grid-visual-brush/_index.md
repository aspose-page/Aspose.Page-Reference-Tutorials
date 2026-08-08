---
date: 2026-04-03
description: Pelajari cara menambahkan persegi panjang transparan dan menerapkan Grid
  Visual Brush di .NET menggunakan Aspose.Page untuk dokumen XPS yang menakjubkan.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Terapkan Kuas Visual Grid
second_title: Aspose.Page .NET API
title: Tambahkan Persegi Panjang Transparan menggunakan Grid Visual Brush (.NET)
url: /id/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Persegi Panjang Transparan menggunakan Grid Visual Brush (.NET)

## Pendahuluan

Jika Anda ingin **menambahkan persegi panjang transparan** ke dokumen XPS sambil menerapkan Grid Visual Brush yang bergaya, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah yang tepat dengan Aspose.Page untuk .NET, sehingga Anda dapat membuat dokumen visual yang kaya dan menonjol. Pada akhir tutorial Anda akan memiliki contoh lengkap yang dapat dijalankan yang menunjukkan kedua teknik dalam satu alur kerja yang mudah diikuti.

## Jawaban Cepat
- **Apa yang dilakukan oleh persegi panjang transparan?** Menambahkan lapisan semi‑opaque yang memungkinkan konten latar belakang terlihat.  
- **API mana yang membuat brush?** `XpsDocument.CreateVisualBrush` membangun Grid Visual Brush.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Apa itu Persegi Panjang Transparan di XPS?
Persegi panjang transparan hanyalah bentuk yang warna isiannya mencakup komponen alfa kurang dari 1.0, sehingga grafik di bawahnya dapat terlihat sebagian. Ini sangat cocok untuk menyorot bagian tanpa menutupi latar belakang sepenuhnya.

## Mengapa menggunakan Grid Visual Brush?
Grid Visual Brush memungkinkan Anda menata ubin grafis vektor kecil di seluruh area yang lebih besar, menciptakan pola seperti grid, hatching, atau tekstur khusus. Menggabungkannya dengan persegi panjang transparan memberikan efek visual berlapis yang ringan dan independen resolusi.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

- **Aspose.Page for .NET** – Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/net/).
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).
- Folder tempat file XPS yang dihasilkan akan disimpan.

## Impor Namespace

Di file C# Anda, impor namespace yang diperlukan:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Sekarang mari kita uraikan solusi menjadi langkah‑langkah yang jelas dan bernomor.

## Langkah 1: Inisialisasi XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Kami memulai dengan membuat instance `XpsDocument`, yang akan menampung semua operasi menggambar selanjutnya.

## Langkah 2: Buat Geometri Grid Magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Geometri ini mendefinisikan kontur grid yang akan diisi oleh visual brush.

## Langkah 3: Rancang VisualBrush Grid Magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Di sini kami menggambar ubin magenta kecil yang akan diulang di seluruh grid.

## Langkah 4: Terapkan VisualBrush ke Grid

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Pemanggilan `CreateVisualBrush` mengaitkan ubin magenta dengan geometri grid dan mengaktifkan penataan ubin.

## Langkah 5: Tambahkan Grid ke Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Kami menempatkan grid berulang pada canvas dan menerapkan transformasi translasi sehingga muncul di lokasi yang diinginkan.

## Langkah 6: Tambahkan Persegi Panjang Transparan

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Pada langkah ini kami **menambahkan persegi panjang transparan** (bentuk merah dengan `Opacity = 0.7f`). Sesuaikan nilai opacity untuk mengontrol seberapa tembus pandang persegi panjang tersebut.

## Langkah 7: Simpan Dokumen

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

File XPS ditulis ke folder yang Anda tentukan sebelumnya.

## Kasus Penggunaan Umum

- **Penyorotan Laporan:** Menempatkan persegi panjang semi‑transparan untuk menekankan grafik atau tabel.  
- **Efek Watermark:** Menggabungkan grid berulang dengan lapisan transparan untuk branding yang halus.  
- **PDF/XPS Interaktif:** Gunakan pola sebagai latar belakang bidang formulir sambil menjaga UI tetap terbaca.

## Tips Pemecahan Masalah

- **Opacity Tidak Terlihat?** Pastikan penampil Anda mendukung transparansi XPS; beberapa penampil lama mungkin mengabaikan properti `Opacity`.  
- **Ukuran Tile Salah?** Verifikasi bahwa rectangle sumber (`new RectangleF(0f, 0f, 10f, 10f)`) sesuai dengan dimensi tile vektor.  
- **File Tidak Tersimpan?** Periksa kembali bahwa `dataDir` mengarah ke direktori yang ada dan dapat ditulisi.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page for .NET di aplikasi web dan desktop?**  
**A: Ya, perpustakaan ini bekerja di semua jenis aplikasi .NET.**

**Q: Apakah ada versi percobaan yang tersedia sebelum membeli?**  
**A: Tentu saja, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).**

**Q: Di mana saya dapat menemukan dukungan tambahan atau diskusi komunitas?**  
**A: Kunjungi [Forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk bantuan dari komunitas dan insinyur Aspose.**

**Q: Bagaimana cara mendapatkan lisensi sementara untuk evaluasi?**  
**A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).**

**Q: Dokumentasi lain apa yang tersedia untuk Aspose.Page for .NET?**  
**A: Jelajahi dokumentasi lengkap [di sini](https://reference.aspose.com/page/net/).**

---

**Terakhir Diperbarui:** 2026-04-03  
**Diuji Dengan:** Aspose.Page 24.12 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
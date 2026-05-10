---
date: 2026-01-12
description: Pelajari cara memodifikasi dokumen XPS menggunakan Aspose.Page untuk
  .NET dan temukan cara menambahkan teks ke file XPS dengan contoh kode sederhana.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Modifikasi Dokumen XPS dengan Aspose.Page untuk .NET
url: /id/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifikasi Dokumen XPS dengan Aspose.Page untuk .NET

## Pendahuluan

Selamat datang di panduan langkah‑demi‑langkah kami tentang **cara memodifikasi dokumen xps** dengan Aspose.Page untuk .NET. Apakah Anda perlu menyisipkan tanda tangan, menambahkan watermark, atau sekadar menempatkan teks khusus pada sebuah halaman, tutorial ini menunjukkan **cara menambahkan teks** ke dokumen XPS dalam hitungan menit. Kami akan menelusuri setiap baris kode, menjelaskan mengapa setiap langkah penting, dan memberi Anda tips untuk menghindari jebakan umum.

### Jawaban Cepat
- **Apa yang dibahas tutorial ini?** Menambahkan teks tanda tangan ("Confirmed") ke halaman terpilih dari file XPS.  
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk .NET (versi terbaru).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10 menit untuk penyisipan tanda tangan dasar.

## Apa itu memodifikasi dokumen XPS?

XPS (XML Paper Specification) adalah format dokumen tata letak tetap milik Microsoft, mirip dengan PDF. Memodifikasi dokumen XPS berarti mengubah konten visualnya secara programatis—menambahkan teks, gambar, atau bentuk—tanpa mengonversi file ke format lain. Aspose.Page menyediakan model objek yang kaya yang memungkinkan Anda mengedit file XPS langsung dari kode .NET Anda.

## Mengapa menggunakan Aspose.Page untuk memodifikasi dokumen XPS?

* **Kontrol penuh** – bekerja dengan halaman, glyph, brush, dan transformasi pada level rendah.  
* **Tanpa ketergantungan eksternal** – perpustakaan .NET murni, tidak memerlukan komponen Office atau Adobe.  
* **Lintas‑platform** – berjalan di Windows, Linux, dan macOS melalui .NET Core.  
* **Kinerja handal** – menangani dokumen besar secara efisien dan mendukung tipografi lanjutan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.Page untuk .NET** – Instal paket NuGet atau unduh perpustakaan dari dokumentasi resmi **[di sini](https://reference.aspose.com/page/net/)**.  
- **File XPS input** – Dapatkan contoh dokumen XPS (misalnya `input1.xps`) dari **[halaman rilis Aspose](https://releases.aspose.com/page/net/)**.  
- **Direktori kerja** – Buat folder di mesin Anda untuk menyimpan file input dan output serta catat jalur lengkapnya; Anda akan menetapkan jalur ini ke variabel `dir` dalam kode.  
- **Lingkungan pengembangan** – Visual Studio 2019/2022, .NET Framework 4.7.2 atau lebih baru, atau proyek .NET Core/5/6 apa pun.

Sekarang semua sudah siap, mari kita selami kode.

## Impor Namespace

Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Langkah 1: Buka Stream Dokumen XPS

Kita akan membuka file XPS sumber sebagai stream dan membuat objek `XpsDocument` yang mewakili seluruh dokumen.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Tip pro:* Bungkus stream dalam blok `using` agar pegangan file dilepaskan secara otomatis.

## Langkah 2: Buat Teks Tanda Tangan

Selanjutnya, buat brush berwarna solid yang akan digunakan untuk melukis glyph tanda tangan.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Anda dapat mengubah `Color.BlueViolet` menjadi `System.Drawing.Color` apa pun yang sesuai dengan merek Anda.

## Langkah 3: Tentukan Halaman dan Tambahkan Tanda Tangan

Tentukan halaman mana yang harus menerima tanda tangan, lalu tambahkan glyph ke setiap halaman.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Mengapa koordinat ini?* Nilai X dan Y diukur dalam poin (1/72 inci). Sesuaikan untuk menempatkan teks tepat di lokasi yang Anda inginkan pada tata letak halaman.

## Langkah 4: Simpan Perubahan ke Dokumen XPS

Akhirnya, tulis dokumen yang telah dimodifikasi kembali ke disk.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

File baru `input1_out.xps` kini berisi tanda tangan “Confirmed” pada halaman 1‑3.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|----------|
| **Tanda tangan tidak terlihat** | Koordinat salah atau halaman tidak dipilih | Pastikan `SelectActivePage` dipanggil untuk setiap halaman dan sesuaikan nilai X/Y. |
| **Exception pada `AddGlyphs`** | Font tidak terpasang di server | Pastikan font yang disebutkan (mis., Arial) tersedia, atau sematkan font khusus menggunakan `document.AddFont`. |
| **File output rusak** | Stream tidak ditutup dengan benar | Gunakan pernyataan `using` untuk semua stream dan panggil `document.Dispose()` bila diperlukan. |
| **Penurunan kinerja pada file besar** | Memuat seluruh dokumen ke memori | Proses halaman secara batch atau gunakan `XpsLoadOptions` dengan opsi streaming (jika tersedia pada versi terbaru). |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Page kompatibel dengan framework .NET terbaru?**  
J: Ya, Aspose.Page secara rutin diperbarui untuk mendukung .NET Framework 4.5+, .NET Core 3.1+, .NET 5, dan .NET 6.

**T: Bisakah saya menyesuaikan font dan gaya teks yang ditambahkan?**  
J: Tentu saja. Ubah parameter `AddGlyphs` (nama font, ukuran, `FontStyle`) sesuai desain Anda.

**T: Apakah ada batas ukuran untuk file XPS?**  
J: Aspose.Page dapat menangani dokumen besar, namun konsumsi memori meningkat seiring ukuran file. Untuk file sangat besar, pertimbangkan memproses halaman satu per satu.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?**  
J: Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**T: Di mana saya dapat mencari bantuan atau terhubung dengan komunitas Aspose?**  
J: Kunjungi **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk mengajukan pertanyaan dan berbagi pengalaman.

## Kesimpulan

Dalam tutorial ini kami menunjukkan cara **memodifikasi dokumen xps** dengan menambahkan teks tanda tangan khusus menggunakan Aspose.Page untuk .NET. Sekarang Anda memiliki fondasi yang kuat untuk menyisipkan teks, watermark, atau anotasi apa pun ke halaman tertentu dari file XPS. Bereksperimenlah dengan berbagai font, warna, dan posisi untuk memenuhi kebutuhan branding aplikasi Anda, dan jelajahi API Aspose.Page yang lebih luas untuk kemampuan grafis dan tata letak lanjutan.

---

**Terakhir Diperbarui:** 2026-01-12  
**Diuji dengan:** Aspose.Page 24.11 untuk .NET (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
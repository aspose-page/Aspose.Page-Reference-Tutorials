---
date: 2025-12-08
description: Pelajari cara menambahkan pola hatch ke dokumen Java PostScript menggunakan
  Aspose.Page Java. Panduan langkah demi langkah ini menunjukkan cara menambahkan
  grafik pola hatch secara efisien.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Tambahkan Pola Hatch di PostScript Java'
url: /id/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Pola Hatch di Java PostScript

## Pendahuluan
Jika Anda bekerja dengan **Aspose.Page Java** dan perlu memperkaya output PostScript Anda dengan grafik bertekstur, pola hatch merupakan solusi yang cepat dan fleksibel. Pada tutorial ini kami akan menjelaskan **cara menambahkan desain hatch** ke dokumen PostScript, mengapa pola ini berguna, dan memberikan contoh kode lengkap yang siap dijalankan. Pada akhir tutorial, Anda akan dapat membuat bentuk dan teks yang diisi hatch secara visual menarik hanya dengan beberapa baris Java.

## Jawaban Cepat
- **Perpustakaan apa yang saya perlukan?** Aspose.Page untuk Java (SDK “aspose page java”).  
- **Efek visual apa yang kita tambahkan?** Pola hatch (misalnya garis diagonal, crosshatch).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi.  
- **Berapa banyak baris kode?** Sekitar 70 baris, dibagi menjadi langkah‑langkah yang jelas.  
- **Bisakah saya menggunakan pendekatan yang sama untuk PDF?** Ya—Aspose.Page mendukung banyak format output, termasuk PDF.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- **Lingkungan Pengembangan Java** – JDK 8 atau lebih tinggi dan IDE pilihan Anda.  
- **Perpustakaan Aspose.Page untuk Java** – Unduh JAR terbaru dari situs resmi [di sini](https://releases.aspose.com/page/java/).  
- **Akses menulis** ke folder tempat file PostScript yang dihasilkan akan disimpan.

## Impor Paket
Pertama, masukkan kelas‑kelas yang diperlukan ke dalam proyek Anda. Impor ini memberi Anda akses ke primitif menggambar, penanganan warna, dan API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Langkah 1: Menyiapkan Parameter Awal
Buat aliran output, konfigurasikan ukuran halaman (A4), dan definisikan beberapa variabel tata letak yang akan digunakan kembali saat menggambar setiap kotak berisi hatch.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Langkah 2: Simpan Status Grafik dan Translasi
Menyimpan status grafik memungkinkan kita kembali ke sistem koordinat asli nanti, sementara `translate` memindahkan asal ke titik awal yang nyaman.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Langkah 3: Buat Persegi untuk Setiap Pola
Definisikan persegi panjang yang dapat digunakan kembali yang akan mewakili setiap sel berisi hatch.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Langkah 4: Siapkan Pen untuk Garis Luar Persegi Pola
`BasicStroke` dengan ketebalan 2 point memberikan garis luar yang tajam di sekitar setiap persegi.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Langkah 5: Iterasi Melalui Pola Hatch
Lakukan perulangan pada setiap nilai dalam enum `HatchStyle`, isi setiap kotak dengan tekstur yang bersesuaian, lalu gambar garis luarnya. Inilah inti dari fungsionalitas **menambahkan pola hatch**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Langkah 6: Pulihkan Status Grafik
Kembali ke sistem koordinat asli setelah selesai menggambar grid persegi.

```java
document.writeGraphicsRestore();
```

## Langkah 7: Isi Teks dengan Pola Hatch
Di sini kami menunjukkan cara melukis teks menggunakan tekstur hatch. Contoh mengisi kata “ABC” dengan pola diagonal‑cross.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Langkah 8: Garis Luar Teks dengan Pola Hatch
Sekarang kami menggambar garis luar pada teks yang sama, namun kali ini menggunakan gaya hatch 70 % dan goresan yang lebih tebal.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Langkah 9: Tutup dan Simpan Dokumen
Selesaikan halaman, tulis file ke disk, dan bebaskan sumber daya.

```java
document.closePage();
document.save();
```

Ikuti langkah‑langkah ini, dan Anda akan memiliki file PostScript yang menampilkan seluruh set pola hatch yang diterapkan pada bentuk maupun teks—semua didukung oleh **aspose page java**.

## Mengapa Menggunakan Pola Hatch dengan Aspose.Page Java?
- **Pembedaan visual** – Isian hatch tetap terlihat meskipun printer terbatas pada output monokrom.  
- **Kinerja** – Tekstur dihasilkan secara dinamis, sehingga Anda menghindari file gambar berukuran besar.  
- **Dukungan lintas format** – Kode yang sama dapat menargetkan PDF, EPS, atau SVG dengan perubahan minimal.

## Kesalahan Umum & Tips
- **Kesalahan jalur file** – Pastikan `dataDir` diakhiri dengan pemisah file yang tepat (`/` atau `\`).  
- **Warna tidak didukung** – Beberapa interpreter PostScript lama mungkin tidak menangani ruang warna tertentu; gunakan RGB dasar untuk kompatibilitas maksimal.  
- **Peringatan lisensi** – Menjalankan contoh tanpa lisensi yang valid akan menambahkan watermark pada output.

## Kesimpulan
Mengintegrasikan pola hatch dapat secara dramatis meningkatkan keterbacaan dan estetika gambar teknis, peta, atau grafik apa pun yang dihasilkan oleh Java. Dengan **Aspose.Page Java**, Anda mendapatkan API ringkas yang mengabstraksi perintah PostScript tingkat rendah, memungkinkan Anda fokus pada desain daripada detail format file.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Page Java dengan kerangka kerja Java lainnya?**  
J: Ya, perpustakaan ini tidak bergantung pada kerangka kerja dan dapat bekerja dengan Spring, Jakarta EE, Android (terbatas), serta Java SE biasa.

**T: Apakah tersedia versi percobaan untuk Aspose.Page Java?**  
J: Tentu. Unduh percobaan gratis 30 hari [di sini](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk pengembangan?**  
J: Minta lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/). Lisensi ini menghilangkan watermark evaluasi.

**T: Di mana saya dapat menemukan lebih banyak tutorial dan dukungan komunitas?**  
J: Kunjungi forum resmi [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) untuk contoh tambahan dan tanya‑jawab.

**T: Apakah ada dokumentasi lengkap untuk semua kelas dan metode?**  
J: Ya, referensi API lengkap tersedia [di sini](https://reference.aspose.com/page/java/).

---

**Terakhir Diperbarui:** 2025-12-08  
**Diuji Dengan:** Aspose.Page untuk Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

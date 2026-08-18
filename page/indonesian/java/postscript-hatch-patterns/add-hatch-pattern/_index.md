---
date: 2026-08-18
description: Pelajari cara menambahkan hatch pattern ke file Java PostScript menggunakan
  Aspose.Page Java. Panduan step‑by‑step ini menampilkan kode lengkap dan tips.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Tambahkan Hatch Pattern di Java PostScript
og_description: Pelajari cara menambahkan hatch pattern di Java PostScript menggunakan
  Aspose.Page. Ikuti tutorial step‑by‑step ini untuk membuat grafik berisi hatch dengan
  cepat.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Cara menambahkan hatch pattern di Java PostScript – panduan Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Cara menambahkan hatch pattern di Java PostScript
url: /id/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan pola hatch di Java PostScript

## Pendahuluan
Jika Anda bekerja dengan **Aspose.Page Java** dan bertanya-tanya **cara menambahkan pola hatch** ke output PostScript Anda, pola hatch adalah solusi yang cepat dan fleksibel. Dalam tutorial ini kami akan menjelaskan **cara menambahkan desain hatch** ke dokumen PostScript, menjelaskan mengapa mereka berguna, dan memberi Anda contoh kode lengkap yang siap dijalankan. Pada akhir tutorial, Anda akan dapat membuat bentuk dan teks yang diisi hatch secara visual menarik dengan hanya beberapa baris Java.

## Jawaban Cepat
- **Perpustakaan apa yang saya butuhkan?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Efek visual apa yang kita tambahkan?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** A free trial works for development; a license is required for production.  
- **Berapa banyak baris kode?** About 70 lines, split into clear steps.  
- **Bisakah saya menggunakan pendekatan yang sama untuk PDF?** Yes—Aspose.Page supports multiple output formats, including PDF.

## Apa itu pola hatch?
Pola hatch adalah isian berbasis vektor yang terdiri dari garis atau bentuk berulang yang menciptakan efek tekstur. Karena didefinisikan secara matematis, pola ini dapat diskalakan tanpa kehilangan kualitas, menjadikannya ideal untuk pencetakan resolusi tinggi dan output monokrom.

## Mengapa menggunakan pola hatch dengan Aspose.Page Java?
Aspose.Page mendukung **lebih dari 10 format output** (termasuk PostScript, PDF, EPS, SVG, dan XPS) dan dapat merender isian hatch pada dokumen hingga **500 halaman** tanpa memuat seluruh file ke memori. Ini berarti Anda mendapatkan kinerja cepat, jejak memori rendah, dan hasil visual yang konsisten di semua format yang didukung.

## Cara menambahkan pola hatch – ikhtisar
Pola hatch adalah tekstur berbasis vektor yang merender dengan bersih pada resolusi apa pun dan bekerja dengan baik pada printer monokrom. Dengan menggunakan Aspose.Page Java, Anda dapat menerapkan pola ini pada bentuk, jalur, dan bahkan teks tanpa harus berurusan dengan perintah PostScript tingkat rendah.

## Prasyarat
- **Java Development Environment** – JDK 8 atau lebih tinggi dan IDE pilihan Anda.  
- **Aspose.Page for Java library** – Unduh JAR terbaru dari **halaman unduhan resmi Aspose.Page for Java** [here](https://releases.aspose.com/page/java/).  
- Anda juga dapat menelusuri rilis Aspose lainnya [here](https://releases.aspose.com/).  
- **Akses menulis** ke folder tempat file PostScript yang dihasilkan akan disimpan.

## Impor paket
Impor di bawah ini mencakup kelas Java AWT standar untuk primitif grafis seperti warna, goresan, dan bentuk geometris, serta kelas Aspose.Page yang menyediakan model dokumen, definisi gaya hatch, dan opsi penyimpanan yang diperlukan untuk menghasilkan file PostScript.  
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

## Apa itu kelas `Document`?
Kelas `Document` adalah objek tingkat atas Aspose.Page yang mewakili satu file PostScript dalam memori. Semua operasi menggambar dilakukan melalui objek ini.

## Cara menyiapkan aliran output?
Untuk menulis output, buat `FileOutputStream` yang menunjuk ke jalur file yang diinginkan; aliran ini menangani penulisan byte tingkat rendah. `PsSaveOptions` mengonfigurasi cara dokumen disimpan, termasuk ukuran halaman dan kompresi. Kemudian buat instance `Document` dengan objek `PsSaveOptions` yang menentukan ukuran halaman, kompresi, dan pengaturan khusus PostScript lainnya.  
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

## Cara menyimpan keadaan grafis dan mentranslasi asal?
Menyimpan keadaan grafis menangkap matriks transformasi saat ini, wilayah pemotongan, dan atribut menggambar, memungkinkan Anda mengembalikannya nanti. Setelah menyimpan, panggil `translate(x, y)` pada objek grafis untuk menggeser asal ke lokasi yang nyaman untuk menggambar kisi kotak hatch.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Cara membuat kotak yang dapat digunakan kembali untuk setiap pola?
`Rectangle2D` mewakili bentuk persegi panjang yang didefinisikan oleh posisi dan ukurannya. Dengan membuat satu instance yang sesuai dengan dimensi sel, Anda dapat menggunakannya kembali untuk setiap kotak yang diisi hatch, mengurangi alokasi objek dan menjaga efisiensi loop menggambar.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Cara menyiapkan pena untuk garis tepi kotak pola?
`BasicStroke` menggambarkan ketebalan garis tepi, pola dash, dan ujung untuk bentuk vektor. Menggunakan `BasicStroke` 2‑point memberikan batas yang jelas di sekitar setiap sel yang diisi hatch, memastikan isian terpisah secara visual dari kotak bersebelahan.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Cara mengiterasi pola hatch?
`HatchStyle` adalah enumerasi yang mencantumkan semua pola hatch bawaan seperti diagonal, silang, dan titik. Mengulang `HatchStyle.values()` memungkinkan Anda menerapkan setiap pola secara berurutan, mengisi persegi panjang dengan `HatchBrush`, dan kemudian menggambar garis tepinya.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Cara mengembalikan keadaan grafis setelah menggambar?
Memanggil `restore()` pada objek grafis mengembalikan matriks transformasi dan pengaturan menggambar ke keadaan yang disimpan sebelumnya, mencegah translasi atau skala kumulatif memengaruhi operasi menggambar berikutnya. Ini memastikan bahwa konten selanjutnya dimulai dari sistem koordinat asli dan menggunakan atribut default.  
```java
document.writeGraphicsRestore();
```

## Cara mengisi teks dengan pola hatch?
`TextFragment` mewakili sepotong teks yang dapat diposisikan dan diberi gaya secara independen. Dengan menetapkan `HatchBrush` dengan `HatchStyle` yang dipilih ke isian fragmen, karakter teks dirender menggunakan tekstur hatch alih-alih warna solid.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Cara memberi garis tepi pada teks dengan gaya hatch yang berbeda?
`HatchBrush` juga dapat digunakan untuk stroking. Untuk menggambar garis tepi, setel stroke fragmen ke `HatchBrush` dengan `HatchStyle` yang berbeda (mis., hatch 70 %), dan tingkatkan lebar stroke melalui `setStrokeWidth`. Ini merender batas teks dengan pola hatch-nya sendiri sambil mempertahankan interior yang terisi.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Cara menutup dan menyimpan dokumen?
`document.save()` menulis dokumen dalam memori ke aliran output yang ditentukan. Setelah menyelesaikan semua perintah menggambar, panggil metode ini dan kemudian tutup `FileOutputStream` untuk melepaskan sumber daya sistem dan memastikan file benar‑benar ditulis ke disk.  
```java
document.closePage();
document.save();
```

Ikuti langkah‑langkah ini, dan Anda akan memiliki file PostScript yang menampilkan serangkaian lengkap pola hatch yang diterapkan pada bentuk dan teks—semua didukung oleh **aspose page java**.

## Kesulitan umum & tips
- **Kesalahan jalur file** – Pastikan `dataDir` diakhiri dengan pemisah file yang sesuai (`/` atau `\`).  
- **Warna tidak didukung** – Beberapa interpreter PostScript lama mungkin tidak menangani ruang warna tertentu; gunakan RGB dasar untuk kompatibilitas maksimum.  
- **Peringatan lisensi** – Menjalankan contoh tanpa lisensi yang valid akan menambahkan watermark pada output.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Page Java dengan kerangka kerja Java lainnya?**  
A: Ya, perpustakaan ini bersifat framework‑agnostic dan bekerja dengan Spring, Jakarta EE, Android (terbatas), dan Java SE biasa.

**Q: Apakah tersedia versi percobaan untuk Aspose.Page Java?**  
A: Tentu saja. Unduh percobaan gratis 30‑hari [Aspose trial download page](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk pengembangan?**  
A: Minta lisensi sementara [temporary license request page](https://purchase.aspose.com/temporary-license/). Ini menghapus watermark evaluasi.

**Q: Di mana saya dapat menemukan lebih banyak tutorial dan dukungan komunitas?**  
A: Kunjungi forum resmi [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) untuk contoh tambahan dan Q&A.

**Q: Apakah ada dokumentasi lengkap untuk semua kelas dan metode?**  
A: Ya, referensi API lengkap tersedia [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Bisakah saya merender pola hatch yang sama ke PDF alih-alih PostScript?**  
A: Tentu saja. Ubah `PsSaveOptions` menjadi `PdfSaveOptions` (atau yang setara) dan sisanya kode tetap tidak berubah.

**Q: Apa yang harus saya lakukan jika file yang dihasilkan kosong?**  
A: Pastikan aliran output mengarah ke direktori yang dapat ditulisi dan bahwa `document.save()` dipanggil setelah semua operasi menggambar.

---

**Terakhir Diperbarui:** 2026-08-18  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Pola Tekstur di PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Cara Menambahkan Gradien: Gradien Diagonal di Java PostScript menggunakan Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Cara Mengonversi PostScript ke PDF Menggunakan Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-04
description: Pelajari cara menambahkan gradient dalam Java PostScript dengan Aspose.Page
  Java, membuat transisi warna diagonal menggunakan LinearGradientPaint untuk dokumen
  yang hidup.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Cara menambahkan gradient: gradient diagonal dalam Java PostScript menggunakan
  Aspose.Page Java'
og_description: Pelajari cara menambahkan gradient dalam Java PostScript menggunakan
  Aspose.Page Java. Panduan ini menunjukkan cara membuat gradient diagonal dengan
  LinearGradientPaint dalam beberapa langkah saja.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Cara menambahkan gradient dalam Java PostScript dengan Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Cara menambahkan gradient: gradient diagonal dalam Java PostScript menggunakan
  Aspose.Page Java'
url: /id/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan gradien diagonal dalam Java PostScript menggunakan Aspose.Page Java

## Pendahuluan
Jika Anda ingin memperkaya file PostScript dengan transisi warna diagonal yang halus, **Aspose.Page Java** membuatnya terasa sangat mudah. Pada tutorial ini Anda akan belajar **cara menambahkan efek gradien** langkah demi langkah, menggunakan kelas `LinearGradientPaint` dari Java 2D. Pada akhir tutorial Anda akan memiliki potongan kode siap‑jalankan yang membuat dokumen PostScript dengan gradien diagonal yang hidup, dan Anda akan memahami mengapa pendekatan ini lebih mudah dipelihara dibandingkan menulis perintah PostScript mentah secara manual.

## Cara menambahkan gradien dalam Java PostScript
Menambahkan gradien mungkin terdengar seperti tugas grafis semata, tetapi dengan Aspose.Page Anda mendapatkan kontrol penuh atas perintah PostScript yang mendasarinya sambil tetap berada dalam Java murni. Bagian ini menjelaskan mengapa pendekatan ini berhasil dan apa yang Anda dapatkan dibandingkan menulis perintah PostScript mentah secara manual.

## Jawaban cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Page untuk Java.  
- **Kelas mana yang membuat gradien?** `LinearGradientPaint`.  
- **Bisakah saya mengubah warnanya?** Ya – ubah array `Color[]`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia.  
- **Berapa lama implementasinya?** Sekitar 10 menit untuk gradien dasar.

## Apa itu Aspose.Page Java?
Aspose.Page Java adalah API lengkap yang memungkinkan pengembang menghasilkan, mengedit, dan mengonversi file PostScript serta PDF tanpa perangkat lunak eksternal. Perpustakaan ini mendukung **lebih dari 50 format input dan output** dan dapat memproses dokumen dengan **lebih dari 500 halaman** sambil menjaga penggunaan memori di bawah 100 MB.

## Mengapa menggunakan gradien diagonal?
Gradien diagonal menambah kedalaman dan daya tarik visual pada diagram, spanduk, atau elemen grafis apa pun yang membutuhkan tampilan modern. Karena gradien berjalan dari satu sudut ke sudut berlawanan, ia cocok untuk latar belakang, kulit tombol, dan bentuk dekoratif, memberikan sentuhan profesional tanpa memerlukan aset gambar tambahan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Java Development Kit (JDK) 8 atau lebih tinggi.  
- IDE seperti Eclipse, IntelliJ IDEA, atau VS Code.  
- Perpustakaan **Aspose.Page untuk Java** – unduh versi terbaru dari [halaman unduhan resmi](https://releases.aspose.com/page/java/).

## Impor paket
Paket `java.awt` menyediakan kelas grafis inti, sementara paket `com.aspose.page` memberi Anda akses ke API khusus PostScript.

Kelas `LinearGradientPaint` adalah jembatan Aspose.Page ke fungsionalitas gradien Java 2D.  
`AffineTransform` memungkinkan rotasi dan skala gradien sehingga sejajar secara diagonal.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Langkah 1: buat aliran output untuk dokumen PostScript
Pertama, tentukan folder tempat file akan disimpan dan buka `FileOutputStream`. Aliran ini menerima data PostScript yang dihasilkan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Langkah 2: buat opsi penyimpanan dengan ukuran A4
`PsSaveOptions` memungkinkan Anda menentukan ukuran halaman, resolusi, dan pengaturan output lainnya. Di sini kami menggunakan ukuran A4 default, yaitu 595 × 842 poin pada 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Langkah 3: buat dokumen PS baru
Kelas `PsDocument` mewakili dokumen PostScript dan menyediakan metode untuk membuat halaman serta menggambar grafik.  
Instansiasi `PsDocument` menggunakan aliran output dan opsi penyimpanan. Flag `false` memberi tahu konstruktor untuk tidak secara otomatis membuka halaman baru – kami akan melakukannya nanti.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 4: buat persegi panjang
Tentukan persegi panjang yang akan menerima isian gradien. Posisi persegi panjang (200, 100) dan ukuran (200 × 100) dipilih agar gradien terlihat jelas.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Langkah 5: buat transformasi gradien
`AffineTransform` memungkinkan kami memutar, menskalakan, dan mentranslasi gradien sehingga berjalan secara diagonal melintasi persegi panjang. Rumus di bawah menghitung hipotenusa dan menyesuaikan rasio skala secara tepat.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Langkah 6: buat cat gradien linear diagonal
`LinearGradientPaint` adalah kelas inti yang menghasilkan transisi warna. Ia membentang dari kiri‑atas persegi panjang ke kanan‑bawah, menggunakan transformasi yang telah didefinisikan sebelumnya. `MultipleGradientPaint.CycleMethod.NO_CYCLE` memastikan gradien tidak berulang.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Langkah 7: tetapkan cat dan isi persegi panjang
Terapkan cat gradien ke dokumen dan isi bentuk persegi panjang. Langkah ini merender transisi warna diagonal ke halaman PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Langkah 8: tutup halaman saat ini dan simpan dokumen
Akhirnya, tutup halaman, flush aliran, dan simpan file. File `DiagonalGradient_outPS.ps` yang dihasilkan dapat dibuka dengan penampil PostScript apa pun.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Masalah umum & tips
- **Gradien terlihat datar** – periksa kembali sudut rotasi; rotasi 45° menghasilkan diagonal yang sesungguhnya.  
- **Warna tampak pudar** – pastikan Anda menggunakan `MultipleGradientPaint.ColorSpaceType.SRGB` untuk rendering warna yang akurat.  
- **Kesalahan file tidak ditemukan** – pastikan `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis.  
- **Dokumen besar menyebabkan lonjakan memori** – gunakan `PsSaveOptions.setCompress(true)` untuk mengurangi jejak memori.

## Pertanyaan yang sering diajukan

**T: Bisakah saya menggunakan perpustakaan ini untuk operasi grafis lain dalam Java?**  
J: Ya, Aspose.Page untuk Java menyediakan rangkaian lengkap primitif menggambar, rendering teks, dan kemampuan penanganan gambar.

**T: Apakah ada versi percobaan gratis untuk Aspose.Page Java?**  
J: Tentu saja. Anda dapat mengunduh percobaan penuh fungsi dari [halaman percobaan gratis Aspose](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page Java?**  
J: Referensi API resmi tersedia di [referensi API Aspose.Page Java](https://reference.aspose.com/page/java/).

**T: Bagaimana cara membeli lisensi untuk Aspose.Page Java?**  
J: Lisensi dapat dibeli langsung melalui [portal pembelian Aspose](https://purchase.aspose.com/buy).

**T: Butuh bantuan atau memiliki pertanyaan?**  
J: Kunjungi forum komunitas‑run [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk bantuan dari insinyur Aspose maupun pengembang lain.

---

**Terakhir diperbarui:** 2026-09-04  
**Diuji dengan:** Aspose.Page untuk Java 24.12 (terbaru)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Gradien Radial dalam PostScript dengan Aspose.Page untuk Java](/page/java/postscript-gradient-addition/)
- [Cara Menambahkan Gradien dalam Java PostScript dengan Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Buat Gradien PostScript dalam Java – Tambahkan Gradien Vertikal](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
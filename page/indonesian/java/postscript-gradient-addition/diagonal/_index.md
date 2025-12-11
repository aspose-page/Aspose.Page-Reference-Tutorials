---
date: 2025-12-07
description: Tingkatkan dokumen Java PostScript Anda dengan gradien diagonal menggunakan
  Aspose.Page Java. Pelajari cara menambahkan efek gradien dengan LinearGradientPaint
  di Java dan buat transisi warna yang hidup dengan mudah.
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Tambahkan Gradien Diagonal di Java PostScript menggunakan Aspose.Page Java
url: /id/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Gradien Diagonal di PostScript Java menggunakan Aspose.Page Java

## Pendahuluan
Jika Anda ingin memperkaya file PostScript dengan transisi warna diagonal yang halus, **Aspose.Page Java** membuatnya terasa sangat mudah. Pada tutorial ini kami akan memandu **cara menambahkan gradien** langkah demi langkah, menggunakan kelas `LinearGradientPaint` dari Java 2D. Pada akhir tutorial Anda akan memiliki potongan kode siap‑jalankan yang menghasilkan dokumen PostScript dengan gradien diagonal yang hidup.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page untuk Java.  
- **Kelas mana yang membuat gradien?** `LinearGradientPaint`.  
- **Apakah saya dapat mengubah warnanya?** Ya – ubah array `Color[]`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia.  
- **Berapa lama implementasinya?** Sekitar 10 menit untuk gradien dasar.

## Apa itu Aspose.Page Java?
Aspose.Page Java adalah API kuat yang memungkinkan pengembang menghasilkan, mengedit, dan mengonversi file PostScript serta PDF tanpa memerlukan perangkat lunak eksternal. API ini mengekspos seluruh kemampuan grafis bahasa PostScript melalui antarmuka Java yang bersih dan berorientasi objek.

## Mengapa menggunakan gradien diagonal?
Gradien diagonal menambah kedalaman dan daya tarik visual pada diagram, spanduk, atau elemen grafis apa pun yang membutuhkan tampilan modern. Karena gradien berjalan dari satu sudut ke sudut berlawanan, ia cocok untuk latar belakang, kulit tombol, dan bentuk dekoratif.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Java Development Kit (JDK) 8 atau lebih tinggi.  
- IDE seperti Eclipse, IntelliJ IDEA, atau VS Code.  
- **Aspose.Page untuk Java** – unduh versi terbaru dari [halaman unduhan resmi](https://releases.aspose.com/page/java/).

## Impor Paket
Pertama, impor paket Java 2D dan kelas Aspose yang diperlukan. Impor ini memberi Anda akses ke definisi warna, bentuk geometris, pengecatan gradien, dan API dokumen PostScript.

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

## Langkah 1: Buat Output Stream untuk Dokumen PostScript
Kami mulai dengan menentukan folder tempat file akan disimpan dan membuka `FileOutputStream`. Stream ini akan menerima data PostScript yang dihasilkan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Langkah 2: Buat Opsi Penyimpanan dengan Ukuran A4
`PsSaveOptions` memungkinkan Anda menentukan ukuran halaman, resolusi, dan pengaturan output lainnya. Di sini kami menggunakan ukuran A4 default.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Langkah 3: Buat Dokumen PS Baru
Instansiasi `PsDocument` menggunakan output stream dan opsi penyimpanan. Flag `false` memberi tahu konstruktor untuk tidak secara otomatis membuka halaman baru – kami akan melakukannya nanti.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Langkah 4: Buat Persegi Panjang
Tentukan persegi panjang yang akan menerima isian gradien. Posisi persegi panjang (200, 100) dan ukuran (200 × 100) dipilih agar gradien terlihat jelas.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Langkah 5: Buat Transformasi Gradien
`AffineTransform` memungkinkan kami memutar, menskalakan, dan mentranslasi gradien sehingga berjalan diagonal melintasi persegi panjang. Rumus di bawah menghitung hipotenusa dan menyesuaikan rasio skala secara tepat.

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

## Langkah 6: Buat Linear Gradient Paint Diagonal
Berikut inti **cara menambahkan gradien** – kami membangun `LinearGradientPaint` yang membentang dari kiri‑atas persegi panjang ke kanan‑bawah, menggunakan transformasi yang telah didefinisikan sebelumnya. `MultipleGradientPaint.CycleMethod.NO_CYCLE` memastikan gradien tidak berulang.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Langkah 7: Atur Paint dan Isi Persegi Panjang
Terapkan paint gradien ke dokumen dan isi bentuk persegi panjang. Langkah ini merender transisi warna diagonal pada halaman PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Langkah 8: Tutup Halaman Saat Ini dan Simpan Dokumen
Akhirnya, tutup halaman, flush stream, dan simpan file. File `DiagonalGradient_outPS.ps` yang dihasilkan dapat dibuka dengan penampil PostScript apa pun.

```java
// Close current page and save the document
document.closePage();
document.save();
```

Dengan mengikuti delapan langkah ini Anda telah berhasil menambahkan gradien diagonal ke dokumen PostScript menggunakan **Aspose.Page Java**. Silakan bereksperimen dengan warna, sudut, dan ukuran persegi panjang yang berbeda untuk menciptakan efek visual khusus.

## Masalah Umum & Tips
- **Gradien tampak datar** – periksa kembali sudut rotasi; rotasi 45° menghasilkan diagonal yang sesungguhnya.  
- **Warna terlihat pudar** – pastikan Anda menggunakan `MultipleGradientPaint.ColorSpaceType.SRGB` untuk rendering warna yang akurat.  
- **Error file tidak ditemukan** – pastikan `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan perpustakaan ini untuk operasi grafis lain di Java?**  
J: Ya, Aspose.Page untuk Java menyediakan rangkaian lengkap primitif menggambar, rendering teks, dan kemampuan penanganan gambar.

**T: Apakah ada versi percobaan gratis untuk Aspose.Page Java?**  
J: Tentu. Anda dapat mengunduh versi percobaan penuh fungsi dari [halaman percobaan gratis Aspose](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page Java?**  
J: Referensi API resmi tersedia [di sini](https://reference.aspose.com/page/java/).

**T: Bagaimana cara membeli lisensi untuk Aspose.Page Java?**  
J: Lisensi dapat dibeli langsung melalui [portal pembelian Aspose](https://purchase.aspose.com/buy).

**T: Butuh bantuan atau memiliki pertanyaan?**  
J: Kunjungi forum komunitas **[Aspose.Page](https://forum.aspose.com/c/page/39)** untuk bantuan dari insinyur Aspose maupun pengembang lain.

---

**Terakhir Diperbarui:** 2025-12-07  
**Diuji Dengan:** Aspose.Page untuk Java 24.12 (terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
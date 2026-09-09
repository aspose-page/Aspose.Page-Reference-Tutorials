---
date: 2026-09-09
description: Pelajari cara membuat radial gradient di Java PostScript menggunakan
  Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara menambahkan color
  stops gradient, mengatur radii, dan menghasilkan PS file dengan cepat.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Menguasai radial gradients di Java
og_description: Pelajari cara membuat radial gradient di Java PostScript menggunakan
  Aspose.Page. Panduan ini menjelaskan cara menambahkan color stops gradient, mengatur
  radii, dan menghasilkan PS file dalam hitungan menit.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Cara membuat radial gradient di Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Cara membuat radial gradient di Java PostScript
url: /id/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gradien radial di Java PostScript dengan Aspose.Page

## Pendahuluan
Jika Anda perlu **membuat gradien radial** di dalam file PostScript, Anda berada di tempat yang tepat. Pada tutorial ini kami akan membahas setiap langkah yang diperlukan untuk menghasilkan dokumen PostScript yang berisi gradien radial halus, menggunakan **Aspose.Page for Java**. Pada akhir tutorial Anda akan memahami API-nya, melihat contoh lengkap yang dapat dijalankan, dan mengetahui cara menyesuaikan warna, posisi, serta radius untuk skenario desain apa pun.

## Jawaban cepat
- **Perpustakaan apa yang membuat gradien radial di PostScript?** Aspose.Page for Java.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya mengubah bentuk gradien?** Ya – sesuaikan radius dan titik pusat di konstruktor `RadialGradientPaint`.

## Cara membuat gradien radial di Java

Muat proyek Java Anda, impor kelas yang diperlukan, dan ikuti panduan langkah‑demi‑langkah di bawah ini. Jawaban intinya adalah Anda menginstansiasi sebuah `RadialGradientPaint` dengan warna‑warna berhenti Anda, lalu menerapkannya pada persegi panjang yang digambar pada sebuah `PsDocument`. Pendekatan dua‑objek ini menangani semua perintah PostScript tingkat rendah untuk Anda.

## Apa itu gradien radial?
`RadialGradientPaint` adalah kelas Java AWT yang mendefinisikan transisi warna melingkar dari titik pusat ke luar. Ia menciptakan perpaduan halus dari beberapa warna berhenti, menjadikannya ideal untuk sorotan, latar belakang lembut, atau efek apa pun di mana warna memancar dari titik fokus.

## Mengapa menggunakan Aspose.Page untuk gradien radial?
Aspose.Page memberi Anda kontrol programatik penuh atas output PostScript sambil menangani beban kerja sintaks PS tingkat rendah. Ia mendukung **lebih dari 50 format input dan output**, dapat merender dokumen ratusan halaman tanpa memuat seluruh file ke memori, dan berjalan pada sistem operasi apa pun yang mendukung Java 8+. Kemampuan terukur ini menjadikannya pilihan andal untuk pembuatan grafis kelas perusahaan.

## Prasyarat
- **Java Development Kit (JDK) 8+** – verifikasi dengan `java -version`.  
- **Aspose.Page for Java** – unduh JAR terbaru dari halaman unduhan resmi [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE pilihan Anda** – Eclipse, IntelliJ IDEA, atau VS Code dengan ekstensi Java.  
- **Folder yang dapat ditulisi** – tempat file `.ps` yang dihasilkan akan disimpan.

## Impor paket
Pertama, impor kelas‑kelas yang akan kita gunakan. Paket `java.awt` menyediakan objek‑objek paint gradien, sementara `com.aspose.eps` berisi kelas‑kelas penanganan dokumen PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: buat persegi panjang dan buka dokumen PS
`PsDocument` adalah kelas Aspose.Page yang mewakili dokumen PostScript dan menyediakan metode untuk menggambar bentuk, teks, dan gambar. Kami memulai dengan membuat aliran output, mengonfigurasi ukuran halaman (A4 secara default), dan mendefinisikan persegi panjang yang akan menampung gradien.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Tip pro:** Sesuaikan koordinat persegi panjang (`200, 100, 200, 200`) untuk menempatkan gradien di mana saja pada halaman.

### Langkah 2: definisikan warna dan fraksi
Gradien radial dibangun dari *color stops* (warna) dan *fractions* (posisi relatif dari stop tersebut). Di sini kami membuat array berisi enam warna dan fraksi‑fraksi yang bersesuaian.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Mengapa ini penting:** Dengan menyesuaikan `fractions` Anda mengontrol seberapa cepat warna bertransisi, memungkinkan efek yang halus atau dramatis.

### Langkah 3: buat radial gradient paint
`RadialGradientPaint` adalah kelas inti yang menggambarkan gradien warna radial, termasuk titik pusat, radius, titik fokus, fraksi, warna, metode siklus, dan ruang warna. Sekarang kami membangun objek `RadialGradientPaint` menggunakan array yang telah didefinisikan di atas.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Catatan:** `transform` dapat `null` jika Anda tidak memerlukan skala atau rotasi tambahan. Silakan bereksperimen dengan `AffineTransform` untuk gradien miring.

### Langkah 4: set paint dan isi persegi panjang
Setelah paint siap, kami memberi tahu `PsDocument` untuk menggunakannya dan kemudian mengisi persegi panjang yang telah didefinisikan sebelumnya.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Pada titik ini halaman PostScript berisi persegi panjang yang terisi mulus dengan gradien radial yang telah kami konfigurasikan.

### Langkah 5: tutup dan simpan dokumen
Akhirnya, tutup halaman saat ini dan tulis file ke disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Buka `RadialGradient1_outPS.ps` di penampil PostScript apa pun (mis., Ghostscript) dan Anda akan melihat gradien dirender persis seperti yang didefinisikan.

## Masalah umum & solusi
| Gejala | Penyebab kemungkinan | Perbaikan |
|---------|--------------|-----|
| Gradien muncul sebagai warna solid | array fractions tidak dimulai pada `0.0f` atau berakhir pada `1.0f` | Pastikan fraksi pertama `0.0f` dan yang terakhir `1.0f`. |
| Warna tampak pudar | Menggunakan `ColorSpaceType` yang salah | Ganti ke `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` untuk output yang lebih hidup. |
| Tidak ada file output yang dihasilkan | Path `FileOutputStream` tidak valid atau tidak dapat ditulisi | Verifikasi `dataDir` ada dan aplikasi memiliki izin menulis. |

## Pertanyaan yang sering diajukan

**T: Apakah saya dapat menggunakan Aspose.Page untuk Java dalam proyek komersial?**  
J: Ya. Lisensi komersial diperlukan untuk penggunaan produksi. Anda dapat membeli satu dari [halaman lisensi Aspose](https://purchase.aspose.com/buy).

**T: Di mana saya dapat menemukan referensi API resmi?**  
J: Dokumentasi lengkap tersedia di [referensi API Aspose.Page Java](https://reference.aspose.com/page/java/).

**T: Apakah tersedia trial gratis untuk pengujian?**  
J: Tentu saja. Unduh versi percobaan dari [halaman rilis Aspose.Page](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk evaluasi?**  
J: Lisensi sementara dapat diminta melalui [halaman permintaan lisensi sementara](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat mendapatkan dukungan komunitas?**  
J: Bergabunglah dengan [forum komunitas Aspose.Page](https://forum.aspose.com/c/page/39).

## Kesimpulan
Anda kini tahu **cara membuat gradien radial** dalam dokumen Java PostScript menggunakan Aspose.Page. Dengan menyesuaikan ukuran persegi panjang, warna berhenti, dan radius gradien, Anda dapat menciptakan tak terhitung efek visual—dari latar belakang halus hingga grafik sorotan tebal. Jangan ragu bereksperimen dengan nilai `AffineTransform` yang berbeda untuk memutar atau memiringkan gradien, dan gabungkan teknik ini dengan teks serta gambar untuk output PDF atau EPS yang lebih kaya.

---

**Terakhir Diperbarui:** 2026-09-09  
**Diuji Dengan:** Aspose.Page for Java terbaru (pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Isi Bentuk dengan Gradien: Contoh Radial Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Buat Gradien PostScript di Java – Tambahkan Gradien Vertikal](/page/java/postscript-gradient-addition/vertical/)
- [Tutorial Transparansi Aspose.Page – Tambahkan Transparansi di Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
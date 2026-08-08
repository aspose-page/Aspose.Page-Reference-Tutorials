---
date: 2026-05-05
description: Pelajari cara menambahkan pola ubin tekstur ke dokumen PostScript dengan
  Aspose.Page untuk Java. Panduan ini menunjukkan cara menambahkan tekstur secara
  efisien dan menjelajahi kemungkinan kreatif.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Tambahkan Pola Ulang Tekstur di Java PostScript
second_title: Aspose.Page Java API
title: Cara Menambahkan Pola Ulang Tekstur di Java PostScript
url: /id/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Pola Ubin Tekstur di Java PostScript

## Pendahuluan
Dalam dunia pengembangan Java, mempelajari **cara menambahkan tekstur** ke dokumen PostScript adalah kebutuhan umum. Aspose.Page for Java membuat tugas ini sederhana, memungkinkan Anda fokus pada desain daripada sintaks PostScript tingkat rendah. Dalam tutorial ini, kami akan membimbing Anda melalui setiap langkah yang diperlukan untuk menambahkan pola ubin tekstur, mengisi bentuk, dan bahkan memberi tekstur pada teks dalam dokumen Java PostScript.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page for Java  
- **Kata kunci utama apa yang ditargetkan panduan ini?** *cara menambahkan tekstur*  
- **Apakah saya memerlukan lisensi untuk pengujian?** Tersedia percobaan gratis; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya menggunakan kembali kuas tekstur untuk beberapa bentuk?** Ya – buat `TexturePaint` sekali dan terapkan pada bentuk apa pun.  
- **Bagaimana cara mengisi persegi panjang dengan tekstur?** Gunakan `document.fill(shape)` setelah mengatur `TexturePaint` sebagai cat saat ini.

## Apa itu pola ubin tekstur?
Pola ubin tekstur mengulang gambar kecil (ubin) di seluruh area yang lebih besar, memungkinkan Anda **mengisi bentuk dengan tekstur** tanpa harus menggambar setiap ubin secara manual. Teknik ini ideal untuk latar belakang, isian, dan efek teks dekoratif dalam PostScript.

## Mengapa menggunakan Aspose.Page untuk Java?
- **Rendering tanpa ketergantungan** – tidak perlu interpreter PostScript eksternal.  
- **Kontrol penuh atas grafis** – gabungkan bentuk vektor, teks, dan tekstur bitmap.  
- **Cross‑platform** – bekerja pada sistem operasi apa pun yang mendukung Java.  

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang bahasa pemrograman Java.  
- Familiaritas dengan struktur dokumen PostScript.  
- Perpustakaan Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/page/java/).

## Impor Paket
Mulailah dengan mengimpor paket yang diperlukan untuk proyek Java Anda:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cara Menambahkan Pola Ubin Tekstur di Java PostScript
Berikut adalah panduan langkah demi langkah. Setiap langkah mencakup penjelasan singkat diikuti oleh kode tepat yang perlu Anda salin.

### Langkah 1: Buat Dokumen PostScript
Mulailah dengan membuat dokumen PostScript baru, menentukan aliran output dan opsi penyimpanan. Pastikan Anda telah mengonfigurasi jalur yang diperlukan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Langkah 2: Siapkan Lingkungan Grafik
Terjemahkan (geser) asal ke lokasi yang nyaman dan muat bitmap yang akan menjadi ubin tekstur.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### Langkah 3: Buat Kuas Tekstur
Definisikan `TexturePaint` yang mengulang bitmap di seluruh area bentuk. Sesuaikan ukuran persegi panjang jika Anda ingin ubin terlihat lebih besar atau lebih kecil.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### Langkah 4: Gambar dan Isi Bentuk
Buat persegi panjang dan **isi persegi panjang dengan tekstur** menggunakan kuas. Kemudian beri garis tepi pada bentuk agar hasilnya terlihat berbeda secara visual.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### Langkah 5: Tambahkan Teks dengan Pola Tekstur
Anda juga dapat menerapkan tekstur yang sama pada glif teks. Ini menunjukkan **cara mengisi tekstur** pada karakter sambil tetap dapat memberi garis pada mereka.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### Langkah 6: Simpan dan Tutup
Akhirnya, tutup halaman, simpan dokumen, dan bebaskan sumber daya.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Masalah Umum & Tips
- **File tekstur tidak ditemukan** – Verifikasi jalur ke `TestTexture.bmp` sudah benar dan file dapat diakses.  
- **Dimensi gambar tidak tepat** – Jika tekstur tampak terdistorsi, sesuaikan `imageArea` agar cocok dengan ukuran gambar asli.  
- **Kinerja** – Gunakan kembali instance `TexturePaint` yang sama untuk beberapa bentuk guna menghindari pembuatan objek yang tidak perlu.  
- **Tips pro:** Gunakan bitmap beresolusi tinggi untuk ubin agar tekstur tetap tajam saat diperbesar.  

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Page untuk Java cocok untuk pemula?**  
A: Tentu saja! Aspose.Page untuk Java menyediakan dokumentasi lengkap, membuatnya dapat diakses oleh pengembang dengan semua tingkat keahlian.

**Q: Bisakah saya mengintegrasikan Aspose.Page untuk Java ke dalam proyek Java saya yang sudah ada?**  
A: Ya, Anda dapat dengan mudah mengintegrasikan Aspose.Page untuk Java ke dalam proyek Anda dengan mengikuti dokumentasi yang disediakan [di sini](https://reference.aspose.com/page/java/).

**Q: Di mana saya dapat menemukan dukungan atau berdiskusi tentang pertanyaan terkait Aspose.Page?**  
A: Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk berinteraksi dengan komunitas dan mencari bantuan.

**Q: Apakah ada percobaan gratis untuk Aspose.Page untuk Java?**  
A: Ya, Anda dapat menjelajahi percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
A: Kunjungi [tautan ini](https://purchase.aspose.com/temporary-license/) untuk mendapatkan lisensi sementara.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari **cara menambahkan tekstur** pola ubin ke dokumen Java PostScript menggunakan Aspose.Page untuk Java. Silakan bereksperimen dengan ubin bitmap yang berbeda, faktor skala, dan operasi komposit untuk memanfaatkan potensi kreatif penuh dari isian tekstur.

---

**Terakhir Diperbarui:** 2026-05-05  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest)  
**Penulis:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
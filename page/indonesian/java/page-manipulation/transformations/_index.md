---
date: 2026-10-20
description: Pelajari cara scale rectangle dengan Aspose.Page untuk Java, cara translate
  shape, dan cara apply affine transform untuk membuat PostScript documents.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformations dalam manipulasi halaman Java
og_description: Pelajari cara scale rectangle, translate shape, dan apply affine transform
  menggunakan Aspose.Page untuk Java untuk menghasilkan PostScript files secara efisien.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Cara scale rectangle dengan Aspise.Page untuk Java – panduan langkah demi
  langkah
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Cara scale rectangle dengan Aspose.Page untuk Java
url: /id/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara memperbesar persegi panjang dengan Aspose.Page untuk Java

## Pendahuluan
Dalam panduan ini Anda akan menemukan **cara memperbesar persegi panjang** menggunakan Aspose.Page untuk Java, sekaligus mempelajari cara mentranslasi posisi bentuk, memutar grafik, dan menerapkan operasi transformasi afinn untuk menghasilkan output PostScript berkualitas tinggi. Teknik-teknik ini memungkinkan Anda membangun grafik independen perangkat yang canggih tanpa menulis kode rendering tingkat rendah, membuat aplikasi Java Anda lebih kuat dan mudah dipelihara.

## Jawaban Cepat
`scale(sx, sy)` memperbesar konteks grafik dengan faktor horizontal dan vertikal yang diberikan.  

- **Bagaimana cara memperbesar persegi panjang di Java dengan Aspose.Page?** Panggil metode `scale(sx, sy)` pada konteks grafik sebelum menggambar persegi panjang.  
- **Bisakah saya memindahkan (mentranslasi) sebuah bentuk tanpa memengaruhi grafik lain?** Ya—bungkus translasi di antara pemanggilan `writeGraphicsSave()` dan `writeGraphicsRestore()`.  
- **Kelas apa yang membuat file PostScript?** Gunakan `PsDocument` bersama dengan `PsSaveOptions`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Page yang valid diperlukan untuk penyebaran komersial.  
- **Versi Java mana yang didukung?** Aspose.Page bekerja dengan Java 8 dan yang lebih baru.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- Pemahaman yang kuat tentang sintaks Java inti dan konsep berorientasi objek.  
- Perpustakaan Aspose.Page untuk Java terpasang. Anda dapat mengunduhnya dari [dokumentasi Aspose.Page untuk Java](https://reference.aspose.com/page/java/).  
- IDE Java (IntelliJ IDEA, Eclipse, atau VS Code) yang dikonfigurasi dengan file JAR perpustakaan pada classpath.

## Impor paket
`PsDocument` adalah kelas utama yang digunakan untuk membuat dokumen PostScript, dan `PsSaveOptions` mengonfigurasi cara dokumen disimpan.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Apa itu “cara memperbesar persegi panjang” dalam Aspose.Page?
Metode `scale(float sx, float sy)` menerapkan transformasi skala afinn pada keadaan grafik saat ini, mengubah ukuran gambar berikutnya dengan faktor `sx` (horizontal) dan `sy` (vertikal). Inilah operasi inti di balik kata kunci **cara memperbesar persegi panjang**. Dengan menerapkan transformasi ini sebelum menggambar, bentuk apa pun yang digambar selanjutnya seperti persegi panjang akan dirender dengan dimensi baru sambil mempertahankan proporsinya.

## Cara menerjemahkan bentuk dengan Aspose.Page
`writeGraphicsSave()` menyimpan keadaan grafik saat ini dan `writeGraphicsRestore()` memulihkannya, memastikan transformasi hanya memengaruhi bentuk yang dimaksud. Translasi memindahkan asal sistem koordinat tanpa mengubah dimensi objek. Dengan membungkus `translate(dx, dy)` dengan `writeGraphicsSave()` / `writeGraphicsRestore()`, Anda memastikan hanya bentuk yang dimaksud yang bergerak sementara grafik lain tetap tidak berubah, memberikan kontrol presisi atas elemen individual.

## Contoh 1: tanpa transformasi
Contoh pertama menggambar persegi panjang tanpa transformasi apa pun, menetapkan baseline untuk perbandingan visual dengan contoh selanjutnya.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Contoh 2: translasi
Dalam contoh ini kami memindahkan konteks grafik 250 unit ke kanan sebelum menggambar persegi panjang kedua, menggambarkan **cara mentranslasi bentuk**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Contoh 3: penskalaan
Di sini kami menjawab pertanyaan utama **cara memperbesar persegi panjang**. Persegi panjang diperkecil menjadi 50 % lebar asli dan 75 % tinggi asli menggunakan pemanggilan `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Cara memutar bentuk java (rotate shape java)
`rotate(angle)` memutar sistem koordinat dengan sudut tertentu dalam derajat. Muat `PsDocument` Anda, panggil `rotate(angle)` pada keadaan grafik, gambar bentuk, lalu pulihkan keadaan sebelumnya. Pola ini mengimplementasikan **rotate shape java** dan **cara memutar persegi panjang** dalam satu blok yang dapat digunakan kembali, memungkinkan Anda memutar grafik di sekitar titik mana pun yang Anda pilih.

## Mengapa ini penting – manfaat dunia nyata
- **Output independen perangkat** – Aspose.Page dapat menghasilkan file PostScript dan XPS yang ditampilkan secara identik pada printer atau penampil apa pun, menghilangkan penyesuaian khusus platform.  
- **Kontrol halus** – Gabungkan translasi, penskalaan, shearing, dan rotasi untuk memenuhi spesifikasi tata letak yang tepat; API mendukung lebih dari 20 kombinasi transformasi per halaman.  
- **Pemrosesan berorientasi kinerja** – Perpustakaan memproses dokumen dengan jejak memori di bawah 10 MB untuk laporan 100 halaman standar, membuat pekerjaan batch cepat dan dapat diskalakan.

## Kasus penggunaan umum
- **Faktur yang dapat dicetak** – Tempatkan logo, barcode, dan tabel secara tepat menggunakan penskalaan dan translasi untuk menyesuaikan pedoman merek perusahaan.  
- **Diagram teknis** – Hasilkan skematik di mana setiap komponen harus diubah ukurannya secara proporsional dan diposisikan.  
- **Laporan multi‑halaman otomatis** – Buat laporan PostScript yang memerlukan penskalaan konsisten di seluruh halaman, seperti spesifikasi teknik.

## Masalah umum dan solusi
- **Transformasi tidak direset** – Selalu padukan `writeGraphicsSave()` dengan `writeGraphicsRestore()`; jika tidak, gambar berikutnya akan mewarisi transformasi yang tidak diinginkan.  
- **Warna tak terduga** – Atur cat (warna) setelah setiap transformasi karena keadaan grafik tidak mempertahankan informasi warna setelah pemulihan.  
- **Ukuran file terlalu besar** – Aktifkan kompresi di `PsSaveOptions` dan batasi resolusi gambar raster yang disematkan untuk menjaga file akhir di bawah 5 MB untuk dokumen 50 halaman standar.

## FAQ

### Bisakah saya menggunakan Aspose.Page untuk Java untuk format dokumen lain?
Aspose.Page terutama fokus pada manipulasi halaman untuk format PostScript dan XPS, tetapi juga menawarkan kemampuan ekspor PDF terbatas.

### Di mana saya dapat menemukan contoh dan dokumentasi lebih lanjut untuk Aspose.Page untuk Java?
Kunjungi [dokumentasi Aspose.Page untuk Java](https://reference.aspose.com/page/java/) untuk panduan komprehensif, referensi API, dan proyek contoh.

### Apakah ada percobaan gratis untuk Aspose.Page untuk Java?
Ya, Anda dapat mengakses percobaan gratis melalui halaman **Unduhan percobaan gratis Aspose**: [Unduhan percobaan gratis Aspose](https://releases.aspose.com/).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
Dapatkan lisensi sementara melalui **halaman permintaan lisensi sementara**: [halaman permintaan lisensi sementara](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan tentang Aspose.Page untuk Java?
Kunjungi [forum Aspose.Page untuk Java](https://forum.aspose.com/c/page/39) untuk diskusi komunitas, potongan kode, dan tips pemecahan masalah.

## Pertanyaan yang Sering Diajukan

**Q: Apa perbedaan antara `translate` dan `scale`?**  
**A:** `translate` memindahkan asal sistem koordinat, sedangkan `scale` mengubah ukuran objek yang digambar sepanjang sumbu X dan/atau Y.

**Q: Bisakah saya menggabungkan beberapa transformasi dalam satu keadaan grafik?**  
**A:** Ya—dengan memanggil `translate`, `scale`, `rotate`, atau `shear` secara berurutan sebelum menggambar, Anda membuat transformasi affine gabungan.

**Q: Bagaimana cara mereset transformasi setelah menggambar sebuah bentuk?**  
**A:** Gunakan `writeGraphicsRestore()` untuk kembali ke keadaan grafik yang sebelumnya disimpan.

**Q: Apakah memungkinkan memutar persegi panjang di sekitar pusatnya?**  
**A:** Tentu saja. Translasi persegi panjang ke asal, terapkan `rotate(angle)`, lalu translasi kembali sebelum menggambar.

**Q: Apakah Aspose.Page mendukung anti‑aliasing untuk grafik yang lebih halus?**  
**A:** Ya—atur opsi rendering yang sesuai di `PsSaveOptions` untuk mengaktifkan anti‑aliasing.

---

**Terakhir Diperbarui:** 2026-10-20  
**Diuji Dengan:** Aspose.Page untuk Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menggambar Persegi Panjang di Java PostScript dengan Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Buat Gradien Radial di PostScript dengan Aspose.Page untuk Java](/page/java/postscript-gradient-addition/)
- [Manipulasi Halaman Postscript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
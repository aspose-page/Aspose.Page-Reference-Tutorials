---
date: 2026-05-25
description: Pelajari cara menambahkan gradient ke dokumen XPS dalam Java menggunakan
  Aspose.Page. Panduan langkah‑demi‑langkah ini menunjukkan cara menambahkan gradient
  diagonal, menerapkan linear gradient brushes, dan menghasilkan file XPS profesional.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Tambahkan Gradient Diagonal di Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Cara Menambahkan Gradient: Gradient Diagonal di Java XPS'
url: /id/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien: Gradien Diagonal di Java XPS

## Pendahuluan
Dalam pengembangan Java modern, menguasai **cara menambahkan gradien** ke dokumen XPS memberikan laporan Anda tampilan yang halus dan menarik perhatian. Tutorial ini memandu Anda membuat file XPS dari awal, menambahkan gradien diagonal, dan menyimpan hasilnya—semua dengan Aspose.Page untuk Java. Anda akan memahami mengapa gradien penting, melihat panggilan API yang tepat, dan mendapatkan tips praktis untuk menghindari jebakan umum.

## Jawaban Cepat
- **Apa perpustakaan utama?** Aspose.Page for Java  
- **Metode mana yang menambahkan gradien?** `createLinearGradientBrush` dengan gradient stops  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk gradien diagonal dasar  
- **Bisakah saya menggunakan ini dengan kerangka kerja Java lain?** Ya, API ini tidak bergantung pada kerangka kerja  

## Apa itu gradien diagonal dalam dokumen XPS?
Gradien diagonal adalah transisi warna halus yang berjalan dari satu sudut bentuk ke sudut berlawanan, menciptakan efek visual miring. Dalam XPS, efek ini didefinisikan oleh kuas gradien linear yang berisi gradient stops berurutan yang menentukan warna dan posisi relatif sepanjang garis diagonal.

## Mengapa menambahkan gradien diagonal dengan Aspose.Page?
Aspose.Page memberikan **ketelitian rendering 100 %** untuk gradien di lebih dari 20 penampil XPS, dan mendukung **lebih dari 30 fitur XPS** seperti teks, gambar, dan bentuk vektor. API ini menyederhanakan markup XPS yang kompleks, memungkinkan Anda fokus pada desain sambil menjamin bahwa file yang sama terlihat identik di platform Windows, macOS, dan Linux.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- JDK terpasang di mesin Anda.  
- Aspose.Page for Java library – unduh **[di sini](https://releases.aspose.com/page/java/)**.  
- IDE seperti IntelliJ IDEA atau Eclipse.

## Impor Paket
Mulailah dengan mengimpor kelas-kelas yang Anda perlukan. Impor ini memberi Anda akses ke geometri, penanganan gradien, dan pembuatan dokumen XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru di IDE pilihan Anda dan tambahkan file JAR Aspose.Page ke jalur build proyek.

## Langkah 2: Tentukan Direktori Dokumen
Tentukan lokasi di mana file XPS yang dihasilkan akan disimpan.

```java
String dataDir = "Your Document Directory";
```

## Langkah 3: Buat Dokumen XPS
`XpsDocument` adalah objek inti yang mewakili file XPS dalam memori. Menginstansiasikannya memberi Anda kanvas untuk menambahkan halaman, bentuk, dan kuas.

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 4: Tambahkan Jalur Gradien Diagonal
Buat jalur persegi panjang yang akan menerima gradien. Geometri jalur menggunakan perintah sederhana move‑line‑close. XpsPath mendefinisikan bentuk vektor dalam dokumen XPS, seperti persegi panjang atau geometri khusus.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Langkah 5: Definisikan Stop Gradien Linear
Atur warna dan posisinya. Setiap stop mendefinisikan titik dalam gradien di mana warna tertentu muncul. XpsGradientStop mewakili satu stop warna dalam gradien, menentukan warna dan offset-nya.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Langkah 6: Terapkan Gradien Linear ke Jalur
`XpsLinearGradientBrush` adalah tipe kuas Aspose.Page untuk transisi warna linear. Ia mengambil dua titik yang menentukan arah gradien dan kumpulan gradient stops yang menentukan warna sepanjang garis tersebut.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Langkah 7: Simpan Dokumen
Simpan file XPS ke disk. File tersebut akan berisi persegi panjang yang diisi dengan gradien diagonal yang Anda definisikan.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Cara menambahkan gradien di Java XPS?
Muat XpsDocument, buat `XpsLinearGradientBrush` dengan titik awal `(0,0)` dan titik akhir `(width,height)`, lampirkan gradient stops, tetapkan kuas ke properti `Fill` bentuk, dan akhirnya panggil `save`. Alur singkat ini memungkinkan Anda menyematkan gradien diagonal hanya dengan beberapa panggilan API, menjaga kode tetap bersih dan mudah dipelihara.

## Kesulitan Umum & Tips
- **Arah gradien** – pastikan titik awal dan akhir kuas mencerminkan diagonal yang diinginkan; menukar keduanya membalikkan gradien.  
- **Presisi warna** – Aspose menggunakan ARGB; sertakan kanal alpha jika Anda membutuhkan transparansi.  
- **Path file** – selalu gunakan path absolut atau pastikan path relatif mengarah ke direktori yang dapat ditulisi.

## FAQ Tambahan

**Q: Bagaimana cara **menambahkan gradien** ke bentuk XPS yang sudah ada?**  
A: Buat `XpsLinearGradientBrush`, definisikan gradient stops, dan tetapkan ke properti `Fill` bentuk seperti yang ditunjukkan pada Langkah 6.

**Q: Apa yang sebenarnya dilakukan **apply linear gradient** di balik layar?**  
A: Ia menghasilkan definisi kuas dalam paket XPS yang merujuk pada titik awal/akhir dan kumpulan gradient stops, yang kemudian dirender oleh penampil sebagai transisi warna halus.

**Q: Apakah ada cara cepat untuk **menggunakan aspose** pada fitur XPS lainnya?**  
A: Ya, API Aspose.Page mencakup metode untuk menambahkan gambar, teks, dan bentuk khusus—cukup jelajahi kelas `XpsDocument` untuk bantuan tambahan.

**Q: Bisakah saya **menambahkan jalur gradien** ke bentuk non‑persegi panjang?**  
A: Tentu saja. Definisikan geometri apa pun menggunakan `createPathGeometry` lalu atur `Fill`-nya ke kuas gradien.

**Q: Apakah gradien memengaruhi ukuran file secara signifikan?**  
A: Hanya sedikit; definisi gradien adalah entri XML ringan dalam paket XPS.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutorial Terkait

- [Penambahan Gradien XPS Aspose Page](/page/java/xps-gradient-addition/)
- [Penambahan Teks XPS Java - Tutorial Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Cara Menambahkan Gambar ke Dokumen XPS Java – Panduan Sederhana dengan Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
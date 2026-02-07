---
date: 2026-02-07
description: Pelajari cara memperbesar persegi panjang dengan Aspose.Page untuk Java,
  cara memindahkan bentuk, dan menerapkan transformasi afinn untuk membuat dokumen
  PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cara Menskalakan Persegi Panjang dengan Aspose.Page untuk Java
url: /id/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menskalakan Persegi Panjang dengan Aspose.Page untuk Java

## Pendahuluan
Selamat datang di panduan komprehensif tentang memanfaatkan fitur kuat **Aspose.Page for Java** untuk melakukan berbagai transformasi halaman. Dalam tutorial ini Anda akan belajar **how to scale rectangle**, menerjemahkan bentuk, memutar objek, dan **apply affine transform** teknik sambil membuat **PostScript document**. Kemampuan ini memungkinkan Anda membangun aplikasi Java yang kaya grafis tanpa harus menangani kode rendering tingkat rendah.

## Jawaban Cepat
- **How do I scale a rectangle in Java with Aspose.Page?** Gunakan metode `document.scale()` sebelum menggambar bentuk.  
- **Can I move (translate) a shape without affecting other graphics?** Ya—simpan keadaan grafik, panggil `document.translate(x, y)`, gambar, lalu pulihkan keadaan.  
- **What class creates a PostScript file?** `PsDocument` bersama dengan `PsSaveOptions`.  
- **Do I need a license for production use?** Lisensi Aspose.Page yang valid diperlukan untuk penyebaran komersial.  
- **Which Java version is supported?** Aspose.Page bekerja dengan Java 8 dan yang lebih baru.

## Prasyarat
Sebelum kita menyelam ke panduan langkah‑demi‑langkah, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang pemrograman Java.  
- Perpustakaan Aspose.Page for Java terpasang. Anda dapat mengunduhnya dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Integrated Development Environment (IDE) Java yang terpasang di mesin Anda.

## Impor Paket
Dalam proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Apa itu “how to scale rectangle” dalam Aspose.Page?
Menskalakan persegi panjang mengubah ukurannya sepanjang sumbu X dan Y sambil mempertahankan bentuknya. Aspose.Page menyediakan metode `scale(float sx, float sy)`, yang menerapkan **affine transform** pada keadaan grafik saat ini. Ini adalah teknik inti di balik kata kunci **how to scale rectangle**.

## Cara Menerjemahkan Bentuk dengan Aspose.Page
Translasi memindahkan bentuk ke lokasi baru tanpa mengubah dimensinya. Ini adalah inti dari **how to translate shape**. Dengan menyimpan keadaan grafik, menerapkan `translate(dx, dy)`, menggambar, dan kemudian memulihkan keadaan, Anda menjaga objek lain tetap tidak terpengaruh.

## Contoh 1: Tanpa Transformasi
Contoh pertama menggambar persegi panjang sederhana tanpa transformasi yang diterapkan. Ini berfungsi sebagai dasar untuk perbandingan dengan contoh selanjutnya.

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

## Contoh 2: Translasi
Di sini kami mendemonstrasikan **how to translate shape** dengan memindahkan konteks grafik 250 unit ke kanan sebelum menggambar persegi panjang kedua.

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

## Contoh 3: Menskalakan
Contoh ini menjawab pertanyaan utama **how to scale rectangle**. Kami memperkecil persegi panjang menjadi 50 % dari lebar aslinya dan 75 % dari tingginya.

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

## Cara Memutar Bentuk Java (rotate shape java)
Rotasi adalah operasi affine umum lainnya. Meskipun potongan kode untuk rotasi dihilangkan demi kepraktisan, pola tersebut identik: simpan keadaan grafik, panggil `document.rotate(angle)`, gambar bentuk, lalu pulihkan. Ini mendemonstrasikan **rotate shape java** dan **how to rotate rectangle** dalam praktik.

## Mengapa Ini Penting – Manfaat di Dunia Nyata
- **Device‑independent output** – Tulis sekali dan hasilkan PostScript atau XPS tanpa penyesuaian khusus platform.  
- **Fine‑grained control** – Gabungkan translasi, skala, shear, dan rotasi untuk memenuhi persyaratan tata letak yang tepat.  
- **Performance‑oriented** – API dengan overhead rendah ideal untuk pemrosesan batch dokumen berskala besar.  

## Kasus Penggunaan Umum
- Membuat faktur yang dapat dicetak – misalnya, solusi **printable invoice java** yang menempatkan logo dan kode batang secara tepat.  
- Membuat diagram teknis di mana skala dan posisi yang tepat diperlukan.  
- Mengotomatiskan produksi laporan multi‑halaman dalam format PostScript.  

## Masalah Umum dan Solusinya
- **Transformation not resetting** – Selalu pasangkan `document.writeGraphicsSave()` dengan `document.writeGraphicsRestore()` untuk menghindari efek carry‑over yang tidak diinginkan.  
- **Unexpected colors** – Pastikan Anda mengatur cat setelah setiap transformasi; keadaan grafik tidak menyimpan pengaturan warna sebelumnya setelah pemulihan.  
- **File size too large** – Gunakan `PsSaveOptions` untuk mengaktifkan kompresi atau mengurangi resolusi gambar saat menyematkan grafik raster.  

## FAQ
### Can I use Aspose.Page for Java for other document formats?
Aspose.Page terutama fokus pada manipulasi halaman untuk format PostScript dan XPS.

### Where can I find more examples and documentation for Aspose.Page for Java?
Kunjungi [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) untuk informasi lengkap.

### Is there a free trial available for Aspose.Page for Java?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

### How can I get a temporary license for Aspose.Page for Java?
Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Where can I seek community support or ask questions about Aspose.Page for Java?
Kunjungi [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) untuk diskusi komunitas.

## Pertanyaan yang Sering Diajukan

**Q: Apa perbedaan antara `translate` dan `scale`?**  
A: `translate` memindahkan asal sistem koordinat, sementara `scale` mengubah ukuran objek yang digambar sepanjang sumbu X dan/atau Y.

**Q: Bisakah saya menggabungkan beberapa transformasi dalam satu keadaan grafik?**  
A: Ya—dengan memanggil `translate`, `scale`, `rotate`, atau `shear` secara berurutan sebelum menggambar, Anda membuat transformasi affine gabungan.

**Q: Bagaimana cara mereset transformasi setelah menggambar sebuah bentuk?**  
A: Gunakan `document.writeGraphicsRestore()` untuk kembali ke keadaan grafik yang sebelumnya disimpan.

**Q: Apakah mungkin memutar persegi panjang di sekitar pusatnya?**  
A: Tentu saja. Translasi persegi panjang ke asal, terapkan `rotate(angle)`, lalu translasi kembali sebelum menggambar.

**Q: Apakah Aspose.Page mendukung anti‑aliasing untuk grafik yang lebih halus?**  
A: Ya—atur opsi rendering yang sesuai dalam `PsSaveOptions` untuk mengaktifkan anti‑aliasing.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
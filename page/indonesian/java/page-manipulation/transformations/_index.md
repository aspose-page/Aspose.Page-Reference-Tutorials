---
date: 2025-12-07
description: Pelajari cara mengubah skala persegi panjang, mentranslasi bentuk, dan
  menerapkan transformasi afine dalam Java menggunakan Aspose.Page untuk membuat dokumen
  PostScript.
language: id
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cara Menskalakan Persegi Panjang dan Menerapkan Transformasi dengan Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menskalakan Persegi Panjang dan Menerapkan Transformasi dengan Aspose.Page

## Pendahuluan
Selamat datang di panduan komprehensif tentang memanfaatkan fitur kuat **Aspose.Page for Java** untuk melakukan berbagai transformasi halaman. Dalam tutorial ini Anda akan belajar **cara menskalakan persegi panjang**, memindahkan (mentranslate) bentuk, memutar objek, dan **menerapkan transformasi afinn** saat membuat **dokumen PostScript**. Kemampuan ini memungkinkan Anda membangun aplikasi Java yang kaya grafis tanpa harus menulis kode rendering tingkat rendah.

## Jawaban Cepat
- **Bagaimana cara menskalakan persegi panjang di Java dengan Aspose.Page?** Gunakan metode `document.scale()` sebelum menggambar bentuk.  
- **Bisakah saya memindahkan (mentranslate) sebuah bentuk tanpa memengaruhi grafik lain?** Ya—simpan keadaan grafik, panggil `document.translate(x, y)`, gambar, lalu pulihkan keadaan.  
- **Kelas apa yang membuat file PostScript?** `PsDocument` bersama dengan `PsSaveOptions`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Page yang valid diperlukan untuk penyebaran komersial.  
- **Versi Java mana yang didukung?** Aspose.Page bekerja dengan Java 8 ke atas.

## Prasyarat
Sebelum kita masuk ke panduan langkah demi langkah, pastikan Anda telah menyiapkan prasyarat berikut:

- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Page for Java terpasang. Anda dapat mengunduhnya dari [dokumentasi Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Lingkungan Pengembangan Terintegrasi (IDE) Java yang sudah terkonfigurasi di mesin Anda.

## Impor Paket
Di proyek Java Anda, impor paket yang diperlukan untuk menggunakan Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Apa itu “cara menskalakan persegi panjang” di Aspose.Page?
Menskalakan persegi panjang mengubah ukurannya sepanjang sumbu X dan Y sambil mempertahankan bentuknya. Aspose.Page menyediakan metode `scale(float sx, float sy)`, yang menerapkan **transformasi afinn** pada keadaan grafik saat ini. Inilah teknik inti di balik kata kunci **cara menskalakan persegi panjang**.

## Cara Mentranslate Bentuk dengan Aspose.Page
Translasi memindahkan sebuah bentuk ke lokasi baru tanpa mengubah dimensinya. Inilah esensi dari **cara mentranslate bentuk**. Dengan menyimpan keadaan grafik, menerapkan `translate(dx, dy)`, menggambar, dan kemudian memulihkan keadaan, Anda menjaga objek lain tetap tidak terpengaruh.

## Contoh 1: Tanpa Transformasi
Contoh pertama menggambar persegi panjang sederhana tanpa transformasi apa pun. Ini berfungsi sebagai dasar perbandingan dengan contoh‑contoh selanjutnya.

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
Di sini kami mendemonstrasikan **cara mentranslate bentuk** dengan memindahkan konteks grafik 250 unit ke kanan sebelum menggambar persegi panjang kedua.

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

## Contoh 3: Skalasi
Contoh ini menjawab pertanyaan utama **cara menskalakan persegi panjang**. Kami memperkecil persegi panjang menjadi 50 % lebar asli dan 75 % tinggi aslinya.

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

## Cara Memutar Bentuk di Java (rotate shape java)
Rotasi adalah operasi afinn lain yang umum. Meskipun potongan kode untuk rotasi dihilangkan demi kepraktisan, pola kerjanya identik: simpan keadaan grafik, panggil `document.rotate(angle)`, gambar bentuk, lalu pulihkan. Ini memperlihatkan **rotate shape java** dan **cara memutar persegi panjang** dalam praktik.

## Mengapa Menggunakan Aspose.Page untuk Transformasi Ini?
- **Tidak bergantung pada perangkat**: Tulis sekali, hasilkan PostScript atau XPS tanpa kode khusus platform.  
- **Kontrol halus**: Akses langsung ke keadaan grafik memungkinkan Anda menggabungkan translasi, skalasi, shearing, dan rotasi.  
- **Kinerja**: API berbiaya rendah cocok untuk pemrosesan batch dokumen besar.  

## Kasus Penggunaan Umum
- Menghasilkan faktur cetak dengan barcode dan logo yang dinamis.  
- Membuat diagram teknis di mana skalasi dan penempatan yang tepat diperlukan.  
- Mengotomatiskan produksi laporan multi‑halaman dalam format PostScript.

## Kesimpulan
Dalam tutorial ini, kami mengeksplorasi berbagai transformasi dalam Manipulasi Halaman Java menggunakan Aspose.Page for Java, dengan fokus pada **cara menskalakan persegi panjang**, **cara mentranslate bentuk**, dan operasi afinn lainnya. Dengan mengikuti contoh‑contoh ini, Anda dapat meningkatkan aplikasi Java Anda dengan kemampuan manipulasi halaman tingkat lanjut dan **membuat output dokumen PostScript** yang memenuhi standar penerbitan profesional.

## FAQ
### Bisakah saya menggunakan Aspose.Page for Java untuk format dokumen lain?
Aspose.Page terutama berfokus pada manipulasi halaman untuk format PostScript dan XPS.

### Di mana saya dapat menemukan contoh dan dokumentasi lebih lanjut untuk Aspose.Page for Java?
Kunjungi [dokumentasi Aspose.Page for Java](https://reference.aspose.com/page/java/) untuk informasi lengkap.

### Apakah ada percobaan gratis untuk Aspose.Page for Java?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page for Java?
Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat mencari dukungan komunitas atau mengajukan pertanyaan tentang Aspose.Page for Java?
Kunjungi [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) untuk diskusi komunitas.

## Pertanyaan yang Sering Diajukan

**T: Apa perbedaan antara `translate` dan `scale`?**  
J: `translate` memindahkan asal sistem koordinat, sedangkan `scale` mengubah ukuran objek yang digambar sepanjang sumbu X dan/atau Y.

**T: Bisakah saya menggabungkan beberapa transformasi dalam satu keadaan grafik?**  
J: Ya—dengan memanggil `translate`, `scale`, `rotate`, atau `shear` secara berurutan sebelum menggambar, Anda menciptakan transformasi afinn gabungan.

**T: Bagaimana cara mengatur ulang transformasi setelah menggambar sebuah bentuk?**  
J: Gunakan `document.writeGraphicsRestore()` untuk kembali ke keadaan grafik yang sebelumnya disimpan.

**T: Apakah memungkinkan memutar persegi panjang di sekitar pusatnya?**  
J: Tentu saja. Translasi persegi panjang ke asal, terapkan `rotate(angle)`, lalu translasi kembali sebelum menggambar.

**T: Apakah Aspose.Page mendukung anti‑aliasing untuk grafik yang lebih halus?**  
J: Ya—atur opsi rendering yang sesuai dalam `PsSaveOptions` untuk mengaktifkan anti‑aliasing.

---

**Terakhir Diperbarui:** 2025-12-07  
**Diuji Dengan:** Aspose.Page for Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
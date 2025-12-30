---
date: 2025-12-30
description: Pelajari cara membuat dokumen XPS Java dengan menambahkan persegi panjang
  menggunakan Aspose.Page. Ikuti panduan langkah demi langkah ini untuk manipulasi
  dokumen XPS yang mulus.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Buat Dokumen XPS Java – Tambahkan Persegi Panjang dengan Aspose.Page
url: /id/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dokumen XPS Java – Tambahkan Persegi Panjang

## Pendahuluan
Dalam tutorial komprehensif ini Anda akan **membuat dokumen XPS Java** dan belajar cara menambahkan persegi panjang menggunakan pustaka Aspose.Page. Baik Anda membuat laporan, faktur, atau grafik khusus, menguasai pembuatan persegi panjang memberi Anda kontrol presisi atas tata letak XPS. Kami akan membimbing Anda melalui setiap langkah, menjelaskan alasan di balik setiap baris kode, dan menunjukkan cara menyesuaikan warna serta garis tepi untuk hasil profesional.

## Jawaban Cepat
- **Perpustakaan apa yang direkomendasikan?** Aspose.Page for Java  
- **Berapa lama implementasinya?** Sekitar 10 menit untuk persegi panjang dasar  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru  
- **Bisakah saya menambahkan beberapa bentuk?** Ya – ulangi langkah‑langkah untuk setiap bentuk

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang bahasa pemrograman Java.  
- Pustaka Aspose.Page terpasang. Jika belum, Anda dapat mengunduhnya dari [dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Lingkungan pengembangan Java yang berfungsi (IDE, JDK, dan Maven/Gradle jika Anda suka).

## Impor Paket
Untuk memulai, impor paket yang diperlukan ke dalam proyek Java Anda. Pastikan pustaka Aspose.Page telah ditambahkan dengan benar ke classpath Anda. Berikut contoh dasar:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk menambahkan persegi panjang dalam XPS Java.

## Langkah 1: Atur Direktori Dokumen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur ke folder tempat Anda ingin menyimpan file XPS.

## Langkah 2: Buat Dokumen XPS Baru
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Baris ini **membuat** dokumen XPS baru yang nantinya dapat Anda isi dengan bentuk, teks, atau gambar.

## Langkah 3: Tambahkan Persegi Panjang Berwarna Solid CMYK dengan Garis Tepi
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Langkah ini menambahkan persegi panjang bergaris tepi dengan warna solid CMYK. Anda dapat mengubah string geometri (`"M 20,10 L 220,10 220,100 20,100 Z"`) untuk mengubah ukuran atau posisi, serta menyesuaikan nilai warna di `createColor` sesuai desain Anda.

## Langkah 4: Simpan Dokumen XPS Hasil
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Akhirnya, simpan dokumen XPS yang telah dimodifikasi dengan persegi panjang yang ditambahkan ke direktori yang Anda tentukan sebelumnya.

## Kasus Penggunaan Umum
- **Header laporan** – Gunakan persegi panjang sebagai blok latar belakang untuk judul.  
- **Tabel faktur** – Sorot sel atau bagian dengan batas berwarna.  
- **Grafik khusus** – Gabungkan beberapa persegi panjang untuk membuat bentuk kompleks.

## Tips Pemecahan Masalah
- **Kesalahan file tidak ditemukan:** Pastikan `dataDir` mengarah ke folder yang ada dan profil ICC (`uswebuncoated.icc`) tersedia.  
- **Warna tidak tepat:** Pastikan profil ICC cocok dengan ruang warna yang ingin Anda gunakan (CMYK vs. RGB).  
- **Dimensi tidak terduga:** Sesuaikan string geometri untuk mencerminkan koordinat yang benar.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara **membuat dokumen XPS Java** dan menambahkan persegi panjang menggunakan Aspose.Page. Dasar ini memungkinkan Anda membangun dokumen XPS yang lebih kaya, menyesuaikan grafik, dan mengintegrasikan bentuk ke dalam alur kerja yang lebih besar.

## FAQ
### Bisakah saya menambahkan beberapa persegi panjang dalam satu dokumen XPS?
Ya, Anda dapat menambahkan sebanyak yang diperlukan dengan mengulangi langkah‑langkah yang dijelaskan dalam tutorial.

### Bagaimana cara mengubah warna persegi panjang?
Ubah nilai warna dalam metode `createColor` untuk mendapatkan warna yang diinginkan.

### Apakah Aspose.Page cocok untuk menangani manipulasi dokumen XPS yang kompleks?
Tentu saja! Aspose.Page menyediakan rangkaian fitur yang kuat untuk menangani berbagai tugas dokumen XPS.

### Di mana saya dapat menemukan contoh tambahan dan dukungan?
Jelajahi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk contoh lebih lanjut dan dapatkan bantuan dari komunitas.

### Bisakah saya mencoba Aspose.Page sebelum membeli?
Ya, Anda dapat menjelajahi [percobaan gratis](https://releases.aspose.com/) untuk merasakan kemampuan Aspose.Page.

## Pertanyaan yang Sering Diajukan

**T: Apakah pendekatan ini bekerja dengan Java 11 atau yang lebih baru?**  
J: Ya, pustaka Aspose.Page kompatibel dengan Java 8 dan yang lebih baru, termasuk Java 11, 17, dan seterusnya.

**T: Bisakah saya menyematkan gambar di dalam area persegi panjang?**  
J: Anda dapat menambahkan elemen `XpsImage` dan menempatkannya di atas atau di dalam persegi panjang menggunakan koordinat geometri yang sama.

**T: Bagaimana cara mengatur warna isi alih-alih hanya garis tepi?**  
J: Panggil `path.setFill(...)` dengan kuas warna solid yang dibuat lewat `doc.createSolidColorBrush(...)`.

**T: Apakah memungkinkan memutar persegi panjang?**  
J: Terapkan matriks transformasi ke path menggunakan `path.setTransform(...)` untuk memutar atau menskalakan.

**T: Lisensi apa yang diperlukan untuk penggunaan produksi?**  
J: Lisensi komersial Aspose.Page diperlukan untuk penyebaran; percobaan gratis terbatas untuk evaluasi dan pengembangan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---
---
date: 2026-04-24
description: Pelajari cara menambahkan teks XPS dalam Java menggunakan Aspose.Page
  – panduan langkah demi langkah untuk membuat dokumen XPS, menambahkan teks, dan
  menyimpan file XPS dengan mudah.
keywords:
- how to add xps
- create xps document
- aspose.page add text
linktitle: Tambahkan Teks di Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Teks XPS di Java – Tutorial Aspose.Page
url: /id/java/xps-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Teks XPS di Java – Tutorial Aspose.Page

## Pendahuluan
Jika Anda perlu **cara menambahkan XPS** secara programatis, Aspose.Page untuk Java memberikan API yang bersih dan berperforma tinggi untuk bekerja dengan file XPS (XML Paper Specification). Dalam tutorial ini kami akan memandu Anda membuat dokumen XPS, menyisipkan teks bergaya, dan menyimpan hasilnya—semua dengan kode yang singkat dan mudah diikuti. Baik Anda membangun mesin pelaporan, menghasilkan faktur, atau sekadar perlu menambahkan teks pada halaman, langkah‑langkah ini akan membantu Anda memulai dengan cepat.

## Jawaban Cepat
- **Perpustakaan apa yang terbaik untuk manipulasi XPS di Java?** Aspose.Page for Java.
- **Bisakah saya membuat dan menyimpan file XPS tanpa lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk produksi.
- **IDE mana yang didukung?** IntelliJ IDEA, Eclipse, NetBeans, atau IDE apa pun yang mendukung Java.
- **Berapa banyak baris kode yang diperlukan untuk menambahkan teks sederhana?** Sekitar 10 baris plus pengaturan.
- **Apakah styling font memungkinkan?** Ya – Anda dapat mengatur keluarga font, ukuran, gaya, dan warna.

## Apa itu XPS dan Mengapa Menambahkan Teks?
XPS (XML Paper Specification) adalah format dokumen tata letak tetap milik Microsoft, mirip dengan PDF namun berbasis XML. Menambahkan teks ke file XPS umum dilakukan ketika Anda memerlukan penempatan yang tepat, seperti label, watermark, atau data dinamis dalam laporan. Menggunakan Aspose.Page memungkinkan Anda memanipulasi XPS tanpa harus berurusan dengan struktur XML tingkat rendah.

## Mengapa Menggunakan Aspose.Page untuk Menambahkan Teks XPS?
- **Kontrol penuh** atas penempatan glyph, gaya font, dan kuas.  
- **Tanpa dependensi eksternal** – API Java murni.  
- **Fidelity tinggi** dalam rendering yang mempertahankan tata letak di semua platform.  
- **Dokumentasi komprehensif** dan contoh kode untuk memulai dengan cepat.

## Prasyarat
- **Java Development Kit (JDK)** – versi terbaru (8 atau lebih tinggi) terpasang.
- **Aspose.Page for Java** – unduh perpustakaan dari situs resmi [di sini](https://releases.aspose.com/page/java/).
- **A Java IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.

## Impor Paket
Mulailah dengan mengimpor kelas yang Anda perlukan untuk manipulasi XPS:

```java
import java.awt.Color;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
```

## Langkah 1: Atur Direktori Dokumen (buat file xps)
Tentukan di mana file XPS yang dihasilkan akan disimpan:

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: Buat Dokumen XPS (buat dokumen xps)
Instansiasi dokumen XPS baru yang kosong:

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Buat Kuas untuk Styling Teks
Kuasa warna solid menentukan warna teks. Di sini kami menggunakan warna hitam:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
```

## Langkah 4: Tambahkan Glyph – Teks Sebenarnya (aspose.page add text)
Tambahkan teks yang ingin muncul dalam dokumen. Metode `addGlyphs` memungkinkan Anda menentukan font, ukuran, gaya, dan koordinat yang tepat:

```java
XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.setFill(textFill);
```

## Langkah 5: Simpan Dokumen XPS Hasil (simpan file xps)
Akhirnya, tulis dokumen ke disk:

```java
doc.save(dataDir + "AddText_out.xps");
```

Ulangi langkah **Add Glyphs** sesuai kebutuhan untuk menyisipkan baris tambahan, mengubah font, atau menyesuaikan posisi.

## Masalah Umum & Tips Pro
- **Koordinat tidak tepat:** XPS menggunakan sistem koordinat yang diukur dalam poin (1/72 inci). Sesuaikan nilai `x` dan `y` untuk menempatkan teks secara tepat.
- **Font tidak ditemukan:** Pastikan nama font (mis., “Arial”) terpasang pada mesin yang menjalankan kode.
- **Pengecualian lisensi:** Tanpa lisensi yang valid, XPS yang dihasilkan dapat berisi watermark. Terapkan lisensi Anda di awal aplikasi untuk menghindarinya.

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Page kompatibel dengan semua IDE Java?
Ya, Aspose.Page bekerja dengan IDE Java populer, termasuk IntelliJ IDEA dan Eclipse.

### Bisakah saya menerapkan gaya font berbeda pada teks yang ditambahkan?
Tentu saja! Gunakan `XpsFontStyle.Bold`, `Italic`, atau gabungkan gaya saat memanggil `addGlyphs`.

### Di mana saya dapat menemukan contoh tambahan dan dokumentasi untuk Aspose.Page?
Jelajahi dokumentasi komprehensif [di sini](https://reference.aspose.com/page/java/).

### Apakah ada percobaan gratis untuk Aspose.Page?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page?
Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Bisakah saya menyematkan gambar bersama teks?**  
**A:** Ya – gunakan objek `XpsImage` bersama glyph untuk membuat tata letak yang kaya.

**Q: Apakah Aspose.Page mendukung karakter Unicode?**  
**A:** Ia sepenuhnya mendukung Unicode, memungkinkan Anda menambahkan teks dalam bahasa apa pun.

**Q: Versi Aspose.Page apa yang digunakan untuk pengujian?**  
**A:** Kode ini diuji dengan Aspose.Page 23.12 untuk Java.

---

**Terakhir Diperbarui:** 2026-04-24  
**Diuji Dengan:** Aspose.Page 23.12 untuk Java  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
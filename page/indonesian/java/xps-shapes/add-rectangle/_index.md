---
title: Tambahkan Persegi Panjang di Java XPS
linktitle: Tambahkan Persegi Panjang di Java XPS
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan persegi panjang di Java XPS menggunakan Aspose.Page. Ikuti panduan langkah demi langkah kami untuk manipulasi dokumen yang lancar. #JavaXPS #AsposePage
type: docs
weight: 11
url: /id/java/xps-shapes/add-rectangle/
---
## Perkenalan
Selamat datang di panduan komprehensif tentang menambahkan persegi panjang di Java XPS menggunakan Aspose.Page! Baik Anda seorang pengembang berpengalaman atau baru memulai dengan Java XPS, tutorial ini akan memandu Anda melalui proses dengan petunjuk langkah demi langkah, memastikan Anda mendapatkan pemahaman mendalam tentang topik tersebut.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar bahasa pemrograman Java.
-  Pustaka Aspose.Page terinstal. Jika belum, Anda dapat mendownloadnya dari[Dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/).
- Lingkungan pengembangan Java yang berfungsi.
## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda. Pastikan perpustakaan Aspose.Page ditambahkan dengan benar ke classpath Anda. Berikut ini contoh dasarnya:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk menambahkan persegi panjang di Java XPS.
## Langkah 1: Atur Direktori Dokumen
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur ke direktori yang Anda inginkan.
## Langkah 2: Buat Dokumen XPS Baru
```java
// Buat Dokumen XPS baru
XpsDocument doc = new XpsDocument();
```
Ini menginisialisasi dokumen XPS baru.
## Langkah 3: Tambahkan Persegi Panjang Berguratan Warna Solid CMYK
```java
// CMYK (biru) warna solid dengan guratan persegi panjang di kiri bawah
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Langkah ini menambahkan persegi panjang bergaris dengan warna solid CMYK.
## Langkah 4: Simpan Dokumen XPS yang Dihasilkan
```java
// Simpan dokumen XPS yang dihasilkan
doc.save(dataDir + "AddRectangle_out.xps");
```
Terakhir, simpan dokumen XPS yang dimodifikasi dengan persegi panjang yang ditambahkan.
Ulangi langkah-langkah ini, sesuaikan parameter sesuai kebutuhan, untuk menyesuaikan persegi panjang Anda lebih lanjut.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan persegi panjang di Java XPS menggunakan Aspose.Page. Tutorial ini memberikan dasar yang kuat untuk upaya manipulasi dokumen XPS Anda.
## FAQ
### Bisakah saya menambahkan beberapa persegi panjang dalam satu dokumen XPS?
Ya, Anda dapat menambahkan persegi panjang sebanyak yang diperlukan dengan mengulangi langkah-langkah yang diuraikan dalam tutorial.
### Bagaimana cara mengubah warna persegi panjang?
 Ubah nilai warna di`createColor` metode untuk mencapai warna yang diinginkan.
### Apakah Aspose.Page cocok untuk menangani manipulasi dokumen XPS yang kompleks?
Sangat! Aspose.Page menyediakan serangkaian fitur canggih untuk menangani berbagai tugas dokumen XPS.
### Di mana saya dapat menemukan contoh dan dukungan tambahan?
 Jelajahi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39)untuk mendapatkan lebih banyak contoh dan mencari bantuan dari komunitas.
### Bisakah saya mencoba Aspose.Page sebelum membeli?
 Ya, Anda dapat menjelajahi a[uji coba gratis](https://releases.aspose.com/) untuk merasakan kemampuan Aspose.Page.
---
date: 2026-01-02
description: Pelajari cara menambahkan transparansi pada dokumen Java XPS menggunakan
  Aspose.Page. Ikuti panduan langkah demi langkah kami untuk menambahkan objek transparan
  dengan efek visual yang menakjubkan.
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Transparansi ke Dokumen XPS Java
url: /id/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Transparansi ke Dokumen Java XPS

## Pendahuluan
Jika Anda ingin **menambahkan transparansi** ke dokumen Java XPS Anda dan memberikan tampilan modern serta berlapis, Aspose.Page for Java mempermudahnya. Dalam tutorial ini kami akan membahas semua yang Anda perlukan—mulai dari menyiapkan lingkungan hingga membuat jalur transparan, mengatur opacity, dan akhirnya menyimpan hasilnya. Pada akhir tutorial, Anda akan dapat menambahkan transparansi ke objek XPS apa pun dengan percaya diri.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Page for Java  
- **Bisakah saya mengontrol opacity secara programatis?** Ya, melalui metode `setOpacity` pada sebuah brush.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan non‑evaluasi.  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru.  
- **Apakah output kompatibel dengan penampil XPS standar?** Tentu—penampil standar menampilkan transparansi dengan benar.

## Apa itu transparansi dalam XPS?
Transparansi memungkinkan Anda merender objek dengan opacity yang bervariasi, sehingga elemen latar belakang dapat terlihat. Efek ini berguna untuk watermark, grafik overlay, atau desain apa pun di mana visual berlapis meningkatkan keterbacaan.

## Mengapa menggunakan Aspose.Page untuk menambahkan transparansi?
- **Kontrol penuh** atas geometri, brush, dan transformasi.  
- **Tanpa dependensi eksternal**—semua ditangani di dalam API.  
- **Dukungan lintas platform**, sehingga kode yang sama bekerja di Windows, Linux, dan macOS.  

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Lingkungan pengembangan Java (JDK 8+).  
- Perpustakaan Aspose.Page for Java terpasang. Anda dapat mengunduhnya dari situs resmi [di sini](https://releases.aspose.com/page/java/).  

## Impor Paket
Di proyek Java Anda, impor paket Aspose.Page yang diperlukan untuk memulai menambahkan objek transparan. Sertakan baris berikut di awal file Java Anda:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

Sekarang, mari kita uraikan contoh kode menjadi beberapa langkah.

## Langkah 1: Inisialisasi Dokumen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
Mulailah dengan menyiapkan dokumen Anda dan menentukan direktori tempat dokumen XPS Anda akan disimpan.

## Langkah 2: Buat Objek Transparan
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
Di sini, kami membuat dua jalur abu-abu yang akan berfungsi sebagai latar belakang untuk bentuk transparan yang akan kami tambahkan nanti.

## Langkah 3: Tambahkan Jalur Terisi
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
Pada langkah ini kami membuat persegi panjang biru padat dan menempatkannya pada halaman. Persegi panjang ini nantinya akan ditutupi oleh bentuk transparan, memperlihatkan efeknya.

## Langkah 4: Manipulasi Transparansi
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
Di sini kami mengubah warna isi jalur yang diduplikasi dan menerapkan transformasi translasi. Ini menunjukkan bagaimana transparansi berinteraksi ketika objek berbagi elemen induk yang sama.

## Langkah 5: Duplikat dan Modifikasi Jalur
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
Kami menggandakan jalur yang ada, memindahkannya, dan menyesuaikan opacity menjadi 0.8 (80 % padat). Langkah ini menampilkan cara Anda dapat menggunakan kembali geometri sambil menyesuaikan transparansi untuk setiap instance.

## Langkah 6: Simpan Dokumen
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
Akhirnya, kami menyimpan file XPS. Buka file yang dihasilkan di penampil XPS apa pun untuk melihat transparansi berlapis beraksi.

## Masalah Umum & Tips
- **Opacity tidak terlihat?** Pastikan Anda menggunakan brush yang mendukung opacity (mis., `createSolidColorBrush`).  
- **Transformasi tidak diterapkan?** Verifikasi bahwa Anda memanggil `setRenderTransform` **sebelum** menambahkan jalur ke dokumen.  
- **Tip kinerja:** Gunakan kembali objek geometri saat membuat banyak bentuk serupa untuk mengurangi beban memori.

## Pertanyaan yang Sering Diajukan
### Q: Bisakah saya menerapkan transparansi pada bentuk lain selain persegi panjang?
A: Ya, Anda dapat menerapkan transparansi pada berbagai bentuk menggunakan geometri yang disediakan.  
### Q: Bagaimana saya dapat mengontrol tingkat transparansi suatu objek?
A: Sesuaikan properti opacity pada isi untuk mengontrol tingkat transparansi.  
### Q: Apakah Aspose.Page cocok untuk pembuatan dokumen profesional?
A: Tentu! Aspose.Page menyediakan fitur kuat untuk manipulasi dokumen profesional.  
### Q: Bisakah saya mengintegrasikan Aspose.Page dengan perpustakaan Java lainnya?
A: Ya, Aspose.Page dapat diintegrasikan dengan mulus ke perpustakaan Java lain untuk fungsionalitas yang lebih luas.  
### Q: Di mana saya dapat menemukan contoh tambahan dan dukungan untuk Aspose.Page?
A: Kunjungi [Aspose.Page Java Forum](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan jelajahi dokumentasi [di sini](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
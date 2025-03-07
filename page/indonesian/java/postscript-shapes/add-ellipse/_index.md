---
title: Tambahkan Ellipse di Java PostScript
linktitle: Tambahkan Ellipse di Java PostScript
second_title: Aspose.Halaman Java API
description: Kuasai membuat dokumen PostScript yang menakjubkan di Java dengan Aspose.Page. Pelajari cara menambahkan elips langkah demi langkah untuk konten yang menarik secara visual.
weight: 10
url: /id/java/postscript-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Ellipse di Java PostScript

## Perkenalan
Dalam dunia perkembangan Java yang dinamis, membuat dokumen yang menarik secara visual merupakan persyaratan umum. Aspose.Page untuk Java adalah perpustakaan canggih yang memberdayakan pengembang untuk memanipulasi file PostScript dengan mudah. Dalam tutorial ini, kita akan mempelajari cara menambahkan elips ke dokumen PostScript menggunakan Aspose.Page untuk Java. Ikuti terus untuk meningkatkan keterampilan pembuatan dokumen Anda!
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda memiliki lingkungan pengembangan Java yang berfungsi terinstal di mesin Anda.
2.  Aspose.Page untuk Java Library: Unduh dan sertakan perpustakaan Aspose.Page dalam proyek Java Anda. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Dalam kode Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Berikut ini contohnya:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Langkah 1: Siapkan Dokumen Anda
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Langkah 2: Isi Ellipse dengan Warna
```java
// Atur cat untuk mengisi elips
document.setPaint(Color.ORANGE);
// Isi elips pertama
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Langkah 3: Buat Garis Besar Ellipse dengan Stroke
```java
// Atur cat untuk membelai elips
document.setPaint(Color.RED);
// Atur pukulan
document.setStroke(new BasicStroke(3));
// Goresan (garis besar) elips kedua
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Langkah 4: Tutup dan Simpan Dokumen
```java
// Tutup halaman saat ini
document.closePage();
// Simpan dokumennya
document.save();
```
Sekarang Anda telah berhasil menambahkan elips ke dokumen PostScript Anda menggunakan Aspose.Page untuk Java! Bereksperimenlah dengan koordinat dan dimensi berbeda untuk menyesuaikan visual Anda.
## Kesimpulan
 Aspose.Page untuk Java menyederhanakan proses pembuatan dan manipulasi dokumen PostScript. Tutorial ini telah membekali Anda dengan pengetahuan untuk menambahkan elips, memberikan dasar yang kuat untuk visualisasi yang lebih kompleks. Menyelam ke dalam[dokumentasi](https://reference.aspose.com/page/java/) untuk rincian dan kemampuan lebih lanjut.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Page untuk Java dengan pustaka Java lainnya?
J: Ya, Aspose.Page untuk Java dirancang untuk berintegrasi secara lancar dengan pustaka Java lainnya.
### T: Bagaimana cara mendapatkan lisensi sementara Aspose.Page untuk Java?
 A: Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.
### T: Apakah Aspose.Page cocok untuk proyek komersial?
 J: Tentu saja! Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk mengeksplorasi opsi lisensi untuk penggunaan komersial.
### T: Di mana saya dapat mencari bantuan atau mendiskusikan pertanyaan terkait Aspose.Page?
 A: Bergabunglah dengan komunitas di[Aspose.Halaman Forum](https://forum.aspose.com/c/page/39) untuk diskusi dan bantuan.
### T: Apakah ada sumber daya gratis untuk mempelajari lebih lanjut tentang Aspose.Page untuk Java?
 J: Gunakan[uji coba gratis](https://releases.aspose.com/) dan jelajahi contoh dalam dokumentasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

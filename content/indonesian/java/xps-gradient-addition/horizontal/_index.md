---
title: Tambahkan Gradien Horizontal di Java XPS
linktitle: Tambahkan Gradien Horizontal di Java XPS
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan gradien horizontal yang menakjubkan ke dokumen XPS di Java menggunakan Aspose.Page. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 11
url: /id/java/xps-gradient-addition/horizontal/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah tentang menambahkan gradien horizontal di Java XPS menggunakan Aspose.Page untuk Java. Aspose.Page untuk Java adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen XPS (Spesifikasi Kertas XML) dengan lancar.
Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan aplikasi Java untuk menambahkan gradien horizontal ke dokumen XPS. Ikuti langkah-langkah di bawah ini untuk mencapainya dengan mudah.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda. Jika tidak, unduh dan instal Java versi terbaru dari[java.com](https://www.java.com).
2.  Aspose.Page untuk Perpustakaan Java: Anda harus memiliki perpustakaan Aspose.Page untuk Java. Anda dapat mengunduhnya dari[Aspose.Page untuk dokumentasi Java](https://reference.aspose.com/page/java/).
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan untuk aplikasi Java Anda. Sertakan perpustakaan Aspose.Page untuk Java dalam proyek Anda. Anda dapat melakukannya dengan menambahkan baris kode berikut:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Langkah 1: Inisialisasi Dokumen
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
//Inisialisasi dokumen
XpsDocument doc = new XpsDocument();
```
## Langkah 2: Buat Gradien Horizontal
```java
// Gradien horisontal
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Langkah 3: Tambahkan Jalur dengan Gradien
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Langkah 4: Simpan Dokumen
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Ulangi langkah-langkah ini sesuai kebutuhan, sesuaikan parameter berdasarkan kebutuhan spesifik Anda.
## Kesimpulan
Selamat! Anda telah berhasil menambahkan gradien horizontal ke dokumen XPS menggunakan Aspose.Page untuk Java. Tutorial ini memberikan panduan komprehensif bagi pengembang yang ingin menyempurnakan aplikasi Java mereka dengan efek gradien.
## FAQ
### T: Dapatkah saya menerapkan beberapa gradien dalam satu dokumen XPS?
Ya, Anda dapat menambahkan beberapa jalur dengan gradien berbeda untuk membuat desain yang rumit.
### T: Apakah Aspose.Page kompatibel dengan versi Java terbaru?
Aspose.Page untuk Java diperbarui secara berkala untuk memastikan kompatibilitas dengan rilis Java terbaru.
### T: Apakah ada tipe gradien lain yang tersedia di Aspose.Page?
Ya, selain gradien linier, Aspose.Page mendukung gradien radial untuk efek yang lebih beragam.
### T: Dapatkah saya menyesuaikan warna dan posisi perhentian gradien?
Sangat! Anda memiliki kendali penuh atas warna dan posisi setiap perhentian gradien.
### T: Apakah ada forum komunitas untuk Aspose.Page tempat saya dapat mencari bantuan?
 Ya, Anda dapat mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk berhubungan dengan masyarakat dan mendapatkan bantuan.
---
title: Tambahkan Radial Gradient Ellipse dengan Aspose.Page
linktitle: Tambahkan Ellipse di Java XPS
second_title: Aspose.Halaman Java API
description: Jelajahi panduan langkah demi langkah tentang menambahkan elips guratan gradien radial di Java XPS menggunakan Aspose.Page untuk Java. Sempurnakan pembuatan dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/java/xps-shapes/add-ellipse/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang menambahkan elips di Java XPS menggunakan Aspose.Page untuk Java. Aspose.Page adalah perpustakaan Java yang kuat yang memungkinkan pengembang untuk bekerja dengan dokumen XPS dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan elips dengan guratan gradien radial dan menyimpannya sebagai dokumen XPS.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Halaman untuk perpustakaan Java diunduh. Kamu bisa mendapatkannya[Di Sini](https://releases.aspose.com/page/java/).
- Editor kode pilihan Anda (Eclipse, IntelliJ, dll.) untuk menulis dan mengeksekusi kode Java.
## Paket Impor
Pastikan Anda memiliki paket yang diperlukan yang diimpor ke proyek Java Anda untuk menggunakan Aspose.Page. Tambahkan pernyataan import berikut ke bagian atas file Java Anda:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Langkah 1: Siapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat dokumen XPS akan disimpan:
```java
String dataDir = "Your Document Directory";
```
## Langkah 2: Buat Dokumen XPS
Inisialisasi dokumen XPS baru menggunakan kode berikut:
```java
XpsDocument doc = new XpsDocument();
```
## Langkah 3: Tentukan Perhentian Gradien Radial
Buat daftar perhentian gradien untuk elips dengan coretan gradien radial:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Langkah 4: Buat Geometri Jalur
Tentukan elips dengan guratan gradien radial menggunakan geometri jalur:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Langkah 5: Tambahkan Kanvas dan Jalur
Tambahkan kanvas baru ke dokumen dan tambahkan jalur dengan geometri yang ditentukan:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Langkah 6: Atur Stroke dan Gradien
Konfigurasikan goresan jalur dengan kuas gradien radial:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Langkah 7: Atur Ketebalan Stroke
Tentukan ketebalan goresan jalur:
```java
path.setStrokeThickness(12f);
```
## Langkah 8: Simpan Dokumen
Simpan dokumen XPS yang dihasilkan:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Selamat! Anda telah berhasil menambahkan elips guratan gradien radial di Java XPS menggunakan Aspose.Page untuk Java.
## Kesimpulan
Dalam tutorial ini, kita menjelajahi langkah-langkah untuk membuat dokumen XPS dengan elips guratan gradien radial yang menarik secara visual. Aspose.Page untuk Java menyederhanakan manipulasi dokumen XPS, memberikan pengembang seperangkat alat yang canggih.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan perpustakaan Java lainnya?
Ya, Aspose.Page untuk Java dapat diintegrasikan dengan perpustakaan Java lainnya dengan lancar.
### Apakah Aspose.Page cocok untuk pemrosesan dokumen skala besar?
Sangat! Aspose.Page dirancang untuk menangani pemrosesan dokumen skala besar secara efisien.
### Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.Page untuk Java?
 Mengunjungi[Aspose.Page untuk dokumentasi Java](https://reference.aspose.com/page/java/)untuk tutorial dan contoh yang komprehensif.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah ada forum komunitas untuk diskusi Aspose.Page?
 Ya, bergabunglah dengan[Aspose.Page forum komunitas](https://forum.aspose.com/c/page/39) untuk terlibat dengan pengembang lain dan mendapatkan bantuan.
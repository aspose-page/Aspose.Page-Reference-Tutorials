---
title: Tambahkan Gradien Vertikal di Java XPS
linktitle: Tambahkan Gradien Vertikal di Java XPS
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan gradien vertikal ke dokumen Java XPS dengan Aspose.Page. Tingkatkan daya tarik visual dengan mudah. Panduan langkah demi langkah di dalam.
weight: 12
url: /id/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Vertikal di Java XPS

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menambahkan gradien vertikal di Java XPS menggunakan Aspose.Page untuk Java. Menambahkan gradien ke dokumen XPS Anda dapat meningkatkan daya tarik visual konten Anda, menjadikannya lebih menarik dan estetis.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Lingkungan pengembangan Java yang berfungsi.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/java/).
- Pemahaman dasar tentang pemrograman Java.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan untuk proyek Java Anda. Pastikan Anda telah menyertakan pustaka Aspose.Page untuk Java dalam dependensi proyek Anda.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
        
// Impor Aspose.Page untuk Java
```
## Langkah 1: Inisialisasi Dokumen
Mulailah dengan menginisialisasi dokumen XPS. Ini menetapkan dasar untuk menambahkan elemen seperti jalur dan gradien ke dokumen Anda.
```java
// Inisialisasi dokumen
XpsDocument doc = new XpsDocument();
```
## Langkah 2: Buat Jalur dengan Gradien Vertikal
Sekarang, mari buat jalur dengan gradien vertikal. Hal ini melibatkan pendefinisian geometri jalur dan penentuan perhentian gradien.
```java
// Buat jalur dengan geometri
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Tentukan perhentian gradien vertikal
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Terapkan gradien vertikal ke jalur
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Langkah 3: Simpan Dokumen
Terakhir, simpan dokumen XPS dengan tambahan gradien vertikal ke direktori yang Anda inginkan.
```java
// Simpan dokumennya
doc.save(dataDir + "VerticalGradient.xps");
```
Selamat! Anda telah berhasil menambahkan gradien vertikal ke dokumen Java XPS Anda menggunakan Aspose.Page.
## Kesimpulan
Meningkatkan dokumen XPS Anda dengan gradien dapat meningkatkan daya tarik visualnya secara signifikan. Aspose.Page untuk Java menyederhanakan proses ini, memungkinkan Anda membuat dokumen menakjubkan dengan mudah.

### FAQ
### Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial?
 Ya, Aspose.Page untuk Java tersedia untuk penggunaan komersial. Anda dapat membelinya[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Butuh bantuan atau punya pertanyaan?
 Kunjungi komunitas Aspose.Page[forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Tambahkan Grid menggunakan Visual Brush di Java
linktitle: Tambahkan Grid menggunakan Visual Brush di Java
second_title: Aspose.Halaman Java API
description: Sempurnakan visual dokumen Java dengan Aspose.Page! Pelajari cara menambahkan kisi menggunakan Visual Brush selangkah demi selangkah. Tingkatkan daya tarik aplikasi Anda dengan mudah.
weight: 10
url: /id/java/visual-elements/add-grid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Grid menggunakan Visual Brush di Java

## Perkenalan
Apakah Anda ingin menyempurnakan aplikasi Java Anda dengan kisi-kisi yang menarik secara visual menggunakan Aspose.Page? Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan grid menggunakan Visual Brush di Java dengan Aspose.Page. Visual Brush memungkinkan Anda melukis area dengan konten visual, menciptakan efek grid yang menakjubkan di dokumen Anda.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.
-  Pustaka Aspose.Page terinstal. Anda dapat mengunduhnya dari[Aspose.Page untuk dokumentasi Java](https://reference.aspose.com/page/java/).
- Java Development Kit (JDK) diinstal pada mesin Anda.
## Paket Impor
Pastikan Anda telah mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```
Mari kita bagi prosesnya menjadi beberapa langkah untuk memudahkan Anda mengikutinya.
## Langkah 1: Siapkan Proyek Anda
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```
## Langkah 2: Buat Kuas Visual Kotak Magenta
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```
## Langkah 3: Tentukan Geometri untuk Kuas Visual Kotak Magenta
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```
## Langkah 4: Buat Kanvas Baru
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```
## Langkah 5: Tambahkan Grid ke Kanvas
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```
## Langkah 6: Tambahkan Persegi Panjang Transparan Merah
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```
## Langkah 7: Simpan Dokumen XPS yang Dihasilkan
```java
doc.save(dataDir + "AddGrid_out.xps");
```
Ikuti langkah-langkah ini, dan Anda akan berhasil menambahkan grid yang menarik secara visual menggunakan Visual Brush di aplikasi Java Anda dengan Aspose.Page.
## Kesimpulan
Selamat! Anda telah mempelajari cara memanfaatkan Aspose.Page untuk Java untuk menambahkan kisi menggunakan Visual Brush. Sempurnakan visual dokumen Anda dengan mudah menggunakan fitur canggih ini.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Page cocok untuk pembuatan dokumen profesional?
Ya, Aspose.Page adalah perpustakaan tangguh yang dirancang untuk pembuatan dokumen profesional di Java.
### Bisakah saya menyesuaikan warna kisi menggunakan Visual Brush?
Sangat! Visual Brush memungkinkan Anda melukis dengan berbagai warna, memberikan fleksibilitas dalam penyesuaian.
### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Page?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi komunitas.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page?
 Ya, Anda dapat mengakses[uji coba gratis](https://releases.aspose.com/) untuk menjelajahi fitur Aspose.Page.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page?
 Memperoleh sebuah[izin sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

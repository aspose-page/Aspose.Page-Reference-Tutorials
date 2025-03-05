---
title: Tambahkan Gradien Horizontal di Java PostScript
linktitle: Tambahkan Gradien Horizontal di Java PostScript
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan gradien horizontal di Java PostScript dengan Aspose.Page untuk Java. Buat dokumen yang menakjubkan secara visual dengan mudah.
type: docs
weight: 11
url: /id/java/postscript-gradient-addition/horizontal/
---
## Perkenalan
Selamat datang di tutorial komprehensif tentang menambahkan gradien horizontal di Java PostScript menggunakan Aspose.Page untuk Java. Aspose.Page adalah perpustakaan Java yang kuat yang memungkinkan pengembang untuk bekerja dengan PostScript dan format dokumen lainnya. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan dokumen PostScript dengan gradien horizontal menggunakan contoh langkah demi langkah.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
- Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya dari[Dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/).
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan dalam proyek Java Anda. Paket-paket ini sangat penting untuk bekerja dengan Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Langkah 1: Buat Persegi Panjang
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
//Buat persegi panjang
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Langkah 2: Buat Cat Gradien Linier Horisontal
```java
// Buat cat gradien linier horizontal. Komponen skala pada transformasi harus sama dengan lebar dan tinggi persegi panjang.
// Komponen terjemahan adalah offset dari persegi panjang.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Atur cat
document.setPaint(paint);
```
## Langkah 3: Isi Persegi Panjang
```java
// Isi persegi panjang
document.fill(rectangle);
```
## Langkah 4: Isi Teks dengan Gradien
```java
// Isi teks dengan gradien
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Langkah 5: Goresan Teks dengan Gradien
```java
// Goreskan teks dengan gradien
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Kesimpulan
Selamat! Anda telah berhasil menambahkan gradien horizontal di Java PostScript menggunakan Aspose.Page untuk Java. Tutorial ini memberi Anda panduan langkah demi langkah terperinci untuk membantu Anda membuat dokumen PostScript yang menarik secara visual.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dalam proyek komersial?
Ya, Aspose.Page untuk Java dapat digunakan dalam proyek komersial. Untuk detail lisensi, kunjungi[Aspose. Pembelian](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat mengakses uji coba gratis Aspose.Page untuk Java[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi dan dukungan tambahan?
 Mengunjungi[Dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/) untuk sumber daya yang komprehensif. Untuk dukungan komunitas, periksa[Aspose.Halaman forum](https://forum.aspose.com/c/page/39).
### Bagaimana saya bisa mendapatkan lisensi sementara?
 Anda dapat memperoleh lisensi sementara dari[Aspose. Pembelian](https://purchase.aspose.com/temporary-license/).
### Apa saja persyaratan sistem untuk Aspose.Page untuk Java?
 Mengacu kepada[dokumentasi](https://reference.aspose.com/page/java/) untuk persyaratan sistem terperinci.
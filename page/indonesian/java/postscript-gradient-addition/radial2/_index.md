---
title: Gradien Radial Java PostScript dengan Aspose.Page
linktitle: Gradien Radial Java PostScript dengan Aspose.Page
second_title: Aspose.Halaman Java API
description: Jelajahi panduan langkah demi langkah untuk menambahkan Radial Gradient di Java PostScript menggunakan Aspose.Page untuk grafik menakjubkan di aplikasi Java Anda.
weight: 13
url: /id/java/postscript-gradient-addition/radial2/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gradien Radial Java PostScript dengan Aspose.Page

## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang menambahkan Radial Gradient 2 di Java PostScript menggunakan Aspose.Page untuk Java. Tutorial ini akan memandu Anda melalui proses pembuatan dokumen PostScript dengan gradien radial yang indah, menyempurnakan aplikasi Java Anda dengan grafik yang menarik secara visual.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan kerja tentang pemrograman Java.
- Menginstal Java Development Kit (JDK) di mesin Anda.
-  Aspose.Page untuk perpustakaan Java, yang dapat Anda unduh dari[Dokumentasi Aspose.Page Java](https://reference.aspose.com/page/java/).
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Langkah 1: Siapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda:
```java
String dataDir = "Your Document Directory";
```
## Langkah 2: Buat Aliran Keluaran
Buat aliran keluaran untuk dokumen PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Langkah 3: Buat Opsi Simpan
Buat opsi penyimpanan dengan ukuran A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Langkah 4: Buat Dokumen PS
Buat Dokumen PS baru dengan halaman terbuka:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Langkah 5: Buat Lingkaran
Definisikan lingkaran menggunakan kelas Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Langkah 6: Tentukan Warna Gradien
Buat susunan warna dan pecahan untuk gradien radial:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Langkah 7: Buat AffineTransform
Buat AffineTransform untuk gradien radial:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Langkah 8: Buat Cat Gradien Radial
Buat RadialGradientPaint dengan parameter yang ditentukan:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Langkah 9: Atur Cat dan Isi Lingkaran
Atur cat dan isi lingkaran dengan gradien radial:
```java
document.setPaint(paint);
document.fill(circle);
```
## Langkah 10: Tutup Halaman dan Simpan Dokumen
Tutup halaman saat ini dan simpan dokumen:
```java
document.closePage();
document.save();
```
Selamat! Anda telah berhasil menambahkan Radial Gradient 2 di Java PostScript menggunakan Aspose.Page untuk Java.
## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara menyempurnakan aplikasi Java Anda dengan gradien radial dalam dokumen PostScript. Aspose.Page untuk Java menyediakan seperangkat alat canggih untuk membuat grafik menakjubkan, memungkinkan Anda membawa proyek Java Anda ke level berikutnya.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/page/java/).
### T: Bagaimana cara mengunduh Aspose.Page untuk Java?
 A: Anda dapat mendownloadnya dari[halaman rilis](https://releases.aspose.com/page/java/).
### T: Apakah tersedia uji coba gratis?
 A: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bisakah saya mendapatkan lisensi sementara Aspose.Page untuk Java?
 A: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat mencari dukungan komunitas dan berpartisipasi dalam diskusi?
 J: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

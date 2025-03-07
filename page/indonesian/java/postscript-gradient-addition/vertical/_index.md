---
title: Tambahkan Gradien Vertikal di Java PostScript
linktitle: Tambahkan Gradien Vertikal di Java PostScript
second_title: Aspose.Halaman Java API
description: Jelajahi panduan langkah demi langkah untuk menambahkan gradien vertikal di Java PostScript dengan Aspose.Page untuk Java. Sempurnakan dokumen Anda dengan mudah dengan visual yang hidup.
weight: 14
url: /id/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Vertikal di Java PostScript

## Perkenalan
Selamat datang di panduan langkah demi langkah tentang menambahkan gradien vertikal di Java PostScript menggunakan Aspose.Page untuk Java. Jika Anda ingin menyempurnakan dokumen Anda dengan gradien yang menarik, tutorial ini cocok untuk Anda. Aspose.Page untuk Java menyediakan alat canggih untuk memanipulasi dokumen PostScript dengan lancar.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk memulai:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Sekarang, mari kita uraikan proses penambahan gradien vertikal di Java PostScript menjadi beberapa langkah.
## Langkah 1: Siapkan Direktori Dokumen Anda
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
## Langkah 2: Buat Aliran Output untuk Dokumen PostScript
```java
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Langkah 3: Buat Opsi Simpan dengan Ukuran A4
```java
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
```
## Langkah 4: Buat Dokumen PS Baru
```java
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Langkah 5: Buat Persegi Panjang
```java
//Buat persegi panjang
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Langkah 6: Atur Warna dan Pecahan untuk Gradien
```java
// Buat susunan warna dan pecahan untuk gradien.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Langkah 7: Buat Transformasi Gradien
```java
// Buat transformasi gradien. Komponen skala pada transformasi harus sama dengan lebar dan tinggi persegi panjang.
// Komponen terjemahan adalah offset dari persegi panjang.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Putar gradien sebesar 90 derajat di sekitar titik asal
transform.rotate(90 * (Math.PI / 180));
```
## Langkah 8: Buat Cat Gradien Linier Vertikal
```java
// Buat cat gradien linier vertikal.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Langkah 9: Atur Cat dan Isi Persegi Panjang
```java
// Atur cat
document.setPaint(paint);
// Isi persegi panjang
document.fill(rectangle);
```
## Langkah 10: Tutup Halaman Saat Ini dan Simpan Dokumen
```java
// Tutup halaman saat ini
document.closePage();
// Simpan dokumennya
document.save();
```
Selamat! Anda telah berhasil menambahkan gradien vertikal ke dokumen Java PostScript Anda menggunakan Aspose.Page untuk Java.
## Kesimpulan
Dalam tutorial ini, kami menjelajahi proses menyempurnakan dokumen Anda dengan gradien vertikal cerah menggunakan Aspose.Page untuk Java. Sekarang, Anda dapat meningkatkan manipulasi dokumen Anda dengan menggabungkan visual yang menakjubkan.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Page untuk Java dengan perpustakaan Java lainnya?
Ya, Aspose.Page untuk Java dirancang untuk bekerja secara lancar dengan pustaka Java lainnya.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi tambahan?
 Dokumentasi terperinci tersedia[Di Sini](https://reference.aspose.com/page/java/).
### Bagaimana saya bisa membeli Aspose.Page untuk Java?
 Anda dapat membeli Aspose.Page untuk Java[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada forum untuk diskusi Aspose.Page?
 Ya, Anda dapat bergabung dengan forum komunitas[Di Sini](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

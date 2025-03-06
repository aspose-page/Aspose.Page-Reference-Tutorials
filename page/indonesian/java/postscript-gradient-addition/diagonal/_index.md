---
title: Tambahkan Gradien Diagonal di Java PostScript
linktitle: Tambahkan Gradien Diagonal di Java PostScript
second_title: Aspose.Halaman Java API
description: Sempurnakan dokumen Java PostScript Anda dengan gradien diagonal menggunakan Aspose.Page untuk Java. Ikuti panduan langkah demi langkah kami untuk menambahkan transisi warna cerah dengan mudah.
weight: 10
url: /id/java/postscript-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Diagonal di Java PostScript

## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang menambahkan gradien diagonal di Java PostScript menggunakan Aspose.Page untuk Java. Dalam tutorial ini, kami akan memandu Anda melalui prosesnya, membagi setiap contoh menjadi beberapa langkah. Sebagai penulis SEO yang mahir, saya akan memastikan bahwa kontennya tidak hanya informatif tetapi juga dioptimalkan untuk mesin pencari, sehingga memudahkan pengembang dan peminat untuk mengikutinya.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
- Lingkungan Pengembangan Terintegrasi (IDE) seperti Eclipse atau IntelliJ.
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
## Langkah 1: Buat Aliran Output untuk Dokumen PostScript
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## Langkah 2: Buat Opsi Simpan dengan Ukuran A4
```java
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
```
## Langkah 3: Buat Dokumen PS Baru
```java
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Langkah 4: Buat Persegi Panjang
```java
//Buat persegi panjang
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Langkah 5: Buat Transformasi Gradien
```java
//Buat transformasi gradien. Komponen skala harus sama dengan lebar dan tinggi persegi panjang.
// Komponen terjemahan adalah offset dari persegi panjang.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Putar gradien, lalu skalakan dan terjemahkan untuk transisi warna yang terlihat
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## Langkah 6: Buat Cat Gradien Linier Diagonal
```java
// Buat cat gradien linier diagonal
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## Langkah 7: Atur Cat dan Isi Persegi Panjang
```java
// Atur cat dan isi persegi panjang
document.setPaint(paint);
document.fill(rectangle);
```
## Langkah 8: Tutup Halaman Saat Ini dan Simpan Dokumen
```java
// Tutup halaman saat ini dan simpan dokumen
document.closePage();
document.save();
```
Dengan mengikuti langkah-langkah ini, Anda akan berhasil menambahkan gradien diagonal di Java PostScript menggunakan Aspose.Page untuk Java.
## Kesimpulan
Selamat! Anda telah mempelajari cara menyempurnakan dokumen Java PostScript Anda dengan gradien diagonal menggunakan Aspose.Page untuk Java. Bereksperimenlah dengan parameter berbeda untuk mendapatkan efek visual yang unik.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan perpustakaan ini untuk operasi grafis lainnya di Java?
J: Ya, Aspose.Page untuk Java menyediakan serangkaian fitur untuk bekerja dengan PostScript dan elemen grafis lainnya.
### T: Apakah tersedia uji coba gratis untuk Aspose.Page untuk Java?
 A: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi Aspose.Page untuk Java?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/page/java/).
### T: Bagaimana cara membeli lisensi Aspose.Page untuk Java?
 A: Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).
### T: Butuh bantuan atau ada pertanyaan?
 J: Kunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

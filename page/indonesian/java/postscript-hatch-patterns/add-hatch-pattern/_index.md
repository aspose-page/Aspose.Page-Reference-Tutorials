---
title: Tambahkan Pola Penetasan di Java PostScript
linktitle: Tambahkan Pola Penetasan di Java PostScript
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan pola penetasan yang menawan ke dokumen Java PostScript menggunakan Aspose.Page. Tingkatkan konten visual Anda dengan mudah.
weight: 10
url: /id/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Pola Penetasan di Java PostScript

## Perkenalan
Dalam dunia pemrograman Java, menyempurnakan elemen visual merupakan kebutuhan umum bagi para pengembang. Salah satu peningkatan visual yang menarik adalah penambahan pola penetasan pada dokumen PostScript. Tutorial ini akan memandu Anda melalui proses menambahkan pola penetasan menggunakan Aspose.Page untuk Java.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki pengaturan berikut:
- Lingkungan Pengembangan Java: Pastikan Anda memiliki lingkungan pengembangan Java yang siap.
-  Aspose.Page untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.Page untuk Java. Anda dapat menemukan file yang diperlukan[Di Sini](https://releases.aspose.com/page/java/).
## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda. Gunakan cuplikan kode berikut:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Langkah 1: Siapkan Parameter Awal
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat aliran keluaran untuk dokumen PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Buat opsi penyimpanan dengan ukuran A4
PsSaveOptions options = new PsSaveOptions();
// Buat Dokumen PS baru dengan halaman terbuka
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Langkah 2: Simpan Status Grafik dan Terjemahkan
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Langkah 3: Buat Kotak untuk Setiap Pola
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Langkah 4: Siapkan Pena untuk Garis Besar Pola Persegi
```java
BasicStroke stroke = new BasicStroke(2);
```
## Langkah 5: Ulangi Melalui Pola Penetasan
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (lanjutkan dengan kode yang disediakan)
}
```
## Langkah 6: Kembalikan Status Grafik
```java
document.writeGraphicsRestore();
```
## Langkah 7: Isi Teks dengan Pola Penetasan
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Langkah 8: Garis Besar Teks dengan Pola Penetasan
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Langkah 9: Tutup dan Simpan Dokumen
```java
document.closePage();
document.save();
```
Ikuti langkah-langkah ini, dan Anda akan berhasil menambahkan pola penetasan ke dokumen Java PostScript Anda menggunakan Aspose.Page.
## Kesimpulan
Memasukkan elemen visual seperti pola penetasan dapat meningkatkan daya tarik aplikasi Java Anda secara signifikan. Aspose.Page untuk Java membuat proses ini lancar, memungkinkan Anda membuat dokumen PostScript yang menakjubkan secara visual dengan mudah.
## FAQ
### Bisakah saya menggunakan Aspose.Page untuk Java dengan kerangka Java lainnya?
Ya, Aspose.Page untuk Java dirancang untuk berintegrasi secara mulus dengan berbagai kerangka kerja Java.
### Apakah versi uji coba tersedia untuk Aspose.Page untuk Java?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Page untuk Java?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan lebih banyak tutorial dan dukungan untuk Aspose.Page untuk Java?
 Jelajahi[Aspose.Halaman untuk forum Java](https://forum.aspose.com/c/page/39) untuk tutorial dan dukungan komunitas.
### Apakah ada sumber dokumentasi yang komprehensif untuk Aspose.Page untuk Java?
 Ya, lihat dokumentasinya[Di Sini](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

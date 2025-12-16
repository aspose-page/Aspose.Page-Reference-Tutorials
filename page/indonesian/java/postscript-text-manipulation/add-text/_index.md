---
date: 2025-12-14
description: Pelajari cara mengatur warna teks di Java menggunakan Aspose.Page untuk
  Java, menambahkan teks ke PostScript, dan menerapkan teks stroke untuk gaya dokumen
  yang kaya.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Mengatur Warna Teks Java dengan Aspose.Page – Panduan Manipulasi Teks
url: /id/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java dengan Aspose.Page – Panduan Manipulasi Teks

## Pendahuluan
Selamat datang di panduan langkah‑demi‑langkah kami tentang **set text color java** saat bekerja dengan file PostScript menggunakan Aspose.Page untuk Java. Aspose.Page untuk Java adalah pustaka yang kuat yang memungkinkan pengembang membuat dan **generate postscript file** dokumen, memanipulasi font, dan menata teks dengan presisi. Dalam tutorial ini Anda akan belajar cara menambahkan teks, mengubah warnanya, menyesuaikan ukuran, dan bahkan **apply stroke text** untuk tampilan yang halus.

## Jawaban Cepat
- **Library apa yang memungkinkan saya mengatur warna teks di Java?** Aspose.Page for Java.
- **Apakah saya dapat menggunakan font sistem dan font khusus?** Ya, keduanya didukung.
- **Bagaimana cara mengubah ukuran teks?** Dengan menentukan ukuran font saat membuat `Font` atau `DrFont`.
- **Apakah memungkinkan untuk mengoutline dan mengisi teks sekaligus?** Tentu – gunakan `fillAndStrokeText`.
- **Format output apa yang dihasilkan tutorial ini?** Dokumen PostScript (`.ps`).

## Apa itu “set text color java”?
Mengatur warna teks di Java berarti mendefinisikan objek `Color` yang digunakan mesin rendering (di sini, Aspose.Page) saat menggambar karakter pada halaman. Operasi ini penting untuk membuat dokumen yang secara visual berbeda, terutama saat menghasilkan **postscript documents** secara programatis.

## Mengapa menggunakan Aspose.Page untuk Java?
- **Full control** atas pembuatan PostScript tanpa memerlukan interpreter PostScript native.
- **Support for both system and external fonts**, memungkinkan Anda menyematkan tipografi apa pun yang Anda butuhkan.
- **Easy API** untuk mengisi, mengoutline, dan **fill and stroke text**, memberi Anda fleksibilitas dalam penataan.
- **Cross‑platform** compatibility – tulis sekali, jalankan di mana saja Java dijalankan.

## Prasyarat
Sebelum menyelam lebih dalam, pastikan Anda memiliki:

- Pengetahuan dasar tentang pemrograman Java.
- Pustaka Aspose.Page untuk Java terinstal. Anda dapat mengunduhnya dari [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Font yang diperlukan tersedia di folder yang ditentukan. Detail tambahan ada di [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Impor Paket
Dalam proyek Java Anda, impor paket yang diperlukan untuk Aspose.Page untuk Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Langkah 1: Siapkan Dokumen
Pertama, kami membuat **PostScript document** baru dan mengonfigurasi opsi output.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Cara Mengatur Warna Teks Java Menggunakan Font Sistem
Sekarang kami mendemonstrasikan **set text color java** dengan font yang disediakan sistem.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** Metode `fillText` secara otomatis menggunakan warna saat ini jika Anda tidak memberikan argumen `Color`, yang defaultnya hitam.

## Menggunakan Font Kustom dan Mengubah Ukuran Teks
Anda juga dapat **change text size** dan menggunakan font kustom yang disimpan di folder font Anda.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Mengoutline (Stroke) Teks – Apply Stroke Text
Mengoutline teks memberikan tepi yang tajam. Di sini kami **apply stroke text** menggunakan `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Mengoutline Teks dengan Font Kustom
Teknik yang sama bekerja dengan font kustom.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Langkah 6: Simpan Dokumen
Akhirnya, tutup halaman dan tulis file ke disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Masalah Umum & Solusi
| Masalah | Solusi |
|-------|----------|
| **Font not found** | Pastikan file font ditempatkan di `necessary_fonts` dan path folder ditambahkan dengan benar melalui `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verifikasi bahwa Anda memanggil overload `fillText` atau `outlineText` yang menyertakan argumen `Color`. |
| **Stroke appears too thin** | Tingkatkan lebar `BasicStroke` (mis., `new BasicStroke(3)`). |
| **Document not opening** | Pastikan file `.ps` yang dihasilkan disimpan dengan ekstensi yang benar dan penampil Anda mendukung PostScript. |

## Pertanyaan yang Sering Diajukan

**Q:** Apakah saya dapat menggunakan font kustom saya sendiri dengan Aspose.Page untuk Java?  
A: Ya, Anda dapat menggunakan font kustom dengan menentukan nama font dan ukuran dalam kelas `DrFont`.

**Q:** Bagaimana cara mengubah warna teks?  
A: Anda dapat mengatur warna yang diinginkan menggunakan kelas `Color` saat mengisi atau mengoutline teks.

**Q:** Apakah memungkinkan menambahkan beberapa halaman ke dokumen PostScript?  
A: Tentu! Anda dapat membuat beberapa halaman dengan mengulangi langkah pembuatan dokumen dan penyimpanan.

**Q:** Apa tujuan kelas `ExternalFontCache`?  
A: `ExternalFontCache` digunakan untuk mengambil font kustom, memastikan mereka tersedia untuk manipulasi teks.

**Q:** Apakah saya dapat menerapkan stroke yang berbeda pada teks yang dioutline?  
A: Ya, Anda dapat menyesuaikan lebar dan warna stroke menggunakan kelas `Stroke` dan kelas `Color`, masing‑masing.

## Kesimpulan
Selamat! Anda kini tahu cara **set text color java**, mengubah ukuran font, **apply stroke text**, dan **create postscript document** menggunakan Aspose.Page untuk Java. Bereksperimenlah dengan berbagai font, warna, dan gaya outline untuk menghasilkan output PostScript yang tampak profesional.

---

**Terakhir Diperbarui:** 2025-12-14  
**Diuji Dengan:** Aspose.Page for Java 23.12 (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
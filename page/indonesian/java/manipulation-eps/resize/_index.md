---
date: 2026-02-07
description: Pelajari cara mengubah ukuran file EPS di Java dan mengubah dimensi EPS
  menggunakan Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara mengubah
  ukuran EPS dengan poin, inci, milimeter, atau persentase.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Cara Mengubah Ukuran File EPS di Java dengan Aspose.Page
url: /id/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah Ukuran File EPS di Java dengan Aspose.Page

## Introduction
Jika Anda mencari cara yang dapat diandalkan **cara mengubah ukuran EPS** secara programatik, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas cara mengubah ukuran gambar EPS di Java menggunakan pustaka Aspose.Page. Baik Anda perlu menggandakan ukuran, memperkecil ke ukuran tertentu, atau bekerja dengan persentase, langkah‑langkah di bawah ini memberi Anda kontrol penuh atas dimensi output. Memahami **cara mengubah ukuran eps** sangat penting ketika Anda perlu menyesuaikan grafik untuk tata letak cetak atau resolusi layar yang berbeda.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I resize using points, inches, or millimeters?** Ya – API mendukung ketiga satuan tersebut serta persentase.  
- **Do I need a license for development?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **What Java version is required?** Java 8 atau lebih baru.  
- **Is the code thread‑safe?** Setiap instance `PsDocument` terisolasi, sehingga Anda dapat memproses file secara paralel.  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) adalah format grafis vektor yang populer digunakan dalam penerbitan dan percetakan. Terkadang file EPS asli dibuat dengan ukuran yang tidak cocok dengan output target Anda – misalnya, logo yang dirancang pada 72 pts mungkin perlu menjadi 144 pts untuk brosur yang lebih besar. Mengetahui **cara mengubah ukuran eps** memungkinkan Anda mempertahankan kualitas vektor sambil menyesuaikan dimensi ke alur kerja apa pun.

## Why Use Aspose.Page for Resizing EPS?
- **Full‑control over units** – kontrol penuh atas satuan – poin, inci, milimeter, atau persentase.  
- **No external dependencies** – tanpa dependensi eksternal – API Java murni, tanpa pustaka native.  
- **High performance** – kinerja tinggi – cocok untuk pemrosesan batch di server.  
- **Preserves vector fidelity** – mempertahankan kesetiaan vektor – output tetap dapat diskalakan tanpa rasterisasi.

## Prerequisites
Sebelum kita masuk ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Pustaka Aspose.Page for Java. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- Pemahaman dasar tentang pemrograman Java.  

## Import Packages
Dalam proyek Java Anda, sertakan impor yang diperlukan sehingga Anda dapat bekerja dengan objek Aspose.Page dan aliran I/O standar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
Pustaka ini memungkinkan Anda **mengubah dimensi eps** cukup dengan memilih enum `Units` yang sesuai. Di bawah ini kami akan menunjukkan pola lima langkah yang sama untuk poin, inci, milimeter, dan persentase. Satu‑satunya yang berubah adalah satuan yang Anda berikan ke `resizeEps`.

## How to Resize EPS Using Points
Berikut adalah contoh lengkap langkah‑demi‑langkah yang menggandakan ukuran file EPS menggunakan poin sebagai satuan pengukuran.

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
Pola lima langkah yang sama berlaku; cukup ganti `Units.Points` dengan `Units.Inches` dan sesuaikan faktor skala ke nilai inci yang diinginkan.

## How to Resize EPS Using Millimeters
Lagi, ikuti langkah yang sama, ganti satuannya menjadi `Units.Millimeters`. Ini berguna ketika Anda memerlukan dimensi berbasis metrik untuk alur kerja cetak.

## How to Resize EPS Using Percentages
Untuk skala berbasis persentase, tetap gunakan satuan `Units.Percent`. Kalikan lebar dan tinggi asli dengan persentase yang diinginkan (misalnya, `0.5` untuk pengurangan 50 %).

## Common Pitfalls & Tips
- **Always close streams** – **Selalu tutup aliran** – Pada kode produksi, bungkus aliran dengan try‑with‑resources untuk menghindari penguncian file.  
- **Preserve aspect ratio** – **Pertahankan rasio aspek** – Kalikan lebar dan tinggi dengan faktor yang sama kecuali Anda memang menginginkan distorsi.  
- **Check DPI** – **Periksa DPI** – Mengubah ukuran tidak mengubah DPI; jika Anda memerlukan DPI yang berbeda, sesuaikan secara terpisah setelah mengubah ukuran.  
- **Thread safety** – **Keamanan thread** – Buat `PsDocument` baru per thread; berbagi instance yang sama dapat menyebabkan hasil yang tidak terduga.  

## Frequently Asked Questions

**Q: Can I use this library for other image formats?**  
A: Tidak, Aspose.Page khusus untuk file PostScript dan EPS saja.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Ya, Anda dapat menjelajahi versi percobaan gratis **[di sini](https://releases.aspose.com/)**.

**Q: Where can I find additional help and discussions?**  
A: Kunjungi **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** untuk dukungan komunitas.

**Q: How can I obtain a temporary license?**  
A: Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q: Are there any example projects available?**  
A: Ya, periksa dokumentasi **[di sini](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
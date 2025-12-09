---
date: 2025-12-02
description: Pelajari cara mengubah ukuran file EPS di Java dengan mudah menggunakan
  Aspose.Page. Panduan langkah demi langkah ini menunjukkan cara mengubah ukuran EPS
  menggunakan poin, inci, milimeter, atau persentase.
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
Jika Anda mencari cara yang dapat diandalkan **cara mengubah ukuran EPS** secara programatis, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas cara mengubah ukuran gambar EPS di Java menggunakan pustaka Aspose.Page. Baik Anda perlu menggandakan ukuran, memperkecil ke ukuran tertentu, atau bekerja dengan persentase, langkah‑langkah di bawah ini memberi Anda kontrol penuh atas dimensi output.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I resize using points, inches, or millimeters?** Yes – the API supports all three units plus percentages.  
- **Do I need a license for development?** A free trial works for testing; a license is required for production.  
- **What Java version is required?** Java 8 or later.  
- **Is the code thread‑safe?** Each `PsDocument` instance is isolated, so you can process files in parallel.

## Prerequisites
Sebelum kita masuk ke kode, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Aspose.Page for Java library. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- Pemahaman dasar tentang pemrograman Java.  

## Import Packages
Di proyek Java Anda, sertakan impor yang diperlukan sehingga Anda dapat bekerja dengan objek Aspose.Page dan aliran I/O standar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

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
Pola lima langkah yang sama berlaku; cukup ganti `Units.Points` dengan `Units.Inches` dan sesuaikan faktor skala sesuai kebutuhan.

## How to Resize EPS Using Millimeters
Sekali lagi, ikuti langkah yang sama, ganti satuannya menjadi `Units.Millimeters`. Ini berguna ketika Anda memerlukan dimensi berbasis metrik untuk alur kerja cetak.

## How to Resize EPS Using Percentages
Untuk skala berbasis persentase, pertahankan satuan sebagai `Units.Percent`. Kalikan lebar dan tinggi asli dengan persentase yang diinginkan (misalnya, `0.5` untuk pengurangan 50 %).

## Common Pitfalls & Tips
- **Selalu tutup aliran** – Pada kode produksi, bungkus aliran dengan try‑with‑resources untuk menghindari penguncian file.  
- **Pertahankan rasio aspek** – Kalikan lebar dan tinggi dengan faktor yang sama kecuali Anda memang ingin distorsi.  
- **Periksa DPI** – Mengubah ukuran tidak mengubah DPI; jika Anda memerlukan DPI yang berbeda, sesuaikan secara terpisah setelah mengubah ukuran.

## Conclusion
Anda sekarang tahu **cara mengubah ukuran file EPS** di Java menggunakan Aspose.Page, baik Anda lebih suka poin, inci, milimeter, atau persentase. Fleksibilitas ini memungkinkan Anda mengintegrasikan manipulasi EPS ke dalam pipeline otomatis, utilitas desktop, atau layanan sisi‑server.

## Frequently Asked Questions

**Q: Can I use this library for other image formats?**  
A: No, Aspose.Page is specialized for PostScript and EPS files only.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can explore the free trial **[di sini](https://releases.aspose.com/)**.

**Q: Where can I find additional help and discussions?**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** for community support.

**Q: How can I obtain a temporary license?**  
A: You can get a temporary license **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q: Are there any example projects available?**  
A: Yes, check the documentation **[di sini](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
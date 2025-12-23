---
date: 2025-12-23
description: Dengan mudah **mengonversi XPS ke PNG** dalam Java menggunakan Aspose.Page.
  Panduan ini menunjukkan cara merender XPS ke file gambar dengan solusi yang andal
  dan ramah pengembang.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Mengonversi XPS ke PNG di Java
url: /id/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convert XPS to PNG in Java

## Introduction
Di dunia pengembangan perangkat lunak yang dinamis, kebutuhan untuk **mengonversi XPS ke PNG** (XML Paper Specification ke Portable Network Graphics) muncul secara sering. Untuk menyelesaikan tugas ini dengan mulus di Java, Aspose.Page menyediakan solusi yang kuat. Pada tutorial ini, kami akan memandu proses mengonversi XPS ke PNG menggunakan Aspose.Page untuk Java.

## Quick Answers
- **What library handles the conversion?** Aspose.Page for Java  
- **Which formats are involved?** XPS (source) → PNG (output)  
- **Do I need a license for production?** Yes, a commercial license is required  
- **Can I set image resolution?** Yes, using `PngSaveOptions.setResolution()`  
- **Is it possible to select specific pages?** Absolutely – provide page numbers in the options object  

## Why Convert XPS to PNG?
Merender XPS ke file gambar berguna ketika Anda perlu menampilkan dokumen di web, menyematkannya dalam laporan, atau menghasilkan thumbnail untuk pratinjau. PNG menawarkan kompresi lossless dan dukungan browser yang luas, menjadikannya pilihan ideal untuk representasi visual berkualitas tinggi dari konten XPS.

## Prerequisites
Sebelum kita masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Pastikan JDK terinstal di sistem Anda.  
2. Aspose.Page for Java: Unduh dan instal pustaka Aspose.Page. Anda dapat menemukan tautan unduhan [di sini](https://releases.aspose.com/page/java/).  
3. Integrated Development Environment (IDE): Pilih IDE yang kompatibel dengan Java seperti IntelliJ IDEA atau Eclipse.  

## How to convert XPS to PNG in Java
Berikut adalah panduan langkah‑demi‑langkah yang menjelaskan **cara mengonversi XPS** menjadi gambar PNG, termasuk potongan kode yang dapat Anda salin langsung ke proyek Anda.

### Import Packages
Di proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Page. Tambahkan pernyataan impor berikut di awal file Java Anda:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Step 1: Set Document Directory
Tentukan folder yang berisi file XPS sumber Anda dan tempat file PNG akan disimpan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Load XPS Document
Buat instance `XpsDocument` yang memuat file XPS sumber.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 3: Initialize Options
Konfigurasikan opsi output PNG. Di sini Anda dapat mengatur smoothing, resolusi, dan menentukan halaman mana yang akan dirender.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Step 4: Create Rendering Device
Buat `ImageDevice` yang akan menampung data gambar yang dirender.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Step 5: Save and Iterate
Render dokumen XPS, kemudian tulis setiap array byte PNG yang dihasilkan ke file di disk.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Dengan mengikuti langkah‑langkah ini, Anda dapat dengan mudah **merender XPS ke gambar** dalam format PNG menggunakan Aspose.Page untuk Java.

## Conclusion
Kesimpulannya, Aspose.Page untuk Java menyederhanakan proses konversi XPS ke PNG, memberikan pengembang alat yang dapat diandalkan dan efisien. Integrasikan pustaka ini ke dalam proyek Java Anda untuk memperlancar tugas manipulasi dokumen.

## FAQs
### Can I use Aspose.Page for Java in commercial projects?
Yes, Aspose.Page is a commercial product. You can find licensing information [here](https://purchase.aspose.com/buy).

### Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Where can I find the documentation for Aspose.Page for Java?
The comprehensive documentation is available [here](https://reference.aspose.com/page/java/).

### How do you obtain a temporary license for testing purposes?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there community forums for Aspose.Page discussions?
Yes, visit the community forums [here](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I convert only selected pages of an XPS file?**  
A: Absolutely. Use the `setPageNumbers` method in `PngSaveOptions` to specify the pages you want to render.

**Q: What image resolution is recommended for high‑quality PNGs?**  
A: A resolution of 300 dpi is a good balance between quality and file size, but you can adjust it via `options.setResolution()`.

**Q: Does the API support multi‑threaded conversion for large documents?**  
A: Yes, you can invoke the conversion logic in parallel threads, each handling a different page or document partition.

**Q: How do I handle memory usage when converting very large XPS files?**  
A: Process pages sequentially and release the `FileOutputStream` after each write, as shown in the sample code.

**Q: Is there a way to add custom metadata to the generated PNG files?**  
A: While `PngSaveOptions` does not directly expose metadata fields, you can post‑process the PNG using standard image libraries to embed metadata.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-13
description: Pelajari cara menambahkan teks pada halaman ASP menggunakan Java, mengatur
  gaya font Java, dan cara menambahkan teks Unicode dengan Aspose.Page. Ikuti panduan
  langkah demi langkah kami.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Halaman ASP Menambah Teks – Unicode dalam Java PostScript
url: /id/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode dalam Java PostScript

## Introduction
Jika Anda perlu **asp page add text** dalam alur kerja Java PostScript sambil mempertahankan karakter Unicode, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas cara menambahkan teks Unicode, mengatur gaya font, dan menyimpan hasilnya menggunakan **Aspose.Page for Java**. Pada akhir tutorial Anda akan memahami cara **set font style java** dan cara menambahkan teks unicode secara efisien dalam proyek Anda.

## Quick Answers
- **Library apa yang dapat menambahkan teks Unicode dalam Java PostScript?** Aspose.Page for Java.  
- **Metode utama mana yang menambahkan teks?** `doc.addGlyphs(...)` dengan objek `XpsGlyphs`.  
- **Apakah saya memerlukan font khusus untuk Unicode?** Font TrueType/OpenType apa pun yang mendukung kode poin yang diperlukan (misalnya, Arial).  
- **Bisakah saya mengubah gaya font?** Ya, dengan menggunakan `XpsFontStyle` (Regular, Bold, Italic, dll.).  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi Aspose.Page yang valid diperlukan untuk penggunaan non‑trial.

## What is asp page add text?
`asp page add text` mengacu pada proses menyisipkan string teks ke dalam dokumen PostScript atau XPS menggunakan API Aspose.Page. API ini mengabstraksi perintah PostScript tingkat rendah, memungkinkan Anda bekerja dengan objek tingkat tinggi seperti `XpsGlyphs`.

## Why use Aspose.Page to set font style java and add Unicode text?
- **Dukungan Unicode penuh** – Menangani skrip kanan‑ke‑kiri dan glif kompleks.  
- **API sederhana** – Pemanggilan satu baris untuk menambahkan teks dan menerapkan gaya.  
- **Lintas platform** – Berfungsi pada lingkungan yang kompatibel dengan Java apa pun.  
- **Tanpa dependensi eksternal** – Tidak memerlukan mesin rendering tambahan.

## Prerequisites
Sebelum kita memulai tutorial, pastikan Anda memiliki prasyarat berikut:

1. **Java Development Kit (JDK)** – Pastikan Java terinstal di mesin Anda.  
2. **Aspose.Page for Java** – Unduh dan instal pustaka Aspose.Page dari [tautan unduhan](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Pilih IDE Java pilihan Anda seperti IntelliJ IDEA atau Eclipse.

## Import Packages
Dalam proyek Java Anda, impor paket yang diperlukan untuk Aspose.Page. Tambahkan baris berikut ke kode Anda:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
Buat proyek Java baru di IDE Anda dan atur struktur proyek. Pastikan untuk menyertakan pustaka Aspose.Page dalam dependensi proyek Anda.

## Step 2: Initialize XPS Document
Mulailah dengan menginisialisasi dokumen XPS baru di dalam proyek Anda:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Sekarang, mari tambahkan teks Unicode ke dokumen XPS Anda menggunakan pustaka Aspose.Page. Gunakan cuplikan kode berikut:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Segmen kode ini menambahkan teks Unicode **"AVAJ rof SPX.esopsA"** ke dokumen XPS pada koordinat (400, 200) dengan font dan gaya yang ditentukan. Perhatikan bagaimana pemanggilan `setBidiLevel(1)` mengaktifkan rendering kanan‑ke‑kiri untuk tampilan Unicode yang tepat.

## Step 4: Save the Document
Simpan dokumen XPS yang dihasilkan menggunakan kode berikut:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
Selamat! Anda telah berhasil **asp page add text** dan mengatur gaya font dalam skenario Java PostScript menggunakan Aspose.Page. Metode ini memberi Anda kontrol yang halus atas rendering dan styling Unicode, menjadikannya ideal untuk laporan, faktur, dan grafik yang diinternasionalisasi.

Feel free to explore more features and capabilities of Aspose.Page in the [documentation](https://reference.aspose.com/page/java/).

## Frequently Asked Questions

**Q:** Can I use Aspose.Page for Java with other programming languages?  
**A:** Aspose.Page is primarily designed for Java, but Aspose provides libraries for various programming languages.

**Q:** Is there a free trial available?  
**A:** Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).

**Q:** Where can I find support and discussions about Aspose.Page?  
**A:** Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for support and discussions.

**Q:** How can I obtain a temporary license for Aspose.Page?  
**A:** You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q:** What are the available font styles in Aspose.Page?  
**A:** Aspose.Page supports font styles such as Regular, Bold, Italic, and BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---
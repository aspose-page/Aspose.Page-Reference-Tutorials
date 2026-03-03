---
date: 2025-12-17
description: Pelajari cara menambahkan teks Unicode dalam Java PostScript menggunakan
  Aspose.Page – panduan langkah demi langkah tentang cara menambahkan string Unicode
  dengan mudah.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Cara Menambahkan Teks Unicode di PostScript Java dengan Aspose.Page
url: /id/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Teks Unicode di Java PostScript dengan Aspose.Page

## Pendahuluan
Jika Anda bertanya-tanya **cara menambahkan Unicode** ke karakter dalam alur kerja PostScript (atau XPS) berbasis Java, Anda berada di tempat yang tepat. Pada tutorial ini kami akan membimbing Anda melalui langkah‑langkah tepat untuk menyematkan string Unicode menggunakan pustaka Aspose.Page untuk Java. Pada akhir panduan, Anda akan dapat menyisipkan teks spesifik bahasa apa pun—Arab, Cina, emoji, apa saja—langsung ke output PostScript Anda.

## Jawaban Cepat
- **Apa perpustakaan yang dibutuhkan?** Aspose.Page for Java  
- **Bisakah saya menambahkan skrip kanan‑ke‑kiri?** Ya, atur level Bidi seperti yang ditunjukkan dalam kode  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi  
- **IDE mana yang paling cocok?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **Apakah kode ini lintas‑platform?** Tentu saja—jalankan di Windows, macOS, atau Linux  

## Apa itu “cara menambahkan Unicode” dalam konteks PostScript?
Menambahkan Unicode berarti menyisipkan karakter yang diwakili oleh titik kode di luar rentang ASCII dasar. Aspose.Page mengabstraksi detail pengkodean tingkat rendah, memungkinkan Anda fokus pada konten teks dan penempatan visualnya.

## Mengapa menggunakan Aspose.Page untuk teks Unicode?
- **Dukungan Unicode penuh** – Menangani skrip kompleks, ligatur, dan bahasa kanan‑ke‑kiri.  
- **Tanpa ketergantungan eksternal** – Tidak perlu mengelola file font secara manual; API bekerja dengan font sistem.  
- **API yang sederhana** – Beberapa pemanggilan metode sudah cukup untuk merender teks multibahasa.  

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK)** – Versi terbaru apa saja (8 atau lebih baru).  
2. **Aspose.Page for Java** – Unduh dan instal pustaka dari [tautan unduhan](https://releases.aspose.com/page/java/).  
3. **IDE pilihan Anda** – IntelliJ IDEA, Eclipse, atau IDE Java lain yang Anda sukai.  

## Impor Paket
Tambahkan kelas Aspose.Page yang diperlukan ke file sumber Java Anda:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru, tambahkan JAR Aspose.Page ke jalur build proyek, dan buat folder tempat file XPS yang dihasilkan akan disimpan. Folder ini akan dirujuk nanti sebagai `dataDir`.

## Langkah 2: Inisialisasi Dokumen XPS
Buat dokumen XPS kosong yang akan menampung konten:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Tambahkan Teks Unicode
Sekarang kita akan benar‑benarnya menambahkan string Unicode. Contoh di bawah menulis frasa terbalik “AVAJ rof SPX.esopsA”, yang hanya berisi karakter ASCII, tetapi Anda dapat menggantinya dengan teks Unicode apa pun (misalnya Arab “مرحبا” atau Cina “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** Untuk merender bahasa kanan‑ke‑kiri dengan benar, atur `glyphs.setBidiLevel(1);`. Untuk skrip kiri‑ke‑kanan Anda dapat mengabaikan baris ini.

## Langkah 4: Simpan Dokumen
Simpan file XPS ke disk:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Setelah menjalankan program, buka `AddEncodingText_out.xps` yang dihasilkan dengan penampil XPS apa pun untuk melihat teks Unicode yang dirender pada koordinat yang ditentukan.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|---------|--------|--------|
| Teks muncul sebagai kotak | Font tidak ditemukan atau tidak mendukung karakter | Gunakan font yang mencakup glyph yang diperlukan (misalnya “Arial Unicode MS”) |
| Teks kanan‑ke‑kiri ditampilkan kiri‑ke‑kanan | Level Bidi tidak diatur | Panggil `glyphs.setBidiLevel(1);` |
| File tidak tersimpan | Jalur `dataDir` tidak valid atau tidak memiliki izin menulis | Pastikan direktori ada dan aplikasi memiliki akses menulis |

## Pertanyaan yang Sering Diajukan
### Apakah saya dapat menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama dirancang untuk Java, tetapi Aspose menyediakan pustaka untuk berbagai bahasa pemrograman.

### Apakah tersedia versi percobaan gratis?
Ya, Anda dapat mengakses versi percobaan gratis Aspose.Page [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan dan diskusi tentang Aspose.Page?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan dan diskusi.

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Page?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Apa saja gaya font yang tersedia di Aspose.Page?
Aspose.Page mendukung gaya font seperti Regular, Bold, Italic, dan BoldItalic.

## Kesimpulan
Anda kini telah menguasai **cara menambahkan Unicode** ke dokumen Java PostScript (XPS) menggunakan Aspose.Page. Kemampuan ini membuka pintu bagi pelaporan multibahasa, faktur internasional, dan skenario apa pun yang memerlukan karakter non‑ASCII. Jangan ragu untuk menjelajahi fitur tambahan seperti rotasi teks, jalur pemotongan, atau penyematan font khusus—detailnya tersedia di [dokumentasi resmi](https://reference.aspose.com/page/java/).

---

**Terakhir Diperbarui:** 2025-12-17  
**Diuji Dengan:** Aspose.Page for Java 23.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-03-13
description: Pelajari cara menambahkan gradien ke dokumen XPS dalam Java menggunakan
  Aspose.Page dan cara menyesuaikan titik-titik gradien untuk efek horizontal yang
  menakjubkan.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Gradien – Gradien Horizontal di Java XPS
url: /id/java/xps-gradient-addition/horizontal/
weight: 11
---

 ensure no extra spaces or missing elements.

Let's craft final.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien – Gradien Horizontal dalam Java XPS

## Introduction
Selamat datang di panduan langkah‑demi‑langkah ini tentang **cara menambahkan gradien** ke dokumen XPS menggunakan Java. Dalam tutorial ini Anda akan belajar cara menambahkan gradien horizontal, mengapa hal ini penting untuk penyempurnaan visual, dan cara **menyesuaikan gradient stops** untuk kontrol warna yang presisi. Aspose.Page untuk Java memudahkan pekerjaan dengan dokumen XPS (XML Paper Specification), memungkinkan Anda fokus pada desain daripada penanganan file tingkat‑rendah.

## Quick Answers
- **Perpustakaan apa yang dibutuhkan?** Aspose.Page for Java  
- **Versi Java mana yang dapat digunakan?** Runtime Java 8+ apa pun  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Bisakah saya mengubah arah gradien?** Ya – cukup ubah titik mulai/akhir dari kuas linear  
- **Apakah memungkinkan menambahkan beberapa gradien?** Tentu – ulangi langkah pembuatan path dengan kuas yang berbeda  

## What is a Horizontal Gradient in XPS?
Gradien horizontal adalah transisi warna yang halus dari kiri ke kanan pada sebuah bentuk. Di XPS, hal ini direpresentasikan oleh kuas gradien linear yang menginterpolasi antara **gradient stops** yang telah didefinisikan. Efek visual ini biasanya dipakai untuk spanduk, tombol, dan isian latar belakang.

## Why Use Aspose.Page for Java?
- **Dukungan XPS penuh** – buat, edit, dan render tanpa alat pihak ketiga.  
- **API sederhana** – objek tingkat‑tinggi seperti `XpsDocument`, `XpsPath`, dan `XpsGradientBrush` menyembunyikan kompleksitas XML.  
- **Performa** – dioptimalkan untuk dokumen besar dan pemrosesan batch.  

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – Instal JDK terbaru dari [java.com](https://www.java.com).  
2. **Perpustakaan Aspose.Page for Java** – Unduh JAR dari [dokumentasi Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## Import Packages
Mulailah dengan mengimpor kelas‑kelas yang diperlukan. Impor ini memberi Anda akses ke pembuatan dokumen, penanganan gradien, dan geometri dasar.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Step 1: Initialize the XPS Document
Buat instance `XpsDocument` baru dan arahkan ke folder tempat Anda ingin menyimpan hasilnya.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
Tentukan daftar **gradient stops** yang mengontrol warna dan posisi setiap titik transisi. Contoh di bawah membangun gradien berwarna pelangi yang hidup.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### How to customize gradient stops
- **Warna** – Gunakan `doc.createColor(alpha, red, green, blue)` untuk mengatur nilai ARGB apa pun.  
- **Posisi** – Argumen kedua (`float` antara `0` dan `1`) menentukan di mana stop muncul sepanjang garis gradien. Sesuaikan nilai ini untuk menggeser warna ke kiri atau kanan.

## Step 3: Add Path with Gradient
Buat path persegi panjang, terapkan transformasi bila diperlukan, dan isi dengan kuas gradien linear. Kuas ini menggunakan dua titik (`(10,0)` ke `(228,0)`) untuk menghasilkan efek horizontal. Karena koordinat Y‑nya identik, kuas ini berfungsi sebagai **kuas gradien horizontal**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** Menggunakan kembali daftar `stops` yang sama untuk beberapa path dapat meningkatkan performa, tetapi ingat untuk memanggil `clear()` sebelum menambahkan stop baru.

## Step 4: Save the Document
Simpan file XPS ke disk. Sekarang Anda dapat membukanya dengan penampil XPS apa pun untuk melihat gradien horizontal beraksi.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## How to Apply Multiple Gradients
Jika Anda ingin **menerapkan beberapa gradien** dalam dokumen XPS yang sama, cukup ulangi langkah “Create Horizontal Gradient” dan “Add Path with Gradient” untuk setiap bentuk baru. Gunakan daftar baru objek `XpsGradientStop` (atau bersihkan daftar yang ada) dan tetapkan `LinearGradientBrush` baru dengan titik mulai/akhir masing‑masing. Pendekatan ini memungkinkan Anda melapisi gradien, membuat latar belakang kompleks, atau menyorot elemen UI yang berbeda dalam satu halaman.

## Why This Matters – Benefits of the Horizontal Gradient Brush
- **Kedalaman visual:** Kuas gradien horizontal menambahkan kesan tiga‑dimensi halus tanpa gambar tambahan.  
- **Efisiensi ukuran file:** Gradien disimpan sebagai definisi vektor, menjaga file XPS tetap ringan.  
- **Skalabilitas:** Karena gradien berbasis vektor, ia skalabel dengan bersih pada tampilan resolusi tinggi.  

## Common Issues & Solutions
| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| Gradien muncul solid | Tidak ada gradient stops yang ditambahkan atau kuas tidak diatur | Pastikan `path.setFill(...)` menggunakan `LinearGradientBrush` dan bahwa stops ditambahkan melalui `getGradientStops().addAll(stops)`. |
| Warna tampak pudar | Nilai alpha (parameter pertama) salah | Gunakan `255` untuk warna sepenuhnya opak kecuali transparansi diinginkan. |
| Ukuran path tidak tepat | Nilai matriks transformasi salah | Sesuaikan parameter matriks (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Frequently Asked Questions

**Q: Bisakah saya menerapkan beberapa gradien dalam satu dokumen XPS?**  
A: Ya, Anda dapat menambahkan beberapa path, masing‑masing dengan kuas gradiennya, untuk membuat desain berlapis yang kompleks.

**Q: Apakah Aspose.Page kompatibel dengan versi Java terbaru?**  
A: Aspose.Page for Java secara rutin diperbarui dan berfungsi dengan Java 8 serta rilis yang lebih baru.

**Q: Apakah ada tipe gradien lain yang tersedia di Aspose.Page?**  
A: Selain gradien linear, Aspose.Page juga mendukung gradien radial untuk transisi warna melingkar.

**Q: Bisakah saya menyesuaikan warna dan posisi gradient stops?**  
A: Tentu! Anda memiliki kontrol penuh atas warna ARGB setiap stop dan posisi relatifnya (rentang 0‑1).

**Q: Apakah ada forum komunitas untuk Aspose.Page tempat saya dapat meminta bantuan?**  
A: Ya, Anda dapat mengunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan bantuan.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
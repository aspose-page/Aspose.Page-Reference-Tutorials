---
date: 2025-12-25
description: Pelajari cara menambahkan gradien ke dokumen XPS dalam Java menggunakan
  Aspose.Page dan cara menyesuaikan titik-titik gradien untuk efek horizontal yang
  menakjubkan.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Gradien – Gradien Horizontal di Java XPS
url: /id/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien – Gradien Horizontal dalam Java XPS

## Pendahuluan
Selamat datang di panduan langkah‑demi‑langkah ini tentang **cara menambahkan gradien** ke dokumen XPS menggunakan Java. Dalam tutorial ini Anda akan belajar cara menambahkan gradien horizontal, mengapa hal itu penting untuk penyempurnaan visual, dan cara **menyesuaikan gradient stops** untuk kontrol warna yang tepat. Aspose.Page untuk Java mempermudah bekerja dengan dokumen XPS (XML Paper Specification), memungkinkan Anda fokus pada desain daripada penanganan file tingkat rendah.

## Jawaban Cepat
- **Library apa yang dibutuhkan?** Aspose.Page for Java  
- **Versi Java mana yang bekerja?** Runtime Java 8+ apa pun  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Bisakah saya mengubah arah gradien?** Ya – cukup ubah titik mulai/akhir dari linear brush  
- **Apakah memungkinkan menambahkan beberapa gradien?** Tentu – ulangi langkah pembuatan path dengan brush yang berbeda  

## Apa Itu Gradien Horizontal dalam XPS?
Gradien horizontal adalah transisi warna yang halus dari kiri ke kanan pada sebuah bentuk. Dalam XPS hal ini direpresentasikan oleh linear gradient brush yang menginterpolasi antara **gradient stops** yang telah didefinisikan. Efek visual ini biasanya digunakan untuk spanduk, tombol, dan pengisian latar belakang.

## Mengapa Menggunakan Aspose.Page untuk Java?
- **Dukungan XPS penuh** – membuat, mengedit, dan merender tanpa alat pihak ketiga.  
- **API sederhana** – objek tingkat tinggi seperti `XpsDocument`, `XpsPath`, dan `XpsGradientBrush` menyembunyikan kompleksitas XML.  
- **Kinerja** – dioptimalkan untuk dokumen besar dan pemrosesan batch.  

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – Instal JDK terbaru dari [java.com](https://www.java.com).  
2. **Pustaka Aspose.Page untuk Java** – Unduh JAR dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Impor Paket
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

## Langkah 1: Inisialisasi Dokumen XPS
Buat instance `XpsDocument` baru dan arahkan ke folder tempat Anda ingin menyimpan hasilnya.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Langkah 2: Buat Gradien Horizontal
Definisikan daftar **gradient stops** yang mengontrol warna dan posisi setiap titik transisi. Contoh di bawah membangun gradien berwarna pelangi yang hidup.

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

### Cara menyesuaikan gradient stops
- **Warna** – Gunakan `doc.createColor(alpha, red, green, blue)` untuk menetapkan nilai ARGB apa pun.  
- **Posisi** – Argumen kedua (`float` antara `0` dan `1`) menentukan di mana stop muncul sepanjang garis gradien. Sesuaikan nilai ini untuk menggeser warna ke kiri atau kanan.

## Langkah 3: Tambahkan Path dengan Gradien
Buat path berbentuk persegi panjang, terapkan transformasi jika diperlukan, dan isi dengan linear gradient brush. Brush ini menggunakan dua titik (`(10,0)` ke `(228,0)`) untuk menghasilkan efek horizontal.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** Menggunakan kembali daftar `stops` yang sama untuk beberapa path dapat meningkatkan kinerja, tetapi ingat untuk `clear()` sebelum menambahkan stops baru.

## Langkah 4: Simpan Dokumen
Simpan file XPS ke disk. Anda sekarang dapat membukanya dengan penampil XPS apa pun untuk melihat gradien horizontal beraksi.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Masalah Umum & Solusinya
| Masalah | Alasan | Solusi |
|---------|--------|--------|
| Gradien muncul solid | Tidak ada gradient stops yang ditambahkan atau brush tidak diatur | Pastikan `path.setFill(...)` menggunakan `LinearGradientBrush` dan bahwa stops ditambahkan melalui `getGradientStops().addAll(stops)`. |
| Warna tampak pudar | Nilai alpha (parameter pertama) salah | Gunakan `255` untuk warna sepenuhnya tidak transparan kecuali transparansi diinginkan. |
| Ukuran path tidak tepat | Nilai matriks transformasi salah | Sesuaikan parameter matriks (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menerapkan beberapa gradien dalam satu dokumen XPS?**  
**J:** Ya, Anda dapat menambahkan beberapa path, masing‑masing dengan brush gradiennya sendiri, untuk membuat desain berlapis yang kompleks.

**T: Apakah Aspose.Page kompatibel dengan versi Java terbaru?**  
**J:** Aspose.Page untuk Java secara rutin diperbarui dan bekerja dengan Java 8 dan rilis yang lebih baru.

**T: Apakah ada tipe gradien lain yang tersedia di Aspose.Page?**  
**J:** Selain gradien linear, Aspose.Page juga mendukung gradien radial untuk transisi warna melingkar.

**T: Bisakah saya menyesuaikan warna dan posisi gradient stops?**  
**J:** Tentu! Anda memiliki kontrol penuh atas setiap warna ARGB stop dan posisi relatifnya (rentang 0‑1).

**T: Apakah ada forum komunitas untuk Aspose.Page dimana saya dapat meminta bantuan?**  
**J:** Ya, Anda dapat mengunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk terhubung dengan komunitas dan mendapatkan bantuan.

---

**Terakhir Diperbarui:** 2025-12-25  
**Diuji Dengan:** Aspose.Page for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
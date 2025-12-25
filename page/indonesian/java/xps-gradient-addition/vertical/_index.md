---
date: 2025-12-25
description: Pelajari cara menambahkan gradien vertikal di Java XPS menggunakan Aspose.Page.
  Ikuti panduan langkah demi langkah ini untuk meningkatkan daya tarik visual dokumen
  Anda.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cara Menambahkan Gradien Vertikal di Java XPS
url: /id/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Gradien Vertikal di Java XPS

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara menambahkan gradien vertikal** ke dokumen XPS saat bekerja dengan Java. Menerapkan gradien vertikal dapat secara dramatis meningkatkan dampak visual laporan, faktur, atau konten yang dapat dicetak apa pun. Kami akan memandu Anda melalui setiap langkah, mulai dari menyiapkan proyek hingga menyimpan file XPS akhir, menggunakan pustaka Aspose.Page for Java yang kuat.

## Jawaban Cepat
- **Apa yang dilakukan gradien vertikal?** Itu menciptakan transisi warna yang halus dari atas ke bawah suatu bentuk.  
- **Pustaka apa yang diperlukan?** Aspose.Page for Java (dapat diunduh dari situs resmi).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Apakah ini kompatibel dengan Java 8+?** Ya, API mendukung Java8 dan versi selanjutnya.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit setelah lingkungan disiapkan.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
- Pustaka Aspose.Page for Java. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/page/java/).  
- Pemahaman dasar tentang konsep pemrograman Java.  

## Impor Paket
Mulailah dengan mengimpor paket yang diperlukan untuk proyek Java Anda. Pastikan pustaka Aspose.Page for Java telah ditambahkan ke classpath proyek Anda.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Langkah 1: Inisialisasi Dokumen
Mulailah dengan membuat dokumen XPS baru. Objek ini akan menampung semua elemen gambar yang akan Anda tambahkan nanti.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Langkah 2: Buat Path dengan Gradien Vertikal
Selanjutnya, definisikan path berbentuk persegi panjang dan terapkan gradien linear vertikal. Titik henti gradien menentukan warna dan posisinya sepanjang sumbu vertikal.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Langkah 3: Simpan Dokumen
Akhirnya, tulis file XPS ke disk. File yang dihasilkan akan berisi persegi panjang yang diisi dengan gradienikal yang Anda definisikan.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Selamat! Anda telah berhasil mempelajari **cara menambahkan gradien vertikal** ke dokumen Java XPS menggunakan Aspose.Page.

## Mengapa Menggunakan Gradien Vertikal?
- **Estetika yang lebih baik:** Gradien menambahkan kedalaman dan tampilan modern pada bentuk statis.  
- **Konsistensi merek:** Menyesuaikan warna perusahaan secara mulus di seluruh halaman.  
- **Kustomisasi mudah:** Mengubah warna atau posisi titik henti tanpa mendesain ulang grafik.

## Masalah Umum & Pemecahan Masalah
- **Gradien tidak terlihat:** Pastikan titik awal dan akhir `LinearGradientBrush` telah diatur dengan benar untuk orientasi vertikal.  
- **File tidak tersimpan:** Pastikan `dataDir` mengarah ke folder yang dapat ditulisi dan Anda memiliki izin menulis file.  
- **Pustaka tidak ditemukan:** Periksa kembali bahwa JAR Aspose.Page telah disertakan dalam jalur build proyek Anda.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page for Java dalam proyek komersial?**  
A: Ya, Aspose.Page for Java tersedia untuk penggunaan komersial. Anda dapat membelinya [here](https://purchase.aspose.com/buy).

**Q: Apakah ada versi percobaan gratis untuk Aspose.Page for Java?**  
A: Ya, Anda dapat mengakses versi percobaan gratis [here](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Page for Java?**  
A: Dokumentasi tersedia [here](https://reference.aspose.com/page/java/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page for Java?**  
A: Dapatkan lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

**Q: Butuh bantuan atau memiliki pertanyaan?**  
A: Kunjungi komunitas Aspose.Page [forum](https://forum.aspose.com/c/page/39).

---

**Terakhir Diperbarui:** 2025-12-25  
**Diuji Dengan:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
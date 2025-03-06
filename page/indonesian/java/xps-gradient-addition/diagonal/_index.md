---
title: Tambahkan Gradien Diagonal di Java XPS
linktitle: Tambahkan Gradien Diagonal di Java XPS
second_title: Aspose.Halaman Java API
description: Pelajari cara menambahkan gradien diagonal yang menakjubkan ke dokumen XPS Anda di Java menggunakan Aspose.Page. Tingkatkan presentasi visual Anda dengan mudah.
weight: 10
url: /id/java/xps-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Gradien Diagonal di Java XPS

## Perkenalan
Dalam dunia pengembangan Java yang terus berkembang, meningkatkan daya tarik visual dokumen XPS Anda sangatlah penting. Salah satu cara efektif untuk mencapai hal ini adalah dengan menggabungkan gradien diagonal. Tutorial ini akan memandu Anda melalui proses menggunakan Aspose.Page untuk Java, memberikan petunjuk langkah demi langkah dan cuplikan kode.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.
- Menginstal Java Development Kit (JDK) di sistem Anda.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
- Editor kode seperti IntelliJ IDEA atau Eclipse.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan untuk proyek Java Anda. Dalam kode Anda, Anda dapat menambahkan impor berikut:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda dan sertakan pustaka Aspose.Page dalam dependensi proyek Anda.
## Langkah 2: Tentukan Direktori Dokumen
Tetapkan jalur ke direktori dokumen Anda tempat file XPS akan disimpan:
```java
String dataDir = "Your Document Directory";
```
## Langkah 3: Buat Dokumen XPS
Inisialisasi objek XpsDocument baru:
```java
XpsDocument doc = new XpsDocument();
```
## Langkah 4: Tambahkan Jalur Gradien Diagonal
Tambahkan jalur ke dokumen XPS dengan gradien diagonal:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## Langkah 5: Tentukan Perhentian Gradien Linier
Siapkan perhentian gradien linier dengan warna dan posisi tertentu:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... ulangi untuk warna dan posisi lainnya
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## Langkah 6: Terapkan Gradien Linier ke Jalur
Terapkan gradien linier ke jalur yang ditentukan sebelumnya:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Langkah 7: Simpan Dokumen
Simpan dokumen XPS dengan menambahkan gradien diagonal:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## Kesimpulan
Selamat! Anda telah berhasil menambahkan gradien diagonal ke dokumen XPS Anda menggunakan Aspose.Page untuk Java. Fitur yang menarik secara visual ini dapat meningkatkan keseluruhan presentasi dokumen Anda.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.Page untuk Java dengan kerangka kerja Java lainnya?
Aspose.Page dirancang untuk berintegrasi secara mulus dengan berbagai kerangka kerja Java, menjadikannya pilihan serbaguna untuk proyek Anda.
### T: Apakah ada pertimbangan lisensi untuk Aspose.Page?
 Ya, pastikan untuk meninjau rincian perizinan di[Aspose.Halaman halaman pembelian](https://purchase.aspose.com/buy).
### T: Dapatkah saya mencoba Aspose.Page untuk Java sebelum membeli?
 Sangat! Anda dapat menjelajahi a[versi uji coba gratis di sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan atau terhubung dengan komunitas Aspose?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk terlibat dengan masyarakat dan mencari bantuan.
### Q: Apakah ada ketentuan untuk izin sementara?
 Ya, Anda bisa mendapatkan a[izin sementara di sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

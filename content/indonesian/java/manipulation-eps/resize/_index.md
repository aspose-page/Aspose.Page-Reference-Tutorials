---
title: Ubah ukuran File EPS di Java dengan Aspose.Page
linktitle: Ubah ukuran File EPS di Java
second_title: Aspose.Halaman Java API
description: Pelajari cara mengubah ukuran file EPS di Java dengan mudah dengan Aspose.Page untuk Java. Ikuti panduan komprehensif kami untuk petunjuk langkah demi langkah.
type: docs
weight: 11
url: /id/java/manipulation-eps/resize/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang mengubah ukuran file EPS di Java menggunakan perpustakaan Aspose.Page yang kuat. Jika Anda perlu menyesuaikan dimensi gambar EPS secara terprogram, Anda berada di tempat yang tepat. Dalam tutorial ini, kita akan menjelajahi berbagai opsi pengubahan ukuran, termasuk titik, inci, milimeter, dan persentase, yang memberi Anda fleksibilitas yang Anda perlukan untuk kebutuhan spesifik Anda.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Page untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).
- Pemahaman dasar tentang pemrograman Java.
## Paket Impor
Dalam proyek Java Anda, pastikan Anda memiliki impor yang diperlukan untuk menggunakan fungsionalitas Aspose.Page. Berikut ini contohnya:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Sekarang, mari kita bagi tutorial menjadi beberapa langkah untuk setiap opsi pengubahan ukuran:
## Ubah ukuran EPS menggunakan Poin
### Langkah 1: Siapkan aliran masukan
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Langkah 2: Inisialisasi objek PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Langkah 3: Ekstrak ukuran gambar EPS saat ini
```java
Dimension oldSize = doc.extractEpsSize();
```
### Langkah 4: Buat aliran keluaran
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Langkah 5: Ubah ukuran dan simpan poin
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Ubah ukuran EPS menggunakan Inci
Ikuti langkah serupa seperti Contoh 1, ganti "Titik" dengan "Inci" dan sesuaikan ukuran barunya.
## Ubah ukuran EPS menggunakan Milimeter
Ikuti langkah serupa seperti Contoh 1, ganti "Titik" dengan "Milimeter" dan sesuaikan ukuran barunya.
## Ubah ukuran EPS menggunakan Persentase
Ikuti langkah serupa seperti Contoh 1, ganti "Poin" dengan "Persentase" dan sesuaikan ukuran barunya.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengubah ukuran file EPS di Java menggunakan Aspose.Page. Panduan ini memberi Anda opsi serbaguna, memastikan Anda dapat menyesuaikan proses pengubahan ukuran untuk memenuhi kebutuhan spesifik Anda.

## FAQ
### Bisakah saya menggunakan perpustakaan ini untuk format gambar lain?
Tidak, Aspose.Page dirancang khusus untuk menangani file PostScript dan EPS.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Page untuk Java?
Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan bantuan dan diskusi tambahan?
 Mengunjungi[Aspose.Halaman forum](https://forum.aspose.com/c/page/39) untuk dukungan masyarakat.
### Bagaimana saya bisa mendapatkan lisensi sementara?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah ada contoh proyek yang tersedia?
 Ya, periksa dokumentasinya[Di Sini](https://reference.aspose.com/page/java/).
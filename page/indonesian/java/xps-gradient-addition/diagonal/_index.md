---
date: 2025-12-25
description: Pelajari cara membuat dokumen XPS di Java dan menambahkan gradien diagonal
  yang menakjubkan menggunakan Aspose.Page. Panduan ini mencakup cara menambahkan
  gradien, menerapkan gradien linier, dan menggunakan Aspose secara efektif.
linktitle: Add Diagonal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cara membuat dokumen XPS dengan gradien diagonal di Java
url: /id/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Gradien Diagonal di Java XPS

## Pendahuluan
Dalam pengembangan Java modern, membuat dokumen XPS yang tampak halus menjadi pembeda utama. Pada tutorial ini Anda akan belajar **cara membuat file dokumen XPS** dan meningkatkan tampilannya dengan gradien diagonal menggunakan Aspose.Page untuk Java. Kami akan membimbing Anda melalui setiap langkah, menjelaskan mengapa setiap bagian penting, serta menunjukkan cara **menambahkan jalur gradien**, **menerapkan gradien linear**, dan mendapatkan hasil visual profesional dengan cepat.

## Jawaban Cepat
- **Apa perpustakaan utama?** Aspose.Page untuk Java  
- **Metode mana yang menambahkan gradien?** `createLinearGradientBrush` dengan gradient stops  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk gradien diagonal dasar  
- **Bisakah saya menggunakan ini dengan kerangka kerja Java lainnya?** Ya, API bersifat framework‑agnostic  

## Apa itu gradien diagonal dalam dokumen XPS?
Gradien diagonal mengubah warna secara halus sepanjang garis miring, memberikan kedalaman dan daya tarik visual pada bentuk. Di XPS, gradien didefinisikan oleh sebuah brush yang berisi beberapa gradient stop, masing‑masing menentukan warna dan posisi relatifnya.

## Mengapa menambahkan gradien diagonal dengan Aspose.Page?
- **Kualitas visual yang kaya** – gradien dirender secara tepat dalam format XPS.  
- **Konsistensi lintas‑platform** – file XPS yang sama terlihat identik pada penampil Windows, macOS, dan Linux.  
- **API sederhana** – Aspose.Page menyederhanakan spesifikasi XPS tingkat rendah, memungkinkan Anda fokus pada desain.  

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- JDK terpasang di mesin Anda.  
- Perpustakaan Aspose.Page untuk Java. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/page/java/)**.  
- IDE seperti IntelliJ IDEA atau Eclipse.

## Mengimpor Paket
Mulailah dengan mengimpor kelas‑kelas yang diperlukan. Impor ini memberi Anda akses ke geometri, penanganan gradien, dan pembuatan dokumen XPS.

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
Buat proyek Java baru di IDE pilihan Anda dan tambahkan file JAR Aspose.Page ke jalur build proyek.

## Langkah 2: Tentukan Direktori Dokumen
Tentukan lokasi di mana file XPS yang dihasilkan akan disimpan.

```java
String dataDir = "Your Document Directory";
```

## Langkah 3: Buat Dokumen XPS
Instansiasikan objek `XpsDocument` – ini adalah objek inti yang akan Anda gunakan untuk **membuat konten dokumen XPS**.

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 4: Tambahkan Jalur Gradien Diagonal
Buat jalur persegi panjang yang akan menerima gradien. Geometri jalur menggunakan perintah sederhana move‑line‑close.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Langkah 5: Definisikan Gradient Stops Linear
Atur warna‑warna dan posisinya. Setiap stop mendefinisikan titik dalam gradien di mana warna tertentu muncul.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Langkah 6: Terapkan Gradien Linear ke Jalur
Sekarang **terapkan gradien linear** ke jalur yang Anda buat. Brush didefinisikan oleh dua titik yang menentukan arah gradien, dan stop‑stop tersebut dilampirkan ke brush.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Langkah 7: Simpan Dokumen
Persistensikan file XPS ke disk. File tersebut akan berisi persegi panjang yang terisi dengan gradien diagonal yang telah Anda definisikan.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Kesalahan Umum & Tips
- **Arah gradien** – pastikan titik awal dan akhir brush mencerminkan diagonal yang Anda inginkan; menukar keduanya akan membalikkan gradien.  
- **isi warna** – Aspose menggunakan ARGB; jika Anda memerlukan transparansi, sertakan kanal alfa saat membuat warna.  
- **Jalur file** – selalu gunakan jalur absolut atau pastikan jalur relatif mengarah ke direktori yang dapat ditulisi.

## FAQ Tambahan

**Q: Bagaimana cara **menambahkan gradien** ke bentuk XPS yang sudah ada?**  
A: Buat `XpsLinearGradientBrush`, definisikan gradient stops, dan tetapkan ke properti `Fill` bentuk seperti yang ditunjukkan pada Langkah 6.

**Q: Apa yang sebenarnya dilakukan **menerapkan gradien linear** di balik layar?**  
A: Ia menghasilkan definisi brush dalam paket XPS yang merujuk pada titik awal/akhir serta koleksi gradient stops, yang kemudian dirender oleh penampil sebagai transisi warna halus.

**Q: Apakah ada cara cepat untuk **menggunakan aspose** pada fitur XPS lainnya?**  
A: Ya, API Aspose.Page mencakup metode untuk menambahkan gambar, teks, dan bentuk khusus—jelajahi kelas `XpsDocument` untuk bantuan tambahan.

**Q: Bisakah saya **menambahkan jalur gradien** ke bentuk non‑persegi panjang?**  
A: Tentu. Definisikan geometri apa pun menggunakan `createPathGeometry` lalu set `Fill`‑nya ke brush gradien.

**Q: Apakah gradien memengaruhi ukuran file secara signifikan?**  
A: Hanya sedikit; definisi gradien merupakan entri XML ringan dalam paket XPS.

---

**Terakhir Diperbarui:** 2025-12-25  
**Diuji Dengan:** Aspose.Page untuk Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
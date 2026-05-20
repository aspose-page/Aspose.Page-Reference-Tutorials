---
date: 2026-04-24
description: Pelajari cara mengatur warna persegi panjang dan menambahkan persegi
  panjang dalam Java XPS menggunakan Aspose.Page. Panduan ini mencakup cara menambahkan
  persegi panjang di Java dan mengubah garis tepi persegi panjang.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Tambah Persegi Panjang di Java XPS
second_title: Aspose.Page Java API
title: Atur Warna Persegi Panjang dan Tambahkan Persegi Panjang di Java XPS
url: /id/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Warna Persegi Panjang dan Tambahkan Persegi Panjang di Java XPS

## Pendahuluan
Dalam panduan ini, Anda akan belajar cara **mengatur warna persegi panjang** dan **menambahkan persegi panjang** di Java XPS menggunakan pustaka Aspose.Page. Baik Anda perlu menggambar bentuk sederhana untuk laporan atau membuat grafik vektor yang kompleks, menguasai gaya persegi panjang memberi Anda kontrol yang tepat atas dokumen XPS Anda.  

## Jawaban Cepat
- **Library apa yang diperlukan?** Aspose.Page for Java  
- **Bisakah saya mengubah garis tepi persegi panjang?** Ya, menggunakan `setStroke` dan `setStrokeThickness`  
- **Apakah profil warna CMYK didukung?** Tentu – Anda dapat memuat profil ICC seperti yang ditunjukkan  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan non‑evaluasi  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk persegi panjang dasar

## Apa itu **set rectangle color**?
Mengatur warna persegi panjang berarti mendefinisikan warna isi atau garis tepi yang akan ditampilkan oleh bentuk tersebut dalam dokumen XPS akhir. Dengan Aspose.Page Anda dapat menggunakan RGB, CMYK, atau bahkan profil warna ICC khusus untuk mencapai pencocokan warna yang tepat.

## Mengapa menggunakan Aspose.Page untuk **add rectangle java** dan **change rectangle stroke**?
- **API lengkap** – mendukung baik warna solid maupun gradien.  
- **Lintas‑platform** – bekerja pada runtime Java apa pun tanpa ketergantungan native.  
- **Dukungan geometri kaya** – buat jalur kompleks, terapkan transformasi, dan kelola ketebalan garis tepi dengan mudah.  

## Prasyarat
Sebelum kita menyelami kode, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Pustaka Aspose.Page terpasang. Jika belum, unduh dari [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Lingkungan pengembangan Java yang berfungsi (IDE, JDK, dll.).  

## Impor Paket
Untuk memulai, impor paket yang diperlukan ke dalam proyek Java Anda. Pastikan pustaka Aspose.Page telah ditambahkan dengan benar ke classpath Anda. Berikut contoh dasar:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk **menambahkan persegi panjang** dan **mengatur warnanya** di Java XPS.

## Langkah 1: Atur Direktori Dokumen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Ganti `"Your Document Directory"` dengan path absolut tempat Anda ingin membaca/menulis file XPS.

## Langkah 2: Buat Dokumen XPS Baru
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Baris ini menginisialisasi dokumen XPS baru yang akan menampung bentuk-bentuk kami.

## Langkah 3: Tambahkan Persegi Panjang Bergaris dengan Warna Solid CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Langkah ini menambahkan **persegi panjang bergaris** dengan warna solid CMYK. Metode `setStroke` menentukan warna garis tepi persegi panjang, sementara `setStrokeThickness` mengontrol lebar garis—sempurna untuk **mengubah garis tepi persegi panjang**.

### Tips Pro:
Jika Anda lebih suka warna RGB, ganti pemanggilan `createColor` dengan `doc.createColor(0, 0, 255)` untuk isian biru solid.

## Langkah 4: Simpan Dokumen XPS Hasil
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Akhirnya, simpan dokumen XPS ke disk. File `AddRectangle_out.xps` kini berisi persegi panjang dengan warna dan garis tepi yang Anda definisikan.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|----------|
| **Persegi panjang tidak terlihat** | Geometri path yang salah atau ketebalan garis tepi diatur ke 0 | Verifikasi string path (`"M 20,10 L 220,10 220,100 20,100 Z"`) dan pastikan `setStrokeThickness` lebih besar dari 0. |
| **Warna salah** | Menggunakan profil ICC yang tidak cocok dengan ruang warna yang dimaksud | Gunakan `doc.createColor(r, g, b)` untuk RGB atau periksa kembali path file ICC. |
| **File tidak tersimpan** | `dataDir` mengarah ke folder yang tidak ada atau tidak memiliki izin menulis | Buat folder tersebut terlebih dahulu atau pilih lokasi yang dapat ditulis. |

## Pertanyaan yang Sering Diajukan

**Q:** *Apakah saya dapat menambahkan beberapa persegi panjang dalam satu dokumen XPS?*  
A: Ya. Cukup ulangi langkah pembuatan geometri dan styling untuk setiap persegi panjang yang Anda butuhkan.

**Q:** *Bagaimana cara mengubah warna isi persegi panjang alih-alih garis tepinya?*  
A: Gunakan `path.setFill(...)` dengan kuas warna solid, mirip dengan cara penggunaan `setStroke`.

**Q:** *Apakah Aspose.Page cocok untuk manipulasi dokumen XPS yang kompleks?*  
A: Tentu. Pustaka ini mendukung fitur lanjutan seperti gradien, transformasi, dan font tersemat.

**Q:** *Di mana saya dapat menemukan contoh tambahan dan dukungan komunitas?*  
A: Jelajahi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk lebih banyak contoh kode dan bantuan sesama pengguna.

**Q:** *Apakah saya dapat mencoba Aspose.Page sebelum membeli?*  
A: Ya, Anda dapat menjelajahi [free trial](https://releases.aspose.com/) untuk mengevaluasi kemampuan API.

---

**Terakhir Diperbarui:** 2026-04-24  
**Diuji Dengan:** Aspose.Page for Java 24.12  
**Penulis:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
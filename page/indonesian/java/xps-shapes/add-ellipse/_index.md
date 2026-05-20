---
date: 2026-04-24
description: Pelajari cara membuat dokumen XPS Java dengan elips gradien radial. Panduan
  langkah demi langkah ini menunjukkan cara mengatur ketebalan garis dan mendefinisikan
  geometri jalur menggunakan Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Tambahkan Elips di Java XPS
second_title: Aspose.Page Java API
title: Buat Dokumen XPS Java – Tambahkan Elips Gradien Radial
url: /id/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah Elips Gradien Radial dengan Aspose.Page

## Pendahuluan
Dalam tutorial ini, Anda akan belajar cara **create XPS document Java** dengan sebuah elips ber‑garis gradien radial yang indah menggunakan Aspose.Page untuk Java. Aspose.Page adalah pustaka yang kuat yang mengabstraksi detail XPS tingkat‑rendah, memungkinkan Anda fokus pada desain daripada kerumitan format file. Pada akhir panduan ini Anda akan memiliki file XPS siap pakai yang dapat Anda sematkan dalam laporan, faktur, atau alur kerja pembuatan dokumen apa pun.

## Jawaban Cepat
- **Apa yang dihasilkan kode ini?** File XPS satu halaman yang berisi sebuah elips dengan garis bergradien radial berwarna‑multiple.  
- **API utama mana yang digunakan?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, dll.).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi sementara cukup untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Apa properti kunci yang kami atur?** Kuas garis (gradien radial), metode penyebaran, titik henti gradien, dan ketebalan garis.  
- **Bisakah saya mengubah ukuran elips?** Ya – ubah string geometri jalur atau koordinat kuas gradien.

## Apa itu “create XPS document Java”?
Membuat dokumen XPS di Java berarti secara program menghasilkan file XML Paper Specification (XPS) — format dokumen tata letak tetap yang mirip PDF — langsung dari kode Java. Aspose.Page menyediakan model objek tingkat tinggi (`XpsDocument`, `XpsCanvas`, dll.) yang mengabstraksi markup XML, menjadikan prosesnya semudah bekerja dengan objek Java standar.

## Mengapa menggunakan elips gradien radial?
Gradien radial memberikan kesan tiga dimensi, sempurna untuk sorotan visual, logo, atau elemen dekoratif dalam laporan. Dibandingkan dengan garis berwarna solid, gradien menambah kedalaman tanpa meningkatkan ukuran file secara signifikan, dan format XPS mempertahankan kualitas vektor untuk skala apa pun.

## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan hal‑hal berikut:
- Java Development Kit (JDK) terpasang di mesin Anda.
- Pustaka Aspose.Page untuk Java telah diunduh. Anda dapat mendapatkannya [di sini](https://releases.aspose.com/page/java/).
- Editor kode pilihan Anda (Eclipse, IntelliJ, dll.) untuk menulis dan mengeksekusi kode Java.

## Impor Paket
Pastikan Anda memiliki paket yang diperlukan diimpor dalam proyek Java Anda untuk menggunakan Aspose.Page. Tambahkan pernyataan impor berikut di bagian atas file Java Anda:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Langkah 1: Siapkan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat file XPS akan disimpan:

```java
String dataDir = "Your Document Directory";
```

## Langkah 2: Buat Dokumen XPS
Inisialisasi dokumen XPS baru menggunakan kode berikut:

```java
XpsDocument doc = new XpsDocument();
```

## Langkah 3: Tentukan Titik Henti Gradien Radial
Buat daftar titik henti gradien untuk elips ber‑garis gradien radial:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Langkah 4: Buat Geometri Jalur
Definisikan elips ber‑garis gradien radial menggunakan geometri jalur:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Langkah 5: Tambahkan Kanvas dan Jalur
Tambahkan kanvas baru ke dokumen dan tambahkan jalur dengan geometri yang telah didefinisikan:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Langkah 6: Atur Garis dan Gradien
Konfigurasikan garis jalur dengan kuas gradien radial:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Langkah 7: Atur Ketebalan Garis
Tentukan **set stroke thickness** jalur:

```java
path.setStrokeThickness(12f);
```

## Langkah 8: Simpan Dokumen
Simpan dokumen XPS yang dihasilkan:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Selamat! Anda telah berhasil menambahkan elips ber‑garis gradien radial sambil **create XPS document Java** dengan Aspose.Page.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Elips terlihat datar** | Menggunakan `XpsSpreadMethod.Pad` alih‑alih `Reflect` | Ubah metode penyebaran menjadi `XpsSpreadMethod.Reflect` seperti yang ditunjukkan pada Langkah 6. |
| **Tidak ada file output** | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau gunakan path absolut. |
| **Warna gradien tampak salah** | Urutan titik henti gradien yang tidak tepat | Verifikasi nilai `offset` (0 → 1) meningkat secara monoton. |
| **Kesalahan kompilasi** | JAR Aspose.Page tidak ada di classpath | Tambahkan `aspose-page-xx.jar` ke dependensi proyek Anda. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Page untuk Java dengan pustaka Java lainnya?**  
A: Ya, Aspose.Page untuk Java dapat diintegrasikan dengan pustaka Java lainnya secara mulus.

**Q: Apakah Aspose.Page cocok untuk pemrosesan dokumen skala besar?**  
A: Tentu! Aspose.Page dirancang untuk menangani pemrosesan dokumen skala besar secara efisien.

**Q: Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.Page untuk Java?**  
A: Kunjungi [dokumentasi Aspose.Page untuk Java](https://reference.aspose.com/page/java/) untuk tutorial dan contoh yang komprehensif.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Page untuk Java?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Apakah ada forum komunitas untuk diskusi Aspose.Page?**  
A: Ya, bergabunglah dengan [forum komunitas Aspose.Page](https://forum.aspose.com/c/page/39) untuk berinteraksi dengan pengembang lain dan mendapatkan bantuan.

---

**Terakhir Diperbarui:** 2026-04-24  
**Diuji Dengan:** Aspose.Page untuk Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-18
description: Pelajari cara menambahkan grid dan menambahkan persegi panjang transparan
  dalam dokumen XPS Java dengan Aspose.Page. Panduan langkah demi langkah untuk menyimpan
  dokumen XPS secara efisien.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Cara Menambahkan Grid dengan Visual Brush di Java
url: /id/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Grid menggunakan Visual Brush di Java

## Introduction
Jika Anda ingin **cara menambahkan grid** ke dokumen XPS yang dihasilkan oleh Java, Anda berada di tempat yang tepat. Pada tutorial ini kami akan memandu Anda menambahkan grid dengan Visual Brush, menumpuk persegi panjang transparan, dan akhirnya **menyimpan dokumen XPS** menggunakan Aspose.Page Java API. Pada akhir tutorial Anda akan memiliki visual yang halus yang dapat digunakan kembali dalam laporan, faktur, atau aplikasi yang banyak memuat dokumen.

## Quick Answers
- **Apa yang dilakukan Visual Brush?** Ia melukis area yang ditentukan dengan konten visual yang dapat digunakan kembali, sempurna untuk pola berulang seperti grid.  
- **Bisakah saya mengubah warna grid?** Ya – ubah pengaturan kuas solid‑color pada brush.  
- **Bagaimana cara menambahkan persegi panjang transparan di atas grid?** Gunakan `setOpacity` pada path yang diisi dengan warna solid.  
- **Metode apa yang menyimpan file?** `doc.save(...)` menulis file XPS ke disk.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.

## What is a Visual Brush Grid?
Visual Brush memungkinkan Anda mendefinisikan visual kecil (pola grid) dan kemudian menatanya di seluruh area yang lebih besar. Pendekatan ini lebih efisien dalam memori dibandingkan menggambar setiap garis secara terpisah dan memberikan pengulangan yang pixel‑perfect.

## Why use Aspose.Page for this task?
- **Cross‑platform** – Berfungsi pada sistem operasi apa pun yang mendukung Java.  
- **High‑fidelity rendering** – Kontrol presisi atas warna, opasitas, dan penataan ubin.  
- **No external dependencies** – Semua ditangani melalui pustaka Aspose.Page.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Pustaka Aspose.Page terinstal – Anda dapat mengunduhnya dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 atau lebih baru terpasang di mesin pengembangan Anda.

## Import Packages
Pertama, impor kelas‑kelas yang diperlukan agar kompilator mengetahui lokasi tipe yang akan kita gunakan:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
Buat instance `XpsDocument` baru dan arahkan ke folder tempat Anda ingin menyimpan file output.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Magenta Grid Visual Brush
Kami mendefinisikan bentuk magenta kecil yang akan ditata di seluruh area grid.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for the Grid Brush
Siapkan area persegi panjang yang akan menerima visual yang ditata.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create a New Canvas for the Document
Tambahkan kanvas ke dokumen dan posisikan di tempat grid akan muncul.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add the Grid to the Canvas
Terapkan visual brush ke geometri, mengaktifkan penataan ubin.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add a Transparent Red Rectangle (Secondary Feature)
Di sini kami mendemonstrasikan **menambahkan persegi panjang transparan** di atas grid untuk penekanan.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save the Resulting XPS Document
Akhirnya, tulis dokumen ke disk—ini adalah langkah **menyimpan dokumen XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Ikuti langkah‑langkah ini, dan Anda akan memiliki grid yang tampak profesional dengan lapisan transparan, semuanya dihasilkan secara programatis.

## Common Issues & Tips

- **Ukuran ubin tidak tepat:** Pastikan `Rectangle2D` yang digunakan untuk brush cocok dengan ukuran pengulangan yang diinginkan; jika tidak pola dapat meregang.  
- **Opacity tidak diterapkan:** Ingat untuk memanggil `setOpacity` pada path yang ingin dibuat transparan; ini tidak akan memengaruhi brush itu sendiri.  
- **File tidak tersimpan:** Verifikasi bahwa `dataDir` mengarah ke folder yang ada dan aplikasi Anda memiliki izin menulis.

## Frequently Asked Questions

**Q: Apakah Aspose.Page cocok untuk pembuatan dokumen profesional?**  
A: Ya, Aspose.Page adalah pustaka yang kuat dirancang untuk menghasilkan XPS dan PDF berkualitas tinggi di Java.

**Q: Bisakah saya menyesuaikan warna grid menggunakan Visual Brush?**  
A: Tentu saja! Ubah parameter `createColor` dalam pemanggilan `setFill` brush ke nilai RGBA apa pun yang Anda butuhkan.

**Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Page?**  
A: Kunjungi [Aspose.Page forum](https://forum.aspose.com/c/page/39) untuk bantuan komunitas dan jawaban resmi.

**Q: Apakah ada versi percobaan gratis untuk Aspose.Page?**  
A: Ya, Anda dapat mengakses [free trial](https://releases.aspose.com/) untuk menjelajahi semua fitur sebelum membeli.

**Q: Bagaimana cara memperoleh lisensi sementara untuk pengujian?**  
A: Dapatkan [temporary license](https://purchase.aspose.com/temporary-license/) yang dapat digunakan untuk pengembangan dan evaluasi.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
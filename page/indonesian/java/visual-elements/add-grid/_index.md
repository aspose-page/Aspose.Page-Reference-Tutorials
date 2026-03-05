---
date: 2026-03-05
description: Pelajari cara menambahkan grid menggunakan Visual Brush di Java dengan
  Aspose.Page. Ikuti panduan langkah demi langkah untuk meningkatkan visual dokumen
  dengan mudah.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Cara Menambahkan Grid dengan Visual Brush di Java
url: /id/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Grid Menggunakan Visual Brush di Java

## Introduction
Jika Anda ingin **menambahkan grid** ke dokumen yang dihasilkan oleh Java, fitur Visual Brush dari Aspose.Page membuatnya menjadi sangat sederhana. Pada tutorial ini kami akan membimbing Anda melalui setiap langkah, menjelaskan mengapa Visual Brush ideal untuk pola grid, dan menunjukkan contoh lengkap yang dapat dijalankan.

## Quick Answers
- **What is a Visual Brush?** Elemen visual yang dapat digunakan kembali dan dapat ditile atau ditarik untuk mengisi sebuah area.  
- **Why use a grid?** Grid membantu menyusun tata letak, membuat pola latar belakang, atau menyorot bagian dalam dokumen XPS.  
- **Prerequisites?** Java JDK, Aspose.Page for Java, dan pemahaman dasar tentang grafis Java.  
- **How long does implementation take?** Sekitar 10‑15 menit setelah pustaka terpasang.  
- **Can I customize colors?** Ya – Anda dapat mengontrol warna isi, opasitas, dan ukuran tile langsung dalam kode.

## Why Use Visual Brush to Add a Grid?
Visual Brush memungkinkan Anda mendefinisikan sebuah visual kecil (“tile”) sekali dan kemudian mengulanginya di seluruh bentuk apa pun. Pendekatan ini efisien dalam penggunaan memori dan menjaga kode tetap bersih, terutama ketika Anda perlu menerapkan pola yang sama ke banyak kanvas.

## Prerequisites
Sebelum kita masuk ke kode, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.  
- Pustaka Aspose.Page terpasang. Anda dapat mengunduhnya dari [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Java Development Kit (JDK) terinstal di mesin Anda.

## Import Packages
Pastikan paket-paket yang diperlukan telah diimpor dalam proyek Java Anda:
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

### Step 1: Set Up Your Project
Pertama, buat instance `XpsDocument` dan arahkan ke folder tempat output akan disimpan.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create Magenta Grid Visual Brush
Kami membuat sebuah tile magenta kecil yang akan diulang. Geometri path mendefinisikan bentuk tile tersebut.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for Magenta Grid Visual Brush
Di sini kami mendeskripsikan area yang akan menerima brush yang ditile.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create New Canvas
Sebuah kanvas baru ditambahkan ke dokumen, dan kami menerapkan transformasi translasi sehingga grid muncul di posisi yang diinginkan.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add Grid to Canvas
Sekarang kami mengikat visual brush ke geometri dan mengatur mode tiling.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add Red Transparent Rectangle
Untuk mendemonstrasikan lapisan, kami menempatkan sebuah persegi panjang merah semi‑transparan di atas grid.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save Resultant XPS Document
Akhirnya, tulis file XPS ke disk.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Ikuti langkah‑langkah ini, dan Anda akan berhasil menambahkan grid yang menarik secara visual menggunakan Visual Brush dalam aplikasi Java Anda dengan Aspose.Page.

## Common Use Cases
- **Report backgrounds:** Tambahkan pola grid halus ke laporan keuangan atau teknik untuk meningkatkan keterbacaan.  
- **Design templates:** Buat templat halaman yang dapat digunakan kembali di mana grid yang sama diulang pada banyak halaman.  
- **Highlight sections:** Lapisi grid berwarna untuk menarik perhatian ke area dokumen tertentu.

## Common Issues and Solutions
| Masalah | Solusi |
|-------|----------|
| **Grid appears stretched** | Pastikan `TileMode` disetel ke `XpsTileMode.Tile` dan bahwa rectangle sumber serta tujuan memiliki ukuran yang sama. |
| **Colors look off** | Pastikan Anda menggunakan nilai RGBA yang tepat saat membuat solid color brush (`createColor(alpha, red, green, blue)`). |
| **Document not saved** | Periksa bahwa `dataDir` mengarah ke folder yang dapat ditulis dan bahwa Anda memiliki izin sistem file yang sesuai. |

## Conclusion
Selamat! Anda telah mempelajari **cara menambahkan grid** menggunakan Visual Brush dari Aspose.Page di Java. Teknik ini memberi Anda kontrol detail atas rendering pola sambil menjaga kode tetap bersih dan mudah dipelihara.

## Frequently Asked Questions
### Is Aspose.Page suitable for professional document generation?
Ya, Aspose.Page adalah pustaka yang kuat dirancang untuk pembuatan dokumen profesional di Java.

### Can I customize the grid colors using Visual Brush?
Tentu saja! Visual Brush memungkinkan Anda melukis dengan berbagai warna, memberikan fleksibilitas dalam kustomisasi.

### Where can I find additional support for Aspose.Page?
Kunjungi [forum Aspose.Page](https://forum.aspose.com/c/page/39) untuk dukungan komunitas dan diskusi.

### Is there a free trial available for Aspose.Page?
Ya, Anda dapat mengakses [free trial](https://releases.aspose.com/) untuk menjelajahi fitur-fitur Aspose.Page.

### How can I obtain a temporary license for Aspose.Page?
Dapatkan [temporary license](https://purchase.aspose.com/temporary-license/) untuk keperluan pengujian.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---
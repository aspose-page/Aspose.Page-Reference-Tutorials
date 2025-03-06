---
title: Tambahkan Namespace di XMP menggunakan Java
linktitle: Tambahkan Namespace di XMP menggunakan Java
second_title: Aspose.Halaman Java API
description: Buka kekuatan manipulasi dokumen dengan Aspose.Page untuk Java. Pelajari cara menambahkan namespace XMP dengan mudah dalam panduan komprehensif ini.
weight: 13
url: /id/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Namespace di XMP menggunakan Java


## Perkenalan

Dalam bidang manipulasi dokumen, Aspose.Page untuk Java menonjol sebagai alat yang tangguh, menawarkan beragam fungsi. Salah satu fitur canggihnya adalah kemampuan untuk menambahkan namespace di XMP (Extensible Metadata Platform) menggunakan Java. Tutorial ini akan memandu Anda melalui prosesnya, membaginya menjadi langkah-langkah yang mudah diikuti.

## Prasyarat

Sebelum mempelajari tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Page untuk Java: Pastikan Anda telah menginstal perpustakaan. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/page/java/).

- Lingkungan Pengembangan Java: Siapkan lingkungan Java di sistem Anda.

- File Dokumen: Memiliki file EPS dengan metadata XMP. Jika tidak berisi metadata XMP, perpustakaan akan membuatnya berdasarkan komentar metadata PS.

## Paket Impor

Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Langkah 1: Dapatkan Metadata XMP

```java

// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Inisialisasi aliran file EPS masukan
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Dapatkan metadata XMP. Jika file EPS tidak berisi metadata XMP, buat yang baru berisi nilai dari komentar metadata PS (%%Creator, %%CreateDate, %%Title, dll.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Langkah 2: Daftarkan Namespace Baru

```java
// Tambahkan namespace XML baru "http://www.some.org/schema/tmp#" dengan awalan "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Langkah 3: Tambahkan Properti Baru

```java
// Tambahkan properti baru "tmp:newKey" di namespace XML baru
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Langkah 4: Simpan Dokumen

```java
// Inisialisasi aliran file EPS keluaran
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Simpan dokumen dengan metadata XMP yang diubah
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Langkah 5: Tutup Aliran

```java
// Tutup aliran EPS masukan
psStream.close();
```

Sekarang Anda telah berhasil menambahkan namespace di XMP menggunakan Aspose.Page untuk Java. Jangan ragu untuk menjelajahi lebih banyak fitur dan mengeluarkan potensi penuh dari perpustakaan ini.

## Kesimpulan

Aspose.Page untuk Java menyederhanakan tugas kompleks dalam memanipulasi metadata XMP dalam file EPS. Dengan mengikuti panduan langkah demi langkah ini, Anda telah memperoleh keterampilan berharga untuk meningkatkan kemampuan pemrosesan dokumen Anda.

## FAQ

### Bisakah saya menggunakan Aspose.Page untuk Java dengan bahasa pemrograman lain?
Aspose.Page terutama mendukung Java, tetapi ada versi yang tersedia untuk bahasa lain seperti .NET.

### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lengkap?
 Lihat dokumentasi[Di Sini](https://reference.aspose.com/page/java/).

### Bagaimana saya bisa mendapatkan lisensi sementara?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Apakah ada forum komunitas untuk Aspose.Page?
 Ya, Anda dapat terlibat dengan komunitas di[Aspose.Halaman forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

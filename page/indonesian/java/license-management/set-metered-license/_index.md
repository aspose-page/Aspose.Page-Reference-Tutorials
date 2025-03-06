---
title: Integrasi Lisensi Terukur yang Mudah dengan Aspose.Page Java
linktitle: Tetapkan Lisensi Terukur di Java
second_title: Aspose.Halaman Java API
description: Jelajahi integrasi Aspose.Page yang mulus dengan Java. Siapkan lisensi terukur dengan mudah dan tingkatkan kemampuan pemrosesan dokumen Anda.
weight: 10
url: /id/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Integrasi Lisensi Terukur yang Mudah dengan Aspose.Page Java

## Perkenalan
Selamat datang di panduan komprehensif kami tentang menyiapkan lisensi terukur di Java menggunakan Aspose.Page. Jika Anda ingin meningkatkan kemampuan pemrosesan dokumen dan memastikan integrasi yang lancar dengan Aspose.Page, Anda berada di tempat yang tepat. Dalam tutorial ini, kami akan memandu Anda melalui prosesnya, memecah setiap langkah menjadi beberapa bagian yang mudah dicerna.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Pustaka Aspose.Page terinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/page/java/).
- Kunci publik dan pribadi terukur, yang dapat Anda peroleh melalui akun Aspose Anda.
## Paket Impor
Mari kita mulai dengan mengimpor paket yang diperlukan untuk program Java kita. Pastikan Anda memiliki perpustakaan Aspose.Page yang terintegrasi ke dalam proyek Anda.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Langkah 1: Inisialisasi Format Dokumen dan Gambar
Langkah pertama adalah menyiapkan dokumen dan menentukan format gambar yang diinginkan.
```java
// mengatur kunci publik dan pribadi terukur
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Akses properti setMeteredKey dan teruskan kunci publik dan pribadi sebagai parameter
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Langkah 2: Inisialisasi Aliran Input PostScript
Pada langkah ini, kami menginisialisasi aliran input PostScript untuk diproses.
```java
// Inisialisasi aliran masukan PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Langkah 3: Periksa Lisensi Dokumen
Sebelum melanjutkan, penting untuk memverifikasi apakah dokumen tersebut memiliki lisensi yang benar.
```java
// Periksa apakah dokumen tersebut berlisensi
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Langkah 4: Inisialisasi Opsi dan Perangkat Gambar
Sekarang, mari kita inisialisasi opsi dan perangkat gambar dengan parameter default.
```java
// Inisialisasi objek opsi dengan parameter default.
ImageSaveOptions options = new ImageSaveOptions();
// Inisialisasi objek ImageDevice dengan parameter default.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Langkah 5: Simpan File EPS sebagai Gambar
Simpan file EPS sebagai gambar menggunakan opsi dan perangkat yang ditentukan.
```java
// Simpan file EPS sebagai gambar
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Langkah 6: Dapatkan dan Simpan Byte Gambar
Ambil byte gambar dan simpan ke file.
```java
// Dapatkan byte gambar. Array satu byte untuk satu halaman. Dalam kasus kami, kami memiliki satu halaman.
byte[][] imagesBytes = device.getImagesBytes();
// Simpan byte gambar ke file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Kesimpulan
Selamat! Anda telah berhasil menyiapkan lisensi terukur di Java menggunakan Aspose.Page. Tutorial ini memberikan panduan langkah demi langkah untuk memastikan proses integrasi yang lancar.
## FAQ
### T: Bagaimana cara mendapatkan kunci publik dan privat terukur?
Anda dapat memperoleh kunci ini melalui akun Aspose Anda.
### T: Apakah perpustakaan Aspose.Page gratis?
 Aspose.Page menawarkan versi uji coba gratis dan berbayar. Mengunjungi[Di Sini](https://releases.aspose.com/) untuk uji coba gratis.
### T: Dapatkah saya menggunakan Aspose.Page untuk proyek komersial?
 Ya, Aspose.Page menawarkan lisensi komersial. Anda dapat membelinya[Di Sini](https://purchase.aspose.com/buy).
### T: Di mana saya dapat menemukan dokumentasi tambahan?
 Lihat dokumentasi[Di Sini](https://reference.aspose.com/page/java/).
### T: Bagaimana cara mendapatkan lisensi sementara?
 Lisensi sementara dapat diperoleh[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-02-05
description: Aspose.Page for Java kullanarak EPS'yi PNG olarak kaydetmeyi, ölçülen
  lisansı yapılandırırken öğrenin. Tam kod örneğiyle adım adım rehber.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java ile EPS'yi PNG olarak kaydedin (Ölçümlü Lisans)
url: /tr/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java (Ölçülü Lisans) ile EPS'yi PNG Olarak Kaydet

## Introduction
Java uygulamanızda **EPS'yi PNG olarak kaydetmek** istiyor ve lisans yönetimini sorunsuz bir şekilde yapmak istiyorsanız doğru yerdesiniz. Bu öğreticide, Aspose.Page için ölçülü bir lisansın nasıl yapılandırılacağını, bir PostScript (EPS) dosyasının nasıl yükleneceğini ve PNG görüntüsüne nasıl dönüştürüleceğini adım adım anlatıyoruz. Sonunda **EPS'yi PNG'ye render etme** ve **Java'da PNG dosyası yazma** kodunu üretim ortamlarında nasıl kullanacağınızı da öğreneceksiniz.

## Quick Answers
- **“save EPS as PNG” ne anlama geliyor?** Vektörel bir EPS dosyasını raster bir PNG görüntüsüne dönüştürür.  
- **Neden ölçülü lisans kullanılmalı?** İşlediğiniz sayfa sayısına göre ödeme yapmanızı sağlar, değişken iş yükleri için idealdir.  
- **İnternet bağlantısına ihtiyaç var mı?** Hayır, ölçülü anahtarlar yerel olarak doğrulanır.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya üzeri.  
- **Kurulum ne kadar sürer?** Temel bir uygulama için yaklaşık 10 dakika.  

## What is “save EPS as PNG”?
EPS'yi PNG olarak kaydetmek, ölçeklenebilir Encapsulated PostScript belgesini yaygın olarak desteklenen bir bitmap formatına dönüştürür. PNG şeffaflığı korur ve kayıpsız sıkıştırma sunar; bu da web grafikleri, küçük resimler ve baskı ön izlemeleri için idealdir.

## Why render EPS to PNG with Aspose.Page?
- **Pure Java API** – yerel bağımlılık yok, JVM'in desteklediği her yerde çalıştırabilirsiniz.  
- **Yüksek doğrulukta render** – vektörel grafikler doğru bir şekilde rasterleştirilir, çizgi kalitesi korunur.  
- **Ölçülü lisanslama** – dönüştürdüğünüz her şey için sadece ödersiniz, maliyetler öngörülebilir olur.  
- **Çoklu çıktı seçenekleri** – PNG'nin yanı sıra JPEG, TIFF vb. de üretebilir, farklı projeler için esneklik sağlar.

## Prerequisites
Başlamadan önce şunların olduğundan emin olun:

- Java programlamaya temel bir hakimiyet.  
- Aspose.Page kütüphanesi yüklü – [buradan](https://releases.aspose.com/page/java/) indirebilirsiniz.  
- Aspose hesabınız üzerinden temin edebileceğiniz ölçülü genel ve özel anahtarlar.

## Import Packages
İhtiyacımız olan sınıfları içe aktarın. Kodun derlenebilmesi için import bloğunu tam olarak gösterildiği gibi tutun.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## How to save EPS as PNG using Aspose.Page Java
Aşağıda lisanslama, yükleme, render etme ve son PNG dosyasını yazma adımlarını birleştiren adım‑adım kılavuz yer alıyor.

### Step 1: Initialize Document and Image Format
Burada ölçülü anahtarları ayarlıyor ve çıktı formatını (PNG) tanımlıyoruz. Bu, **save EPS as PNG** işleminin temelini oluşturur.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Step 2: Initialize PostScript Input Stream
Dönüştürmek istediğiniz EPS dosyasını açın. Akış, belgeyi Aspose.Page'e besler.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Step 3: Check Document License
İşleme başlamadan önce ölçülü lisansın doğru uygulanıp uygulanmadığını her zaman doğrulayın.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Step 4: Initialize Options and Image Device
Dönüştürme ayarlarını kontrol eden seçenek nesnesini ve render edilen görüntüyü alacak cihazı oluşturun.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Step 5: Save EPS File as Image
Bu, temel **save EPS as PNG** çağrısıdır. Belge, yapılandırdığınız seçeneklerle görüntü cihazına render edilir.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Step 6: Get and Save Image Bytes
PNG baytlarını cihazdan çıkarın ve diske bir dosya olarak yazın. Bu adım, **write PNG file Java** işlemini güvenli bir şekilde gösterir.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | Anahtarlar hatalı veya yanlış sırada. | Genel/özel anahtar dizelerini iki kez kontrol edin ve `setMeteredKey`'in belge işleme öncesinde çağrıldığından emin olun. |
| **Output file is empty** | `device.getImagesBytes()` `null` döndü. | EPS dosyasının geçerli olduğundan ve `ImageSaveOptions`'ın sıfır boyutlu bir tuval ayarlamadığından emin olun. |
| **OutOfMemoryError on large EPS** | Büyük vektör dosyalarının render edilmesi çok bellek tüketir. | Sayfaları tek tek işleyin veya JVM yığın boyutunu artırın (`-Xmx2g`). |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: Bu anahtarları Aspose hesabınız üzerinden temin edebilirsiniz.

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page hem ücretsiz deneme hem de ücretli sürümler sunar. Ücretsiz deneme için [buraya](https://releases.aspose.com/) bakın.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Evet, Aspose.Page ticari lisanslar sunar. Lisansları [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Q: Where can I find additional documentation?**  
A: Dokümantasyona [buradan](https://reference.aspose.com/page/java/) ulaşabilirsiniz.

**Q: How can I get temporary licenses?**  
A: Geçici lisansları [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**Q: What if I need to convert multi‑page EPS files?**  
A: `device.getImagesBytes()` ile her sayfayı döngüye alıp ayrı PNG dosyalarına yazabilirsiniz.

**Q: Can I change the PNG quality or color depth?**  
A: Evet, `ImageSaveOptions`'ı (ör. `options.setCompressionLevel(...)`) `document.save(...)` çağrısından önce yapılandırabilirsiniz.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-03
description: Aspose.Page for Java kullanarak EPS'yi PNG olarak kaydetmeyi ve ölçülen
  lisansı yapılandırmayı öğrenin. Tam kod örneğiyle adım adım rehber.
language: tr
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java ile EPS'yi PNG olarak kaydet (Ölçülü Lisans)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS'yi PNG Olarak Kaydetme Aspose.Page Java (Ölçülü Lisans)

## Giriş
Java uygulamanızda **EPS'yi PNG olarak kaydetmek** istiyor ve lisans yönetimini sorunsuz bir şekilde yapmak istiyorsanız doğru yerdesiniz. Bu öğreticide, Aspose.Page için ölçülü bir lisans yapılandırmayı, bir PostScript (EPS) dosyasını yüklemeyi ve PNG görüntüsüne dönüştürmeyi, adım adım ve net bir şekilde anlatacağız.

## Hızlı Yanıtlar
- **“EPS'yi PNG olarak kaydetmek” ne anlama geliyor?** Vektörel bir EPS dosyasını raster bir PNG görüntüsüne dönüştürür.  
- **Ölçülü lisans neden kullanılmalı?** İşlediğiniz sayfa sayısına göre ödeme yapmanızı sağlar; değişken iş yükleri için idealdir.  
- **İnternet bağlantısı gerekiyor mu?** Hayır, ölçülü anahtarlar yerel olarak doğrulanır.  
- **Hangi Java sürümü gerekli?** Java 8 veya üzeri.  
- **Kurulum ne kadar sürer?** Temel bir uygulama için yaklaşık 10 dakika.

## “EPS'yi PNG Olarak Kaydetme” nedir?
EPS'yi PNG olarak kaydetmek, ölçeklenebilir Encapsulated PostScript belgesini yaygın olarak desteklenen bir bitmap formatına dönüştürür. PNG şeffaflığı korur ve kayıpsız sıkıştırma sunar; bu da web grafikleri, küçük resimler ve baskı ön izlemeleri için idealdir.

## Bu görev için Aspose.Page neden kullanılır?
- **Saf Java API** – yerel bağımlılık yok.  
- **Yüksek doğruluk** – vektör grafikleri doğru bir şekilde render edilir.  
- **Ölçülü lisanslama** – yalnızca dönüştürdükleriniz için ödeme yaparsınız.  
- **Birden çok çıktı formatı desteği** – PNG, JPEG, TIFF vb.

## Önkoşullar
Başlamadan önce şunların olduğundan emin olun:

- Java programlama temelleri.  
- Aspose.Page kütüphanesi yüklü – [buradan](https://releases.aspose.com/page/java/) indirebilirsiniz.  
- Aspose hesabınız üzerinden temin edebileceğiniz ölçülü genel ve özel anahtarlar.

## Paketleri İçe Aktar
İhtiyacımız olan sınıfları içe aktaralım. Kodun derlenebilmesi için import bloğunu tam olarak gösterildiği gibi tutun.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Adım 1: Belge ve Görüntü Formatını Başlatma
Burada ölçülü anahtarları ayarlıyor ve çıktı formatını (PNG) tanımlıyoruz. Bu, **EPS'yi PNG olarak kaydetme** işleminin temelini oluşturur.

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

## Adım 2: PostScript Giriş Akışını Başlatma
Dönüştürmek istediğiniz EPS dosyasını açın. Akış, belgeyi Aspose.Page’e besler.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Adım 3: Belge Lisansını Kontrol Et
İşleme başlamadan önce ölçülü lisansın doğru uygulanıp uygulanmadığını her zaman doğrulayın.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Adım 4: Seçenekleri ve Görüntü Aygıtını Başlatma
Dönüştürme ayarlarını kontrol eden seçenek nesnesini ve render edilen görüntüyü alacak aygıtı oluşturun.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Adım 5: EPS Dosyasını Görüntü Olarak Kaydet
Bu, temel **EPS'yi PNG olarak kaydetme** çağrısıdır. Belge, yapılandırdığınız seçeneklerle görüntü aygıtına render edilir.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Adım 6: Görüntü Baytlarını Al ve Kaydet
PNG baytlarını aygıttan çıkarın ve diske bir dosya olarak yazın.

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

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| **Lisans tanınmıyor** | Anahtarlar hatalı veya yanlış sırada. | Genel/özel anahtar dizesini iki kez kontrol edin ve `setMeteredKey` çağrısının herhangi bir belge işleminden önce yapıldığından emin olun. |
| **Çıktı dosyası boş** | `device.getImagesBytes()` `null` döndü. | EPS dosyasının geçerli olduğunu ve `ImageSaveOptions`'ın sıfır boyutlu bir tuval olarak ayarlanmadığını doğrulayın. |
| **Büyük EPS'te OutOfMemoryError** | Büyük vektör dosyalarının render edilmesi çok bellek tüketir. | Sayfaları tek tek işleyin veya JVM yığın boyutunu artırın (`-Xmx2g`). |

## Sıkça Sorulan Sorular

**S:** **Ölçülü genel ve özel anahtarları nasıl elde ederim?**  
**C:** Bu anahtarları Aspose hesabınız üzerinden temin edebilirsiniz.

**S:** **Aspose.Page kütüphanesi ücretsiz mi?**  
**C:** Aspose.Page hem ücretsiz deneme hem de ücretli sürümler sunar. Ücretsiz deneme için [buraya](https://releases.aspose.com/) bakın.

**S:** **Aspose.Page'i ticari projelerde kullanabilir miyim?**  
**C:** Evet, Aspose.Page ticari lisanslar sunar. Lisansları [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S:** **Ek dokümantasyona nereden ulaşabilirim?**  
**C:** Dokümantasyonu [buradan](https://reference.aspose.com/page/java/) inceleyin.

**S:** **Geçici lisansları nasıl alabilirim?**  
**C:** Geçici lisansları [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-03  
**Test Edilen Versiyon:** Aspose.Page 24.12 for Java  
**Yazar:** Aspose  

---
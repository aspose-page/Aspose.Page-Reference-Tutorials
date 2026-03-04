---
date: 2025-12-21
description: Aspose.Page kullanarak Java’da XPS’yi BMP’ye dönüştürürken çözünürlüğü
  nasıl ayarlayacağınızı öğrenin. Bu Java görüntü dönüştürme rehberi yüksek kaliteli
  sonuçlar sağlar.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Java'da XPS'yi BMP'ye Dönüştürürken Çözünürlüğü Nasıl Ayarlarsınız
url: /tr/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS'yi Java'da BMP'ye Dönüştür

## Giriş
Bu adım adım kılavuza hoş geldiniz; Java'da Aspose.Page kullanarak XPS (XML Paper Specification) dosyalarını BMP (Bitmap) formatına dönüştürürken **çözünürlüğün nasıl ayarlanacağını** gösterir. Aspose.Page for Java, XPS belgeleriyle çalışmak için kapsamlı özellikler sunan güçlü bir kütüphanedir. Bu öğreticide, XPS dosyalarını BMP görüntülerine sorunsuz bir şekilde dönüştürme sürecini size anlatacağız.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Page for Java, en eksiksiz XPS → BMP dönüşüm özelliklerini sağlar.  
- **Görüntü kalitesini kontrol edebilir miyim?** Evet – çözünürlüğü ve yumuşatma modunu ayarlamak için `BmpSaveOptions` kullanın.  
- **Yalnızca belirli sayfaları dönüştürmem gerekiyor mu?** Kesinlikle, `options.setPageNumbers()` ile tam olarak istediğiniz sayfaları seçebilirsiniz.  
- **Bu gerçek bir Java görüntü dönüşümü mü?** API, XPS sayfalarını doğrudan bitmap verisine işler, bu yüzden ara formatlara ihtiyaç yoktur.  
- **Hangi Java sürümü destekleniyor?** Tüm modern Java sürümleri (8 ve üzeri) uyumludur.

## Çözünürlük ayarlamanın amacı nedir?
Çözünürlük, oluşturulan BMP görüntüsündeki inç başına düşen nokta sayısını (DPI) belirler. Daha yüksek DPI, daha keskin görüntüler sağlar; bu, baskı veya ayrıntılı grafik çalışmaları için gereklidir. Çözünürlüğü ayarlamak, **java convert xps** iş akışınızın çıktı kalitesi üzerinde tam kontrol sağlar.

## XPS → BMP dönüşümü için Aspose.Page neden kullanılmalı?
- **Yüksek doğruluk** – orijinal XPS'nin vektör kalitesini korur.  
- **İnce ayarlı kontrol** – DPI, yumuşatma ayarlarını yapabilir ve hatta dönüştürmek istediğiniz belirli sayfaları seçebilirsiniz.  
- **Harici bağımlılık yok** – saf Java, yerel kütüphane gerektirmez.  
- **Ölçeklenebilir** – tek sayfalı belgeler ve büyük çok sayfalı XPS dosyaları için çalışır.

## Önkoşullar
Dönüşüm sürecine başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- **Java Geliştirme Ortamı** – Makinenizde Java 8 veya daha yeni bir sürüm kurulu.  
- **Aspose.Page for Java Kütüphanesi** – Aspose.Page for Java kütüphanesini projenize indirin ve ekleyin. Kütüphaneyi [burada](https://releases.aspose.com/page/java/) bulabilirsiniz.  
- **Örnek XPS Dosyası** – BMP'ye dönüştürmek istediğiniz bir örnek XPS belgesi hazırlayın.

## Paketleri İçe Aktarma
Java kodunuzda gerekli Aspose.Page paketlerini dahil edin:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## XPS'den BMP'ye Dönüşümde Çözünürlüğü Nasıl Ayarlarsınız
Aşağıda, çözünürlüğün tam olarak nerede ve nasıl ayarlanacağını ve **belirli sayfaları nasıl dönüştüreceğinizi** gösteren kısa, numaralı bir rehber bulunmaktadır.

### Adım 1: XPS Belgesini Yükle
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Adım 2: Seçenekleri Başlat (Çözünürlük ve Sayfa Seçimi)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Adım 3: İşleme Aygıtı Oluştur
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Adım 4: Seçenekleri Kullanarak Belgeyi Kaydet
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Adım 5: Oluşturulan Görüntüler Üzerinde Döngü Yap ve Dosyalara Yaz
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Dönüşüm sürecinde ihtiyaç duyabileceğiniz ek özelleştirme veya değişiklikler için bu adımları tekrarlayın.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Çözüm |
|-------|----------|
| **Düşük kaliteli BMP çıktısı** | `options.setResolution()` değerinin ≥ 300 DPI olduğundan emin olun. |
| **Belgenin yalnızca bir kısmı dönüştürülüyor** | `options.setPageNumbers()`'ın istenen tüm sayfa indekslerini içerdiğinden emin olun. |
| **Büyük XPS dosyalarında OutOfMemoryError** | Belgeyi daha küçük bölümlerde işleyin veya JVM yığın boyutunu (`-Xmx`) artırın. |
| **Dosya bulunamadı** | `dataDir` yolunu ve giriş XPS dosyasının var olduğunu iki kez kontrol edin. |

## Sıkça Sorulan Sorular
### Q: BMP görüntülerinin çözünürlüğünü özelleştirebilir miyim?
A: Evet, kodda `options.setResolution()` parametresini değiştirerek çözünürlüğü ayarlayabilirsiniz.

### Q: Aspose.Page farklı Java sürümleriyle uyumlu mu?
A: Evet, Aspose.Page geniş bir Java sürüm yelpazesini destekler. Uy compatible bir sürüm kurduğunuzdan emin olun.

### Q: XPS dosyalarını belirli bir sayfa aralığından nasıl dönüştürebilirim?
A: Dönüştürmek istediğiniz sayfa numaralarını belirtmek için `options.setPageNumbers()` metodunu kullanın.

### Q: Aspose.Page tarafından desteklenen başka çıktı formatları var mı?
A: Evet, Aspose.Page çeşitli çıktı formatlarını destekler. Kapsamlı liste için belgelere bakın.

### Q: Ek yardım veya destek nereden bulabilirim?
A: Topluluk desteği ve tartışmalar için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
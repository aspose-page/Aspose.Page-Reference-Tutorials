---
date: 2026-03-08
description: Java'da XPS'yi BMP'ye nasıl dönüştüreceğinizi ve Aspose.Page java görüntü
  dönüştürme kütüphanesini kullanarak BMP çözünürlüğünü nasıl ayarlayacağınızı öğrenin.
  Bu rehber yüksek kaliteli çıktı ve bellek dostu ipuçlarını kapsar.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Java’da XPS’yi BMP’ye Dönüştür – Yüksek Kaliteli Çıktı İçin Çözünürlüğü Ayarla
url: /tr/java/xps-conversion/to-bmp/
weight: 10
---

 missed items: The list under Quick Answers, bullet points. Ensure bold formatting preserved.

Also ensure we didn't translate URLs.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS'yi Java'da BMP'ye Dönüştür

## Giriş
Java'da **XPS'yi BMP'ye dönüştürme** ve Aspose.Page kullanarak optimal görüntü kalitesi için çözünürlüğü ayarlama konusunda adım adım bir rehbere hoş geldiniz. Baskı hattı oluşturuyor, küçük resimler üretiyor ya da yüksek çözünürlüklü grafiklere ihtiyacınız olsun, DPI kontrolü herhangi bir gereksinimi karşılamak için size esneklik sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Page for Java, XPS → BMP için en eksiksiz **java image conversion library**'dir.  
- **Görüntü kalitesini kontrol edebilir miyim?** Evet – `BmpSaveOptions` kullanarak **BMP çözünürlüğünü ayarlayın** ve yumuşatma modunu belirleyin.  
- **Büyük XPS dosyalarını işlerken Java OutOfMemoryError hatasından nasıl kaçınırım?** Sayfaları bölümlerde render edin veya JVM yığınını (`-Xmx`) artırın.  
- **Sadece belirli sayfaları dönüştürmem gerekiyor mu?** Kesinlikle, `options.setPageNumbers()` tam olarak istediğiniz sayfaları seçmenizi sağlar.  
- **Hangi Java sürümleri destekleniyor?** Tüm modern Java sürümleri (8 ve üzeri) sorunsuz çalışır.

## Çözünürlüğü ayarlamanın amacı nedir?
Çözünürlük, oluşturulan BMP görüntüsündeki inç başına düşen nokta sayısını (DPI) belirler. Daha yüksek DPI, daha keskin görüntüler sağlar; bu, baskı veya detaylı grafik çalışmaları için gereklidir. Çözünürlüğü ayarlamak, **convert xps to bmp** iş akışınızın çıktı kalitesi üzerinde tam kontrol sağlar.

## Neden XPS → BMP dönüşümü için Aspose.Page kullanmalısınız?
- **Yüksek doğruluk** – orijinal XPS'nin vektör kalitesini korur.  
- **Detaylı kontrol** – DPI, yumuşatma ayarlarını yapabilir ve hatta belirli sayfaları dönüştürmeyi seçebilirsiniz.  
- **Harici bağımlılık yok** – saf Java, yerel kütüphane gerektirmez.  
- **Ölçeklenebilir** – tek sayfalı belgeler ve büyük çok sayfalı XPS dosyaları için çalışır.  

## Önkoşullar
Dönüşüm sürecine başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- **Java Geliştirme Ortamı** – Makinenizde Java 8 veya daha yeni bir sürüm yüklü.  
- **Aspose.Page for Java Kütüphanesi** – Aspose.Page for Java kütüphanesini projenize indirin ve ekleyin. Kütüphaneyi [burada](https://releases.aspose.com/page/java/) bulabilirsiniz.  
- **Örnek XPS Dosyası** – BMP'ye dönüştürmek istediğiniz bir örnek XPS belgesi hazırlayın.

## Paketleri İçe Aktarma
Java kodunuzda gerekli Aspose.Page paketlerini dahil edin:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## XPS'yi BMP'ye Dönüştürürken Çözünürlüğü Nasıl Ayarlarsınız
Aşağıda, çözünürlüğün tam olarak nerede ve nasıl ayarlanacağını ve **belirli sayfaları dönüştürmeyi** gösteren kısa, numaralı bir adım adım kılavuz bulunmaktadır.

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

### Adım 3: Render Cihazı Oluştur
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Adım 4: Seçenekleri Kullanarak Belgeyi Kaydet
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Adım 5: Render Edilen Görüntüler Üzerinde Döngü Oluştur ve Dosyalara Yaz
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

Dönüşüm sürecinde ihtiyaç duyabileceğiniz ek özelleştirmeler veya değişiklikler için bu adımları tekrarlayın.

## Büyük XPS Dosyalarını Dönüştürürken Java OutOfMemoryError Hatasından Kaçınma
- **Bölümler halinde işleyin** – Örnek, belgeyi bölümler halinde (`device.getResult()`) render eder, bu da bellek baskısını azaltır.  
- **JVM yığınını artırın** – Büyük belgeler için daha fazla bellek ayırmak amacıyla `-Xmx` bayrağını (ör. `-Xmx2g`) kullanın.  
- **Kaynakları serbest bırakın** – İşiniz bittiğinde yerel kaynakları serbest bırakmak için `document.close()` çağırın.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Çözüm |
|-------|----------|
| **Düşük kaliteli BMP çıktısı** | `options.setResolution()` değerinin ≥ 300 DPI olduğundan emin olun. |
| **Belgenin yalnızca bir kısmı dönüştürülüyor** | `options.setPageNumbers()`'ın istenen tüm sayfa indekslerini içerdiğinden emin olun. |
| **Büyük XPS dosyalarında OutOfMemoryError** | Belgeyi daha küçük bölümlerde işleyin veya JVM yığın boyutunu (`-Xmx`) artırın. |
| **Dosya bulunamadı** | `dataDir` yolunu ve giriş XPS dosyasının mevcut olduğunu iki kez kontrol edin. |

## Sıkça Sorulan Sorular
### Q: BMP görüntülerinin çözünürlüğünü özelleştirebilir miyim?
A: Evet, kodda `options.setResolution()` parametresini değiştirerek çözünürlüğü ayarlayabilirsiniz.

### Q: Aspose.Page farklı Java sürümleriyle uyumlu mu?
A: Evet, Aspose.Page geniş bir Java sürüm yelpazesini destekler. Uyumlulu bir sürümün yüklü olduğundan emin olun.

### Q: XPS dosyalarını belirli bir sayfa aralığından nasıl dönüştürebilirim?
A: Dönüştürmek istediğiniz sayfa numaralarını belirtmek için `options.setPageNumbers()` metodunu kullanın.

### Q: Aspose.Page tarafından desteklenen başka çıktı formatları var mı?
A: Evet, Aspose.Page çeşitli çıktı formatlarını destekler. Kapsamlı liste için belgelere bakın.

### Q: Ek yardım veya destek nereden bulunabilir?
A: Topluluk desteği ve tartışmalar için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

---

**Son Güncelleme:** 2026-03-08  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
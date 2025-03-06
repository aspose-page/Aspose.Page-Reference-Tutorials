---
title: XSP'yi Java'da TIFF'e dönüştürün
linktitle: XSP'yi Java'da TIFF'e dönüştürün
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile XPS'yi zahmetsizce TIFF'e dönüştürün. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin. Şimdi İndirin!
weight: 14
url: /tr/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XSP'yi Java'da TIFF'e dönüştürün

Günümüzün dijital çağında, belge dönüştürme çeşitli uygulamalarda çok önemli bir rol oynamaktadır. XPS (XML Kağıt Belirtimi) belgelerini TIFF'e (Etiketli Görüntü Dosyası Formatı) dönüştürmek için sağlam bir çözüm arayan bir Java geliştiricisiyseniz Aspose.Page for Java, başvuracağınız kitaplıktır. Bu adım adım kılavuzda, ayrıntılı açıklamalar ve kod parçacıklarıyla sorunsuz bir deneyim yaşamanızı sağlayarak süreç boyunca size yol göstereceğiz.
## Önkoşullar
Dönüştürme sürecine dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Page Java kütüphanesi için. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
-  Aspose.Page for Java için geçerli bir lisans. Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) veya tam lisans satın alın[Burada](https://purchase.aspose.com/buy).
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Aspose.Page for Java kütüphanesinin projenize eklendiğinden emin olun.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 1. Adım: Belge Dizinini Ayarlayın
Giriş XPS dosyasının bulunduğu belge dizininizin yolunu tanımlayın.
```java
String dataDir = "Your Document Directory";
```
## Adım 2: XPS Belgesini Yükleyin
Aspose.Page kütüphanesini kullanarak XPS belgesini yükleyin.
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 3. Adım: TiffSaveOptions'ı başlatın
TiffSaveOptions nesnesini düzgünleştirme modu, çözünürlük ve belirli sayfa numaraları gibi gerekli parametrelerle başlatın.
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Adım 4: İşleme Cihazı Oluşturun
ImageDevice sınıfını kullanarak TIFF formatı için bir işleme cihazı oluşturun.
```java
ImageDevice device = new ImageDevice();
```
## Adım 5: Belgeyi TIFF'e Kaydetme
Belirtilen seçenekleri ve işleme cihazını kullanarak XPS belgesini TIFF formatında kaydedin.
```java
document.save(device, options);
```
## Adım 6: TIFF Görüntülerini Yineleyin ve Kaydedin
Görüntü çıkış akışlarını başlatarak ve TIFF görüntülerini kaydederek belge bölümleri ve sayfaları yineleyin.
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 Tebrikler! Aspose.Page'i kullanarak XPS'yi Java'da TIFF'e başarıyla dönüştürdünüz. Kütüphanenin daha fazla özelliğini ve işlevini keşfetmekten çekinmeyin.[dokümantasyon](https://reference.aspose.com/page/java/).
## Çözüm
Bu eğitimde Aspose.Page'i kullanarak XPS'yi Java'da TIFF'e dönüştürmek için gerekli adımları ele aldık. Belge dönüştürme artık parmaklarınızın ucunda, çok yönlü dosya formatı desteğiyle uygulamalarınızı geliştirmenize olanak tanıyor.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı lisans olmadan kullanabilir miyim?
 Değerlendirme için geçici bir lisans alabilirsiniz ancak üretim amaçlı kullanım için geçerli bir lisans gereklidir. Lisansınızı alın[Burada](https://purchase.aspose.com/buy).
### Dönüştürme için XPS dosyalarının boyutunda herhangi bir sınırlama var mı?
Aspose.Page for Java, çeşitli boyutlardaki belgeleri yönetir, ancak kendi ortamınızda daha büyük dosyalarla test etmeniz önerilir.
### Aspose.Page for Java hakkında nasıl destek alabilirim veya soru sorabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüyle kütüphaneyi keşfedebilirsiniz. İndir[Burada](https://releases.aspose.com/).
### Bu dönüştürmede TIFF görüntüleri için önerilen çözünürlük nedir?
Sağlanan örnekte 300 DPI çözünürlük kullanılmaktadır ancak bunu özel gereksinimlerinize göre ayarlayabilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

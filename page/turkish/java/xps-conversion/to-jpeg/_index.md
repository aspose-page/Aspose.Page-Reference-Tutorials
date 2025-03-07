---
title: Java'da XPS'yi JPEG'e dönüştürün
linktitle: Java'da XPS'yi JPEG'e dönüştürün
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java'da XPS'yi JPEG'e nasıl dönüştüreceğinizi öğrenin. Sorunsuz entegrasyon için adım adım talimatlar içeren kapsamlı bir kılavuz.
weight: 11
url: /tr/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da XPS'yi JPEG'e dönüştürün

## giriiş
Bu eğitimde, Aspose.Page for Java'yı kullanarak XPS (XML Kağıt Belirtimi) dosyalarını JPEG görüntülere nasıl dönüştürebileceğimizi inceleyeceğiz. Aspose.Page, geliştiricilerin XPS ve diğer belge formatlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir Java kütüphanesidir. Bu adım adım kılavuz, süreci anlamanıza ve Java uygulamalarınızda uygulamanıza yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java Geliştirme Ortamı: Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.
-  Aspose.Page for Java Library: Aspose.Page for Java kütüphanesini indirip yükleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/page/java/).
- Örnek XPS Belgesi: JPEG'e dönüştürmek istediğiniz örnek bir XPS belgeniz olsun.
## Paketleri İçe Aktar
Gerekli paketleri Java sınıfınıza aktararak başlayın:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 1. Adım: Yolları ve XPS Belgesini Başlatın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// XPS giriş akışını başlat
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Adım 2: JpegSaveOptions'ı ayarlayın
```java
// Seçenekler nesnesini gerekli parametrelerle başlatın.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 3. Adım: İşleme Cihazı Oluşturun
```java
// PDF formatı için işleme cihazı oluşturun
ImageDevice device = new ImageDevice();
```
## 4. Adım: XPS'yi JPEG olarak kaydedin
```java
document.save(device, options);
```
## Adım 5: JPEG Sayfalarını Yineleyin ve Kaydedin
```java
//Belge bölümleri boyunca yineleme yapın (XPS terimleriyle sabit belgeler)
for (int i = 0; i < device.getResult().length; i++) {
    // Bölüm sayfalarını yineleyin
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Görüntü çıkış akışını başlat
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Resim yaz
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //akışı kapat
        imageStream.close();
    }
}
```
Bu adım dizisi, XPS belgenizi, her biri ayrı ayrı kaydedilen JPEG görüntülerine etkili bir şekilde dönüştürecektir.
## Çözüm
Tebrikler! Aspose.Page'i kullanarak XPS'yi Java'da JPEG'e nasıl dönüştüreceğinizi başarıyla öğrendiniz. Bu süreç, Java uygulamalarında belge dönüştürmeyle çalışan geliştiriciler için çok değerlidir.
## Sıkça Sorulan Sorular

### S: Aspose.Page ticari projeler için uygun mudur?
 C: Evet, Aspose.Page, lisanslama seçeneklerinin mevcut olduğu ticari bir üründür. Kontrol etmek[Burada](https://purchase.aspose.com/buy) detaylar için.
### S: Satın almadan önce Aspose.Page'i deneyebilir miyim?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Page belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### S: Aspose.Page için nasıl destek alabilirim?
 C: Ziyaret edin[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) topluluk temelli destek için.
### S: Test için geçici bir lisansa ihtiyacım var mı?
 C: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

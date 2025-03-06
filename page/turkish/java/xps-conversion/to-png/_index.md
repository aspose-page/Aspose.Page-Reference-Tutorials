---
title: Java'da XPS'yi PNG'ye dönüştürün
linktitle: Java'da XPS'yi PNG'ye dönüştürün
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak XPS'yi Java'da zahmetsizce PNG'ye dönüştürün. Bu güvenilir ve geliştirici dostu çözümle belge görevlerini kolaylaştırın.
weight: 13
url: /tr/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da XPS'yi PNG'ye dönüştürün

## giriiş
Yazılım geliştirmenin dinamik dünyasında, XPS (XML Kağıt Belirtimi) belgelerini PNG (Taşınabilir Ağ Grafikleri) görüntülerine dönüştürme ihtiyacı sıklıkla ortaya çıkar. Aspose.Page, Java'da bu görevi sorunsuz bir şekilde gerçekleştirmek için güçlü bir çözüm sunar. Bu eğitimde Aspose.Page for Java'yı kullanarak XPS'yi PNG'ye dönüştürme sürecini anlatacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Page for Java: Aspose.Page kütüphanesini indirip yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/page/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi Java uyumlu bir IDE seçin.
## Paketleri İçe Aktar
Aspose.Page işlevlerini kullanmak için Java projenizde gerekli paketleri içe aktarın. Java dosyanızın başına aşağıdaki içe aktarma ifadelerini ekleyin:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 1. Adım: Belge Dizinini Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
## Adım 2: XPS Belgesini Yükleyin
```java
// XPS belgesini yükle
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 3. Adım: Seçenekleri Başlat
```java
// Seçenekler nesnesini gerekli parametrelerle başlatın.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Adım 4: İşleme Cihazı Oluşturun
```java
// PDF formatı için işleme cihazı oluşturun
ImageDevice device = new ImageDevice();
```
## Adım 5: Kaydet ve Yinele
```java
// Seçenekleri ve cihazı kullanarak XPS belgesini PNG'ye kaydedin
document.save(device, options);
//Belge bölümleri boyunca yineleme yapın (XPS terimleriyle sabit belgeler)
for (int i = 0; i < device.getResult().length; i++) {
    // Bölüm sayfalarını yineleyin
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Görüntü çıkış akışını başlat
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Resim yaz
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Akışı Kapat
        imageStream.close();
    }
}
```
Bu adımları izleyerek, Aspose.Page for Java'yı kullanarak XPS belgelerini zahmetsizce PNG görüntülerine dönüştürebilirsiniz.
## Çözüm
Sonuç olarak Aspose.Page for Java, geliştiricilere güvenilir ve etkili bir araç sağlayarak XPS'den PNG'ye dönüştürme işlemini basitleştirir. Belge işleme görevlerini kolaylaştırmak için bu kitaplığı Java projelerinize ekleyin.
## SSS
### Aspose.Page for Java'yı ticari projelerde kullanabilir miyim?
 Evet, Aspose.Page ticari bir üründür. Lisans bilgilerini bulabilirsiniz[Burada](https://purchase.aspose.com/buy).
### Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java belgelerini nerede bulabilirim?
 Kapsamlı belgeler mevcuttur[Burada](https://reference.aspose.com/page/java/).
### Test amaçlı geçici lisansı nasıl edinebilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page tartışmaları için topluluk forumları var mı?
 Evet, topluluk forumlarını ziyaret edin[Burada](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

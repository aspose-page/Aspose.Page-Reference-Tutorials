---
title: Java kullanarak XMP'deki Dizi Öğelerini Değiştirme
linktitle: Java kullanarak XMP'deki Dizi Öğelerini Değiştirme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java'yı kullanarak XMP'deki dizi öğelerini nasıl değiştireceğinizi öğrenin. Adım adım kılavuzumuzla meta verileri zahmetsizce değiştirin. EPS belgelerinizi şimdi geliştirin!
weight: 15
url: /tr/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP'deki Dizi Öğelerini Değiştirme

## giriiş
Aspose.Page for Java'yı kullanarak XMP'deki dizi öğelerini değiştirmeye ilişkin kapsamlı kılavuzumuza hoş geldiniz! Aspose.Page, EPS dosyalarındaki XMP meta verileriyle sorunsuz bir şekilde çalışmanıza olanak tanıyan güçlü bir Java kütüphanesidir. Bu eğitimde, XMP meta verileri içindeki dizi öğelerini değiştirme sürecinde size yol göstererek EPS belgelerinizi geliştirmenize ve özelleştirmenize yardımcı olacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Java için Aspose.Page kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktaralım. Aspose.Page kütüphanesinin projenize dahil olduğundan emin olun.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## 1. Adım: XMP Meta Verilerini Alın
Öncelikle XMP meta verilerini EPS dosyanızdan alın. EPS dosyası zaten XMP meta verilerini içermiyorsa, %%Creator, %%CreateDate, %%Title vb. gibi PS meta veri yorumlarındaki değerlerle yeni bir tane oluşturulacaktır.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP meta verilerini alın. EPS dosyası XMP meta verilerini içermiyorsa, yeni bir dosya PS meta veri yorumlarındaki değerlerle doldurulacaktır.
XmpMetadata xmp = document.getXmpMetadata();
```
## Adım 2: "dc:title" Dizi Öğesini Ayarlayın
Şimdi "dc:title" dizi öğesini 0 indeksine yeni bir değerle ayarlayalım.
```java
// "dc:title" dizi öğesini 0 dizinine göre ayarla
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Adım 3: "dc:creator" Dizi Öğesini Ayarlayın
Benzer şekilde, "dc:creator" dizi öğesini yeni bir yaratıcı değeriyle 0 dizinine ayarlayın.
```java
// "dc:creator" dizi öğesini 0 dizinine göre ayarla
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Adım 4: Çıktı EPS Dosya Akışını Başlatın
Değiştirilen belgenin kaydedileceği çıktı EPS dosya akışını hazırlayın.
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Adım 5: Belgeyi Değiştirilmiş XMP Meta Verileriyle Kaydetme
Belgeyi güncellenmiş XMP meta verileriyle kaydedin.
```java
//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak XMP'de dizi öğelerini nasıl değiştireceğinizi başarıyla öğrendiniz. Bu eğitim, EPS belgelerinizi özelleştirilmiş meta verilerle zahmetsizce geliştirebilmenizi sağlayan adım adım rehberlik sağladı.

## SSS
### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java için tasarlanmıştır ancak Aspose diğer diller için de benzer kütüphaneler sağlar.
### Aspose.Page for Java'nın ayrıntılı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'nın tam sürümünü nereden satın alabilirim?
 Tam sürümünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

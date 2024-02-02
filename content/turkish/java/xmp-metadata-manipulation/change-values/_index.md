---
title: Java kullanarak XMP'deki Değerleri Değiştirme
linktitle: Java kullanarak XMP'deki Değerleri Değiştirme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile EPS belgelerini geliştirin. Özelleştirilmiş ve profesyonel içerik için XMP meta verilerini zahmetsizce değiştirin. #JavaGeliştirme
type: docs
weight: 17
url: /tr/java/xmp-metadata-manipulation/change-values/
---
## giriiş
Belge işleme ve işleme alanında Aspose.Page for Java güçlü bir araç olarak öne çıkıyor. Bu eğitimde, Aspose.Page kütüphanesi ile Java kullanılarak EPS (Encapsulated PostScript) belgelerinde XMP (Genişletilebilir Meta Veri Platformu) değerlerinin değiştirilmesi süreci anlatılmaktadır. Sağlanan adım adım kılavuzu takip ederek meta verileri zahmetsizce nasıl değiştireceğinizi öğrenecek ve belgelerinizin özel gereksinimlerinize göre uyarlanmasını sağlayacaksınız.
## Önkoşullar
Bu eğitime başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Java Geliştirme Ortamı: Makinenizde çalışan bir Java geliştirme ortamının olduğundan emin olun.
2.  Aspose.Page for Java Library: Aspose.Page for Java kütüphanesini indirip yükleyin. Gerekli paketi bulabilirsiniz[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Bu paketler, EPS belgeleriyle etkileşimde bulunmak ve bunları değiştirmek için hayati öneme sahiptir.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## 1. Adım: XMP Meta Verilerini Alın
EPS belgesinden XMP meta verilerini alın. EPS dosyası XMP meta verilerini içermiyorsa, %%Creator, %%CreateDate ve %%Title gibi PS meta veri yorumlarındaki değerlerle yeni bir tane oluşturulacaktır.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// XMP meta verilerini alın. EPS dosyası XMP meta verilerini içermiyorsa PS meta veri yorumlarındaki değerlerle yeni bir tane oluşturulur
XmpMetadata xmp = document.getXmpMetadata();
```
## 2. Adım: "ModifyDate" Değerini Değiştirin
İstediğiniz tarihi yansıtacak şekilde XMP meta verilerindeki "ModifyDate" değerini değiştirin.
```java
// "ModifyDate" değerini değiştirin
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## 3. Adım: "Yaratıcı" Değerini Değiştirin
Belgenin oluşturucusunu belirtmek için XMP meta verilerindeki "Oluşturucu" değerini güncelleyin.
```java
// "Yaratıcı" değerini değiştir
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Adım 4: "Başlık" Değerini Değiştirin
Belgeye uygun bir başlık ayarlamak için XMP meta verilerindeki "Başlık" değerini değiştirin.
```java
//"Başlık" değerini değiştir
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Adım 5: Belgeyi Değiştirilmiş XMP Meta Verileriyle Kaydetme
Güncellenmiş XMP meta verilerini içeren belgeyi yeni bir EPS dosyasına kaydedin.
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak EPS belgelerindeki XMP değerlerini değiştirme sürecini başarıyla tamamladınız. Bu eğitim sizi meta verileri değiştirme bilgisiyle donatarak belgelerinizin özel gereksinimlerinize sorunsuz bir şekilde uyum sağlamasını sağlar.
## SSS
### S: XMP değerlerini değiştirirken saat dilimi hususlarını nasıl ele alabilirim?
 Faydalanmak`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` saat dilimi ayarlarında tutarlılığı sağlamak için.
### S: Tek bir işlemde birden fazla XMP değerini değiştirebilir miyim?
 Evet, kullanarak`put` İstediğiniz her değer için yöntemi kullanarak birden fazla XMP değerini aynı anda değiştirebilirsiniz.
### S: Aspose.Page for Java'ya ilişkin ek belgeleri nerede bulabilirim?
 Kapsamlı belgeleri keşfedin[Burada](https://reference.aspose.com/page/java/).
### S: Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
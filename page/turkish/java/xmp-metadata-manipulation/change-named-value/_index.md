---
title: Java kullanarak XMP'deki Adlandırılmış Değeri Değiştirme
linktitle: Java kullanarak XMP'deki Adlandırılmış Değeri Değiştirme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java'yı keşfedin - Kolaylaştırılmış belge işleme için adım adım kılavuzumuzla EPS dosyalarındaki XMP meta verilerini zahmetsizce değiştirin.
weight: 16
url: /tr/java/xmp-metadata-manipulation/change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP'deki Adlandırılmış Değeri Değiştirme

Belge işleme alanında Aspose.Page for Java, geliştiricilerin EPS dosyalarındaki XMP meta verileriyle sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir araç olarak öne çıkıyor. Bu adım adım kılavuz, Aspose.Page for Java'yı kullanarak XMP'de adlandırılmış bir değeri değiştirme sürecinde size yol gösterecektir. Ayrıntılara girmeden önce bir girişle sahneyi hazırlayalım.
## giriiş
Aspose.Page for Java, EPS dosyalarının değiştirilmesini ve işlenmesini kolaylaştıran güçlü bir Java kütüphanesidir. Bu dosyalar içindeki XMP meta verilerinin işlenmesi söz konusu olduğunda Aspose.Page, geliştiricilere kapsamlı bir dizi özellik sunar. Bu eğitimde, XMP'de adlandırılmış bir değeri değiştirmeye odaklanacağız ve belge işleme yeteneklerini geliştirmek isteyen geliştiriciler için açık ve kısa bir kılavuz sunacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Java Geliştirme Ortamı: Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.
2.  Aspose.Page for Java Kütüphanesi: Aspose.Page for Java kütüphanesini indirin ve projenize entegre edin. Kütüphaneyi ve ayrıntılı belgeleri bulabilirsiniz.[Burada](https://reference.aspose.com/page/java/).
3. Örnek EPS Dosyası: Deney için örnek bir EPS dosyasını hazır bulundurun. Elinizde yoksa, sağlanan "xmp4.eps" adlı örnek dosyayı kullanabilirsiniz.
## Paketleri İçe Aktar
Süreci başlatmak için gerekli paketleri Java kodunuza aktarın. Bu paketler Aspose.Page for Java ile etkileşim için gereklidir. Java dosyanızın başına aşağıdaki satırları ekleyin:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
Şimdi Aspose.Page for Java kullanarak XMP'de adlandırılmış bir değeri değiştirme sürecini birden fazla adıma ayıralım:
## 1. Adım: Giriş EPS Dosya Akışını Başlatın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
        
// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## 2. Adım: PsDocument'i başlatın
```java
PsDocument document = new PsDocument(psStream);
```
## 3. Adım: XMP Meta Verilerini Alın
```java
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarından gelen değerlerle dolu yeni bir tane alırız (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Adım 4: XMP'de Yeni Değer Ayarlayın
```java
// "xmpTPg:MaxPageSize" yapısının "stDim:unit" adlı değeri için yeni "İnç" dize değerini ayarlayın
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## Adım 5: Çıktı EPS Dosya Akışını Başlatın
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## Adım 6: Belgeyi Değiştirilmiş XMP Meta Verileriyle Kaydetme
```java
//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Adım 7: Giriş EPS Akışını Kapatın
```java
// Giriş EPS akışını kapat
psStream.close();
```
Bu adım adım kılavuz, Aspose.Page for Java kullanarak XMP'de adlandırılmış bir değeri değiştirmeye sistematik bir yaklaşım sağlar. Bu adımları izleyerek bu işlevselliği Java uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## Çözüm
Sonuç olarak Aspose.Page for Java, EPS dosyalarındaki XMP meta verileriyle çalışma sürecini basitleştirir. Bu eğitim sizi XMP'de adlandırılmış bir değeri etkili bir şekilde değiştirme bilgisiyle donatarak belge işleme yeteneklerinizi geliştirdi.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak Aspose çeşitli programlama dilleri için benzer kütüphaneler sağlar.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Page for Java'nın ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java hakkında ek destek ve tartışmaları nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'yı nereden satın alabilirim?
 Aspose.Page for Java'yı satın almak için şu adresi ziyaret edin:[satın alma sayfası](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

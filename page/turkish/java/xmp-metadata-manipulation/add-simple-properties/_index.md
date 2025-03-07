---
title: Java kullanarak XMP'ye Basit Özellikler Ekleme
linktitle: Java kullanarak XMP'ye Basit Özellikler Ekleme
second_title: Aspose.Page Java API'si
description: EPS dosyalarındaki XMP meta verilerine özellikler ekleme kılavuzumuzla Aspose.Page for Java'nın potansiyelini ortaya çıkarın. Belge işlemeyi zahmetsizce geliştirin!
weight: 14
url: /tr/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP'ye Basit Özellikler Ekleme

## giriiş
Sürekli gelişen belge işleme ortamında, meta verileri verimli bir şekilde yönetmek çok önemlidir. Aspose.Page for Java, geliştiricilerin Genişletilebilir Meta Veri Platformu (XMP) verilerini sorunsuz bir şekilde işlemesine olanak tanır. Bu eğitimde, Java kullanarak XMP'ye basit özellikler ekleme sürecini inceleyerek size kapsamlı bir adım adım kılavuz sunacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Page for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
- Meta verileri içeren örnek bir EPS dosyası. Eğer elinizde yoksa, sağlanan "xmp3.eps" dosyasını kullanmaktan çekinmeyin.
## Paketleri İçe Aktar
Projenizi başlatmak için gerekli paketleri içe aktardığınızdan emin olun:
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
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarından gelen değerlerle dolu yeni bir tane alırız (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.getXmpMetadata();
```
## 2. Adım: Tarih Özelliğini Ekle
```java
// Tarih özelliği "xmp:Date1" değerini ekle
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Adım 3: Tamsayı Özelliği Ekleme
```java
// Tamsayı özelliği "xmp:Intg1" değerini ekle
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Adım 4: Çift Özellik Ekleme
```java
// Çift özellik "xmp:Double1" değerini ekle
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Adım 5: Dize Özelliği Ekleme
```java
// Dize özelliği "xmp:String1" değerini ekle
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Adım 6: Belgeyi Kaydet
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 7. Adım: Akışları Kapatın
```java
// Giriş EPS akışını kapat
psStream.close();
```
## Çözüm
Aspose.Page for Java, EPS dosyalarındaki XMP meta verilerini değiştirme işlemini basitleştirir. Bu adım adım kılavuzu izleyerek belgenizin meta verilerini geliştirmek için basit özellikleri zahmetsizce ekleyebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak .NET gibi diğer diller için de versiyonlar mevcuttur.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü edinerek Aspose.Page'in özelliklerini keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java'nın ayrıntılı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alınabilir[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'yı nereden satın alabilirim?
 Ürünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

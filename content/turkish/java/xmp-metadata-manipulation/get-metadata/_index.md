---
title: Java kullanarak XMP'den Meta Veri Alma
linktitle: Java kullanarak XMP'den Meta Veri Alma
second_title: Aspose.Page Java API'si
description: XMP meta verilerini zahmetsizce çıkarmak için Aspose.Page for Java'nın gücünün kilidini açın. Adım adım kılavuzumuzla belge analizini geliştirin!
type: docs
weight: 18
url: /tr/java/xmp-metadata-manipulation/get-metadata/
---
## giriiş
XMP dosyalarından meta veri çıkarmak için Aspose.Page for Java'nın kullanımına ilişkin adım adım kılavuzumuza hoş geldiniz. XMP (Genişletilebilir Meta Veri Platformu), meta verileri dosyalarda depolamanın standartlaştırılmış bir yolunu sağlar. Bu eğitim, Java kullanarak XMP'den temel bilgilerin alınmasına odaklanarak belge ayrıntılarına ilişkin öngörüler sunar.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java Geliştirme Kiti (JDK): Makinenizde Java'nın kurulu olduğundan emin olun.
-  Aspose.Page for Java: Burada bulabileceğiniz Aspose.Page kütüphanesini indirip yükleyin.[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Java projenizde gerekli paketleri içe aktarın:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## 1. Adım: Giriş EPS Dosya Akışını Başlatın
Belge dizininizin yolunu ayarlayarak ve giriş EPS dosya akışını başlatarak başlayın.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## 2. Adım: XMP Meta Verilerini Alın
EPS dosyasından XMP meta verilerini alın. Dosyada XMP meta verileri eksikse PS meta veri yorumlarından alınan değerlerle yeni bir dosya oluşturulacaktır.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## 3. Adım: CreatorTool Bilgilerini Çıkarın
XMP meta verilerinden "CreatorTool" değerini kontrol edip yazdırın.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Adım 4: CreateDate Bilgilerini Çıkarın
XMP meta verilerinden "CreateDate" değerini kontrol edip yazdırın.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Adım 5: Küçük Resim Genişliğini Alın
Küçük resimler varsa, ilk küçük resmin genişliğini çıkarın ve yazdırın.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Adım 6: Format Bilgilerini Çıkarın
XMP meta verilerinden "format" değerini kontrol edin ve yazdırın.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Adım 7: DocumentID'yi edinin
XMP meta verisinden "DocumentID" değerini kontrol edip yazdırın.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak XMP meta verilerini nasıl çıkaracağınızı başarıyla öğrendiniz. Bu kılavuz, sürece ilişkin kapsamlı bir genel bakış sunarak belgelerinizden önemli bilgileri etkili bir şekilde alabilmenizi sağlar.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
 Evet, Aspose.Page, Java, .NET ve daha fazlası dahil olmak üzere birçok dili destekler. Kontrol edin[dokümantasyon](https://reference.aspose.com/page/java/) detaylar için.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java desteğini nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.
### Aspose.Page for Java için nasıl geçici lisans edinebilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'ya yönelik ek kaynaklar var mı?
 Tamamını keşfedin[dokümantasyon](https://reference.aspose.com/page/java/) ve kütüphaneyi indirin[Burada](https://releases.aspose.com/page/java/).
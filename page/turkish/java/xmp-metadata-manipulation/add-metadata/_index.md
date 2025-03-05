---
title: Java kullanarak XMP'ye Meta Veri Ekleme
linktitle: Java kullanarak XMP'ye Meta Veri Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java'nın kusursuz entegrasyonunu keşfedin ve XMP meta verilerini EPS dosyalarınıza zahmetsizce nasıl ekleyeceğinizi öğrenin. Belge yönetimi oyununuzu bugün yükseltin!
type: docs
weight: 11
url: /tr/java/xmp-metadata-manipulation/add-metadata/
---
## giriiş
Java kullanarak XMP bilgileri ekleyerek belgenizin meta verilerini geliştirmek mi istiyorsunuz? Başka yerde arama! Bu adım adım kılavuz, Aspose.Page for Java kütüphanesini kullanarak bir EPS dosyasına meta veri ekleme sürecinde size yol gösterecektir. Aspose.Page, Java uygulamalarındaki belge düzenleme görevlerini basitleştiren güçlü bir araçtır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Page for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
- Değiştirmek istediğiniz bir EPS dosyası.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java programınıza aktarın:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## 1. Adım: XMP Meta Verilerini Alın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarındaki değerler kullanılarak yeni bir tane oluşturulur (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.getXmpMetadata();
```
"Belge Dizininiz"i belgelerinizin saklandığı gerçek yolla değiştirdiğinizden emin olun.

## Adım 2: CreatorTool Değerini Alın
```java
// "CreatorTool" değerini alın
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 3. Adım: CreateDate Değerini Alın
```java
// "CreateDate" değerini alın
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Adım 4: Başlık Değerini Alın
```java
// "Başlık" değerini al
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Adım 5: Format Değerini Alın
```java
//"Biçim" değerini al
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 6. Adım: İçerik Oluşturucunun Değerini Alın
```java
// "Yaratıcı" değerini alın
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Adım 7: MetadataDate Değerini Alın
```java
// "MetadataDate" değerini alın
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## 8. Adım: Belgeyi Yeni XMP Meta Verileriyle Kaydetme
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Belgeyi yeni XMP meta verileriyle kaydedin
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Son olarak giriş EPS akışını kapatmayı unutmayın:
```java
// Giriş EPS akışını kapat
psStream.close();
```
Artık Aspose.Page for Java'yı kullanarak EPS dosyanıza meta verileri başarıyla eklediniz!
## Çözüm
Bu eğitimde Aspose.Page for Java kütüphanesini kullanarak bir EPS dosyasına XMP meta verileri ekleme sürecini inceledik. Bu güçlü araç, belgeleri sorunsuz bir şekilde yönetmenize olanak tanıyarak genel belge yönetimi deneyiminizi geliştirir.
## SSS
### S: Aspose.Page for Java'nın kullanımı ücretsiz midir?
 C: Aspose.Page for Java ticari bir üründür. Ücretsiz deneme yoluyla özelliklerini keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Page for Java belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### S: Aspose.Page for Java için nasıl geçici lisans alabilirim?
 C: Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Page for Java hangi dosya formatlarını destekliyor?
C: Aspose.Page for Java, EPS, PDF ve XPS dahil çeşitli formatları destekler.
### S: Java için Aspose.Page'i satın alabilir miyim?
 C: Evet, Java için Aspose.Page'i satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
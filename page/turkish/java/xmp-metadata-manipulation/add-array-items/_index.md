---
title: Java kullanarak XMP Meta Verilerine Dizi Öğeleri Ekleme
linktitle: Java kullanarak XMP Meta Verilerine Dizi Öğeleri Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile EPS dosyalarını geliştirin. XMP meta verilerine dizi öğelerini zahmetsizce eklemeyi öğrenin. Şimdi adım adım kılavuzumuzu takip edin!
type: docs
weight: 10
url: /tr/java/xmp-metadata-manipulation/add-array-items/
---
## giriiş
XMP meta verilerine dizi öğeleri eklemek için Aspose.Page for Java'yı kullanmayla ilgili adım adım kılavuzumuza hoş geldiniz. Aspose.Page, EPS dosyaları da dahil olmak üzere çeşitli belge formatlarını değiştirmenize ve bunlarla çalışmanıza olanak tanıyan güçlü bir Java kütüphanesidir. Bu öğreticide, Java kullanarak XMP meta verilerine dizi öğeleri ekleme gibi özel bir göreve odaklanacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Page for Java kütüphanesi kuruldu.
- Java programlamanın temel anlayışı.
- Mevcut XMP meta verilerini veya PS meta veri yorumlarını içeren geçerli bir EPS dosyası.
## Paketleri İçe Aktar
Başlamak için Aspose.Page ile çalışmak için gerekli paketleri içe aktarmanız gerekiyor. Java dosyanızın başına aşağıdaki satırları ekleyin:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
Bu adımda mevcut XMP meta verilerini EPS dosyasından alıyoruz. EPS dosyası halihazırda XMP meta verileri içermiyorsa Aspose.Page yeni bir tane oluşturur ve onu PS meta veri yorumlarından gelen değerlerle doldurur.
## Adım 2: "dc:title" Dizi Öğesini ekleyin
```java
// Bir "dc:title" dizi öğesi daha ekleyin
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Şimdi XMP meta verilerindeki "dc:title" özelliğine yeni bir dizi öğesi ekliyoruz. "NewTitle"ı istediğiniz başlıkla değiştirin.
## 3. Adım: "dc:creator" Dizi Öğesini ekleyin
```java
// Bir "dc:creator" dizi öğesi daha ekleyin
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Benzer şekilde XMP meta verilerindeki "dc:creator" özelliğine yeni bir dizi öğesi ekliyoruz. "NewCreator"ı istenen yaratıcı bilgileriyle değiştirin.
## Adım 4: Çıktı EPS Dosya Akışını Başlatın
```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Güncellenmiş XMP meta verileriyle değiştirilen belgenin kaydedileceği çıktı EPS dosya akışını hazırlayın.
## Adım 5: Belgeyi Değiştirilmiş XMP Meta Verileriyle Kaydetme
```java
//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Güncellenmiş XMP meta verilerini içeren belgeyi çıktı EPS dosyasına kaydedin.
## Çözüm
Tebrikler! Aspose.Page for Java kullanarak XMP meta verilerine dizi öğelerinin nasıl ekleneceğini başarıyla öğrendiniz. Bu güçlü kitaplık, EPS dosyalarını işleme sürecini basitleştirir ve belge işleme için kapsamlı işlevsellik sağlar.
## Sıkça Sorulan Sorular

### Aspose.Page for Java'yı diğer belge formatlarıyla kullanabilir miyim?
Evet, Aspose.Page EPS, PDF ve XPS dahil olmak üzere çeşitli belge formatlarını destekler.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page for Java'yı nasıl satın alabilirim?
 Ürünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### Aspose.Page for Java için geçici lisanslar mevcut mu?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
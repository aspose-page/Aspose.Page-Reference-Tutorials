---
date: 2025-12-18
description: Aspose.Page for Java kullanarak EPS dosyalarının XMP meta verilerine
  dizi öğeleri ekleyerek meta veri eklemeyi öğrenin. Adım adım rehberimizi izleyin.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Meta Verileri Nasıl Eklenir – XMP'de Dizi Öğeleri Ekleme (Java)
url: /tr/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP Meta Verilerine Dizi Öğeleri Eklemek – Java

## Meta Verileri Nasıl Eklenir
Aspose.Page for Java ile **meta verileri nasıl ekleyeceğinize** dair adım‑adım rehberimize hoş geldiniz. Bu öğreticide, EPS dosyalarına XMP meta verilerine dizi öğeleri eklemeyi—başlıklar veya yazarlar gibi belge bilgilerini zenginleştirmeniz gerektiğinde sıkça karşılaşılan bir gereksinimi—göreceksiniz. Sonunda, XMP’nin neden değerli olduğunu, programatik olarak nasıl manipüle edileceğini ve güncellenmiş EPS dosyasının nasıl kaydedileceğini anlayacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Page for Java  
- **Hedef dosya formatı nedir?** EPS (Encapsulated PostScript)  
- **Birden fazla başlık ekleyebilir miyim?** Evet, `xmp.addArrayItem("dc:title", ...)` ifadesini tekrar tekrar kullanın  
- **Üretim ortamı için lisans gerekiyor mu?** Evet, geçerli bir Aspose.Page lisansı zorunludur  
- **Kod Java 8+ ile uyumlu mu?** Kesinlikle, tüm modern Java sürümleriyle çalışır  

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulları karşıladığınızdan emin olun:
- Aspose.Page for Java kütüphanesi yüklü.
- Java programlamaya temel düzeyde hakimiyet.
- Mevcut XMP meta verileri veya PS meta veri yorumları içeren geçerli bir EPS dosyası.

## Paketleri İçe Aktarma
Aspose.Page ile çalışmak için gerekli paketleri içe aktarmanız gerekir. Java dosyanızın başına aşağıdaki satırları ekleyin:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Adım 1: XMP Meta Verilerini Alın
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Bu adımda, EPS dosyasından mevcut XMP meta verileri alınır. EPS dosyasında hâlihazırda XMP meta verisi yoksa, Aspose.Page yeni bir XMP oluşturur ve PS meta veri yorumlarından değerlerle doldurur.

## Adım 2: "dc:title" Dizi Öğesi Ekleyin
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Şimdi, XMP meta verilerindeki **dc:title** özelliğine yeni bir dizi öğesi ekliyoruz. `"NewTitle"` ifadesini istediğiniz başlıkla değiştirin.

## Adım 3: "dc:creator" Dizi Öğesi Ekleyin
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Benzer şekilde, XMP meta verilerindeki **dc:creator** özelliğine yeni bir dizi öğesi ekliyoruz. `"NewCreator"` ifadesini istediğiniz yaratıcı bilgisiyle değiştirin.

## Adım 4: Çıktı EPS Dosyası Akışını Başlatın
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Değiştirilmiş XMP meta verileriyle birlikte belgeyi kaydedeceğiniz çıktı EPS dosyası akışını hazırlayın.

## Adım 5: Değiştirilen XMP Meta Verileriyle Belgeyi Kaydedin
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Güncellenmiş XMP meta verileriyle belgeyi çıktı EPS dosyasına kaydedin.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak XMP meta verilerine dizi öğeleri ekleyerek **meta verileri nasıl ekleyeceğinizi** başarıyla öğrendiniz. Bu güçlü kütüphane, EPS dosyalarını manipüle etme sürecini basitleştirir ve belge işleme için kapsamlı işlevsellik sunar.

## Sık Sorulan Sorular

### Aspose.Page for Java’yı başka belge formatlarıyla kullanabilir miyim?
Evet, Aspose.Page EPS, PDF ve XPS dahil çeşitli belge formatlarını destekler.

### Aspose.Page for Java için ücretsiz deneme sürümü var mı?
Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page for Java dokümantasyonunu nereden bulabilirim?
Dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

### Aspose.Page for Java’yı nasıl satın alabilirim?
Ürünü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Aspose.Page for Java için geçici lisanslar mevcut mu?
Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

## Ek Sık Sorulan Sorular

**S: Aynı özelliğe birden fazla dizi öğesi ekleyebilir miyim?**  
C: Kesinlikle. Aynı özellik için `xmp.addArrayItem` ifadesini birden çok kez çağırarak değer listesi oluşturabilirsiniz.

**S: Bu yaklaşım Dublin Core dışındaki mevcut XMP şemalarıyla da çalışır mı?**  
C: Evet, ad alanı doğru şekilde referans edildiği sürece herhangi bir XMP özelliğine dizi öğeleri ekleyebilirsiniz.

**S: Meta verilerin doğru eklendiğini nasıl doğrularım?**  
C: Sonuç EPS dosyasını XMP destekleyen bir görüntüleyicide (ör. Adobe Bridge) açın veya `XmpMetadata` metodlarını kullanarak programatik olarak meta verileri çıkarın.

---

**Son Güncelleme:** 2025-12-18  
**Test Edilen Sürüm:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
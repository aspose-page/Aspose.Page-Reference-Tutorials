---
date: 2025-12-20
description: Aspose.Page for Java kullanarak EPS dosyalarında XMP meta verileri oluşturmayı
  öğrenin. Basit XMP özelliklerini programlı olarak eklemek için adım adım rehber.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Java ile XMP meta verisi EPS nasıl oluşturulur
url: /tr/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP'ye Basit Özellikler Ekleme

## Giriş
Modern belge iş akışlarında, **XMP metadata EPS** dosyalarını programlı olarak oluşturabilmek, grafiklerinizin nasıl tanımlandığı, aranıp arşivlendiği üzerinde tam kontrol sağlar. Aspose.Page for Java ile EPS belgeleri içinde XMP paketlerini okuyabilir, değiştirebilir ve yazabilirsiniz; Java ekosisteminden çıkmanıza gerek yok. Bu öğreticide, bir EPS dosyasına basit XMP özellikleri eklemek için gereken adımları adım adım göstereceğiz, böylece grafiklerinizi özel metadata ile hızlı ve güvenilir bir şekilde zenginleştirebilirsiniz.

## Hızlı Yanıtlar
- **“create xmp metadata eps” ne anlama geliyor?** EPS dosyasına bir XMP paketi (XML‑tabanlı metadata) eklemek.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (Aspose sitesinden indirilebilir).  
- **Test için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gerekir.  
- **Kaç satır kod?** Birkaç import ifadesiyle birlikte 30 satırdan az Java kodu.  
- **Başka veri tipleri ekleyebilir miyim?** Evet – tarih, tam sayı, çift, string ve hatta diziler desteklenir.

## XMP metadata EPS oluşturma nedir?
XMP (Extensible Metadata Platform), dosyalar içinde zengin metadata gömmek için bir standarttır. **XMP metadata EPS** oluşturduğunuzda, bir XML paketini EPS (Encapsulated PostScript) belgesine gömersiniz; bu sayede sonraki uygulamalar yazar, oluşturma tarihi, özel etiketler ve daha fazlasını okuyabilir.

## Neden EPS dosyalarına XMP metadata eklenir?
- **Aranabilirlik:** DAM sistemleri tarafından otomatik indekslemeyi sağlar.  
- **Uyumluluk:** Yasal veya lisans bilgilerini doğrudan dosyada saklar.  
- **Otomasyon:** Sonraki işlem hatlarının gömülü verilere dayanarak karar vermesini sağlar.  
- **Taşınabilirlik:** Metadata EPS ile birlikte taşınır, platformlar arasında tutarlılığı sağlar.

## Önkoşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- Java programlama temelleri.  
- Aspose.Page for Java kütüphanesi yüklü. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Metadata içeren örnek bir EPS dosyası. Yoksa sağlanan **`xmp3.eps`** dosyasını kullanabilirsiniz.

## Paketleri İçe Aktarma
İhtiyacınız olan sınıfları ilk olarak içe aktarın. İçe aktarmalar, orijinal örnekle tamamen aynı kalır:

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

## Adım 1: EPS belgesini yükleyin ve XMP metadata alın
EPS dosyasını açar, bir `PsDocument` örneği oluşturur ve XMP paketini (varsa) alır ya da oluşturur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 2: Tarih özelliği ekleyin
Bir tarih eklemek, bir `Date` nesnesi oluşturup XMP haritasına koymak kadar basittir.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Adım 3: Tam sayı özelliği ekleyin
Sayısal tanımlayıcılar veya sürüm numaraları gibi değerleri tam sayı olarak depolayabilirsiniz.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Adım 4: Double özelliği ekleyin
Ölçümler veya puanlamalar için kayan nokta sayıları kullanışlıdır.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Adım 5: String özelliği ekleyin
Özel metin etiketleri (ör. proje kodları) string olarak saklanır.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Adım 6: Güncellenmiş EPS dosyasını kaydedin
Tüm özellikler eklendikten sonra belgeyi diske geri yazın.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Adım 7: Kaynakları temizleyin
Dosya‑tutama sızıntılarını önlemek için giriş akışını her zaman kapatın.

```java
// Close input EPS stream
psStream.close();
```

## Yaygın Sorunlar ve Çözümler
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null XMP metadata** | EPS dosyasında XMP paketi yoktu ve kütüphane PS yorumlarını çıkaramadı. | Kaynak EPS'in en az bir PS yorumu (ör. `%%Creator`) içerdiğinden emin olun. Kütüphane otomatik olarak minimal bir XMP paketi oluşturacaktır. |
| **Time zone mismatch** | Tarihler başka bir uygulamada açıldığında kaymış görünüyor. | `Date` nesnesi oluşturulmadan önce `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` ayarlayın, Adım 2'de gösterildiği gibi. |
| **License exception** | Çalışma zamanı `LicenseException` hatası fırlatıyor. | API'yi kullanmadan önce geçerli bir Aspose.Page lisansı uygulayın veya değerlendirme için deneme modunda çalıştırın. |

## Sonuç
Bu adımları izleyerek artık Aspose.Page for Java kullanarak **XMP metadata EPS** dosyaları oluşturabileceğinizi biliyorsunuz. Tarih, tam sayı, double ve string gibi basit özellikleri eklemek oldukça kolaydır; ortaya çıkan EPS dosyaları, herhangi bir sonraki iş akışına fayda sağlayan zengin ve aranabilir metadata taşır.

## Sık Sorulan Sorular
### Aspose.Page for Java'yı diğer programlama dilleriyle kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak .NET gibi diğer diller için de sürümler mevcuttur.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, [buradan](https://releases.aspose.com/) ücretsiz deneme alarak Aspose.Page'in özelliklerini keşfedebilirsiniz.

### Aspose.Page for Java için ayrıntılı belgeleri nerede bulabilirim?
Dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

### Aspose.Page for Java için geçici lisans nasıl alabilirim?
Geçici bir lisans [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.

### Aspose.Page for Java'yi nereden satın alabilirim?
Ürünü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Son Güncelleme:** 2025-12-20  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
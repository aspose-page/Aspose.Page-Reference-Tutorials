---
date: 2026-05-20
description: Aspose.Page for Java ile EPS dosyalarına XMP meta verisi eklemeyi öğrenin.
  Programlı olarak basit XMP özelliklerini gömmek için adım adım kılavuz.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Java ile XMP'de Basit Özellikler Ekleyin
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java Kullanarak EPS Dosyalarına XMP Meta Verisi Ekleyin
url: /tr/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS Dosyalarına Java Kullanarak XMP Metaverisi Ekleme

## Giriş
Modern grafik iş akışlarında, EPS dosyalarına programlı olarak **XMP metaverisi ekleyebilmek**, illüstrasyonlarınızın nasıl tanımlandığı, aranıp arşivlendiği üzerinde tam kontrol sağlar. Aspose.Page for Java ile EPS belgeleri içinde XMP paketlerini okuyabilir, değiştirebilir ve yazabilirsiniz; Java ekosisteminden çıkmanıza gerek kalmaz. Bu öğreticide, bir EPS dosyasına basit XMP özellikleri eklemek için gereken adımları adım adım göstereceğiz, böylece grafiklerinizi özel metaveriyle hızlı ve güvenilir bir şekilde zenginleştirebilirsiniz.

## Hızlı Yanıtlar
- **“add XMP metadata to EPS” ne anlama geliyor?** EPS dosyasına bir XMP paketi (XML tabanlı metaveri) gömmek.  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (Aspose sitesinden indirilebilir).  
- **Test için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Kaç satır kod?** 30'dan az Java satırı ve birkaç import ifadesi.  
- **Başka veri tipleri ekleyebilir miyim?** Evet – tarih, tamsayı, çift, dize ve hatta diziler desteklenir.

## Java Kullanarak EPS Dosyalarına XMP Metaverisi Nasıl Eklenir?
EPS dosyasını `new PsDocument("input.eps")` ile yükleyin, XMP paketini alın veya oluşturun, istenen özellikleri ekleyin ve ardından belgeyi diske kaydedin – tümü on satırdan az Java kodu ile. Bu yaklaşım, EPS kaynağını manuel olarak düzenlemeden aranabilir, standartlara uygun metaveri gömmenizi sağlar.

## EPS'de XMP Metaverisi Nedir?
EPS'deki XMP metaverisi, EPS dosyasının içinde yer alan ve yazar, oluşturma tarihi ve özel etiketler gibi bilgileri saklayan bir XML paketidir. Bu paketin gömülmesi, sonraki araçların veriyi ayrı yan dosyalara ihtiyaç duymadan okumasını ve işlem yapmasını sağlar.

## EPS Dosyalarına Neden XMP Metaverisi Eklenir?
XMP metaverisi gömmek, EPS varlıklarını anında aranabilir kılar, lisans bilgilerini dosyanın içinde saklayarak uyumluluğu sağlar, otomatik iş akışlarının gömülü etiketlere göre karar vermesini mümkün kılar ve metaverinin grafikle birlikte tüm platformlarda taşınmasını garantiler. Aspose.Page, tüm belgeyi belleğe yüklemeden 500 MB'a kadar dosyaları işleyebilir ve büyük ölçekli iş yükleri için hızlı performans sunar.

## Ön Koşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- Java programlama temelleri bilgisi.  
- Aspose.Page for Java kütüphanesi yüklü. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Metaveri içeren bir örnek EPS dosyası. Eğer yoksa, sağlanan **`xmp3.eps`** dosyasını kullanabilirsiniz.

## Paketleri İçe Aktar
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. Import ifadeleri, orijinal örnekteki gibi tam olarak aynı kalır:

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

## Adım 1: EPS belgesini yükleyin ve XMP metaverisini alın
`PsDocument` sınıfı bir EPS dosyasını temsil eder ve içeriğine ve metaverisine erişim sağlayan yöntemler sunar.  
`XmpMetadata` nesnesi, belgeyle ilişkili XMP paketini tutar.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 2: Date özelliği ekleyin
`Date` sınıfı, milisaniye hassasiyetiyle belirli bir zaman anını temsil eder.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Adım 3: Integer özelliği ekleyin
`Integer` sınıfı, ilkel `int` değerini bir nesne olarak sarar.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Adım 4: Double özelliği ekleyin
`Double` sınıfı, ilkel `double` değerini bir nesne olarak sarar.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Adım 5: String özelliği ekleyin
`String` sınıfı, karakter dizisini temsil eder.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Adım 6: Güncellenmiş EPS dosyasını kaydedin
`save` yöntemi, değiştirilmiş belgeyi diske yazar ve EPS yapısını korur.

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
Dosya tanıtıcı sızıntılarını önlemek ve tüm tamponların boşaltıldığından emin olmak için her zaman akışları kapatın.

```java
// Close input EPS stream
psStream.close();
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Null XMP metadata** | EPS dosyasında XMP paketi yoktu ve kütüphane PS yorumlarını çıkaramıyordu. | Kaynak EPS dosyasının en az bir PS yorumu (ör. `%%Creator`) içerdiğinden emin olun. Kütüphane otomatik olarak minimal bir XMP paketi oluşturur. |
| **Time zone mismatch** | Tarihler başka bir uygulamada açıldığında kaymış görünüyor. | `Date` nesnesi oluşturulmadan önce `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` ayarlayın, adım 2'de gösterildiği gibi. |
| **License exception** | Çalışma zamanı `LicenseException` hatası fırlatıyor. | API'yi kullanmadan önce geçerli bir Aspose.Page lisansı uygulayın veya değerlendirme için deneme modunda çalıştırın. |

## Sıkça Sorulan Sorular
**Q: Aspose.Page for Java'ı diğer programlama dilleriyle kullanabilir miyim?**  
A: Aspose.Page öncelikle Java'yı destekler, ancak .NET, C++ ve Python için eşdeğer kütüphaneler mevcuttur.

**Q: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
A: Evet, Aspose.Page'in özelliklerini ücretsiz bir deneme **[buradan](https://releases.aspose.com/)** alarak keşfedebilirsiniz.

**Q: Aspose.Page for Java için ayrıntılı belgeleri nerede bulabilirim?**  
A: Dokümantasyon **[burada](https://reference.aspose.com/page/java/)** mevcuttur.

**Q: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
A: Geçici bir lisans **[buradan](https://purchase.aspose.com/temporary-license/)** edinilebilir.

**Q: Aspose.Page for Java'ı nereden satın alabilirim?**  
A: Ürünü **[buradan](https://purchase.aspose.com/buy)** satın alabilirsiniz.

---

**Son Güncelleme:** 2026-05-20  
**Test Edilen:** Aspose.Page for Java 24.12 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Java Kullanarak XMP Metaverisini Okuma – Aspose.Page Kılavuzu](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp öğreticisi – Java Kullanarak XMP'ye Namespace Ekleme](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java Kullanarak XMP Metaverisine Dizi Öğeleri Ekleme](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
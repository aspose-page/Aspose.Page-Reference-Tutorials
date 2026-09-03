---
date: 2026-05-25
description: Aspose.Page ile Java kullanarak EPS belgelerinde xmp'yi nasıl değiştireceğinizi
  öğrenin. Metaverileri hızlı ve güvenilir bir şekilde güncelleyin.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Java kullanarak XMP'de Değerleri Değiştir
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page ile xmp nasıl değiştirilir – Java kullanarak XMP'de Değerleri Değiştir
url: /tr/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile XMP Değerlerini Değiştirme

## Giriş
Eğer Java ile bir EPS dosyası içinde **how to modify xmp** arıyorsanız, doğru yere geldiniz. Bu eğitim, mevcut XMP bloğunu okuma, yaratıcı, başlık ve değiştirme tarihi gibi alanları güncelleme ve son olarak değişiklikleri EPS belgesine geri kaydetme adımlarını size adım adım gösterir. Sonunda, dosyalarınızın marka, uyumluluk veya arama motoru indekslemesi için doğru meta verileri taşımasını sağlayan, herhangi bir otomatik iş akışına uyabilecek yeniden kullanılabilir bir kod parçasına sahip olacaksınız.

## Hızlı Yanıtlar
- **What does “aspose.page modify xmp” do?** Aspose.Page Java API'si aracılığıyla EPS dosyalarında XMP meta verilerini okumanıza ve yazmanıza olanak tanır.  
- **Which library version is required?** Herhangi bir son Aspose.Page for Java sürümü (API sürümler arasında kararlıdır).  
- **Do I need a license to run the sample?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Can I change multiple XMP fields at once?** Evet—belgeyi kaydetmeden önce her alan için `put` çağırın.  
- **Is timezone handling needed?** Varsayılan saat dilimini (ör. UTC) ayarlamak tutarlı tarih değerleri sağlar.

## XMP Nedir ve Neden Değiştirilir?
XMP (Extensible Metadata Platform), EPS, PDF ve görüntüler gibi dosyalar içine doğrudan zengin meta veri yerleştirmek için standartlaştırılmış, XML‑tabanlı bir formattır. XMP'yi güncellemek, belgelerin nasıl indekslendiğini, görüntülendiğini ve arandığını kontrol etmenizi sağlar—marka tutarlılığı, yasal uyumluluk ve otomatik içerik hatları için kritik öneme sahiptir.

## Neden Aspose.Page for Java Kullanılır?
Aspose.Page, **tam özellikli, saf‑Java API** sağlayarak dış araçlara veya yerel kütüphanelere ihtiyaç duymadan çalışmanızı sağlar. **50+ giriş ve çıkış formatını** destekler ve EPS dosyalarını **500 MB**'a kadar belgenin tamamını belleğe yüklemeden işleyebilir, böylece herhangi bir Java çalıştıran işletim sisteminde hızlı ve düşük bellek tüketimli meta veri manipülasyonu sunar.

## Önkoşullar
Bu eğitime başlamadan önce aşağıdaki önkoşulların sağlandığından emin olun:
1. **Java Development Environment** – JDK (8 veya üzeri) ve tercih ettiğiniz bir IDE veya derleme aracı.  
2. **Aspose.Page for Java Library** – Aspose.Page for Java kütüphanesini indirin ve kurun. Gerekli paketi [burada](https://releases.aspose.com/page/java/) bulabilirsiniz.

## Paketleri İçe Aktarma
Java projenize gerekli paketleri içe aktararak başlayın. Bu paketler, EPS belgeleriyle etkileşim kurmak ve onları manipüle etmek için hayati öneme sahiptir.

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

## Java Kullanarak EPS'te XMP Nasıl Değiştirilir?
`Document` Aspose.Page sınıfı, bir EPS dosyasını temsil eder ve içeriğine ve meta verilerine erişim sağlar. `XmpMetadata` belgeye eklenmiş XMP bloğunu temsil eder ve meta veri alanlarını okuma ve yazma imkanı sunar. `put` XmpMetadata nesnesine bir meta veri girdisi ekler veya günceller. `save` değiştirilen belgeyi, güncellenmiş XMP meta verisi dahil, bir dosyaya yazar.

`new Document("input.eps")` ile EPS dosyasını yükleyin, `XmpMetadata` nesnesini alın, istenen anahtarları `put` ile güncelleyin ve sonunda `save` ile değişiklikleri yeni bir dosyaya yazın. Bu kısa akış, eksik XMP bloklarını otomatik olarak ele alır, gerektiğinde PostScript yorumlarından bir blok oluşturur ve saat dilimi‑tutarlı tarihleri garanti eder.

## Adım 1: XMP Metaverisini Al
`XmpMetadata` sınıfı, bir EPS belgesine eklenmiş XMP bloğunu temsil eder. `document.getXmpMetadata()` çağrıldığında API, mevcut bloğu döndürür veya `%%Creator`, `%%CreateDate` ve `%%Title` gibi PS yorumlarından yeni bir blok oluşturur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 2: "ModifyDate" Değerini Değiştir
Yeni değişiklik zaman damgasını yansıtmak için `"ModifyDate"` girdisini güncelleyin. `java.util.Date` ile birlikte `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` kullanarak saklanan değerin saat diliminden bağımsız olmasını sağlayın.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Adım 3: "Creator" Değerini Değiştir
`"Creator"` anahtarı, EPS dosyasını oluşturan uygulama veya kişinin adını saklar. Mevcut değeri özel bir tanımlayıcıyla değiştirmek için `xmp.put("dc:creator", "Your Company Name")` çağırın.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Adım 4: "Title" Değerini Değiştir
`"Title"` alanı birçok varlık‑yönetim sistemi tarafından görüntülenir. `xmp.put("dc:title", "New Document Title")` ile ayarlamak, belgenin kataloglarda ve arama sonuçlarında doğru şekilde görünmesini sağlar.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Adım 5: Değiştirilmiş XMP Metaverisiyle Belgeyi Kaydet
Tüm değişikliklerden sonra `document.save("output.eps")` çağırın. Kütüphane, güncellenmiş XMP bloğunu EPS akışına geri yazar ve orijinal grafik içeriğini değiştirmeden korur.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Yaygın Sorunlar ve Çözümler
- **Missing XMP block** – API, PS yorumlarından otomatik olarak bir blok oluşturur, ancak gerektiğinde `XmpMetadata` nesnesini manuel olarak da örnekleyebilirsiniz.  
- **Timezone mismatches** – Beklenmedik sapmaları önlemek için `Date` nesnesini oluşturmadan önce her zaman `TimeZone.setDefault` ayarlayın.  
- **File access errors** – Girdi ve çıktı yollarının doğru olduğundan ve uygulamanızın okuma/yazma izinlerine sahip olduğundan emin olun.

## Sık Sorulan Sorular

**S: XMP değerlerini değiştirirken saat dilimi konularını nasıl yönetebilirim?**  
C: Saat dilimi ayarlarının tutarlılığını sağlamak için `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` kullanın.

**S: Tek bir işlemde birden fazla XMP değeri değiştirebilir miyim?**  
C: Evet, istenen her değer için `put` metodunu kullanarak birden fazla XMP değerini aynı anda değiştirebilirsiniz.

**S: Aspose.Page for Java için ek belgeleri nerede bulabilirim?**  
C: Kapsamlı belgeleri [burada](https://reference.aspose.com/page/java/) keşfedebilirsiniz.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz denemeye [burada](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [burada](https://purchase.aspose.com/temporary-license/) elde edebilirsiniz.

**S: XMP'yi değiştirmek EPS'in görsel içeriğini etkiler mi?**  
C: Hayır. XMP değişiklikleri yalnızca meta veriyi etkiler ve EPS dosyasının grafik öğelerini değiştirmez.

**S: Değişiklikleri doğrulamak için güncellenen değerleri programlı olarak okuyabilir miyim?**  
C: Kesinlikle—belgeyi kaydettikten ve kapatmadan önce `xmp.get("dc:creator")` (veya ilgili anahtar) çağırarak güncellenen değeri alabilirsiniz.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak EPS belgelerinde **how to modify xmp** değerlerini nasıl değiştireceğinizi öğrendiniz. Doğru yaratıcı, başlık ve değiştirme‑tarihi meta verilerini ekleyerek varlıklarınızın aranabilir, uyumlu ve marka standartlarınıza uygun olmasını sağlarsınız. Bu deseni toplu‑işlem hatları, CI/CD adımları veya herhangi bir otomatik belge‑oluşturma iş akışına entegre etmekten çekinmeyin.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## İlgili Eğitimler

- [Aspose Page Java Eğitimi – EPS Dosyalarına XMP Metaverisi Ekle](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Java ile XMP Metaverisini Okuma – Aspose.Page Kılavuzu](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - XMP'de Dizi Öğelerini Java ile Değiştirme](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
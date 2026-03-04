---
date: 2025-12-21
description: Java kullanarak EPS belgelerinde XMP'yi Aspose.Page ile nasıl değiştireceğinizi
  öğrenin. Aspose.Page for Java ile meta verileri hızlıca geliştirin.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page xmp'yi değiştir – Java kullanarak XMP'deki değerleri değiştir
url: /tr/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP'de Değerleri Java Kullanarak Değiştirme

## Giriş
Eğer bir EPS dosyası içinde **aspose.page modify xmp** verilerini değiştirmeniz gerekiyorsa, doğru yerdesiniz. Bu öğreticide, Aspose.Page Java kütüphanesini kullanarak XMP (Extensible Metadata Platform) değerlerini okuma, güncelleme ve kaydetme adımlarını ayrıntılı olarak göstereceğiz. Sonunda, belge meta verilerini—örneğin oluşturucu başlık ve değiştirme tarihi—projenizin gereksinimlerine göre özelleştirebileceksiniz.

## Hızlı Yanıtlar
- **aspose.page modify xmp ne yapar?** Aspose.Page Java API'si aracılığıyla EPS dosyalarında XMP meta verilerini okumanıza ve yazmanıza olanak tanır.  
- **Hangi kütüphane sürümü gereklidir?** Java için herhangi bir yeni Aspose.Page sürümü (API sürümler arasında kararlıdır).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Birden fazla XMP alanını aynı anda değiştirebilir miyim?** Evet—belgeyi kaydetmeden önce her alan için `put` çağırın.  
- **Zaman dilimi ayarlaması gerekli mi?** Varsayılan zaman dilimini (ör. UTC) ayarlamak tutarlı tarih değerleri sağlar.

## XMP Nedir ve Neden Değiştirilir?
XMP (Extensible Metadata Platform), EPS, PDF ve görüntüler gibi dosyalar içine zengin meta verileri doğrudan gömmenin standart bir yoludur. XMP'yi güncellemek, belgelerin nasıl indekslendiğini, görüntülendiğini ve arandığını kontrol etmenizi sağlar—markalaşma, uyumluluk ve iş akışı otomasyonu için kritik öneme sahiptir.

## Neden Aspose.Page for Java Kullanmalısınız?
- **Tam özellikli API** – Harici araçlara gerek yok; her şey işlem içinde yönetilir.  
- **Çapraz platform** – Java destekleyen herhangi bir işletim sisteminde çalışır.  
- **Yerel bağımlılık yok** – Saf Java uygulaması dağıtımı basitleştirir.  
- **Güçlü destek** – Mevcut XMP bloklarını yönetir ve eksik olduğunda PS yorumlarından yeni oluşturur.

## Ön Koşullar
Bu öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
1. **Java Geliştirme Ortamı** – JDK (8 veya üzeri) ve tercih ettiğiniz bir IDE veya derleme aracı.  
2. **Aspose.Page for Java Kütüphanesi** – Aspose.Page for Java kütüphanesini indirin ve kurun. Gerekli paketi [burada](https://releases.aspose.com/page/java/) bulabilirsiniz.

## Paketleri İçe Aktarma
Gerekli paketleri Java projenize içe aktararak başlayın. Bu paketler, EPS belgeleriyle etkileşim kurmak ve onları işlemek için hayati öneme sahiptir.

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

## Adım 1: XMP Meta Verilerini Alın
EPS belgesinden XMP meta verilerini alın. EPS dosyası XMP meta verisi içermiyorsa, %%Creator, %%CreateDate ve %%Title gibi PS meta veri yorumlarından değerler alarak yeni bir XMP bloğu oluşturulur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 2: "ModifyDate" Değerini Değiştirin
XMP meta verisindeki "ModifyDate" değerini istenen tarihi yansıtacak şekilde değiştirin.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Adım 3: "Creator" Değerini Değiştirin
XMP meta verisindeki "Creator" değerini belgenin oluşturucusunu belirtecek şekilde güncelleyin.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Adım 4: "Title" Değerini Değiştirin
XMP meta verisindeki "Title" değerini belge için uygun bir başlık ayarlayacak şekilde değiştirin.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Adım 5: Değiştirilmiş XMP Meta Verileriyle Belgeyi Kaydedin
Güncellenmiş XMP meta verileriyle belgeyi yeni bir EPS dosyasına kaydedin.

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
- **XMP bloğu eksik** – API, PS yorumlarından otomatik olarak bir blok oluşturur, ancak gerekirse `XmpMetadata`'yi manuel olarak da örnekleyebilirsiniz.  
- **Zaman dilimi uyumsuzlukları** – Beklenmeyen kaymaların önüne geçmek için `Date` nesnesi oluşturulmadan önce her zaman `TimeZone.setDefault` ayarlayın.  
- **Dosya erişim hataları** – Giriş ve çıkış yollarının doğru olduğundan ve uygulamanızın okuma/yazma izinlerine sahip olduğundan emin olun.

## Sıkça Sorulan Sorular

**S: XMP değerlerini değiştirirken zaman dilimi hususlarını nasıl ele alabilirim?**  
C: Zaman dilimi ayarlarında tutarlılık sağlamak için `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` kullanın.

**S: Tek bir işlemde birden fazla XMP değerini değiştirebilir miyim?**  
C: Evet—her istenen değer için `put` metodunu kullanarak birden fazla XMP değerini aynı anda değiştirebilirsiniz.

**S: Aspose.Page for Java için ek belgeleri nerede bulabilirim?**  
C: Kapsamlı belgeleri [burada](https://reference.aspose.com/page/java/) inceleyin.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edin.

**S: XMP'yi değiştirmek EPS'in görsel içeriğini etkiler mi?**  
C: Hayır. XMP değişiklikleri yalnızca meta veriyi etkiler ve EPS dosyasının grafik öğelerini değiştirmez.

**S: Değişikliği doğrulamak için güncellenen değerleri programlı olarak geri okuyabilir miyim?**  
C: Kesinlikle—belgeyi kaydettikten ve kapatmadan önce `xmp.get("dc:creator")` (veya ilgili anahtar) çağırarak değerleri kontrol edebilirsiniz.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak EPS belgelerinde **aspose.page modify xmp** değerlerini başarıyla değiştirdiniz. Bu öğretici, meta verileri değiştirmenize olanak tanıyan bilgiyle donatmıştır; böylece belgeleriniz belirli gereksinimlerinize sorunsuz bir şekilde uyum sağlar.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen:** Aspose.Page for Java (latest release)  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

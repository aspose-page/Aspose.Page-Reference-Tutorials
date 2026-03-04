---
date: 2025-12-21
description: aspose page xmp tutorial – Aspose.Page for Java ile EPS dosyalarındaki
  XMP meta verilerini net, adım adım bir rehberde nasıl değiştireceğinizi öğrenin.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: aspose sayfa xmp öğreticisi – Java kullanarak XMP'de Adlandırılmış Değeri Değiştir
url: /tr/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp öğreticisi – XMP'de Adlandırılmış Değeri Java Kullanarak Değiştirme

Modern belge iş akışlarında, **Aspose.Page for Java**, EPS dosyaları içinde XMP meta verilerini okuma, düzenleme ve yazmayı kolaylaştırır. Bu **aspose page xmp tutorial**, XMP paketindeki adlandırılmış bir değeri değiştirmenizi adım adım gösterir, böylece belge meta verilerinizi doğru ve aranabilir tutabilirsiniz. Sayfa boyutlarını, yazar bilgilerini veya özel etiketleri güncelliyor olun, aşağıdaki adımlar Java'da bunu tam olarak nasıl yapacağınızı gösterir.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.Page for Java kullanarak bir EPS dosyasında adlandırılmış bir XMP değerini değiştirme.  
- **Hangi kütüphane sürümü gerekiyor?** Son zamanlardaki herhangi bir Aspose.Page for Java sürümü (API birkaç yıldır kararlıdır).  
- **Bir lisansa ihtiyacım var mı?** Üretim için geçici veya tam lisans gereklidir; ücretsiz deneme testi için çalışır.  
- **Uygulama ne kadar sürer?** Java I/O'ya aşina bir geliştirici için yaklaşık 10‑15 dakika.  
- **Bunu diğer dosya formatlarıyla kullanabilir miyim?** XMP API'si PDF, SVG ve Aspose.Page tarafından desteklenen diğer formatlar için de mevcuttur.

## XMP meta verisi nedir?
XMP (Extensible Metadata Platform), yaratıcı, başlık ve özel özellikler gibi zengin meta verileri doğrudan dosyaların içine yerleştirmek için standart bir formattır. EPS belgelerinde XMP, geleneksel PostScript yorumlarının yanında bulunur ve uygulamaların görsel içeriği değiştirmeden meta verileri okumasına ve değiştirmesine olanak tanır.

## Neden XMP'yi düzenlemek için Aspose.Page for Java kullanmalısınız?
- **Tam kontrol** – Ham XML'i ayrıştırmadan, özel yapılar dahil herhangi bir XMP özelliğine erişim.  
- **Çapraz‑format tutarlılığı** – Aynı API EPS, PDF ve SVG için çalışır, kod bakımını basitleştirir.  
- **Harici bağımlılık yok** – Saf Java kütüphanesi, yerel kod veya ek ayrıştırıcılar gerekmez.  
- **Sağlam hata yönetimi** – Yerleşik doğrulama, oluşturulan EPS'nin standartlara uygun kalmasını sağlar.

## Giriş
Aspose.Page for Java, EPS dosyalarının manipülasyonu ve işlenmesini kolaylaştıran sağlam bir Java kütüphanesidir. Bu dosyalar içinde XMP meta verilerini ele alırken, Aspose.Page geliştiricilere kapsamlı bir özellik seti sunar. Bu öğreticide, XMP'de adlandırılmış bir değeri değiştirmeye odaklanacağız ve belge işleme yeteneklerini geliştirmek isteyen geliştiriciler için net ve öz bir rehber sunacağız.

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:
1. **Java Geliştirme Ortamı** – Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.  
2. **Aspose.Page for Java Kütüphanesi** – Aspose.Page for Java kütüphanesini projenize indirin ve entegre edin. Kütüphaneyi ve ayrıntılı belgeleri [burada](https://reference.aspose.com/page/java/) bulabilirsiniz.  
3. **Örnek EPS Dosyası** – Deneme için bir örnek EPS dosyanız olsun. Eğer yoksa, sağlanan **"xmp4.eps"** adlı örnek dosyayı kullanabilirsiniz.

## Paketleri İçe Aktarma
İşleme başlamak için Java kodunuzda gerekli paketleri içe aktarın. Bu paketler Aspose.Page for Java ile etkileşim için gereklidir. Java dosyanızın başına aşağıdaki satırları ekleyin:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Şimdi, Aspose.Page for Java kullanarak XMP'de adlandırılmış bir değeri değiştirme sürecini birden fazla adıma ayıralım:

## Adım 1: Giriş EPS Dosya Akışını Başlatma
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Adım 2: PsDocument'i Başlatma
```java
PsDocument document = new PsDocument(psStream);
```

## Adım 3: XMP Meta Verisini Alın
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 4: XMP'de Yeni Değeri Ayarlama
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Adım 5: Çıktı EPS Dosya Akışını Başlatma
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Adım 6: Değiştirilmiş XMP Meta Verisiyle Belgeyi Kaydetme
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Adım 7: Giriş EPS Akışını Kapatma
```java
// Close input EPS stream
psStream.close();
```

Bu adım‑adım kılavuz, Aspose.Page for Java kullanarak XMP'de adlandırılmış bir değeri değiştirmek için sistematik bir yaklaşım sağlar. Bu adımları izleyerek, bu işlevi Java uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **FileNotFoundException** – `dataDir`'in doğru klasöre işaret ettiğini ve `xmp4.eps` dosyasının mevcut olduğunu doğrulayın.  
- **LicenseException** – Lisans hataları görürseniz, `PsDocument` oluşturulmadan önce geçerli bir Aspose.Page lisans dosyasının yüklendiğinden emin olun.  
- **Metadata Not Updated** – Kaydetmeden sonra, oluşturulan EPS'yi bir meta veri görüntüleyicide (ör. Adobe Bridge) açarak yeni değerin göründüğünü doğrulayın.

## Sonuç
Sonuç olarak, Aspose.Page for Java, EPS dosyalarında XMP meta verileriyle çalışmayı basitleştirir. Bu öğretici, XMP'de adlandırılmış bir değeri verimli bir şekilde değiştirmeniz için gerekli bilgiyi sağladı ve belge işleme yeteneklerinizi artırdı.

## Sıkça Sorulan Sorular
### Aspose.Page for Java'yi diğer programlama dilleriyle kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak Aspose çeşitli programlama dilleri için benzer kütüphaneler sunar.

### Aspose.Page for Java için ücretsiz bir deneme mevcut mu?
Evet, Aspose.Page for Java ücretsiz denemesini [burada](https://releases.aspose.com/) keşfedebilirsiniz.

### Aspose.Page for Java hakkında ek destek ve tartışmaları nerede bulabilirim?
Topluluk desteği ve tartışmalar için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### Aspose.Page for Java için geçici bir lisans nasıl alabilirim?
Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### Aspose.Page for Java'yi nereden satın alabilirim?
Aspose.Page for Java'yi satın almak için [satın alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

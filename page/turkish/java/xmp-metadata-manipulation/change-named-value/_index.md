---
date: 2026-05-15
description: Aspose.Page for Java ile EPS dosyalarında XMP meta verilerini nasıl düzenleyeceğinizi
  ve XMP değerlerini nasıl değiştireceğinizi öğrenin – adım adım açık bir rehber.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Java ile XMP'de Adlandırılmış Değeri Değiştir
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: xmp'yi nasıl düzenlenir – Java ile XMP'de Adlandırılmış Değeri Değiştir
url: /tr/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP'yi Düzenleme – Java Kullanarak XMP'de Adlandırılmış Değeri Değiştirme

Modern belge iş akışlarında, **Aspose.Page for Java** EPS dosyaları içinde XMP meta verilerini okuma, düzenleme ve yazmayı kolaylaştırır. **Bu öğretici, EPS belgelerinde XMP meta verilerini nasıl düzenleyeceğinizi** gösterir, böylece belge bilgilerinizin doğru, aranabilir ve sektör standartlarına uygun kalmasını sağlayabilirsiniz. Sayfa boyutlarını, yazar bilgilerini veya özel etiketleri güncelliyor olun, aşağıdaki adımlar Java'da süreci size adım adım anlatır.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.Page for Java ile bir EPS dosyasında adlandırılmış bir XMP değerini değiştirme.  
- **Hangi kütüphane sürümü gerekiyor?** Son birkaç yıldır kararlı olan herhangi bir yeni Aspose.Page for Java sürümü.  
- **Lisans gerekli mi?** Üretim için geçici veya tam lisans gerekir; test için ücretsiz deneme sürümü çalışır.  
- **Uygulama ne kadar sürer?** Java I/O'ya aşina bir geliştirici için yaklaşık 10‑15 dakika.  
- **Bunu diğer dosya formatlarıyla kullanabilir miyim?** XMP API, Aspose.Page tarafından desteklenen PDF, SVG ve diğer formatlarda da mevcuttur.

## XMP meta verisi nedir?
XMP (Extensible Metadata Platform), dosyalar içine doğrudan zengin meta veri (oluşturucu, başlık, özel özellikler vb.) gömmek için standartlaştırılmış XML tabanlı bir formattır. EPS belgelerinde XMP, geleneksel PostScript yorumlarının yanında bulunur ve uygulamaların görsel içeriği değiştirmeden meta verileri okumasına ve değiştirmesine olanak tanır.

## XMP'yi düzenlemek için Aspose.Page for Java neden kullanılmalı?
Aspose.Page, **150'den fazla XMP şema özelliği üzerinde tam kontrol** sağlar ve EPS, PDF ve SVG formatları arasında tutarlı çalışır. Belgeleri **500 MB**'a kadar, tüm belgeyi belleğe yüklemeden işler ve sonuçta EPS'nin standartlara uygun kalmasını garantileyen yerleşik doğrulama içerir. Harici XML ayrıştırıcıları veya yerel kütüphaneler gerekmez.

## Giriş
Aspose.Page for Java, EPS dosyalarının manipülasyonu ve işlenmesini kolaylaştıran sağlam bir kütüphanedir. Bu dosyalar içinde XMP meta verisini yönetirken, Aspose.Page geliştiricilere kapsamlı bir özellik seti sunar. Bu öğreticide, XMP'de adlandırılmış bir değeri değiştirmeye odaklanacağız ve belge işleme yeteneklerini geliştirmek isteyen geliştiriciler için net ve öz bir rehber sunacağız.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
1. **Java Development Environment** – JDK (8 ve üzeri) ve bir IDE veya yapı aracı (Maven/Gradle).  
2. **Aspose.Page for Java Library** – Aspose.Page for Java kütüphanesini projenize indirin ve entegre edin. Kütüphaneyi ve ayrıntılı dokümantasyonu [burada](https://reference.aspose.com/page/java/) bulabilirsiniz.  
3. **Sample EPS File** – Deney yapmak için bir örnek EPS dosyanız olsun. Eğer yoksa, sağlanan **"xmp4.eps."** adlı örnek dosyayı kullanın.

## Paketleri İçe Aktar
`import` ifadeleri, gerekli Aspose.Page sınıflarını kapsam içine alır.

`PsDocument` sınıfı, bellek içinde bir EPS belgesini temsil eden Aspose.Page'in temel nesnesidir.  
`XmpMetadata` sınıfı, EPS dosyasına gömülü XMP paketine erişim sağlar.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## XMP meta verisini nasıl düzenlersiniz?
EPS dosyasını yükleyin, XMP paketini alın, istenen özelliği değiştirin ve belgeyi kaydedin—hepsi birkaç basit satırda. Bu yaklaşım, standart Dublin Core alanı olsun ya da tanımladığınız özel bir ad alanı olsun, herhangi bir adlandırılmış XMP değeri için çalışır.

## Adım 1: Giriş EPS Dosya Akışını Başlat
`FileInputStream` kaynak EPS dosyasına yalnızca okuma izniyle bir akış açar, böylece Aspose.Page dosya sistemini kilitlemeden belgeyi alabilir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Adım 2: PsDocument'i Başlat
`PsDocument`, EPS içeriğini kapsayan ve meta veri, sayfalar ve kaynaklara erişim sağlayan birincil nesnedir.

```java
PsDocument document = new PsDocument(psStream);
```

## Adım 3: XMP Meta Verisini Al
`XmpMetadata`, EPS dosyasındaki XMP paketini temsil eder ve bireysel özellikleri okuma, değiştirme veya silme yöntemleri sunar.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 4: XMP'de Yeni Değeri Ayarla
`setProperty`, meta veri paketindeki belirli bir XMP özelliğinin değerini ayarlar.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Adım 5: Çıktı EPS Dosya Akışını Başlat
`FileOutputStream`, değiştirilmiş EPS dosyasını kaydetmek için yazılabilir bir akış oluşturur.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Adım 6: Değiştirilen XMP Meta Verisiyle Belgeyi Kaydet
`save`, güncellenmiş XMP dahil olmak üzere bellek içindeki PsDocument'i çıktı akışına yazar.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Adım 7: Giriş EPS Akışını Kapat
`close`, dosya tutamacını serbest bırakır ve giriş akışıyla ilişkili kaynakları temizler.

```java
// Close input EPS stream
psStream.close();
```

## Yaygın Sorunlar ve Çözümler
- **FileNotFoundException** – `dataDir`'in doğru klasöre işaret ettiğini ve `xmp4.eps` dosyasının mevcut olduğunu doğrulayın.  
- **LicenseException** – Lisans hataları alıyorsanız, `PsDocument` oluşturulmadan önce geçerli bir Aspose.Page lisans dosyasının yüklendiğinden emin olun.  
- **Metadata Not Updated** – Kaydettikten sonra, yeni değerin göründüğünden emin olmak için EPS'yi bir meta veri görüntüleyicide (ör. Adobe Bridge) açın.

## Sıkça Sorulan Sorular
**S: Aspose.Page for Java'yı diğer programlama dilleriyle kullanabilir miyim?**  
C: Aspose.Page öncelikle Java'yı destekler, ancak Aspose .NET, C++ ve Python için benzer XMP manipülasyon yetenekleri sunan eşdeğer kütüphaneler sağlar.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, Aspose.Page for Java ücretsiz denemesini [burada](https://releases.aspose.com/) keşfedebilirsiniz.

**S: Aspose.Page for Java hakkında ek destek ve tartışmalara nereden ulaşabilirim?**  
C: Topluluk desteği ve tartışmalar için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Page for Java'yı nereden satın alabilirim?**  
C: Aspose.Page for Java'yı satın almak için [satın alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin.

---

**Son Güncelleme:** 2026-05-15  
**Test Edilen:** Aspose.Page for Java (latest release)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java Kullanarak XMP Meta Verisini Okuma – Aspose.Page Rehberi](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java Öğreticisi – EPS Dosyalarına XMP Meta Verisi Ekleme](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Java Kullanarak XMP'de Değerleri Değiştirme](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
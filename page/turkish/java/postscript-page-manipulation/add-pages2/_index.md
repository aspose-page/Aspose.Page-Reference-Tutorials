---
date: 2025-12-11
description: Aspose.Page kullanarak Java PostScript belgelerinde özel sayfa boyutu
  ayarlamayı ve sayfa eklemeyi öğrenin. Sorunsuz belge manipülasyonu için adım adım
  rehberimizi izleyin.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java Öğreticisi – PostScript'te Sayfa Ekleme Sırasında Özel Sayfa
  Boyutu Ayarlama
url: /tr/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Öğreticisi – PostScript'te Sayfa Eklerken Özel Sayfa Boyutu Ayarlama

## Giriş
Modern Java uygulamalarında, **özel bir sayfa boyutu ayarlamak** genellikle gerekir—faturalar, biletler veya özel grafikler oluşturuyor olsanız da. Aspose.Page for Java bu görevi basitleştirir. Bu öğreticide, bir PostScript belgesine sayfa eklemeyi ve özel sayfa boyutları ayarlamayı adım adım öğrenecek ve her seferinde tam istediğiniz düzeni üretebileceksiniz.

## Hızlı Yanıtlar
- **Her sayfa için farklı sayfa boyutları ayarlayabilir miyim?** Evet, `document.openPage(width, height)` kullanarak özel boyutlarda sayfalar açabilirsiniz.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Değerlendirme dışı dağıtımlar için geçerli bir Aspose.Page lisansı gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Kütüphane Java 8 ve üzeri sürümlerle çalışır.  
- **API iş parçacığı güvenli mi?** Document örnekleri iş parçacığı güvenli değildir; her iş parçacığı için ayrı bir `PsDocument` oluşturun.  
- **Bir PostScript dosyası ne kadar büyük olabilir?** Aspose.Page çok megabaytlık dosyaları verimli bir şekilde işler; bellek kullanımı sayfa sayısına değil, içeriğe göre ölçeklenir.

## Ön Koşullar
İlerlemeye başlamadan önce, şunların olduğundan emin olun:

- Java programlamaya temel bir anlayış.  
- Projeye Aspose.Page for Java eklenmiş (Maven/Gradle ya da manuel JAR).  
- Java geliştirme ortamı (IDE, JDK 8+).  

## Paketleri İçe Aktarma
Başlamak için, Aspose.Page kütüphanesinden gerekli sınıfları içe aktarın.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: Çok Sayfalı bir PostScript Belgesi Oluşturma
İlk olarak, çok sayfalı olarak yapılandırılmış yeni bir `PsDocument` oluşturun. Bu, çıktı akışını ayarlar ve kütüphaneye çok sayfalı bir dosyayla çalışacağımızı bildirir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Adım 2: İlk Sayfaya İçerik Ekleme
Belge hazır olduğunda, ilk sayfaya ihtiyacınız olan herhangi bir içeriği ekleyebilirsiniz. İşiniz bittiğinde, sayfanın içeriğini kilitlemek için sayfayı kapatın.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Özel Sayfa Boyutu Nasıl Ayarlanır
Varsayılan sayfa boyutu ihtiyacınızı karşılamıyorsa, yeni bir sayfa açarken **özel bir sayfa boyutu ayarlayabilirsiniz**. Bu, makbuzlar, etiketler veya herhangi bir standart dışı düzen için faydalıdır.

## Adım 3: Farklı Boyutta İkinci Sayfa Ekleme
Aşağıda ikinci bir sayfa açıyor ve açıkça özel bir genişlik ve yükseklik (puan cinsinden) belirtiyoruz. Bu, bireysel sayfalar için özel bir sayfa boyutu nasıl ayarlanır gösterir.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Adım 4: Belgeyi Kaydetme
Son olarak, belgeyi kaydederek değişiklikleri kalıcı hale getirin. Tüm sayfalar—özel boyutlu olanlar dahil—çıktı dosyasına yazılır.

```java
// Save the document
document.save();
```

Bu adımları izleyerek, Aspose.Page kullanarak Java PostScript belgesine sorunsuz bir şekilde sayfa ekleyebilir ve **özel sayfa boyutları ayarlayabilirsiniz**, bu da her sayfanın düzeni üzerinde tam kontrol sağlar.

## Sonuç
Aspose.Page for Java, PostScript belgelerini işlemek için sağlam ve geliştirici dostu bir API sunar. Artık birden fazla sayfa eklemeyi, özel boyutlar uygulamayı ve sonucu kaydetmeyi biliyorsunuz—bu da herhangi bir Java tabanlı çözüm için tam olarak biçimlendirilmiş çıktı üretmenizi sağlar.

## Sıkça Sorulan Sorular
### Tek bir PostScript belgesine farklı boyutlarda sayfalar ekleyebilir miyim?
Evet, bu öğreticide gösterildiği gibi, çok sayfalı bir PostScript belgesinde farklı boyutlarda sayfalar ekleyebilirsiniz.  
### Ekleyebileceğim sayfa sayısı konusunda herhangi bir sınırlama var mı?
Aspose.Page, bir belgeye pratik olarak sınırsız sayıda sayfa eklemeyi destekler.  
### Sayfalara resim veya grafik gibi özel içerik ekleyebilir miyim?
Kesinlikle! Aspose.Page, metin, resimler ve diğer grafik öğeler dahil olmak üzere geniş bir içerik yelpazesi eklemenize olanak tanır.  
### Aspose.Page büyük belgeleri işlemek için uygun mu?
Evet, Aspose.Page, hem küçük hem de büyük belgeleri sorunsuz bir şekilde verimli bir şekilde işlemek için tasarlanmıştır.  
### Aspose.Page için ek kaynakları ve desteği nereden bulabilirim?
Explore the [Aspose.Page documentation](https://reference.aspose.com/page/java/), or visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.  

**Ek Soru‑Cevap**

**S:** *PostScript sayfasına çizim yaparken hangi görüntü formatları desteklenir?*  
**C:** Çizim API'sini kullanarak PNG, JPEG, BMP ve GIF görüntülerini doğrudan gömebilirsiniz.  

**S:** *Belgenin varsayılan DPI'sını nasıl değiştiririm?*  
**C:** `PsDocument` oluşturulmadan önce `PsSaveOptions.setResolution(int dpi)` metodunu ayarlayın.  

**S:** *PostScript dosyasını bir şifreyle şifreleyebilir miyim?*  
**C:** PostScript kendisi şifrelemeyi desteklemez, ancak isterseniz çıktıyı bir PDF içine alıp güvenlik ayarları uygulayabilirsiniz.  

---

**Son Güncelleme:** 2025-12-11  
**Test Edilen:** Aspose.Page for Java 24.10  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

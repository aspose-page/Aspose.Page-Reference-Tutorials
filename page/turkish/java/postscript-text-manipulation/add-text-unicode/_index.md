---
date: 2026-05-20
description: Aspose.Page kullanarak Java PostScript'te Unicode metin eklemeyi öğrenin
  – Unicode dizelerini zahmetsizce eklemek için adım adım bir rehber.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Java PostScript'te Unicode Dizesi Kullanarak Metin Ekleme
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java PostScript'te Unicode Metin Nasıl Eklenir – Aspose.Page ile
url: /tr/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Aspose.Page ile Unicode Metin Ekleme

## Giriş
Java tabanlı bir PostScript (veya XPS) iş akışına **Unicode** karakterleri eklemenin nasıl yapılacağını merak ediyorsanız, doğru yerdesiniz. Bu öğreticide, Aspose.Page Java kütüphanesini kullanarak Unicode dizgilerini gömmek için gereken adımları adım adım göstereceğiz. Rehberin sonunda, PostScript çıktınıza doğrudan herhangi bir dilde metin—Arapça, Çince, emoji vb.—ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Sağ‑dan‑sol betikleri ekleyebilir miyim?** Evet, kodda gösterildiği gibi Bidi seviyesini ayarlayın  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme yeterli; üretim için ticari lisans gerekir  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Kod platform bağımsız mı?** Kesinlikle—Windows, macOS veya Linux'ta çalıştırabilirsiniz  

## “Unicode ekleme” PostScript bağlamında ne anlama geliyor?
Unicode metin eklemek, temel ASCII aralığının dışındaki kod noktalarına sahip karakterleri—örneğin Arapça, Çince veya emoji—Aspose.Page kullanarak bir PostScript (veya XPS) belgesine gömmek demektir. Kütüphane, bu kod noktalarını seçilen fonttaki uygun gliflere otomatik olarak eşler, karmaşık şekillendirme, ligatürler ve sağ‑dan‑sol sıralamayı manuel kodlama yapmadan yönetir.

## Neden Unicode metin için Aspose.Page kullanmalı?
Aspose.Page, **%100 saf‑Java** bir çözüm sunar, **50'den fazla giriş ve çıkış formatını** destekler ve bellek içine tüm dosyayı yüklemeden 1.000 sayfaya kadar çok dilli metni işleyebilir. Harici font‑işleme araçlarına ihtiyaç duymaz, geliştirme süresini %70 azaltır ve Windows, macOS ve Linux ortamlarında tutarlı görsel çıktı garantiler.

## Önkoşullar
İlerlemeye başlamadan önce aşağıdaki öğelerin hazır olduğundan emin olun:

1. **Java Development Kit (JDK)** – 8 veya daha yeni bir sürüm.  
2. **Aspose.Page for Java** – Kütüphaneyi [indir linki](https://releases.aspose.com/page/java/) üzerinden indirin ve kurun. Tüm sürümlere [buradan](https://releases.aspose.com/) göz atabilirsiniz.  
3. **Tercih ettiğiniz IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz başka bir Java IDE.

## Paketleri İçe Aktarma
Gerekli Aspose.Page sınıflarını Java kaynak dosyanıza ekleyin:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Adım 1: Projenizi Kurun
Yeni bir Java projesi oluşturun, Aspose.Page JAR dosyasını projenin derleme yoluna ekleyin ve oluşturulan XPS dosyasının kaydedileceği bir klasör oluşturun. Bu klasör daha sonra `dataDir` olarak referans verilecektir.

## Adım 2: XPS Belgesini Başlatın
`XpsDocument` sınıfı, bellekte bir XPS dosyasını temsil eder ve tüm çizim işlemleri için bir tuval sağlar.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Adım 3: Unicode Metin Ekleme
Şimdi Unicode dizgisini gerçekten ekleyeceğiz. Aşağıdaki örnek, yalnızca ASCII karakterler içeren ters çevrilmiş “AVAJ rof SPX.esopsA” ifadesini yazar; ancak bunu istediğiniz herhangi bir Unicode metinle (ör. Arapça “مرحبا” veya Çince “你好”) değiştirebilirsiniz. Bu, belgenize **java add arabic text** ya da **java add chinese text** eklemenin yoludur.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **İpucu:** Sağ‑dan‑sol dilleri doğru şekilde renderlamak için `glyphs.setBidiLevel(1);` satırını ekleyin. Sol‑dan‑sağ betikler için bu satırı atlayabilirsiniz.

## Adım 4: Belgeyi Kaydetme
XPS dosyasını diske kalıcı olarak yazın:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Programı çalıştırdıktan sonra, oluşturulan `AddEncodingText_out.xps` dosyasını herhangi bir XPS görüntüleyicide açarak Unicode metnin belirtilen koordinatlarda renderlandığını görebilirsiniz.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Metin kareler olarak görünüyor | Font bulunamadı veya karakterleri desteklemiyor | Gerekli glifleri içeren bir font kullanın (ör. “Arial Unicode MS”) |
| Sağ‑dan‑sol metin sol‑dan‑sağ olarak gösteriliyor | Bidi seviyesi ayarlanmamış | `glyphs.setBidiLevel(1);` çağrısını ekleyin |
| Dosya kaydedilmiyor | `dataDir` yolu geçersiz veya yazma izni yok | Klasörün var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun |

## Sıkça Sorulan Sorular
**S: Aspose.Page for Java’yı başka programlama dilleriyle kullanabilir miyim?**  
C: Aspose.Page özellikle Java için geliştirilmiştir, ancak .NET, C++ ve Python için eşdeğer kütüphaneler sunulur, böylece çok‑dilli destek elde edebilirsiniz.

**S: Ücretsiz deneme mevcut mu?**  
C: Evet, Aspose.Page’in ücretsiz denemesine [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Destek ve topluluk tartışmalarını nerede bulabilirim?**  
C: Yardım, örnekler ve sorun giderme ipuçları için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**S: Test için geçici bir lisans nasıl alınır?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

**S: Aspose.Page hangi font stillerini destekliyor?**  
C: API, yüklediğiniz herhangi bir TrueType veya OpenType font için Normal, Kalın, Italik ve Kalınİtalik stillerini destekler.

## Sonuç
Artık Aspose.Page kullanarak Java PostScript (XPS) belgesine **Unicode metin ekleme** konusunda uzmanlaştınız. Bu yetenek, çok dilli raporlamayı, uluslararası faturalamayı ve ASCII dışı karakterlerin gerektiği her senaryoyu mümkün kılar. Metin döndürme, kırpma yolları veya özel font gömme gibi ek özellikleri keşfetmekten çekinmeyin—detaylar resmi [belgelendirmede](https://reference.aspose.com/page/java/) mevcuttur.

---

**Son Güncelleme:** 2026-05-20  
**Test Edilen Sürüm:** Aspose.Page for Java 23.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [How to Add Text in PostScript with Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Set Text Color Java with Aspose.Page – Text Manipulation Guide](/page/java/postscript-text-manipulation/add-text/)
- [Add Pages PostScript Java – A Seamless Guide with Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
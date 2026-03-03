---
date: 2025-12-17
description: Aspose.Page kullanarak Java PostScript'te Unicode metni eklemeyi öğrenin
  – Unicode dizelerini zahmetsizce eklemenin adım adım rehberi.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page ile Java PostScript'te Unicode Metni Nasıl Eklenir
url: /tr/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Unicode Metin Nasıl Eklenir Aspose.Page ile

## Giriş
Java tabanlı bir PostScript (veya XPS) iş akışına **Unicode** karakterleri eklemenin yolunu merak ediyorsanız, doğru yerdesiniz. Bu öğreticide, Aspose.Page Java kütüphanesini kullanarak Unicode dizgilerini gömmek için gereken adımları adım adım göstereceğiz. Kılavuzun sonunda, Arapça, Çince, emoji gibi herhangi bir dildeki metni doğrudan PostScript çıktınıza ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Sağ‑dan‑sol scriptler ekleyebilir miyim?** Evet, kodda gösterildiği gibi Bidi seviyesini ayarlayın  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme yeterli; üretim için ticari lisans gerekir  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Kod platform bağımsız mı?** Kesinlikle—Windows, macOS veya Linux üzerinde çalıştırabilirsiniz

## “Unicode ekleme” PostScript bağlamında ne anlama geliyor?
Unicode eklemek, temel ASCII aralığının ötesindeki kod noktalarıyla temsil edilen karakterleri yerleştirmek demektir. Aspose.Page, düşük seviyeli kodlama detaylarını soyutlayarak, metin içeriğine ve görsel konumlandırmaya odaklanmanızı sağlar.

## Neden Unicode metin için Aspose.Page kullanmalı?
- **Tam Unicode desteği** – Karmaşık scriptler, ligaturler ve sağ‑dan‑sol dilleri yönetir.  
- **Harici bağımlılık yok** – Yazı tipi dosyalarını manuel olarak yönetmenize gerek yok; API sistem yazı tipleriyle çalışır.  
- **Basit API** – Çok dilli metin oluşturmak için sadece birkaç metod çağrısı yeterlidir.

## Ön Koşullar
İlerlemeye başlamadan önce aşağıdaki öğelerin hazır olduğundan emin olun:

1. **Java Development Kit (JDK)** – Herhangi bir güncel sürüm (8 veya üzeri).  
2. **Aspose.Page for Java** – Kütüphaneyi [indir linki](https://releases.aspose.com/page/java/) üzerinden indirip kurun.  
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
Yeni bir Java projesi oluşturun, Aspose.Page JAR dosyasını projenin derleme yoluna ekleyin ve oluşturulacak XPS dosyasının kaydedileceği bir klasör oluşturun. Bu klasör daha sonra `dataDir` olarak referans verilecektir.

## Adım 2: XPS Belgesini Başlatın
İçeriği tutacak boş bir XPS belgesi örneği oluşturun:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Adım 3: Unicode Metin Ekleyin
Şimdi Unicode dizgisini ekleyeceğiz. Aşağıdaki örnek, yalnızca ASCII karakterler içeren ters çevrilmiş “AVAJ rof SPX.esopsA” ifadesini yazar; ancak bunu istediğiniz herhangi bir Unicode metinle (ör. Arapça “مرحبا” veya Çince “你好”) değiştirebilirsiniz.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **İpucu:** Sağ‑dan‑sol dilleri doğru şekilde render etmek için `glyphs.setBidiLevel(1);` satırını ekleyin. Sol‑dan‑sağ scriptler için bu satırı atlayabilirsiniz.

## Adım 4: Belgeyi Kaydedin
XPS dosyasını diske kalıcı olarak yazın:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Programı çalıştırdıktan sonra, oluşturulan `AddEncodingText_out.xps` dosyasını herhangi bir XPS görüntüleyicide açarak Unicode metnin belirtilen koordinatlarda render edildiğini görebilirsiniz.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Metin kareler olarak görünüyor | Yazı tipi bulunamıyor veya karakterleri desteklemiyor | Gerekli glifleri içeren bir yazı tipi kullanın (örn. “Arial Unicode MS”) |
| Sağ‑dan‑sol metin sol‑dan‑sağ gösteriliyor | Bidi seviyesi ayarlanmamış | `glyphs.setBidiLevel(1);` çağrısını ekleyin |
| Dosya kaydedilmiyor | `dataDir` yolu geçersiz veya yazma izni yok | Klasörün var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun |

## Sık Sorulan Sorular
### Aspose.Page for Java’yı başka programlama dilleriyle kullanabilir miyim?
Aspose.Page öncelikle Java için tasarlanmıştır, ancak Aspose çeşitli programlama dilleri için kütüphaneler sunar.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.Page’in ücretsiz denemesine [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page hakkında destek ve tartışma nereden bulunur?
Destek ve tartışmalar için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### Aspose.Page için geçici bir lisans nasıl alınır?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### Aspose.Page’de hangi yazı tipi stilleri bulunur?
Aspose.Page Regular, Bold, Italic ve BoldItalic gibi yazı tipi stillerini destekler.

## Sonuç
Artık Aspose.Page kullanarak Java PostScript (XPS) belgesine **Unicode metin ekleme** konusunda uzmanlaştınız. Bu yetenek, çok dilli raporlamalar, uluslararası faturalar ve ASCII dışı karakterlerin gerektiği her senaryo için kapıları açar. Metin döndürme, kırpma yolları veya özel yazı tipleri gömme gibi ek özellikleri keşfetmekten çekinmeyin—detaylar resmi [dökümantasyonda](https://reference.aspose.com/page/java/) mevcuttur.

---

**Son Güncelleme:** 2025-12-17  
**Test Edilen Versiyon:** Aspose.Page for Java 23.12 (yazım anındaki en güncel)  
**Yazar:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

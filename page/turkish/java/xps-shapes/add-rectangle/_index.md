---
date: 2025-12-30
description: Aspose.Page kullanarak dikdörtgenler ekleyerek Java’da XPS belgesi oluşturmayı
  öğrenin. Sorunsuz XPS belgesi manipülasyonu için bu adım adım rehberi izleyin.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: XPS Belgesi Oluşturma Java – Aspose.Page ile Dikdörtgen Ekle
url: /tr/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Document Java Oluşturma – Dikdörtgen Ekleme

## Giriş
Bu kapsamlı öğreticide **XPS document Java** dosyaları oluşturacak ve Aspose.Page kütüphanesini kullanarak dikdörtgen eklemeyi öğreneceksiniz. Raporlar, faturalar veya özel grafikler oluşturuyor olun, dikdörtgen oluşturmayı öğrenmek XPS düzeni üzerinde hassas kontrol sağlar. Her adımı birlikte inceleyecek, kodun her satırının nedenini açıklayacak ve profesyonel sonuçlar için renk ve çizgi stillerini nasıl özelleştireceğinizi göstereceğiz.

## Hızlı Yanıtlar
- **Hangi kütüphane önerilir?** Aspose.Page for Java  
- **Uygulama ne kadar sürer?** Temel bir dikdörtgen için yaklaşık 10 dakika  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gerekir  
- **Hangi Java sürümü desteklenir?** Java 8 ve üzeri  
- **Birden fazla şekil ekleyebilir miyim?** Evet – her şekil için adımları tekrarlayın

## Önkoşullar
Başlamadan önce şunların olduğundan emin olun:

- Java programlama diline temel aşinalık.  
- Aspose.Page kütüphanesi yüklü. Yüklü değilse, [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.  
- Çalışan bir Java geliştirme ortamı (IDE, JDK ve tercihinize göre Maven/Gradle).

## Paketleri İçe Aktarma
Başlamak için gerekli paketleri Java projenize dahil edin. Aspose.Page kütüphanesinin sınıf yolunuza doğru şekilde eklendiğinden emin olun. İşte temel bir örnek:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Şimdi, sağlanan örneği Java XPS içinde bir dikdörtgen eklemek için birden fazla adıma ayıralım.

## Adım 1: Belge Dizini Ayarlama
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini XPS dosyalarını saklamak istediğiniz klasörün yolu ile değiştirin.

## Adım 2: Yeni bir XPS Belgesi Oluşturma
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Bu satır **yeni** bir XPS belgesi oluşturur; daha sonra şekiller, metin veya görseller ekleyebilirsiniz.

## Adım 3: CMYK Katı Renkli Çizgili Dikdörtgen Ekleme
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Bu adım, CMYK katı renkli bir çizgiyle dikdörtgen ekler. Boyut veya konumu değiştirmek için geometri dizesini (`"M 20,10 L 220,10 220,100 20,100 Z"`) düzenleyebilir, tasarımınıza uygun renk değerlerini `createColor` içinde ayarlayabilirsiniz.

## Adım 4: Oluşturulan XPS Belgesini Kaydetme
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Son olarak, eklenen dikdörtgenle değiştirilmiş XPS belgesini önceki adımda belirttiğiniz dizine kaydedin.

## Yaygın Kullanım Senaryoları
- **Rapor başlıkları** – Başlıklar için arka plan blokları olarak dikdörtgen kullanın.  
- **Fatura tabloları** – Hücreleri veya bölümleri renkli kenarlıklarla vurgulayın.  
- **Özel grafikler** – Karmaşık şekiller oluşturmak için birden fazla dikdörtgen birleştirin.

## Sorun Giderme İpuçları
- **Dosya bulunamadı hatası:** `dataDir` değişkeninin mevcut bir klasöre işaret ettiğini ve ICC profilinin (`uswebuncoated.icc`) bulunduğunu doğrulayın.  
- **Yanlış renkler:** ICC profilinin kullanmak istediğiniz renk uzayıyla (CMYK vs. RGB) eşleştiğinden emin olun.  
- **Beklenmeyen boyutlar:** Geometri dizesini doğru koordinatları yansıtacak şekilde ayarlayın.

## Sonuç
Tebrikler! Aspose.Page kullanarak **XPS document Java** dosyaları oluşturmayı ve dikdörtgen eklemeyi başarıyla öğrendiniz. Bu temel, daha zengin XPS belgeleri oluşturmanıza, grafikleri özelleştirmenize ve şekilleri daha büyük iş akışlarına entegre etmenize olanak tanır.

## SSS
### Tek bir XPS belgesine birden fazla dikdörtgen ekleyebilir miyim?
Evet, öğreticide açıklanan adımları tekrarlayarak ihtiyacınız kadar dikdörtgen ekleyebilirsiniz.

### Dikdörtgenin rengini nasıl değiştirebilirim?
İstediğiniz rengi elde etmek için `createColor` metodundaki renk değerlerini değiştirin.

### Aspose.Page karmaşık XPS belge manipülasyonları için uygun mu?
Kesinlikle! Aspose.Page, çeşitli XPS belge görevlerini yönetmek için güçlü bir özellik seti sunar.

### Ek örnekler ve destek nereden bulunur?
Daha fazla örnek ve topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini inceleyin.

### Satın almadan önce Aspose.Page'i deneyebilir miyim?
Evet, Aspose.Page'in yeteneklerini keşfetmek için bir [free trial](https://releases.aspose.com/) deneyebilirsiniz.

## Sık Sorulan Sorular

**S: Bu yaklaşım Java 11 veya daha yeni sürümlerle çalışır mı?**  
C: Evet, Aspose.Page kütüphanesi Java 8 ve üzeri, Java 11, 17 ve sonrası sürümlerle uyumludur.

**S: Dikdörtgen alanının içine görsel ekleyebilir miyim?**  
C: Aynı geometri koordinatlarını kullanarak bir `XpsImage` öğesi ekleyebilir ve dikdörtgenin üzerine ya da içine konumlandırabilirsiniz.

**S: Sadece çizgi yerine doldurma rengi nasıl ayarlanır?**  
C: `doc.createSolidColorBrush(...)` ile oluşturulan katı renk fırçasını `path.setFill(...)` ile çağırın.

**S: Dikdörtgeni döndürebilir miyim?**  
C: `path.setTransform(...)` ile bir dönüşüm matrisi uygulayarak döndürme veya ölçekleme yapabilirsiniz.

**S: Üretim kullanımı için hangi lisans gereklidir?**  
C: Dağıtım için ticari bir Aspose.Page lisansı gerekir; ücretsiz deneme yalnızca değerlendirme ve geliştirme amaçlıdır.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-30  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en yeni)  
**Yazar:** Aspose  

---
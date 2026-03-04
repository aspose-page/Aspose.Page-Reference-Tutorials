---
date: 2025-12-25
description: Aspose.Page kullanarak Java'da XPS belgelerine degrade eklemeyi ve çarpıcı
  yatay efektler için degrade duraklarını nasıl özelleştireceğinizi öğrenin.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPS'de Degrade Ekleme – Yatay Degrade
url: /tr/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'te Degrade Ekleme – Yatay Degrade

## Giriş
Java kullanarak bir XPS belgesine **degrade ekleme** konusunda adım adım bir kılavuza hoş geldiniz. Bu öğreticide yatay bir degrade nasıl eklenir, görsel şıklık için neden önemlidir ve kesin renk kontrolü için **degrade duraklarını nasıl özelleştirirsiniz** öğreneceksiniz. Aspose.Page for Java, XPS (XML Paper Specification) belgeleriyle çalışmayı basitleştirir; düşük seviyeli dosya işlemleriyle uğraşmadan tasarıma odaklanmanızı sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Hangi Java sürümü çalışır?** Herhangi bir Java 8+ çalışma zamanı  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir  
- **Degrade yönünü değiştirebilir miyim?** Evet – lineer fırçanın başlangıç/bitiş noktalarını değiştirin  
- **Birden fazla degrade eklemek mümkün mü?** Kesinlikle – farklı fırçalarla yol oluşturma adımlarını tekrarlayın  

## XPS'te Yatay Degrade Nedir?
Yatay degrade, bir şekil üzerinde soldan sağa doğru renklerin yumuşak bir geçişidir. XPS'te, tanımlı **degrade durakları** arasında ara değerler oluşturan lineer bir degrade fırçası ile temsil edilir. Bu görsel etki genellikle afişlerde, düğmelerde ve arka plan doldurmalarında kullanılır.

## Neden Aspose.Page for Java Kullanmalı?
- **Tam XPS desteği** – üçüncü‑taraf araçlara ihtiyaç duymadan oluşturun, düzenleyin ve render edin.  
- **Basit API** – `XpsDocument`, `XpsPath` ve `XpsGradientBrush` gibi yüksek seviyeli nesneler XML karmaşıklığını gizler.  
- **Performans** – büyük belgeler ve toplu işleme için optimize edilmiştir.  

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Java Geliştirme Ortamı** – En son JDK'yı [java.com](https://www.java.com) adresinden indirin.  
2. **Aspose.Page for Java Kütüphanesi** – JAR dosyasını [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) sayfasından indirin.  

## Paketleri İçe Aktarma
Gerekli sınıfları içe aktararak başlayın. Bu importlar belge oluşturma, degrade işleme ve temel geometriye erişim sağlar.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Adım 1: XPS Belgesini Başlatma
Yeni bir `XpsDocument` örneği oluşturun ve sonucu kaydetmek istediğiniz klasörü belirtin.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Adım 2: Yatay Degrade Oluşturma
Renk ve konumu kontrol eden **degrade durakları** listesini tanımlayın. Aşağıdaki örnek, canlı bir gökkuşağı‑benzeri degrade oluşturur.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Degrade duraklarını nasıl özelleştirirsiniz
- **Renk** – Herhangi bir ARGB değerini ayarlamak için `doc.createColor(alpha, red, green, blue)` kullanın.  
- **Konum** – İkinci argüman (`0` ile `1` arasında bir `float`) degrade çizgisi üzerindeki durak konumunu belirler. Bu değerleri değiştirerek renkleri sola ya da sağa kaydırabilirsiniz.

## Adım 3: Degrade ile Yolu Ekleyin
Dikdörtgen bir yol oluşturun, gerekirse bir dönüşüm uygulayın ve lineer degrade fırçası ile doldurun. Fırça, yatay etki oluşturmak için iki nokta (`(10,0)` ile `(228,0)`) kullanır.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**İpucu:** Aynı `stops` listesini birden fazla yol için yeniden kullanmak performansı artırabilir; ancak yeni duraklar eklemeden önce `clear()` yapmayı unutmayın.

## Adım 4: Belgeyi Kaydetme
XPS dosyasını diske kalıcı olarak kaydedin. Artık herhangi bir XPS görüntüleyiciyle açıp yatay degradeyi görebilirsiniz.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Yaygın Sorunlar & Çözümler
| Sorun | Nedeni | Çözüm |
|-------|--------|-----|
| Degrade tek renk gibi görünüyor | Degrade durakları eklenmemiş veya fırça ayarlanmamış | `path.setFill(...)` ifadesinin bir `LinearGradientBrush` kullandığından ve durakların `getGradientStops().addAll(stops)` ile eklendiğinden emin olun. |
| Renkler soluk | Alpha değeri (ilk parametre) hatalı | Şeffaflık istenmiyorsa `255` kullanın. |
| Yol boyutu yanlış | Dönüşüm matrisi değerleri hatalı | Matris parametrelerini (`scaleX, skewY, skewX, scaleY, translateX, translateY`) ayarlayın. |

## Sık Sorulan Sorular

**S: Tek bir XPS belgesinde birden fazla degrade uygulayabilir miyim?**  
C: Evet, her biri kendi degrade fırçasına sahip birden fazla yol ekleyerek karmaşık katmanlı tasarımlar oluşturabilirsiniz.

**S: Aspose.Page en yeni Java sürümleriyle uyumlu mu?**  
C: Aspose.Page for Java düzenli olarak güncellenir ve Java 8 ve üzeri sürümlerle çalışır.

**S: Aspose.Page'de başka degrade tipleri var mı?**  
C: Lineer degradelerin yanı sıra, dairesel renk geçişleri için radyal degradeler de desteklenir.

**S: Degrade duraklarının renklerini ve konumlarını özelleştirebilir miyim?**  
C: Kesinlikle! Her durak için ARGB rengini ve 0‑1 aralığındaki relatif konumunu tam kontrol edebilirsiniz.

**S: Aspose.Page için topluluk forumu var mı?**  
C: Evet, toplulukla iletişime geçmek ve yardım almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2025-12-25  
**Test Edilen Sürüm:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
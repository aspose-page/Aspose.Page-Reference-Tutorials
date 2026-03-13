---
date: 2026-03-13
description: Aspose.Page kullanarak Java'da XPS belgelerine degrade eklemeyi ve çarpıcı
  yatay efektler için degrade duraklarını nasıl özelleştireceğinizi öğrenin.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPS'te Gradyan Ekleme – Yatay Gradyan
url: /tr/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Gradient Ekleme – Yatay Gradient

## Giriş
Java kullanarak bir XPS belgesine **gradient ekleme** konusunda adım adım bu kılavuza hoş geldiniz. Bu öğreticide yatay bir gradient nasıl eklenir, görsel şıklık için neden önemli ve kesin renk kontrolü için **gradient stop'ları (gradient stops) özelleştirme** nasıl yapılır öğreneceksiniz. Aspose.Page for Java, XPS (XML Paper Specification) belgeleriyle çalışmayı basitleştirir, düşük seviyeli dosya işlemleri yerine tasarıma odaklanmanızı sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Hangi Java sürümü çalışır?** Herhangi bir Java 8+ çalışma zamanı  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir  
- **Gradient yönünü değiştirebilir miyim?** Evet – sadece lineer fırçanın başlangıç/bitiş noktalarını değiştirin  
- **Birden fazla gradient eklemek mümkün mü?** Kesinlikle – farklı fırçalarla yol oluşturma adımlarını tekrarlayın  

## XPS'de Yatay Gradient Nedir?
Yatay gradient, bir şekil üzerinde soldan sağa doğru renklerin yumuşak bir geçişidir. XPS'de bu, tanımlı **gradient stop**'lar arasında ara değer alarak çalışan bir lineer gradient fırçası ile temsil edilir. Bu görsel etki genellikle afişlerde, düğmelerde ve arka plan doldurmalarında kullanılır.

## Neden Aspose.Page for Java Kullanmalı?
- **Tam XPS desteği** – üçüncü taraf araçları olmadan oluşturma, düzenleme ve renderleme.  
- **Basit API** – `XpsDocument`, `XpsPath` ve `XpsGradientBrush` gibi yüksek seviyeli nesneler XML karmaşıklığını gizler.  
- **Performans** – büyük belgeler ve toplu işleme için optimize edilmiştir.  

## Önkoşullar
1. **Java Geliştirme Ortamı** – En yeni JDK'yı [java.com](https://www.java.com) adresinden kurun.  
2. **Aspose.Page for Java Kütüphanesi** – JAR dosyasını [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) adresinden indirin.  

## Paketleri İçe Aktarma
Gerekli sınıfları içe aktararak başlayın. Bu importlar belge oluşturma, gradient işleme ve temel geometriye erişim sağlar.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Adım 1: XPS Belgesini Başlatın
Yeni bir `XpsDocument` örneği oluşturun ve sonucu kaydetmek istediğiniz klasöre yönlendirin.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Adım 2: Yatay Gradient Oluşturun
**gradient stop**'ların renk ve konumunu kontrol eden bir liste tanımlayın. Aşağıdaki örnek, canlı bir gökkuşağı benzeri gradient oluşturur.

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

### Gradient stop'ları nasıl özelleştirirsiniz
- **Renk** – Herhangi bir ARGB değerini ayarlamak için `doc.createColor(alpha, red, green, blue)` kullanın.  
- **Pozisyon** – İkinci argüman (`0` ile `1` arasında `float`) stop'un gradient çizgisi üzerindeki konumunu belirler. Renkleri sola ya da sağa kaydırmak için bu değerleri ayarlayın.

## Adım 3: Gradient ile Yolu Ekleyin
Dikdörtgen bir yol oluşturun, gerekirse bir dönüşüm uygulayın ve lineer gradient fırçası ile doldurun. Fırça, yatay bir etki oluşturmak için iki nokta (`(10,0)` ile `(228,0)`) kullanır. Y koordinatları aynı olduğundan bu fırça bir **yatay gradient fırçası** olarak çalışır.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro ipucu:** Aynı `stops` listesini birden fazla yol için yeniden kullanmak performansı artırabilir, ancak yeni stop'lar eklemeden önce `clear()` yapmayı unutmayın.

## Adım 4: Belgeyi Kaydedin
XPS dosyasını diske kaydedin. Artık herhangi bir XPS görüntüleyiciyle açarak yatay gradientin çalışmasını görebilirsiniz.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Birden Çok Gradient Nasıl Uygulanır
Aynı XPS belgesi içinde **birden çok gradient uygulamak** istiyorsanız, her yeni şekil için “Yatay Gradient Oluştur” ve “Gradient ile Yolu Ekle” adımlarını tekrarlamanız yeterlidir. Yeni bir `XpsGradientStop` nesne listesi kullanın (veya mevcut listeyi temizleyin) ve kendi başlangıç/bitiş noktalarına sahip yeni bir `LinearGradientBrush` atayın. Bu yaklaşım, gradient'leri katmanlamanıza, karmaşık arka planlar oluşturmanıza veya tek bir sayfada farklı UI öğelerini vurgulamanıza olanak tanır.

## Neden Önemli – Yatay Gradient Fırçasının Faydaları
- **Görsel derinlik:** Yatay gradient fırçası, ekstra görüntü kullanmadan hafif bir üç boyutlu his ekler.  
- **Dosya boyutu verimliliği:** Gradient'ler vektör tanımları olarak saklanır, XPS dosyasını hafif tutar.  
- **Ölçeklenebilirlik:** Gradient vektör tabanlı olduğu için yüksek çözünürlüklü ekranlarda sorunsuz ölçeklenir.  

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Gradient katı görünüyor | Gradient stop eklenmemiş veya fırça ayarlanmamış | `path.setFill(...)` ifadesinin bir `LinearGradientBrush` kullandığından ve stop'ların `getGradientStops().addAll(stops)` ile eklendiğinden emin olun. |
| Renkler soluk görünüyor | Yanlış alfa değeri (ilk parametre) | Şeffaflık istenmiyorsa tam opak renkler için `255` kullanın. |
| Yol boyutu hatalı | Dönüşüm matris değerleri yanlış | Matris parametrelerini (`scaleX, skewY, skewX, scaleY, translateX, translateY`) ayarlayın. |

## Sık Sorulan Sorular

**S: Tek bir XPS belgesinde birden çok gradient uygulayabilir miyim?**  
C: Evet, her biri kendi gradient fırçasına sahip birden fazla yol ekleyerek karmaşık katmanlı tasarımlar oluşturabilirsiniz.

**S: Aspose.Page en yeni Java sürümleriyle uyumlu mu?**  
C: Aspose.Page for Java düzenli olarak güncellenir ve Java 8 ve üzeri sürümlerle çalışır.

**S: Aspose.Page'de başka gradient türleri var mı?**  
C: Lineer gradient'lerin yanı sıra Aspose.Page, dairesel renk geçişleri için radyal gradient'leri de destekler.

**S: Gradient stop'ların renklerini ve konumlarını özelleştirebilir miyim?**  
C: Kesinlikle! Her stop'un ARGB rengini ve göreceli konumunu (0‑1 aralığı) tam kontrol edebilirsiniz.

**S: Yardım alabileceğim bir Aspose.Page topluluk forumu var mı?**  
C: Evet, toplulukla iletişime geçmek ve yardım almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2026-03-13  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
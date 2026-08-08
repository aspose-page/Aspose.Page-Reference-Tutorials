---
date: 2026-05-25
description: Java kullanarak Aspose.Page ile XPS belgelerine gradient eklemeyi öğrenin.
  Bu adım adım kılavuz, diyagonal gradient eklemeyi, linear gradient brushes uygulamayı
  ve profesyonel XPS dosyaları üretmeyi gösterir.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Java XPS'de Diagonal Gradient Ekle
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Nasıl Gradient Eklenir: Java XPS''de Diagonal Gradient'
url: /tr/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nasıl Degrade Eklenir: Java XPS'de Diyagonal Degrade

## Giriş
Modern Java geliştirmede, XPS belgelerine **degrade eklemeyi** ustalıkla öğrenmek, raporlarınıza cilalı, göz alıcı bir görünüm kazandırır ve öne çıkar. Bu eğitim, sıfırdan bir XPS dosyası oluşturmayı, diyagonal bir degrade eklemeyi ve sonucu kaydetmeyi—tümü Aspose.Page for Java ile—adım adım gösterir. Neden degradelerin önemli olduğunu anlayacak, kesin API çağrılarını görecek ve yaygın hatalardan kaçınmak için pratik ipuçları elde edeceksiniz.

## Hızlı Yanıtlar
- **Birincil kütüphane nedir?** Aspose.Page for Java  
- **Hangi yöntem degrade ekler?** `createLinearGradientBrush` ile gradient stops  
- **Lisans gerekli mi?** Geliştirme için deneme sürümü çalışır; üretim için ticari lisans gerekir  
- **Uygulama ne kadar sürer?** Temel bir diyagonal degrade için yaklaşık 10‑15 dakika  
- **Bunu diğer Java framework'leriyle kullanabilir miyim?** Evet, API framework‑agnostiktir  

## XPS belgesinde diyagonal degrade nedir?
Diyagonal degrade, bir şeklin bir köşesinden karşı köşesine doğru akan pürüzsüz bir renk geçişidir ve eğik bir görsel etki yaratır. XPS'te bu etki, sıralı gradient stop'ları içeren bir lineer degrade fırçası ile tanımlanır; bu stop'lar renkleri ve diyagonal çizgi üzerindeki göreli konumları belirtir.

## Aspose.Page ile diyagonal degrade neden eklenir?
Aspose.Page, **%100 render doğruluğu** sağlayarak degradeleri 20'den fazla XPS görüntüleyicide aynı şekilde gösterir ve **30+ XPS özelliği** (metin, resim, vektör şekiller vb.) destekler. API, karmaşık XPS işaretlemesini soyutlayarak tasarıma odaklanmanızı sağlar ve dosyanın Windows, macOS ve Linux platformlarında aynı görünmesini garantiler.

## Önkoşullar
- Temel Java programlama bilgisi.  
- Makinenizde JDK yüklü.  
- Aspose.Page for Java kütüphanesi – **[buradan](https://releases.aspose.com/page/java/)** indirin.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.

## Paketleri İçe Aktar
Gerekli sınıfları içe aktararak başlayın. Bu import'lar geometri, degrade işleme ve XPS belge oluşturma erişimini sağlar.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Adım 1: Projenizi Kurun
Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Page JAR dosyalarını projenin derleme yoluna ekleyin.

## Adım 2: Belge Dizinini Tanımlayın
Oluşturulacak XPS dosyasının kaydedileceği yeri belirtin.

```java
String dataDir = "Your Document Directory";
```

## Adım 3: XPS Belgesi Oluşturun
`XpsDocument` bellek içinde bir XPS dosyasını temsil eden temel nesnedir. Örnekleyerek sayfalar, şekiller ve fırçalar ekleyebileceğiniz bir tuval elde edersiniz.

```java
XpsDocument doc = new XpsDocument();
```

## Adım 4: Diyagonal Degrade Yolu Ekleyin
Degrade alacak dikdörtgen bir yol oluşturun. Yol geometrisi basit bir move‑line‑close komutu kullanır.  
XpsPath, XPS belgesinde bir vektör şekli (örneğin dikdörtgen veya özel geometri) tanımlar.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Adım 5: Lineer Degrade Duraklarını Tanımlayın
Renkleri ve konumlarını ayarlayın. Her durak, degradede belirli bir rengin göründüğü noktayı tanımlar.  
XpsGradientStop, bir degradede tek bir renk durakını temsil eder; renk ve offset (kaydırma) değerini belirtir.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Adım 6: Yola Lineer Degrade Uygula
`XpsLinearGradientBrush`, Aspose.Page'in lineer renk geçişleri için fırça tipidir. Degrade yönünü tanımlayan iki nokta ve bu çizgi boyunca renkleri belirleyen bir degrade durakları koleksiyonu alır.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Adım 7: Belgeyi Kaydedin
XPS dosyasını diske kalıcı olarak yazın. Dosya, tanımladığınız diyagonal degrade ile doldurulmuş dikdörtgeni içerecektir.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Java XPS'de nasıl degrade eklenir?
`XpsDocument`'i yükleyin, başlangıç noktası `(0,0)` ve bitiş noktası `(width,height)` olan bir `XpsLinearGradientBrush` oluşturun, degrade duraklarını ekleyin, fırçayı şeklin `Fill` özelliğine atayın ve son olarak `save` metodunu çağırın. Bu kısa akış, sadece birkaç API çağrısıyla diyagonal bir degrade eklemenizi sağlar ve kodunuzu temiz ve sürdürülebilir tutar.

## Yaygın Tuzaklar ve İpuçları
- **Degrade yönü** – fırçanın başlangıç ve bitiş noktalarının istediğiniz diyagonalı yansıttığından emin olun; yerlerini değiştirirseniz degrade tersine döner.  
- **Renk hassasiyeti** – Aspose ARGB kullanır; şeffaflık gerekiyorsa alfa kanalını da ekleyin.  
- **Dosya yolu** – her zaman mutlak bir yol kullanın veya göreli yolun mevcut ve yazılabilir bir dizine işaret ettiğini doğrulayın.

## Ek SSS

**S: Mevcut bir XPS şekline **how to add gradient** nasıl eklerim?**  
C: `XpsLinearGradientBrush` oluşturun, degrade duraklarını tanımlayın ve şeklin `Fill` özelliğine atayın; adım 6'da gösterildiği gibi.

**S: **apply linear gradient** aslında sahne arkasında ne yapıyor?**  
C: Başlangıç/bitiş noktalarını ve degrade durakları koleksiyonunu referans alan bir fırça tanımını XPS paketine ekler; görüntüleyici bunu pürüzsüz bir renk geçişi olarak işler.

**S: Diğer XPS özellikleri için **how to use aspose** hızlı bir yol var mı?**  
C: Evet, Aspose.Page API'si resim, metin ve özel şekiller eklemek için metodlar içerir—ek yardımcılar için `XpsDocument` sınıfını keşfedin.

**S: **add gradient path**'i dikdörtgen olmayan şekillere uygulayabilir miyim?**  
C: Kesinlikle. `createPathGeometry` ile herhangi bir geometri tanımlayın ve ardından `Fill` özelliğini bir degrade fırçasına ayarlayın.

**S: Degrade dosya boyutunu önemli ölçüde etkiler mi?**  
C: Yalnızca çok az; degrade tanımları XPS paketindeki hafif XML girdileri olarak yer alır.

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## İlgili Eğitimler

- [Aspose Page XPS Gradient Addition](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
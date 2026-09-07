---
date: 2026-09-04
description: Linear Gradient Paint Java'ı Aspose.Page for Java ile kullanarak bir
  PostScript dosyasında yatay gradyan java nasıl oluşturulacağını öğrenin. Adım adım
  kod, yaygın hatalar ve SSS.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Aspose kullanarak PostScript'te yatay gradyan java oluşturun
og_description: Linear Gradient Paint Java ile PostScript'te yatay gradyan java oluşturun.
  Bu Aspose.Page öğreticisi, tam adımları, ön koşulları ve 15 dakikadan kısa sürede
  sorun giderme ipuçlarını gösterir.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Aspose kullanarak PostScript'te yatay gradyan java oluşturun
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Aspose kullanarak PostScript'te yatay gradyan java oluşturun
url: /tr/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Linear Gradient Paint Kullanarak Yatay Gradyan Nasıl Eklenir

## Giriş
Bu kapsamlı öğreticide, Aspose.Page for Java ile birlikte gelen **Linear Gradient Paint Java** sınıfını kullanarak bir PostScript belgesinde **yatay gradyan java** oluşturmayı öğreneceksiniz. Projeyi kurmaktan gradyanı hem şekillerde hem de metinde renderlemeye kadar her adımı adım adım göstereceğiz, böylece dakikalar içinde cilalı, baskıya hazır grafikler üretebileceksiniz. Raporlama motoru, tasarım‑otomasyon aracı veya özel bir yazıcı sürücüsü geliştiriyor olun, bu kılavuz ihtiyacınız olan tam kodu sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (includes Linear Gradient Paint Java).  
- **Uygulama ne kadar sürer?** Temel bir yatay gradyan için yaklaşık 10‑15 dakika.  
- **Lisans gerekli mi?** Üretim kullanımında geçici veya tam lisans gereklidir.  
- **Hangi JDK sürümü çalışır?** Java 8 veya daha yeni.  
- **Gradyanı hem şekillerde hem de metinde kullanabilir miyim?** Evet – aynı `LinearGradientPaint` örneği şekilleri doldurabilir ve metin çizgilerine veya doldurmalarına uygulanabilir.

## Yatay gradyan nedir ve neden kullanılır?
Yatay bir gradyan, bir nesnenin sol kenarından sağ kenarına doğru renkleri karıştırarak derinlik ve görsel ilgi ekleyen pürüzsüz bir geçiş oluşturur. Modern UI bileşenleri, vurgulanan başlıklar veya PDF ya da PostScript raporlarındaki ince arka plan gölgeleri için idealdir. **Linear Gradient Paint Java** kullanarak başlangıç ve bitiş renklerini, opaklığı ve ölçeklemeyi hassas bir şekilde kontrol edebilir, sonucun herhangi bir cihazda veya yazıcıda net görünmesini sağlayabilirsiniz.

## Önkoşullar
Kodun içine girmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java Development Kit (JDK) makinenizde kurulu.
- Aspose.Page for Java kütüphanesi. Bunu [Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.

## Paketleri İçe Aktar
Java projenizde gerekli paketleri içe aktararak başlayın. Bu importlar, grafik temel öğelerine, gradyan işleme ve Aspose.Page API'sine erişim sağlar.

`PsDocument` sınıfı, üzerine grafik çizebileceğiniz bir PostScript belgesini temsil eder.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: bir dikdörtgen oluştur
İlk olarak, çıktı akışını, belgeyi ve gradyanı barındıracak bir dikdörtgeni ayarlayın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Adım 2: yatay lineer gradyan boyası oluştur
`LinearGradientPaint` lineer renk geçişini tanımlayan temel sınıftır.  
`LinearGradientPaint` sınıfı, bir düz çizgi boyunca gradyan çizen bir boya nesnesini temsil eder; başlangıç/bitiş noktalarını, renk duraklarını ve şeklinize ölçeklemek için isteğe bağlı bir `AffineTransform` belirtebilirsiniz.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Adım 3: dikdörtgeni doldur
Şimdi, az önce tanımladığımız gradyan ile dikdörtgeni doldurun.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Adım 4: metni gradyan ile doldur
Aynı gradyanı metne de uygulayabilir, çarpıcı bir görsel etki yaratabilirsiniz.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Adım 5: metni gradyan ile konturla
Son olarak, metni gradyanı çizgi rengi olarak kullanarak konturlayın.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Yaygın sorunlar ve çözümler
| Sorun | Neden oluşur | Çözüm |
|-------|----------------|-----|
| Gradyan uzatılmış görünüyor | Yanlış `AffineTransform` ölçeklemesi | Dönüşümün genişlik ve yüksekliğinin dikdörtgenin boyutlarıyla (örnekte 200 × 100) eşleştiğinden emin olun. |
| Renkler soluk görünüyor | Alfa değerleri çok düşük ayarlanmış | Alfa bileşenini artırın (`new Color(r,g,b,alpha)` içindeki dördüncü değer). |
| Metin görünmüyor | Metin çizilmeden önce boya ayarlanmamış | `document.setPaint(paint)` metodunu **herhangi bir** `fillAndStrokeText` veya `outlineText` çağrısından **önce** çağırın. |

## Sıkça Sorulan Sorular
**S:** Aspose.Page for Java'ı ticari projelerde kullanabilir miyim?  
**C:** Evet, Aspose.Page for Java ticari projelerde kullanılabilir. Lisans detayları için [Aspose.Purchase](https://purchase.aspose.com/buy) sayfasını ziyaret edin.

**S:** Ücretsiz deneme mevcut mu?  
**C:** Evet, Aspose.Page for Java için ücretsiz deneme sürümüne [Aspose.Page for Java ücretsiz deneme](https://releases.aspose.com/) sayfasından erişebilirsiniz.

**S:** Ek belge ve destek nereden bulunabilir?  
**C:** Kapsamlı kaynaklar için [Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/) sayfasını ziyaret edin. Topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresine bakın.

**S:** Geçici bir lisans nasıl alabilirim?  
**C:** Geçici lisansı [Aspose.Purchase geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S:** Aspose.Page for Java için sistem gereksinimleri nelerdir?  
**C:** Detaylı sistem gereksinimleri için [Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/) sayfasına bakın.

---

**Son Güncelleme:** 2026-09-04  
**Test Edilen:** Aspose.Page for Java 24.11  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java'da PostScript Gradyanı Oluştur – Dikey Gradyan Ekle](/page/java/postscript-gradient-addition/vertical/)
- [Gradyan Ekleme: Java PostScript'te Aspose.Page Java kullanarak Diyagonal Gradyan](/page/java/postscript-gradient-addition/diagonal/)
- [PostScript Gradyanı Oluştur – Java'da Radyal Gradyan](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
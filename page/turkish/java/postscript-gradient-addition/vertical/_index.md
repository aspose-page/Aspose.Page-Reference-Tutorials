---
date: 2026-09-14
description: Aspose.Page ile postscript gradient java oluşturmayı öğrenin. Bu adım
  adım rehber, sadece birkaç Java kod satırıyla bir PostScript dosyasına vertical
  gradient eklemeyi gösterir.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Java PostScript'te Vertical Gradient ekle
og_description: Aspose.Page ile postscript gradient java oluşturmayı öğrenin. Bu adım
  adım rehber, sadece birkaç Java kod satırıyla bir PostScript dosyasına vertical
  gradient eklemeyi gösterir.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Postscript gradient java oluşturma – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Postscript gradient java oluşturma – vertical gradient
url: /tr/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript gradyan java oluşturma – dikey gradyan

## Giriş
Aspose.Page for Java, PostScript ve PDF dosyalarını programlı olarak oluşturmayı ve manipüle etmeyi sağlayan bir kütüphanedir. Bu kapsamlı öğreticide, bu kütüphaneyi kullanarak **create postscript gradient java** öğreneceksiniz. Dikey bir gradyan eklemek belgelerinizi daha canlı ve profesyonel gösterir ve sadece birkaç satır kodla çarpıcı görsel efektler elde edebilirsiniz. Her adımı sizinle birlikte inceleyecek, her parçanın neden önemli olduğunu açıklayacak ve yaygın hatalardan kaçınmanız için pratik ipuçları vereceğiz. Bu rehberin sonunda, sorunsuz ve göz alıcı dikey renk geçişlerine sahip PostScript dosyaları oluşturabileceksiniz.

## Hızlı cevaplar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Renkleri özelleştirebilir miyim?** Evet, herhangi bir `java.awt.Color` kullanılabilir  
- **Döndürme destekleniyor mu?** Evet, gradyanı bir `AffineTransform` ile döndürebilirsiniz  
- **Hangi çıktı formatı üretilir?** Standart bir PostScript (.ps) dosyası  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir  

## Neden bir PostScript belgesine dikey gradyan eklenir?
Bir dikey gradyan eklemek sayfalarınıza derinlik kazandırır, görsel hiyerarşiyi iyileştirir ve gradyan vektör biçiminde tanımlandığı için dosya boyutunu düşük tutar; raster görüntüler yerine. Bu teknik, rapor başlıkları, teknik kılavuzlar veya ölçeklenebilirliği kaybetmeden modern bir görünüm gerektiren her türlü broşür için mükemmeldir.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların karşılandığından emin olun:
- Makinenizde yüklü Java Development Kit (JDK).  
- Aspose.Page for Java kütüphanesi. Bunu [Aspose.Page for Java sürüm sayfasından](https://releases.aspose.com/page/java/) indirebilirsiniz.

## Paketleri içe aktar
Java projenizde, başlamak için gerekli paketleri içe aktarın:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Şimdi, dikey bir gradyan ekleme sürecini adım adım inceleyelim.

## PostScript gradyan java nasıl oluşturulur
Java ortamınızı yükleyin, bir `PsSaveOptions` örneği oluşturun ve `Document.save` metodunu çağırın – bu, dikey bir gradyana sahip bir PostScript dosyası oluşturan temel dizidir. API, renk ara değerlemesini, koordinat dönüşümlerini ve sayfa temizlemeyi sizin yerinize yönetir, bu yüzden sadece dikdörtgeni ve gradyan parametrelerini tanımlamaya odaklanmanız yeterlidir.

### Adım 1: belge dizininizi ayarlayın
`File` nesneleri, çıktının yazılacağı klasörü temsil eder. Dizin, akış açılmadan önce mevcut olmalıdır, aksi takdirde bir `IOException` fırlatılır.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Adım 2: PostScript belgesi için çıktı akışı oluşturun
`FileOutputStream` ikili PostScript verisini diske yazar. Bir `try‑with‑resources` bloğu kullanmak, bir istisna oluşsa bile akışın kapatılmasını garanti eder.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Adım 3: A4 boyutunda kaydetme seçenekleri oluşturun
`PsSaveOptions` sayfa boyutunu, DPI'yi ve yazı tiplerinin gömülüp gömülmeyeceğini belirlemenizi sağlar. Boyutu A4 (595 × 842 point) olarak ayarlamak, çoğu yazdırılabilir belgeyle eşleşir.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Adım 4: yeni bir PS belgesi oluşturun
`Document` bellekte tek bir PostScript dosyasını temsil eden üst‑seviye nesnedir. Tüm çizim komutları bu nesne üzerinden yürütülür.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Adım 5: bir dikdörtgen oluşturun
`Rectangle2D.Double` gradyanla doldurulacak alanı tanımlar. Dikdörtgenin koordinatları point biriminde ifade edilir (1 point = 1/72 inç).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Adım 6: gradyan için renkleri ve kesirleri ayarlayın
`float[]` dizisi, her renk durak noktasının konumunu (0.0 ile 1.0 arasında) tanımlar. `Color` nesneleri gerçek RGB değerlerini tutar. İstediğiniz herhangi bir `java.awt.Color` kullanabilirsiniz.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Adım 7: gradyan dönüşümünü oluşturun
`AffineTransform` gradyanı ölçeklendirir ve döndürür. Saf bir dikey gradyan için yalnızca Y‑ekseni ölçeklendirilir; istenirse döndürme daha sonra eklenebilir.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Adım 8: dikey lineer gradyan boyasını oluşturun
`LinearGradientPaint` dikdörtgeni, renk duraklarını ve dönüşümü birleştirir. Bu nesne daha sonra grafik bağlamına aktarılır.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Adım 9: boyayı ayarla ve dikdörtgeni doldur
`Graphics2D.setPaint` gradyanı uygular ve `fill` daha önce tanımladığınız dikdörtgenin içinde render eder.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Adım 10: mevcut sayfayı kapat ve belgeyi kaydet
`document.save` çağrısı, tüm PostScript akışını çıktı dosyasına yazar ve tüm yerel kaynakları serbest bırakır.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Tebrikler! Aspose.Page for Java kullanarak Java PostScript belgenize başarılı bir şekilde dikey bir gradyan eklediniz.

## Yaygın sorunlar ve çözümler
- **Gradyan düz görünüyor:** `AffineTransform` ölçeklemesinin dikdörtgen boyutlarıyla eşleştiğinden emin olun.  
- **Renkler soluk görünüyor:** Doğru `ColorSpaceType` (SRGB) kullandığınızı ve kesir dizisinin 0.0'dan 1.0'a sıralandığını doğrulayın.  
- **Dosya oluşturulmadı:** Çıktı dizininin (`dataDir`) mevcut olduğunu ve uygulamanın yazma izinlerine sahip olduğunu kontrol edin.  

## Sıkça sorulan sorular

**Q: Aspose.Page for Java'yi diğer Java kütüphaneleriyle kullanabilir miyim?**  
A: Evet, Aspose.Page for Java, Apache Commons veya Spring gibi diğer Java kütüphaneleriyle sorunsuz çalışacak şekilde tasarlanmıştır.

**Q: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
A: Evet, ücretsiz bir deneme alabilirsiniz [ücretsiz deneme indirme sayfası](https://releases.aspose.com/).

**Q: Ek belgeleri nerede bulabilirim?**  
A: Detaylı dokümantasyon [Aspose.Page Java API referansı](https://reference.aspose.com/page/java/) adresinde mevcuttur.

**Q: Aspose.Page for Java'yi nasıl satın alabilirim?**  
A: Aspose.Page for Java'yi [Aspose.Page satın alma sayfası](https://purchase.aspose.com/buy) adresinden satın alabilirsiniz.

**Q: Aspose.Page tartışmaları için bir forum var mı?**  
A: Evet, topluluk forumuna [Aspose.Page topluluk forumu](https://forum.aspose.com/c/page/39) adresinden katılabilirsiniz.

## Ek sıkça sorulan sorular

**Q: Başka gradyan yönleri (yatay, diyagonal) oluşturabilir miyim?**  
A: Kesinlikle. `LinearGradientPaint` içindeki başlangıç ve bitiş noktalarını ayarlayın ve `AffineTransform` içindeki döndürme açısını değiştirin.

**Q: Bu PDF çıktısı için de çalışır mı?**  
A: Aynı gradyan mantığı, `PsSaveOptions` yerine `PdfSaveOptions` kullanarak PDF'ye kaydederken uygulanabilir.

**Q: Gradyan boyutunu dinamik olarak nasıl değiştiririm?**  
A: Çalışma zamanında dikdörtgen boyutlarını hesaplayın ve bu değerleri hem `Rectangle2D` hem de `AffineTransform` yapıcılarına iletin.

---

**Son Güncelleme:** 2026-09-14  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11 (latest)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Page for Java ile PostScript'te Radial Gradyan Oluşturma](/page/java/postscript-gradient-addition/)
- [Aspose.Page Java API kullanarak PostScript'i PDF'ye nasıl dönüştürülür](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page Şeffaflık Öğreticisi – Java PostScript'te Şeffaflık Ekleme](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-04
description: Aspose.Page Java ile Java PostScript'te gradient eklemeyi öğrenin, LinearGradientPaint
  kullanarak diyagonal renk geçişleri oluşturarak canlı belgeler üretin.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Nasıl gradient eklenir: Aspose.Page Java kullanarak Java PostScript''te
  diyagonal gradient'
og_description: Aspose.Page Java kullanarak Java PostScript'te gradient eklemeyi öğrenin.
  Bu kılavuz, sadece birkaç adımda LinearGradientPaint ile diyagonal bir gradient
  oluşturmayı gösterir.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Aspose.Page Java ile Java PostScript'te gradient ekleme
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Nasıl gradient eklenir: Aspose.Page Java kullanarak Java PostScript''te diyagonal
  gradient'
url: /tr/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Aspose.Page Java ile diyagonal degrade ekleme

## Giriş
Eğer bir PostScript dosyasını yumuşak bir diyagonal renk geçişiyle zenginleştirmek istiyorsanız, **Aspose.Page Java** bunu şaşırtıcı derecede kolaylaştırıyor. Bu öğreticide, Java 2D'den `LinearGradientPaint` sınıfını kullanarak **degrade eklemeyi** adım adım öğreneceksiniz. Sonunda, canlı bir diyagonal degrade oluşturan ve çalıştırılmaya hazır bir kod parçacığına sahip olacaksınız ve bu yaklaşımın ham PostScript komutlarını elle kodlamaktan daha sürdürülebilir olduğunu anlayacaksınız.

## Java PostScript'te degrade ekleme
Degrade eklemek sadece grafikle ilgili bir görev gibi görünebilir, ancak Aspose.Page ile saf Java içinde kalırken temel PostScript komutları üzerinde tam kontrol elde edersiniz. Bu bölüm, yaklaşımın neden işe yaradığını ve ham PostScript'i elle kodlamaya kıyasla ne gibi avantajlar sağladığını açıklar.

## Hızlı cevaplar
- **Hangi kütüphane gereklidir?** Aspose.Page for Java.  
- **Hangi sınıf degrade oluşturur?** `LinearGradientPaint`.  
- **Renkleri değiştirebilir miyim?** Evet – `Color[]` dizisini değiştirin.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz deneme mevcuttur.  
- **Uygulama ne kadar sürer?** Temel bir degrade için yaklaşık 10 dakika.

## Aspose.Page Java nedir?
Aspose.Page Java, geliştiricilerin dış bir yazılım kullanmadan PostScript ve PDF dosyalarını oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan tam özellikli bir API'dir. Kütüphane **50+ giriş ve çıkış formatını** destekler ve **500+ sayfa** içeren belgeleri işleyebilirken bellek kullanımını 100 MB'nin altında tutar.

## Neden diyagonal degrade kullanmalı?
Diyagonal bir degrade, grafikler, afişler veya modern bir görünüme ihtiyaç duyan herhangi bir grafik öğeye derinlik ve görsel ilgi katar. Degrade bir köşeden karşı köşeye aktığı için arka planlar, düğme görünümleri ve dekoratif şekiller için çok uygundur; ekstra görüntü varlıkları olmadan profesyonel bir bitiş sağlar.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- Java Development Kit (JDK) 8 ve üzeri.  
- Eclipse, IntelliJ IDEA veya VS Code gibi bir IDE.  
- **Aspose.Page for Java** kütüphanesi – en son sürümü [resmi indirme sayfasından](https://releases.aspose.com/page/java/) indirin.

## Paketleri içe aktar
`java.awt` paketi temel grafik sınıflarını sağlar, `com.aspose.page` paketi ise PostScript‑özel API'lerine erişim sunar.

`LinearGradientPaint` sınıfı, Aspose.Page'in Java 2D degrade işlevselliğine köprüsüdür.  
`AffineTransform`, degradeyi döndürüp ölçeklendirerek diyagonal hizalanmasını sağlar.

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

## Adım 1: PostScript belgesi için çıktı akışı oluşturma
İlk olarak, dosyanın kaydedileceği klasörü tanımlayın ve bir `FileOutputStream` açın. Bu akış, oluşturulan PostScript verilerini alır.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Adım 2: A4 boyutunda kaydetme seçenekleri oluşturma
`PsSaveOptions`, sayfa boyutu, çözünürlük ve diğer çıktı ayarlarını belirlemenizi sağlar. Burada varsayılan A4 boyutunu kullanıyoruz; bu, 72 dpi'de 595 × 842 nokta anlamına gelir.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Adım 3: Yeni PS belgesi oluşturma
`PsDocument` sınıfı bir PostScript belgesini temsil eder ve sayfa oluşturma ve grafik çizme yöntemleri sunar.  
Çıktı akışı ve kaydetme seçeneklerini kullanarak bir `PsDocument` örneği oluşturun. `false` bayrağı, yapıcıya otomatik olarak yeni bir sayfa açmamasını söyler – bunu daha sonra yapacağız.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 4: Bir dikdörtgen oluşturma
Degrade doldurmasını alacak dikdörtgeni tanımlayın. Dikdörtgenin konumu (200, 100) ve boyutu (200 × 100), degradeyi net bir şekilde görebilmek için seçilmiştir.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Adım 5: Degrade dönüşümü oluşturma
`AffineTransform`, degradeyi dikdörtgen boyunca diyagonal olarak çalışacak şekilde döndürmemizi, ölçeklendirmemizi ve çevirmemizi sağlar. Aşağıdaki matematik, hipotenüsü hesaplar ve ölçek oranını buna göre ayarlar.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Adım 6: Diyagonal lineer degrade boyası oluşturma
`LinearGradientPaint`, renk geçişini oluşturan temel sınıftır. Önceden tanımlanan dönüşümü kullanarak, dikdörtgenin sol‑üst köşesinden sağ‑alt köşesine uzanır. `MultipleGradientPaint.CycleMethod.NO_CYCLE`, degradeyin tekrarlanmamasını sağlar.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Adım 7: Boyayı ayarla ve dikdörtgeni doldur
Degrade boyasını belgeye uygulayın ve dikdörtgen şekliyle doldurun. Bu adım, diyagonal renk geçişini PostScript sayfasına çizer.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Adım 8: Mevcut sayfayı kapat ve belgeyi kaydet
Son olarak, sayfayı kapatın, akışı boşaltın ve dosyayı kaydedin. Oluşan `DiagonalGradient_outPS.ps` dosyası herhangi bir PostScript görüntüleyici ile açılabilir.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Yaygın sorunlar ve ipuçları
- **Degrade düz görünüyor** – dönüş açıını iki kez kontrol edin; 45° dönüş gerçek bir diyagonal oluşturur.  
- **Renkler soluk görünüyor** – doğru renk işleme için `MultipleGradientPaint.ColorSpaceType.SRGB` kullandığınızdan emin olun.  
- **Dosya bulunamadı hatası** – `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanın yazma iznine sahip olduğunu doğrulayın.  
- **Büyük belgeler bellek dalgalanmalarına neden olur** – bellek kullanımını azaltmak için `PsSaveOptions.setCompress(true)` kullanın.

## Sıkça sorulan sorular

**S: Bu kütüphaneyi Java'da diğer grafik işlemleri için kullanabilir miyim?**  
C: Evet, Aspose.Page for Java, tam bir çizim ilkel seti, metin renderleme ve görüntü işleme yetenekleri sunar.

**S: Aspose.Page Java için ücretsiz bir deneme mevcut mu?**  
C: Kesinlikle. Tam işlevsel bir denemeyi [Aspose ücretsiz deneme sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Page Java için belgeleri nerede bulabilirim?**  
C: Resmi API referansı [Aspose.Page Java API referansı](https://reference.aspose.com/page/java/) adresinde mevcuttur.

**S: Aspose.Page Java için lisans nasıl satın alınır?**  
C: Lisanslar doğrudan [Aspose satın alma portalından](https://purchase.aspose.com/buy) alınabilir.

**S: Yardıma mı ihtiyacınız var ya da sorularınız mı var?**  
C: Aspose mühendisleri ve diğer geliştiricilerden yardım almak için topluluk tarafından yürütülen [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

---

**Son Güncelleme:** 2026-09-04  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (latest)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Page for Java ile PostScript'te Radial Degrade Oluşturma](/page/java/postscript-gradient-addition/)
- [Java PostScript'te Linear Gradient Paint ile Degrade Nasıl Eklenir](/page/java/postscript-gradient-addition/horizontal/)
- [Java'da PostScript Degrade Oluşturma – Dikey Degrade Ekle](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-09-09
description: Aspose.Page kullanarak Java PostScript'te radial gradient nasıl oluşturulacağını
  öğrenin. Bu adım adım rehber, bir color stops gradient eklemeyi, radii ayarlamayı
  ve PS dosyasını hızlı bir şekilde oluşturmayı gösterir.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Java'da radial gradient'lerde ustalaşma
og_description: Aspose.Page kullanarak Java PostScript'te radial gradient nasıl oluşturulacağını
  öğrenin. Bu rehber, color stops gradient eklemeyi, radii ayarlamayı ve PS dosyasını
  dakikalar içinde oluşturmayı açıklar.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Java PostScript'te radial gradient nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Java PostScript'te radial gradient nasıl oluşturulur
url: /tr/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Aspose.Page ile radyal degrade nasıl oluşturulur

## Giriş
Eğer bir PostScript dosyası içinde **radyal degrade oluşturmak** istiyorsanız, doğru yerdesiniz. Bu öğreticide, **Aspose.Page for Java** kullanarak pürüzsüz bir radyal degrade içeren bir PostScript belgesi oluşturmak için gereken tüm adımları adım adım inceleyeceğiz. Sonunda API'yi anlayacak, tam çalışan bir örnek görecek ve herhangi bir tasarım senaryosu için renkleri, konumları ve yarıçapları nasıl ayarlayacağınızı bileceksiniz.

## Hızlı cevaplar
- **PostScript'te radyal degrade oluşturan kütüphane hangisidir?** Aspose.Page for Java.  
- **Uygulamanın süresi ne kadardır?** Temel bir örnek için yaklaşık 10‑15 dakika.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Degrade şeklini değiştirebilir miyim?** Evet – `RadialGradientPaint` yapıcısında yarıçapı ve merkez noktasını ayarlayın.

## Java'da radyal degrade nasıl oluşturulur
Java projenizi yükleyin, gerekli sınıfları içe aktarın ve aşağıdaki adım adım kılavuzu izleyin. Temel cevap, renk duraklarınızla bir `RadialGradientPaint` örneği oluşturup bunu bir `PsDocument` üzerine çizilen bir dikdörtgene uygulamaktır. Bu iki nesne yaklaşımı, tüm düşük seviyeli PostScript komutlarını sizin için yönetir.

## Radyal degrade nedir?
`RadialGradientPaint`, merkezi bir noktadan dışa doğru dairesel bir renk geçişi tanımlayan bir Java AWT sınıfıdır. Birden fazla renk duraklarının pürüzsüz bir karışımını oluşturur ve bu da spot ışıkları, yumuşak arka planlar veya renklerin bir odak noktasından yayıldığı herhangi bir etki için idealdir.

## Radyal degrade için neden Aspose.Page kullanmalı?
Aspose.Page, düşük seviyeli PS sözdiziminin zorluğunu hallederken PostScript çıktısı üzerinde tam programatik kontrol sağlar. **50+ giriş ve çıkış formatını** destekler, tüm dosyayı belleğe yüklemeden çok sayfalı belgeleri işleyebilir ve Java 8+ destekleyen herhangi bir işletim sisteminde çalışır. Bu ölçülebilir yetenek, kurumsal düzeyde grafik üretimi için güvenilir bir seçim olmasını sağlar.

## Önkoşullar
- **Java Development Kit (JDK) 8+** – `java -version` ile doğrulayın.  
- **Aspose.Page for Java** – resmi [Aspose.Page download page](https://releases.aspose.com/page/java/) adresinden en son JAR'ı indirin.  
- **IDE of your choice** – Eclipse, IntelliJ IDEA veya Java uzantılarına sahip VS Code.  
- **A writable folder** – oluşturulan `.ps` dosyasının kaydedileceği yazılabilir bir klasör.

## Paketleri içe aktar
İlk olarak, ihtiyacımız olan sınıfları içe aktaralım. `java.awt` paketi degrade boya nesnelerini sağlarken, `com.aspose.eps` PostScript belge işleme sınıflarını içerir.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım adım kılavuz

### Adım 1: bir dikdörtgen oluştur ve bir PS belgesi aç
`PsDocument`, bir PostScript belgesini temsil eden ve şekil, metin ve görüntü çizmeye yarayan yöntemler sağlayan Aspose.Page sınıfıdır. Öncelikle bir çıktı akışı oluşturur, sayfa boyutunu (varsayılan olarak A4) yapılandırır ve degrade barındıracak bir dikdörtgen tanımlarız.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** Dikdörtgenin koordinatlarını (`200, 100, 200, 200`) ayarlayarak degradeyi sayfanın istediğiniz yerine konumlandırabilirsiniz.

### Adım 2: renkleri ve kesirleri tanımla
Radyal degrade, *renk duraklarından* (renkler) ve *kesirlerden* (bu durakların göreli konumları) oluşur. Burada altı renk ve bunlara karşılık gelen kesirleri içeren bir dizi oluşturuyoruz.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Neden önemli:** `fractions` değerlerini ayarlayarak renk geçişlerinin ne kadar hızlı gerçekleşeceğini kontrol eder, ince ya da dramatik etkiler elde edersiniz.

### Adım 3: radyal degrade boyası oluştur
`RadialGradientPaint`, merkez noktası, yarıçap, odak noktası, kesirler, renkler, döngü yöntemi ve renk uzayı dahil olmak üzere radyal bir renk degrade tanımlayan temel sınıftır. Şimdi yukarıda tanımlanan dizileri kullanarak `RadialGradientPaint` nesnesini oluşturuyoruz.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Not:** Ek ölçekleme veya döndürme ihtiyacınız yoksa `transform` `null` olabilir. Eğik degradeler için `AffineTransform` ile denemeler yapmaktan çekinmeyin.

### Adım 4: boyayı ayarla ve dikdörtgeni doldur
Boyama hazır olduğunda, `PsDocument`'e bunu kullanmasını söyler ve ardından önceden tanımladığımız dikdörtgeni doldururuz.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Bu noktada PostScript sayfası, yapılandırdığınız radyal degrade ile pürüzsüz bir şekilde doldurulmuş bir dikdörtgen içerir.

### Adım 5: belgeyi kapat ve kaydet
Son olarak, mevcut sayfayı kapatıp dosyayı diske yazarız.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` dosyasını herhangi bir PostScript görüntüleyicide (ör. Ghostscript) açın ve degradeyi tanımlandığı gibi render edilmiş olarak göreceksiniz.

## Yaygın sorunlar ve çözümler
| Semptom | Muhtemel neden | Çözüm |
|---------|----------------|-------|
| Gradient appears as a solid color | `fractions` array does not start at `0.0f` or end at `1.0f` | Ensure the first fraction is `0.0f` and the last is `1.0f`. |
| Colors look washed out | Using the wrong `ColorSpaceType` | Switch to `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` for more vibrant output. |
| No output file generated | `FileOutputStream` path is invalid or not writable | Verify `dataDir` exists and the application has write permissions. |

## Sıkça sorulan sorular

**S: Aspose.Page for Java'ı ticari projelerde kullanabilir miyim?**  
C: Evet. Üretim kullanımı için ticari bir lisans gereklidir. Bunu [Aspose lisans sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Resmi API referansını nerede bulabilirim?**  
C: Tam dokümantasyon [Aspose.Page Java API referansı](https://reference.aspose.com/page/java/) adresinde mevcuttur.

**S: Test için ücretsiz deneme sürümü mevcut mu?**  
C: Kesinlikle. [Aspose.Page sürüm sayfasından](https://releases.aspose.com/) bir deneme sürümü indirebilirsiniz.

**S: Değerlendirme için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisans, [geçici lisans talep sayfasından](https://purchase.aspose.com/temporary-license/) istenebilir.

**S: Topluluk desteğini nereden alabilirim?**  
C: Aspose.Page topluluk forumuna [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39) adresinden katılabilirsiniz.

## Sonuç
Artık Aspose.Page kullanarak bir Java PostScript belgesinde **radyal degrade nasıl oluşturulur** biliyorsunuz. Dikdörtgen boyutunu, renk duraklarını ve degrade yarıçapını ayarlayarak sayısız görsel etki yaratabilirsiniz—hafif arka plan doldurmalarından cesur spot ışığı grafiklerine kadar. Farklı `AffineTransform` değerleriyle degradeyi döndürmek veya eğmek için deney yapmaktan çekinmeyin ve bu tekniği metin ve görüntülerle birleştirerek daha zengin PDF veya EPS çıktıları elde edin.

---

**Son Güncelleme:** 2026-09-09  
**Test Edilen Versiyon:** Aspose.Page for Java en son (yazım tarihi itibarıyla)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Degrade ile Şekil Doldurma: Java PostScript Radyal Örnek](/page/java/postscript-gradient-addition/radial2/)
- [Java’da PostScript Degrade Oluşturma – Dikey Degrade Ekle](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Şeffaflık Öğreticisi – Java PostScript’te Şeffaflık Ekle](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-10-31
description: Aspose.Page kullanarak Java PostScript'te paint color ayarlamayı ve ellipse
  doldurmayı öğrenin. Bu kılavuz, ellipse doldurmayı, ellipse konturunu çizmeyi ve
  stroke thickness'i net kod adımlarıyla nasıl ayarlayacağınızı gösterir.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Java PostScript'te Ellipse Ekle
og_description: Aspose.Page kullanarak Java PostScript'te ellipse doldurma ve paint
  color ayarlamayı öğrenin. Saniyeler içinde doldurulmuş ve konturlu ellipses çizmek
  için adım adım kodu izleyin.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Java PostScript'te ellipse doldurma ve paint color ayarlama
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Java PostScript'te ellipse doldurma ve paint color ayarlama
url: /tr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te elips doldurma ve boya rengini ayarlama

## Giriş
Vektör grafikleri çizerken **boya rengini ayarlamanız** gerekiyorsa, Aspose.Page for Java kütüphanesi her bir çizgi ve doldurma üzerinde tam kontrol sağlar. Bu öğreticide **boya rengini ayarlamayı**, **elips doldurmayı** ve **elips ana hatını çizmeyi** basit, adım adım bir yaklaşımla keşfedeceksiniz. Sonunda, faturalar, raporlar veya herhangi bir yazdırılabilir belgeye yüksek kaliteli PostScript elipsleri ekleyebileceksiniz.

## Hızlı cevaplar
- **Java'da PostScript grafikleri çizmek için en iyi kütüphane hangisidir?** Aspose.Page for Java.  
- **Bir elipsi katı bir renk ile doldurabilir miyim?** Evet – `fill`'den önce `document.setPaint(Color.YOUR_COLOR)` kullanın.  
- **Sadece bir elipsin ana hatını nasıl çizerim?** Boya ve çizgi kalınlığını ayarlayın, ardından `document.draw(...)` çağırın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; test için geçici bir lisans mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Şu anki Aspose.Page sürümüyle herhangi bir Java 8+ çalışma zamanı çalışır.

## PostScript elipsi nedir?
PostScript elipsi, sınırlayıcı bir dikdörtgenle tanımlanan bir vektör şeklidir. Raster görüntülerden farklı olarak kalite kaybı olmadan ölçeklenir, bu da yüksek çözünürlüklü baskı ve PDF dönüşümü için idealdir. Şekil matematiksel olarak tanımlandığı için, keskin kenarları ve pürüzsüz eğrileri koruyarak herhangi bir boyut veya çözünürlükte render edilebilir.

## PostScript elipsi oluşturmak için neden Aspose.Page kullanmalı?
Aspose.Page, her bir çizim ilkeline deterministik kontrol sağlar. **3 ana işletim sistemini (Windows, Linux, macOS)**, **0 yerel bağımlılığı** destekler ve tipik bir sunucuda saniyede **50+ vektör ilkel** render edebilir. Kütüphane saf Java'dır, bu yüzden ek yerel kütüphaneler olmadan herhangi bir Java 8+ uygulamasına gömebilirsiniz.

## Önkoşullar
Başlamadan önce şunların olduğundan emin olun:

1. Fonksiyonel bir Java geliştirme ortamı (JDK 8 veya daha yeni).  
2. Projenize eklenmiş Aspose.Page for Java kütüphanesi. **[Aspose.Page for Java sürüm sayfasından](https://releases.aspose.com/page/java/)** indirebilirsiniz.  

## Paketleri içe aktar
Java kaynak dosyanızda, PostScript içeriğini çizmek ve kaydetmek için gereken sınıfları içe aktarın.

`java.awt` paketi, `Color`, `Ellipse2D` ve `BasicStroke` gibi temel grafik türlerini sağlar. `com.aspose.page` paketi ise PostScript çıktısı yazan `PsDocument` sınıfını sunar.

- **`Color`** – boyama için kullanılan bir sRGB rengi temsil eder.  
- **`Ellipse2D`** – sınırlayıcı bir dikdörtgenle tanımlanan bir elips şekli tanımlar.  
- **`BasicStroke`** – ana hatları çizerken çizgi kalınlığını, kesikli deseni ve uç kapak stilini belirler.  
- **`PsDocument`** – bir PostScript belgesini temsil eder ve grafik çizmeye ve sayfaları yönetmeye yönelik yöntemler sunar.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bir elips için boya rengini nasıl ayarlarsınız
İlk adım, belgeye bir sonraki çizim işlemi için hangi rengin kullanılacağını söylemektir. `setPaint` yöntemi, sonraki çağrıya bağlı olarak doldurma ya da çizgiye uygulanacak katı bir rengi ayarlar.

### Adım 1: PostScript belgesini kurun
Bir çıktı akışı oluşturun, sayfa boyutunu yapılandırın ve bir `PsDocument` örneği başlatın.

`PsDocument`, bellekte bir PostScript dosyasını temsil eden temel sınıftır. Tüm çizim komutları bu nesne üzerinden yönlendirilir ve sayfa düzeni, kaynak yönetimi ve nihai dosya üretimini yönetir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Adım 2: Elipsi doldurun – set paint rengini kullanın
**Elipsi doldurmak** için, önce istediğiniz doldurma rengiyle `setPaint` çağırmalı, ardından bir `Ellipse2D` örneğiyle `fill` metodunu çalıştırmalısınız.

`setPaint` sonraki doldurma veya çizgi işlemleri için kullanılan mevcut çizim rengini ayarlar.  
`Ellipse2D` elipsin geometrik sınırlarını tanımlar; yapıcı, sol üst köşenin X‑Y koordinatlarını ve genişlik‑yüksekliği alır.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Adım 3: Elipsin ana hatını çizin ve çizgi kalınlığını ayarlayın
Doldurmanın ardından, boyayı farklı bir renge değiştirebilir, çizgi kalınlığını kontrol etmek için bir `BasicStroke` tanımlayabilir ve elipsin ana hatını çizebilirsiniz.

`BasicStroke` ana hatları çizerken çizgi kalınlığını, kesikli deseni ve uç kapak stilini belirler. `width` özelliğini ayarlayarak elips kenarının ne kadar kalın görüneceğini kontrol edersiniz.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Adım 4: Belgeyi kapatın ve kaydedin
Sayfayı sonlandırın ve PostScript dosyasını diske yazın.

`document.close()` çağrısı bekleyen tüm çizim komutlarını temizler ve kaynakları serbest bırakır. Ortaya çıkan `.ps` dosyası herhangi bir PostScript görüntüleyiciyle açılabilir veya PDF'ye dönüştürülebilir.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Artık içinde iki elips bulunan bir PostScript dosyanız var—biri turuncu ile doldurulmuş, diğeri kırmızıyla ana hatlandırılmış. Tasarım ihtiyaçlarınıza uygun farklı koordinatlar, boyutlar ve renklerle denemeler yapmaktan çekinmeyin.

## Yaygın tuzaklar ve sorun giderme
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Lisans eksik** – Geçerli bir lisans olmadan, kütüphane değerlendirme modunda çalışır ve filigran ekleyebilir.  
- **Renk uygulanmadı** – `document.setPaint(...)`'i her `fill` veya `draw` çağrısından *önce* ayarlamayı unutmayın; boya ayarı ayrı işlemler arasında otomatik olarak kalıcı değildir.

## Sıkça sorulan sorular

**S: Aspose.Page for Java'yı diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Page for Java, diğer Java kütüphaneleriyle sorunsuz entegrasyon için tasarlanmıştır.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Test amaçlı bir geçici lisans **[Aspose geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/)** elde edebilirsiniz.

**S: Aspose.Page ticari projeler için uygun mu?**  
C: Kesinlikle! Ticari kullanım için lisans seçeneklerini keşfetmek üzere **[Aspose satın alma sayfasını](https://purchase.aspose.com/buy)** ziyaret edin.

**S: Aspose.Page ile ilgili sorular için nereden yardım alabilir veya tartışma yapabilirim?**  
C: Tartışmalar ve destek için **[Aspose.Page Forumuna](https://forum.aspose.com/c/page/39)** katılın.

**S: Aspose.Page for Java hakkında daha fazla öğrenmek için ücretsiz kaynaklar var mı?**  
C: **[Aspose ücretsiz deneme sayfasını](https://releases.aspose.com/)** kullanın ve belgelerdeki örnekleri keşfedin.

## Sonuç
Aspose.Page for Java, **boya rengini ayarlamayı**, **elips doldurmayı** ve **elips ana hatını çizmeyi**—basit bir doldurulmuş şekil ya da karmaşık bir çizgi grafiği ihtiyacınız olsun—kolaylaştırır. Yukarıdaki adımlarla herhangi bir yazdırılabilir belgeye profesyonel düzeyde vektör grafikleri hızlıca ekleyebilirsiniz. Daha derin keşifler için—örneğin birden fazla şekli birleştirme, degrade uygulama veya PDF'ye dönüştürme—resmi **[Aspose.Page Java belgelerine](https://reference.aspose.com/page/java/)** bakın.

---

**Son Güncelleme:** 2026-10-31  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java PostScript'te Aspose.Page ile Dikdörtgen Çizme](/page/java/postscript-shapes/add-rectangle/)
- [Java PostScript'te Aspose.Page ile Unicode Metin Ekleme](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Java için Aspose.Page ile PostScript'te Radial Gradient Oluşturma](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
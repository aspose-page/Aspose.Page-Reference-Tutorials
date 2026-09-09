---
date: 2026-09-09
description: Java PostScript'te gradient oluşturmayı ve Aspose.Page kullanarak şekle
  gradient eklemeyi öğrenin. Kod ve ipuçlarıyla adım adım bu rehberi izleyin.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Aspose.Page ile Java PostScript Radial Gradient
og_description: Java PostScript'te gradient oluşturmayı ve Aspose.Page kullanarak
  şekle gradient eklemeyi öğrenin. Kod ve ipuçlarıyla adım adım bu rehberi izleyin.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Java PostScript'te radial fill ile gradient nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Java PostScript'te radial fill ile gradient nasıl oluşturulur
url: /tr/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te radyal dolgu ile degrade nasıl oluşturulur

## Giriş
Bu öğreticide Java ve Aspose.Page kullanarak bir PostScript belgesinde **degrade nasıl oluşturulacağını** öğreneceksiniz. Proje kurulumundan pürüzsüz bir radyal degrade ile doldurulmuş bir daireyi render etmeye kadar her adımı adım adım göstereceğiz; böylece **şekle degrade ekleyebilir** ve Java uygulamalarınızın görsel kalitesini anında artırabilirsiniz.

## Hızlı cevaplar
- **Bu öğretici ne oluşturur?** Radyal degrade ile doldurulmuş bir daire içeren bir PostScript dosyası (`.ps`).
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (en son sürüm).
- **Uygulamanın süresi ne kadar?** Çalışan bir örnek için yaklaşık 10‑15 dakika.
- **Lisans gerekli mi?** Üretim kullanımı için geçici veya tam lisans gerekir; geliştirme için ücretsiz deneme sürümü çalışır.
- **Kodu PDF veya SVG için yeniden kullanabilir miyim?** Evet—Aspose.Page, minimal değişikliklerle birden fazla çıktı formatını destekler.

## PostScript'te şekle degrade nasıl uygulanır
PostScript'te bir şekli radyal degrade ile doldurmak için bir `PsDocument` oluşturur, bir `RadialGradientPaint` tanımlar, hedef şekle uygular ve son olarak belgeyi kaydedersiniz. Bu özlü iş akışı, raster görüntüler olmadan profesyonel görünümlü vektör grafikler üretmenizi sağlar ve aynı kod PDF veya SVG çıktısı için yeniden kullanılabilir. İşlem basittir ve tüm desteklenen formatlarda tutarlı çalışır.

## Radyal degrade nedir?
Radyal degrade, renkleri merkezi bir noktadan dışa doğru geçiş yaparak pürüzsüz, dairesel bir karışım oluşturur. Vurgular, düğme arka planları veya doğal bir “parıltı” etkisi gerektiren herhangi bir görsel için idealdir. Renk duraklarını ve yarıçapı değiştirerek, aydınlatma, derinlik ve malzeme özelliklerini saf vektör biçiminde simüle edebilirsiniz.

## Neden Aspose.Page'i radyal degradeler için kullanmalısınız?
Aspose.Page, tek bir Java API'si ile cihaz bağımsız vektör grafikler oluşturmanıza olanak tanır. PostScript, PDF ve SVG dahil olmak üzere 50'den fazla giriş ve çıkış formatını destekler; renk doğruluğunu ve yüksek çözünürlüklü çıktılar için anti-aliasing'i korur. Kütüphane ayrıca kullanımı kolay degrade sınıfları sunar, böylece karmaşık görsel efektleri basitçe uygulayabilirsiniz.

## Önkoşullar
- Java programlamaya temel aşinalık.  
- Makinenizde JDK 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Page for Java kütüphanesi (indir: [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).

## Paketleri içe aktar
İlk olarak, ihtiyacımız olan sınıfları içe aktarın. Bunlar standart AWT grafik tiplerini ve Aspose.Page API'sini içerir.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: belge dizinini ayarla
Oluşturulan PostScript dosyasının kaydedileceği klasörü tanımlayın. Yer tutucuyu sisteminizdeki gerçek bir yol ile değiştirin.

```java
String dataDir = "Your Document Directory";
```

## Adım 2: çıktı akışı oluştur
FileOutputStream, ham baytları bir dosyaya yazar ve ikili verilerin kaydedilmesini sağlar. `.ps` dosyasına yönelik bir akış açmak, Aspose.Page'in oluşturulan PostScript verilerini doğrudan diske akıtmasına izin verir.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Adım 3: kaydetme seçeneklerini oluştur
PsSaveOptions, bir PostScript dosyasının nasıl kaydedileceğini yapılandırır; sayfa boyutu ve sıkıştırma gibi ayarları içerir. Bu ayarları özelleştirebilirsiniz, ancak bu örnek için varsayılanlar yeterlidir.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Adım 4: ps belgesi oluştur
PsDocument, bellekte bir PostScript belgesini temsil eder ve sayfa ve grafik eklemek için yöntemler sunar.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 5: bir daire oluştur
`Ellipse2D.Float`, bir elips şekli tanımlar; genişlik = yükseklik olduğunda mükemmel bir daire olur. Bu nesne, degrade doldurmamız için bir tuval görevi görecektir.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Daireyi degrade ile nasıl çizersiniz
Radyal degrade ile bir daire çizmek için, bir `RadialGradientPaint`'i grafik bağlamına yüklersiniz ve ardından önceden tanımlanmış elipsi doldurursunuz. Bu tek işlem, şekli merkezden dışa doğru pürüzsüz bir renk geçişiyle boyar ve görsel olarak çekici bir etki oluşturur.

## Adım 6: degrade renklerini tanımla
İki dizi hazırlayın: birincisi degrade içinde görünecek renkler için, ikincisi ise karşılık gelen kesirli konumlar (0 = merkez, 1 = kenar) için.

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Adım 7: affinetransform oluştur
AffineTransform, grafik nesnelerini çevirebilen, döndürebilen, ölçekleyebilen veya kaydırabilen bir matristir. Burada, degradeyi ölçeklendirir ve çevirir, böylece daireye tam olarak sığar.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Adım 8: radyal degrade boyası oluştur
RadialGradientPaint, bir merkez nokta, yarıçap ve renk duraklarına dayalı radyal renk degradesi oluşturur.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Adım 9: boya ayarla ve daireyi doldur
Degrade boyasını belgeye uygulayın ve önceden tanımlanmış daireyi doldurun. Bu, **radyal degrade örneğimizin** çekirdeğidir ve **şekle degrade nasıl doldurulur** gösterir.

```java
document.setPaint(paint);
document.fill(circle);
```

## Adım 10: sayfayı kapat ve belgeyi kaydet
Sayfayı sonlandırın, içeriği diske yazın ve akışı kapatın. PostScript dosyanız artık herhangi bir PS görüntüleyiciyle görüntülenmeye hazır.

```java
document.closePage();
document.save();
```

Tebrikler! Aspose.Page kullanarak Java PostScript'te bir radyal degrade örneği başarıyla oluşturdunuz. Artık **şekle degrade doldurma** için yeniden kullanılabilir bir deseniniz var; bu desen diğer şekillere ve çıktı formatlarına uyarlanabilir.

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|---------|----------|
| **FileNotFoundException** çıktısı akışı açarken | `dataDir`'in mevcut bir klasöre işaret ettiğini ve yazma izninizin olduğunu doğrulayın. |
| Degrade düz veya eksik görünüyor | `fractions` dizisinin `colors` dizisi uzunluğuyla eşleştiğinden ve `AffineTransform`'in doğru ölçeklendiğinden emin olun. |
| Renkler ters görünüyor | `colors` dizisindeki renk sırasını değiştirin veya `focus` nokta koordinatlarını ayarlayın. |

## Sıkça sorulan sorular

**Q:** Aspose.Page for Java belgelerini nerede bulabilirim?  
A: Tam API referansı [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/) adresinde mevcuttur.

**Q:** Aspose.Page for Java'ı nasıl indirebilirim?  
A: En son JAR dosyasını [releases page](https://releases.aspose.com/page/java/) adresinden edinin.

**Q:** Ücretsiz deneme sürümü mevcut mu?  
A: Evet—[Aspose free trial download page](https://releases.aspose.com/) adresinden bir deneme sürümü indirin.

**Q:** Test için geçici bir lisans alabilir miyim?  
A: Kesinlikle, [temporary license page](https://purchase.aspose.com/temporary-license/) adresinden bir tane isteyin.

**Q:** Topluluk desteğini nereden alabilirim?  
A: Tartışmaya [Aspose.Page forum](https://forum.aspose.com/c/page/39) üzerinden katılın.

## Sonuç
Bu rehberde Aspose.Page for Java kullanarak bir PostScript belgesi için tam bir **radyal degrade örneği** oluşturduk. Adımları izleyerek artık **şekle degrade doldurma** için yeniden kullanılabilir bir deseniniz var; bu deseni PDF, SVG veya Aspose.Page'in desteklediği diğer formatlara uyarlayabilirsiniz. Farklı renkler, yarıçaplar ve şekillerle deney yaparak Java grafik projelerinizi zenginleştirin.

---

**Son Güncelleme:** 2026-09-09  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java'da PostScript Degrade Oluştur – Dikey Degrade Ekle](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page for Java ile PostScript'te Doku Deseni Oluştur](/page/java/postscript-texture-patterns/)
- [Aspose.Page Şeffaflık Öğreticisi – Java PostScript'te Şeffaflık Ekle](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
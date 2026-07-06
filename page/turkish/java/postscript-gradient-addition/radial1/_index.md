---
date: 2026-02-13
description: Aspose.Page for Java kullanarak radyal renk duraklarıyla PostScript gradyanı
  nasıl oluşturacağınızı öğrenin. Bu adım adım kılavuz, belgelerinize renk durakları
  gradyanı eklemenizi gösterir.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: PostScript Gradyanı Oluştur – Java'da Radyal Gradyan
url: /tr/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Aspose.Page ile Radial Gradient Nasıl Eklenir

## Giriş
Eğer **PostScript gradient** oluşturmanız gerektiğinde pürüzsüz ve göz alıcı bir renk geçişi istiyorsanız, radial gradient eklemeyi öğrenmek başlamak için mükemmel bir yerdir. Bu öğreticide, **Aspose.Page for Java** kütüphanesini kullanarak güzel bir radial gradient içeren bir PostScript dosyası üretmek için gereken tüm adımları adım adım göstereceğiz. Sonunda API'yi anlayacak, tam çalışan bir örnek görecek ve renkleri, konumları ve yarıçapları istediğiniz tasarıma göre nasıl ayarlayacağınızı öğreneceksiniz.

## Hızlı Yanıtlar
- **PostScript'te radial gradient oluşturan kütüphane nedir?** Aspose.Page for Java.  
- **Uygulamanın süresi ne kadar?** Temel bir örnek için yaklaşık 10‑15 dakika.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Gradient'in şeklini değiştirebilir miyim?** Evet – `RadialGradientPaint` yapıcısında yarıçapı ve merkez noktasını ayarlayarak.

## Radial Doldurma ile PostScript Gradient Nasıl Oluşturulur
Aşağıda, radial doldurma kullanarak **PostScript gradient** içeriği oluşturmanın tam olarak nasıl yapılacağını gösteren kısa ve adım adım bir rehber bulacaksınız. Her adım kısa bir açıklama ve ardından (değiştirilmemiş) orijinal kod bloğu içerir.

## Radial Gradient Nedir?
Radial gradient, renkleri merkezi bir noktadan dışa doğru yayarak, kenarlara doğru yavaşça karıştıran bir boyamadır. Lineer gradientlerin aksine, renk geçişi dairesel (veya eliptik) bir desen izler; bu da vurgular, spot ışıklar veya yumuşak arka plan doldurmaları için idealdir.

## Neden Aspose.Page'i Radial Gradientler İçin Kullanmalısınız?
- **PostScript çıktısı üzerinde tam kontrol** – düşük seviyeli PS komutlarını elle yazmaya gerek yok.  
- **Çapraz platform** – Java çalıştıran herhangi bir işletim sisteminde çalışır.  
- **Zengin renk yönetimi** – birden fazla renk durağı, farklı renk uzayları ve döngü yöntemlerini destekler.  
- **Entegrasyona hazır** – metin, resim ve vektör şekilleri gibi diğer Aspose.Page özellikleriyle birleştirilebilir.

## Önkoşullar
Kodun içine dalmadan önce aşağıdakilerin hazır olduğundan emin olun:

- **Java Development Kit (JDK) 8+** – `java -version` ile doğrulayın.  
- **Aspose.Page for Java** – resmi [Aspose.Page indirme sayfasından](https://releases.aspose.com/page/java/) en son JAR'ı indirin.  
- **Tercih ettiğiniz IDE** – Eclipse, IntelliJ IDEA veya Java uzantılarına sahip VS Code.  
- **Yazılabilir bir klasör** – oluşturulan `.ps` dosyasının kaydedileceği yer.

## Paketleri İçe Aktarma
İhtiyacımız olan sınıfları önce içe aktaralım. `java.awt` paketi gradient boya nesnelerini sağlarken, `com.aspose.eps` PostScript belge işleme sınıflarını içerir.

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

## Adım‑Adım Kılavuz

### Adım 1: Bir Dikdörtgen Oluşturun ve PS Belgesi Açın
Bir çıktı akışı oluşturuyor, sayfa boyutunu (varsayılan A4) yapılandırıyor ve gradient'i barındıracak bir dikdörtgen tanımlıyoruz.

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

> **Pro ipucu:** Gradient'i sayfanın istediğiniz yerine konumlandırmak için dikdörtgenin koordinatlarını (`200, 100, 200, 200`) ayarlayın.

### Adım 2: Renkleri ve Kesirleri Tanımlayın
Radial gradient, *color stops* (renkler) ve *fractions* (bu durakların göreli konumları) ile oluşturulur. Burada altı renk ve bunlara karşılık gelen kesirleri içeren bir dizi oluşturuyoruz.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Neden önemli:** `fractions` değerlerini ayarlayarak renk geçişinin hızını kontrol eder, ince ya da dramatik etkiler elde edersiniz.

Radial Doldurmanıza Renk Durağı Gradient'i Eklemek  
Renk durakları gradient'i **add color stops gradient** eklemeniz gerektiğinde `colors` ve `fractions` dizileri anahtar rol oynar. Görsel tasarımınıza uygun şekilde öğeleri yeniden sıralamaktan, eklemekten veya kaldırmaktan çekinmeyin.

### Adım 3: Radial Gradient Paint Oluşturun
Şimdi `RadialGradientPaint` nesnesini oluşturuyoruz. Yapıcı, gradient'in merkez noktası, yarıçap, odak noktası, kesirler, renkler, döngü yöntemi, renk uzayı ve isteğe bağlı bir dönüşüm alır.

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

> **Not:** `transform` ek ölçekleme veya döndürme ihtiyacınız yoksa `null` olabilir. Eğik gradientler için `AffineTransform` ile denemeler yapabilirsiniz.

### Adım 4: Boyayı Ayarlayın ve Dikdörtgeni Doldurun
Boyamız hazır olduğunda, `PsDocument`'e bunu kullanmasını söyler ve daha önce tanımladığımız dikdörtgeni doldururuz.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Bu noktada PostScript sayfası, yapılandırdığımız radial gradient ile sorunsuz bir şekilde doldurulmuş bir dikdörtgen içerir.

### Adım 5: Belgeyi Kapatın ve Kaydedin
Son olarak mevcut sayfayı kapatır ve dosyayı diske yazarız.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` dosyasını herhangi bir PostScript görüntüleyicide (ör. Ghostscript) açın; gradient'in tam olarak tanımlandığı gibi render edildiğini göreceksiniz.

## Yaygın Sorunlar ve Çözümler
| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| Gradient tek renk gibi görünüyor | `fractions` dizisi `0.0f` ile başlamıyor ya da `1.0f` ile bitmiyor | İlk kesirin `0.0f`, sonuncusunun ise `1.0f` olduğundan emin olun. |
| Renkler soluk görünüyor | `ColorSpaceType`'ın yanlış kullanılması | Daha canlı çıktı için `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB`'ye geçin. |
| Çıktı dosyası oluşturulmadı | `FileOutputStream` yolu geçersiz ya da yazılabilir değil | `dataDir`'in mevcut olduğunu ve uygulamanın yazma iznine sahip olduğunu doğrulayın. |

## Sıkça Sorulan Sorular

**Q: Aspose.Page for Java'yi ticari projelerde kullanabilir miyim?**  
A: Evet. Üretim kullanımı için ticari bir lisans gereklidir. Lisansı [Aspose lisans sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Q: Resmi API referansını nereden bulabilirim?**  
A: Tam dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

**Q: Test için ücretsiz bir deneme sürümü var mı?**  
A: Kesinlikle. Deneme sürümünü [Aspose.Page releases sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**Q: Değerlendirme için geçici bir lisans nasıl alınır?**  
A: Geçici lisans [buradan](https://purchase.aspose.com/temporary-license/) talep edilebilir.

**Q: Topluluk desteği nereden alınır?**  
A: Aspose.Page topluluk forumuna [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39) adresinden katılabilirsiniz.

## Sonuç
Artık Aspose.Page kullanarak Java PostScript belgesine **radial gradient eklemeyi** biliyorsunuz. Dikdörtgen boyutunu, renk duraklarını ve gradient yarıçapını ayarlayarak sayısız görsel etki yaratabilirsiniz – ince arka plan doldurmalarından cesur spot ışık grafiklerine kadar. Farklı `AffineTransform` değerleriyle gradient'i döndürmek veya eğmek için deney yapmaktan çekinmeyin ve bu tekniği metin ve resimlerle birleştirerek daha zengin PDF veya EPS çıktıları elde edin.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen:** Aspose.Page for Java latest (as of writing)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
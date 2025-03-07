---
title: Java PostScript'te Çapraz Degrade Ekleme
linktitle: Java PostScript'te Çapraz Degrade Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java'yı kullanarak Java PostScript belgelerinizi diyagonal degradelerle geliştirin. Zahmetsizce canlı renk geçişleri eklemek için adım adım kılavuzumuzu izleyin.
weight: 10
url: /tr/java/postscript-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Çapraz Degrade Ekleme

## giriiş
Aspose.Page for Java'yı kullanarak Java PostScript'te çapraz degrade eklemeye ilişkin adım adım kılavuzumuza hoş geldiniz. Bu eğitimde, her örneği birden çok adıma bölerek süreç boyunca size yol göstereceğiz. Uzman bir SEO yazarı olarak içeriğin yalnızca bilgilendirici olmasını değil aynı zamanda arama motorları için optimize edilmesini sağlayarak geliştiricilerin ve meraklıların takip etmesini kolaylaştıracağım.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Eclipse veya IntelliJ gibi Entegre Geliştirme Ortamı (IDE).
-  Aspose.Page Java kütüphanesi için. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).
## Paketleri İçe Aktar
Başlamak için Java projenizde gerekli paketleri içe aktarın:
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
## 1. Adım: PostScript Belgesi için Çıktı Akışı Oluşturun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## 2. Adım: A4 Boyutunda Kaydetme Seçenekleri Oluşturun
```java
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
```
## 3. Adım: Yeni PS Belgesi Oluşturun
```java
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Adım 4: Bir Dikdörtgen Oluşturun
```java
//Bir dikdörtgen oluştur
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Adım 5: Degrade Dönüşümü Oluşturun
```java
//Degrade dönüşümünü oluşturun. Ölçek bileşenleri dikdörtgenin genişliğine ve yüksekliğine eşit olmalıdır.
// Çeviri bileşenleri dikdörtgenin uzaklıklarıdır.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Degradeyi döndürün, ardından görünür renk geçişi için ölçekleyin ve çevirin
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## Adım 6: Çapraz Doğrusal Degrade Boya Oluşturun
```java
// Çapraz doğrusal degrade boya oluşturma
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## Adım 7: Boyayı Ayarlayın ve Dikdörtgeni Doldurun
```java
// Boyayı ayarlayın ve dikdörtgeni doldurun
document.setPaint(paint);
document.fill(rectangle);
```
## Adım 8: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin
```java
// Geçerli sayfayı kapatın ve belgeyi kaydedin
document.closePage();
document.save();
```
Bu adımları izleyerek Aspose.Page for Java'yı kullanarak Java PostScript'te başarılı bir şekilde çapraz degrade ekleyeceksiniz.
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript belgelerinizi çapraz geçişlerle nasıl geliştireceğinizi öğrendiniz. Benzersiz görsel efektler elde etmek için farklı parametrelerle denemeler yapın.
## Sıkça Sorulan Sorular
### S: Bu kitaplığı Java'daki diğer grafik işlemleri için kullanabilir miyim?
C: Evet, Aspose.Page for Java, PostScript ve diğer grafik öğeleriyle çalışmak için çeşitli özellikler sağlar.
### S: Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Page for Java belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### S: Aspose.Page for Java lisansını nasıl satın alabilirim?
 C: Lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### S: Yardıma mı ihtiyacınız var veya sorularınız mı var?
 C: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

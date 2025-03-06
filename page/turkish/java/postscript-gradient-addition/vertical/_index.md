---
title: Java PostScript'te Dikey Degrade Ekleme
linktitle: Java PostScript'te Dikey Degrade Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile Java PostScript'te dikey degradeler eklemeye yönelik adım adım kılavuzu keşfedin. Canlı görsellerle belgelerinizi zahmetsizce geliştirin.
weight: 14
url: /tr/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Dikey Degrade Ekleme

## giriiş
Aspose.Page for Java kullanarak Java PostScript'te dikey degrade eklemeyi anlatan bu adım adım kılavuza hoş geldiniz. Belgenizi göz alıcı degradelerle geliştirmek istiyorsanız bu eğitim tam size göre. Aspose.Page for Java, PostScript belgelerini sorunsuz bir şekilde işlemek için güçlü araçlar sağlar.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
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
Şimdi Java PostScript'te dikey degrade ekleme işlemini birden çok adıma ayıralım.
## 1. Adım: Belge Dizininizi Kurun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun
```java
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## 3. Adım: A4 Boyutunda Kaydetme Seçenekleri Oluşturun
```java
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
```
## 4. Adım: Yeni Bir PS Belgesi Oluşturun
```java
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Adım 5: Bir Dikdörtgen Oluşturun
```java
//Bir dikdörtgen oluştur
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Adım 6: Degrade için Renkleri ve Kesirleri Ayarlayın
```java
// Degrade için renk ve kesir dizileri oluşturun.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Adım 7: Degrade Dönüşümünü Oluşturun
```java
// Degrade dönüşümünü oluşturun. Dönüşümdeki ölçek bileşenleri dikdörtgenin genişliğine ve yüksekliğine eşit olmalıdır.
// Çeviri bileşenleri dikdörtgenin uzaklıklarıdır.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Degradeyi bir başlangıç noktası etrafında 90 derece döndürün
transform.rotate(90 * (Math.PI / 180));
```
## Adım 8: Dikey Doğrusal Degrade Boya Oluşturun
```java
// Dikey doğrusal degrade boya oluşturun.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Adım 9: Boyayı Ayarlayın ve Dikdörtgeni Doldurun
```java
// Boyayı ayarla
document.setPaint(paint);
// Dikdörtgeni doldur
document.fill(rectangle);
```
## Adım 10: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin
```java
// Geçerli sayfayı kapat
document.closePage();
// Belgeyi kaydet
document.save();
```
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript belgenize başarılı bir şekilde dikey degrade eklediniz.
## Çözüm
Bu eğitimde Aspose.Page for Java'yı kullanarak belgelerinizi canlı dikey degradelerle geliştirme sürecini inceledik. Artık çarpıcı görseller ekleyerek belge düzenlemelerinizi bir sonraki seviyeye taşıyabilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?
Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz çalışacak şekilde tasarlanmıştır.
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### Ek belgeleri nerede bulabilirim?
 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page for Java'yı nasıl satın alabilirim?
 Java için Aspose.Page'i satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### Aspose.Page tartışmaları için bir forum var mı?
 Evet, topluluk forumuna katılabilirsiniz[Burada](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

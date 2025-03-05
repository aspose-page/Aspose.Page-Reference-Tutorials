---
title: Aspose.Page ile Java PostScript Radyal Degrade
linktitle: Aspose.Page ile Java PostScript Radyal Degrade
second_title: Aspose.Page Java API'si
description: Java uygulamalarınızda göz kamaştırıcı grafikler elde etmek için Aspose.Page'i kullanarak Java PostScript'e Radyal Degrade eklemeye yönelik adım adım kılavuzu keşfedin.
type: docs
weight: 13
url: /tr/java/postscript-gradient-addition/radial2/
---
## giriiş
Aspose.Page for Java'yı kullanarak Java PostScript'e Radyal Gradient 2 eklemeye ilişkin adım adım kılavuzumuza hoş geldiniz. Bu eğitim, güzel bir radyal degradeye sahip bir PostScript belgesi oluşturma sürecinde size yol gösterecek ve Java uygulamalarınızı görsel olarak çekici grafiklerle geliştirecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java programlama konusunda çalışma bilgisi.
- Makinenize Java Development Kit'i (JDK) yüklediniz.
-  Aspose.Page for Java kütüphanesini şu adresten indirebilirsiniz:[Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/).
## Paketleri İçe Aktar
Aspose.Page için gerekli paketleri Java projenize aktarın:
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
## 1. Adım: Belge Dizinini Ayarlayın
Belge dizininizin yolunu tanımlayın:
```java
String dataDir = "Your Document Directory";
```
## 2. Adım: Çıktı Akışı Oluşturun
PostScript belgesi için bir çıktı akışı oluşturun:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## 3. Adım: Kaydetme Seçenekleri Oluşturun
A4 boyutunda kaydetme seçenekleri oluşturun:
```java
PsSaveOptions options = new PsSaveOptions();
```
## 4. Adım: PS Belgesi Oluşturun
Açılan sayfayla yeni bir PS Belgesi oluşturun:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 5. Adım: Bir Çevre Oluşturun
Ellipse2D.Float sınıfını kullanarak bir daire tanımlayın:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Adım 6: Degrade Renkleri Tanımlayın
Radyal degrade için renk ve kesir dizileri oluşturun:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Adım 7: AffineTransform'u oluşturun
Radyal degrade için bir AffinTransform oluşturun:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Adım 8: Radyal Degrade Boya Oluşturun
Belirtilen parametrelerle bir RadialGradientPaint oluşturun:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Adım 9: Boya ve Dolgu Çemberini Ayarlayın
Boyayı ayarlayın ve daireyi radyal degradeyle doldurun:
```java
document.setPaint(paint);
document.fill(circle);
```
## Adım 10: Sayfayı Kapatın ve Belgeyi Kaydedin
Geçerli sayfayı kapatın ve belgeyi kaydedin:
```java
document.closePage();
document.save();
```
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript'e Radial Gradient 2'yi başarıyla eklediniz.
## Çözüm
Bu eğitimde, Java uygulamalarınızı PostScript belgelerindeki radyal degradelerle nasıl geliştirebileceğinizi araştırdık. Aspose.Page for Java, çarpıcı grafikler oluşturmak için güçlü bir araç seti sunarak Java projelerinizi bir sonraki seviyeye taşımanıza olanak tanır.
## SSS
### S: Aspose.Page for Java belgelerini nerede bulabilirim?
 C: Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### S: Aspose.Page for Java'yı nasıl indirebilirim?
 Cevap: Buradan indirebilirsiniz.[sürümler sayfası](https://releases.aspose.com/page/java/).
### S: Ücretsiz deneme mevcut mu?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Page for Java için geçici bir lisans alabilir miyim?
 C: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Topluluk desteğini nereden alabilirim ve tartışmalara nerede katılabilirim?
 C: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39).
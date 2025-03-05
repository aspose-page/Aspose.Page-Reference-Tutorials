---
title: Java PostScript'te Yatay Degrade Ekleme
linktitle: Java PostScript'te Yatay Degrade Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile Java PostScript'te nasıl yatay degrade ekleyeceğinizi öğrenin. Zahmetsizce görsel olarak etkileyici belgeler oluşturun.
type: docs
weight: 11
url: /tr/java/postscript-gradient-addition/horizontal/
---
## giriiş
Aspose.Page for Java'yı kullanarak Java PostScript'te yatay degrade eklemeyle ilgili bu kapsamlı eğitime hoş geldiniz. Aspose.Page, geliştiricilerin PostScript ve diğer belge formatlarıyla çalışmasına olanak tanıyan güçlü bir Java kütüphanesidir. Bu eğitimde, adım adım örnekler kullanarak yatay degradeli bir PostScript belgesi oluşturma sürecinde size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.Page Java kütüphanesi için. adresinden indirebilirsiniz.[Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/).
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. Bu paketler Aspose.Page ile çalışmak için çok önemlidir.
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
## 1. Adım: Bir Dikdörtgen Oluşturun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PostScript belgesi için çıktı akışı oluşturun
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
// Sayfa açıkken yeni PS Belgesi oluşturun
PsDocument document = new PsDocument(outPsStream, options, false);
//Bir dikdörtgen oluştur
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Adım 2: Yatay Doğrusal Degrade Boya Oluşturun
```java
// Yatay doğrusal degrade boya oluşturun. Dönüşümdeki ölçek bileşenleri dikdörtgenin genişliğine ve yüksekliğine eşit olmalıdır.
// Çeviri bileşenleri dikdörtgenin uzaklıklarıdır.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Boyayı ayarla
document.setPaint(paint);
```
## Adım 3: Dikdörtgeni Doldurun
```java
// Dikdörtgeni doldur
document.fill(rectangle);
```
## Adım 4: Bir Metni Degradeyle Doldurun
```java
// Bir metni degradeyle doldurma
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Adım 5: Bir Metni Degradeyle Konturlayın
```java
// Metni degradeyle konturlama
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak Java PostScript'te başarılı bir şekilde yatay degrade eklediniz. Bu eğitimde, görsel olarak çekici PostScript belgeleri oluşturmanıza yardımcı olacak ayrıntılı, adım adım bir kılavuz sağlanmıştır.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı ticari projelerde kullanabilir miyim?
Evet, Aspose.Page for Java ticari projelerde kullanılabilir. Lisans ayrıntıları için şu adresi ziyaret edin:[Aspose.Satın Alma](https://purchase.aspose.com/buy).
### Ücretsiz deneme mevcut mu?
 Evet, Aspose.Page for Java'nın ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Ek belgeleri ve desteği nerede bulabilirim?
 Ziyaret edin[Aspose.Page Java belgeleri](https://reference.aspose.com/page/java/) kapsamlı kaynaklar için. Topluluk desteği için şurayı kontrol edin:[Aspose.Page forumu](https://forum.aspose.com/c/page/39).
### Geçici lisansı nasıl alabilirim?
 adresinden geçici lisans alabilirsiniz.[Aspose.Satın Alma](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java'nın sistem gereksinimleri nelerdir?
 Bakın[dokümantasyon](https://reference.aspose.com/page/java/) ayrıntılı sistem gereksinimleri için.
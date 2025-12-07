---
date: 2025-12-07
description: Java PostScript'te Linear Gradient Paint Java kullanarak Aspose.Page
  for Java ile yatay bir degrade eklemeyi öğrenin.
language: tr
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Java PostScript'te Linear Gradient Paint kullanarak Gradient ekle
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Linear Gradient Paint Java Kullanarak Degrade Ekleme

## Giriş
Bu kapsamlı öğreticide, **Linear Gradient Paint Java** kullanarak bir PostScript belgesinde güzel bir yatay degrade oluşturmayı öğreneceksiniz. Aspose.Page for Java, PostScript, PDF ve diğer vektör formatlarıyla çalışmayı kolaylaştırır ve `LinearGradientPaint` sınıfı renk geçişleri üzerinde ince ayar yapmanızı sağlar. Bu rehberin sonunda, şekiller **ve** metin üzerinde degrade render edebilecek, belgelerinize profesyonel ve göz alıcı bir görünüm kazandırabileceksiniz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java (Linear Gradient Paint Java destekler).  
- **Uygulama ne kadar sürer?** Temel bir degrade için yaklaşık 10‑15 dakika.  
- **Lisans gerekli mi?** Üretim kullanımı için geçici ya da tam lisans gereklidir.  
- **Hangi JDK sürümü çalışır?** Java 8 ve üzeri.  
- **Degradeyi hem şekillerde hem de metinde kullanabilir miyim?** Evet – aynı degradeyi şekilleri doldurmak ve metni doldurmak ya da kontur çizmek için kullanabilirsiniz.

## Önkoşullar
Kodlamaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde Java Development Kit (JDK) kurulu.  
- Aspose.Page for Java kütüphanesi. İndirilebilir: [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Paketleri İçe Aktarma
Java projenizde gerekli paketleri içe aktararak başlayın. Bu importlar, grafik primitive'lerine, degrade işleme ve Aspose.Page API'sine erişim sağlar.

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

## Adım 1: Bir Dikdörtgen Oluşturma
İlk olarak çıktı akışını, belgeyi ve degradeyi barındıracak bir dikdörtgeni ayarlayın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Adım 2: Yatay Linear Gradient Paint Oluşturma
Burada, yatay bir renk geçişi tanımlayan **Linear Gradient Paint Java** nesnesini oluşturuyoruz. `AffineTransform`, degradeyi dikdörtgenin genişliği ve yüksekliğiyle eşleşecek şekilde ölçeklendirir.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Adım 3: Dikdörtgeni Doldurma
Şimdi, az önce tanımladığımız degradeyi kullanarak dikdörtgeni dolduralım.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Adım 4: Metni Degrade ile Doldurma
Aynı degradeyi metne de uygulayabilir, çarpıcı bir görsel etki yaratabilirsiniz.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Adım 5: Metni Degrade ile Çizme
Son olarak, metnin konturunu degradeyi renk olarak kullanarak çizin.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Yaygın Sorunlar ve Çözümleri
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| Degrade uzatılmış görünüyor | Yanlış `AffineTransform` ölçeklendirmesi | Dönüşümün genişlik ve yüksekliğinin dikdörtgenin boyutlarıyla (örnekte 200 × 100) eşleştiğinden emin olun. |
| Renkler soluk görünüyor | Alfa değerleri çok düşük ayarlanmış | Alfa bileşenini artırın (`new Color(r,g,b,alpha)` içindeki dördüncü değer). |
| Metin görünmüyor | Metin çizmeye başlamadan önce boya (paint) ayarlanmamış | `document.setPaint(paint)` metodunu **herhangi bir** `fillAndStrokeText` veya `outlineText` çağrısından **önce** çağırın. |

## Sıkça Sorulan Sorular
### Aspose.Page for Java'ı ticari projelerde kullanabilir miyim?
Evet, Aspose.Page for Java ticari projelerde kullanılabilir. Lisans detayları için [Aspose.Purchase](https://purchase.aspose.com/buy) sayfasını ziyaret edin.

### Ücretsiz deneme mevcut mu?
Evet, Aspose.Page for Java için ücretsiz deneme sürümüne [burada](https://releases.aspose.com/) ulaşabilirsiniz.

### Ek belge ve destek nereden bulunur?
Kapsamlı kaynaklar için [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) sayfasına bakın. Topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini kontrol edin.

### Geçici bir lisans nasıl alınır?
Geçici lisansı [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) üzerinden temin edebilirsiniz.

### Aspose.Page for Java için sistem gereksinimleri nelerdir?
Detaylı sistem gereksinimleri için [documentation](https://reference.aspose.com/page/java/) sayfasına bakın.

---

**Son Güncelleme:** 2025-12-07  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
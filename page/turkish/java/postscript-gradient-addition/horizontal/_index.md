---
date: 2026-02-13
description: Aspose.Page for Java ile Linear Gradient Paint Java kullanarak Java PostScript'e
  nasıl degrade ekleyeceğinizi öğrenin.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Java PostScript'te Lineer Gradient Paint ile Gradyan Nasıl Eklenir
url: /tr/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Linear Gradient Paint ile Degrade Nasıl Eklenir

## Giriş
Bu kapsamlı öğreticide Java kullanarak bir PostScript belgesine **degrade eklemenin** nasıl yapılacağını keşfedeceksiniz. **Linear Gradient Paint Java** sınıfını kullanarak güzel bir yatay degrade oluşturmayı adım adım göstereceğiz; bu sınıf renk geçişleri üzerinde piksel‑tam kontrol sağlar. Aspose.Page for Java ile hem şekillerde **hem** metinde degrade render edebilir, belgelerinize göz alıcı, profesyonel bir görünüm kazandırabilirsiniz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java (Linear Gradient Paint Java'ı destekler).  
- **Uygulama ne kadar sürer?** Temel bir degrade için yaklaşık 10‑15 dakika.  
- **Lisans gerekiyor mu?** Üretim kullanımı için geçici veya tam lisans gereklidir.  
- **Hangi JDK sürümü çalışır?** Java 8 veya daha yeni.  
- **Degradeyi hem şekillerde hem de metinde kullanabilir miyim?** Evet – aynı degradeyi şekilleri doldurmak ve metni çizgiyle (stroke) ya da doldurmak için kullanabilirsiniz.

## Yatay Degrade Nedir ve Neden Kullanılır?
Yatay degrade, bir şekil veya metin üzerinde renkleri soldan sağa sorunsuz bir şekilde karıştırır. Modern UI öğeleri, vurgulanan başlıklar veya raporlardaki hafif arka plan efektleri oluşturmak için idealdir. **Linear Gradient Paint Java** kullanarak başlangıç ve bitiş renklerini, opaklığı ve ölçeklemeyi tam olarak tanımlayabilir, böylece sonuç herhangi bir cihazda net görünür.

## Önkoşullar
Koda başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde yüklü Java Development Kit (JDK).  
- Aspose.Page for Java kütüphanesi. Bunu [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.

## Paketleri İçe Aktarma
Java projenizde gerekli paketleri içe aktararak başlayın. Bu importlar grafik primitive'lerine, degrade işleme ve Aspose.Page API'sine erişim sağlar.

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

## Adım 1: Bir Dikdörtgen Oluşturun
İlk olarak, çıktı akışını, belgeyi ve degradeyi barındıracak bir dikdörtgeni ayarlayın.

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

## Adım 2: Yatay Linear Gradient Paint Oluşturun
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

## Adım 3: Dikdörtgeni Doldurun
Şimdi, az önce tanımladığımız degrade ile dikdörtgeni doldurun.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Adım 4: Metni Degrade ile Doldurun
Aynı degradeyi metne de uygulayabilir, çarpıcı bir görsel etki yaratabilirsiniz.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Adım 5: Metni Degrade ile Çizgiyle Çizin
Son olarak, metni degradeyi çizgi (stroke) rengi olarak kullanarak konturlayın.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Yaygın Sorunlar ve Çözümleri
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| Degrade uzatılmış görünüyor | Yanlış `AffineTransform` ölçeklemesi | Transformun genişlik ve yüksekliğinin dikdörtgenin boyutlarıyla (örnekte 200 × 100) eşleştiğinden emin olun. |
| Renkler soluk görünüyor | Alfa değerleri çok düşük ayarlanmış | `new Color(r,g,b,alpha)` içindeki alfa bileşenini artırın. |
| Metin görünmüyor | Metin çizmeye başlamadan önce boya (paint) ayarlanmamış | `document.setPaint(paint)` **herhangi bir** `fillAndStrokeText` veya `outlineText` çağrısından **önce** çağırın. |

## Sık Sorulan Sorular
**S:** Aspose.Page for Java'ı ticari projelerde kullanabilir miyim?  
**C:** Evet, Aspose.Page for Java ticari projelerde kullanılabilir. Lisans detayları için [Aspose.Purchase](https://purchase.aspose.com/buy) adresini ziyaret edin.

**S:** Ücretsiz deneme mevcut mu?  
**C:** Evet, Aspose.Page for Java için ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S:** Ek belge ve destek nereden bulunur?  
**C:** Kapsamlı kaynaklar için [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) adresini ziyaret edin. Topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresine bakın.

**S:** Geçici bir lisans nasıl alabilirim?  
**C:** Geçici lisansı [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) adresinden alabilirsiniz.

**S:** Aspose.Page for Java için sistem gereksinimleri nelerdir?  
**C:** Ayrıntılı sistem gereksinimleri için [documentation](https://reference.aspose.com/page/java/) adresine bakın.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen Sürüm:** Aspose.Page for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
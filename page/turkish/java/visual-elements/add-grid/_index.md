---
date: 2026-03-05
description: Java'da Aspose.Page ile Visual Brush kullanarak ızgara eklemeyi öğrenin.
  Belge görsellerini zahmetsizce geliştirmek için adım adım rehberi izleyin.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Java'da Görsel Fırça Kullanarak Izgara Nasıl Eklenir
url: /tr/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Visual Brush Kullanarak Izgara Ekleme

## Giriş
Java ile oluşturulan belgelerinize **izgara ekleme** öğeleri eklemek istiyorsanız, Aspose.Page'in Visual Brush özelliği bunu şaşırtıcı derecede basit hale getirir. Bu öğreticide her adımı adım adım gösterecek, Visual Brush'ın ızgara desenleri için neden ideal olduğunu açıklayacak ve size eksiksiz, çalıştırılabilir bir örnek sunacağız.

## Hızlı Yanıtlar
- **Visual Brush nedir?** Alanı doldurmak için döşenebilen veya gerilebilir yeniden kullanılabilir bir görsel öğe.  
- **Neden ızgara kullanılır?** Izgaralar, düzenleri yapılandırmaya, arka plan desenleri oluşturmaya veya XPS belgelerinde bölümleri vurgulamaya yardımcı olur.  
- **Önkoşullar?** Java JDK, Aspose.Page for Java ve Java grafiklerine temel bir anlayış.  
- **Uygulama ne kadar sürer?** Kütüphane kurulduktan sonra yaklaşık 10‑15 dakika.  
- **Renkleri özelleştirebilir miyim?** Evet – doldurma renklerini, opaklığı ve döşeme boyutunu doğrudan kod içinde kontrol edebilirsiniz.

## Izgara Eklemek İçin Visual Brush Neden Kullanılır?
Visual Brush, küçük bir görseli ("döşeme") bir kez tanımlamanıza ve ardından bunu herhangi bir şekil üzerinde tekrarlamanıza olanak tanır. Bu yaklaşım bellek açısından verimlidir ve aynı deseni birden fazla kanvasa uygulamanız gerektiğinde kodunuzu temiz tutar.

## Önkoşullar
Koda geçmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamaya temel bir anlayış.  
- Aspose.Page kütüphanesi yüklü. Bunu [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.  
- Makinenizde Java Development Kit (JDK) yüklü.

## Paketleri İçe Aktarma
Java projenizde gerekli paketlerin içe aktarıldığından emin olun:
```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

### Adım 1: Projenizi Kurun
İlk olarak, bir `XpsDocument` örneği oluşturun ve çıktının kaydedileceği klasöre işaret edin.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Adım 2: Magenta Izgara Visual Brush Oluşturun
Tekrarlanacak küçük bir magenta döşeme oluşturuyoruz. Yol geometrisi, döşemenin şeklini tanımlar.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Adım 3: Magenta Izgara Visual Brush için Geometri Tanımlayın
Burada, döşeme fırçasının uygulanacağı alanı tanımlıyoruz.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Adım 4: Yeni Bir Kanvas Oluşturun
Belgeye yeni bir kanvas eklenir ve ızgaranın istenen konumda görünmesi için bir çeviri dönüşümü uygulanır.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Adım 5: Kanvasa Izgara Ekleyin
Şimdi visual brush'ı geometriye bağlayıp döşeme modunu ayarlıyoruz.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Adım 6: Kırmızı Şeffaf Dikdörtgen Ekleyin
Katmanlamayı göstermek için, ızgaranın üzerine yarı şeffaf kırmızı bir dikdörtgen yerleştiriyoruz.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Adım 7: Oluşan XPS Belgesini Kaydedin
Son olarak, XPS dosyasını diske yazın.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Bu adımları izleyerek, Aspose.Page ile Java uygulamanıza görsel olarak çekici bir ızgara ekleyebilirsiniz.

## Yaygın Kullanım Senaryoları
- **Rapor arka planları:** Finansal veya mühendislik raporlarına daha iyi okunabilirlik için ince ızgara desenleri ekleyin.  
- **Tasarım şablonları:** Aynı ızgaranın birden fazla sayfada tekrar ettiği yeniden kullanılabilir sayfa şablonları oluşturun.  
- **Bölümleri vurgulama:** Belirli belge alanlarına dikkat çekmek için renkli ızgaralar ekleyin.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Izgara uzatılmış görünüyor** | `TileMode`'un `XpsTileMode.Tile` olarak ayarlandığını ve kaynak ile hedef dikdörtgenlerin aynı boyutta olduğunu doğrulayın. |
| **Renkler doğru görünmüyor** | Katı renk fırçası oluştururken (`createColor(alpha, red, green, blue)`) doğru RGBA değerlerini kullandığınızdan emin olun. |
| **Belge kaydedilmiyor** | `dataDir`'in var olan yazılabilir bir klasöre işaret ettiğini ve dosya sistemi izinlerinizin uygun olduğunu kontrol edin. |

## Sonuç
Tebrikler! Aspose.Page'in Visual Brush özelliğini kullanarak Java'da **ızgara ekleme** öğelerini nasıl ekleyeceğinizi öğrendiniz. Bu teknik, desen render'ı üzerinde ayrıntılı kontrol sağlar ve kodunuzu temiz ve sürdürülebilir tutar.

## Sıkça Sorulan Sorular
### Aspose.Page profesyonel belge oluşturma için uygun mu?
Evet, Aspose.Page, Java'da profesyonel belge oluşturma için tasarlanmış sağlam bir kütüphanedir.

### Visual Brush kullanarak ızgara renklerini özelleştirebilir miyim?
Kesinlikle! Visual Brush, çeşitli renklerle boyama imkanı sunar ve özelleştirme konusunda esneklik sağlar.

### Aspose.Page için ek destek nereden bulunur?
Topluluk desteği ve tartışmalar için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### Aspose.Page için ücretsiz deneme mevcut mu?
Evet, Aspose.Page'in özelliklerini keşfetmek için [ücretsiz deneme](https://releases.aspose.com/) sürümüne erişebilirsiniz.

### Aspose.Page için geçici lisans nasıl alınır?
Test amaçlı bir [geçici lisans](https://purchase.aspose.com/temporary-license/) edinin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-05  
**Test Edilen:** Aspose.Page for Java (en son sürüm)  
**Yazar:** Aspose
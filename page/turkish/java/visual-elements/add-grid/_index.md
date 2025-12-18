---
date: 2025-12-18
description: Aspose.Page ile Java XPS belgelerine ızgara eklemeyi ve şeffaf dikdörtgen
  eklemeyi öğrenin. XPS belgesini verimli bir şekilde kaydetmek için adım adım rehber.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Java'da Görsel Fırça Kullanarak Izgara Nasıl Eklenir
url: /tr/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Visual Brush ile Grid Ekleme

## Giriş
Java ile oluşturulan XPS belgelerinize **grid ekleme** yöntemini arıyorsanız doğru yerdesiniz. Bu öğreticide Visual Brush kullanarak bir grid eklemeyi, üzerine şeffaf bir dikdörtgen katmanlamayı ve son olarak Aspose.Page Java API'si ile **XPS belgesini kaydetmeyi** adım adım göstereceğiz. Sonunda raporlar, faturalar veya belge ağırlıklı herhangi bir uygulamada yeniden kullanılabilecek şık bir görsel elde edeceksiniz.

## Hızlı Yanıtlar
- **Visual Brush ne işe yarar?** Tanımlı bir alanı yeniden kullanılabilir görsel içerikle doldurur; grid gibi tekrarlayan desenler için mükemmeldir.  
- **Grid rengini değiştirebilir miyim?** Evet – fırçanın solid‑color ayarlarını değiştirin.  
- **Grid'in üzerine şeffaf bir dikdörtgen nasıl eklenir?** Katı renk ile doldurulmuş bir yolun `setOpacity` metodunu kullanın.  
- **Dosyayı kaydeden yöntem hangisidir?** `doc.save(...)` XPS dosyasını diske yazar.  
- **Lisans gerekli mi?** Üretim kullanımında geçici veya tam lisans gereklidir.

## Visual Brush Grid Nedir?
Visual Brush, küçük bir görsel (grid deseni) tanımlamanıza ve bunu daha büyük bir alana döşemenize olanak tanır. Bu yöntem, her bir çizgiyi ayrı ayrı çizmeye göre daha bellek‑verimli olup piksel‑tam tekrarlanabilirlik sağlar.

## Neden Aspose.Page'i Bu Görev İçin Kullanmalısınız?
- **Çapraz‑platform** – Java destekleyen herhangi bir işletim sisteminde çalışır.  
- **Yüksek‑doğruluklu render** – Renkler, opaklık ve döşeme üzerinde hassas kontrol.  
- **Harici bağımlılık yok** – Her şey Aspose.Page kütüphanesi üzerinden yönetilir.

## Önkoşullar
İlerlemeye başlamadan önce şunların kurulu olduğundan emin olun:

- Temel Java programlama bilgisi.  
- Aspose.Page kütüphanesi yüklü – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.  
- Geliştirme makinenizde JDK 8 veya üzeri kurulu.

## Paketleri İçe Aktarma
Derleyicinin kullanacağımız tipleri bulabilmesi için gerekli sınıfları içe aktarın:

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

## Adım Adım Kılavuz

### Adım 1: Projenizi Kurun
Yeni bir `XpsDocument` örneği oluşturun ve çıktının kaydedileceği klasörü belirtin.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Adım 2: Magenta Grid Visual Brush Oluşturun
Küçük bir magenta şekli tanımlayarak bu şeklin grid alanına döşenmesini sağlayacağız.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Adım 3: Grid Brush için Geometri Tanımlayın
Döşenecek görselin yer alacağı dikdörtgen alanı ayarlayın.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Adım 4: Belge İçin Yeni Bir Canvas Oluşturun
Belgeye bir canvas ekleyin ve grid'in görüneceği konumu belirleyin.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Adım 5: Grid'i Canvas'a Ekleyin
Geometriye visual brush uygulayarak döşeme işlemini etkinleştirin.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Adım 6: Şeffaf Kırmızı Dikdörtgen Ekleyin (İkincil Özellik)
Burada grid'in üzerine **şeffaf dikdörtgen ekleme** işlemini gösteriyoruz.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Adım 7: Oluşturulan XPS Belgesini Kaydedin
Son olarak belgeyi diske yazın—bu **XPS belgesini kaydet** adımıdır.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Bu adımları izleyerek programatik olarak şeffaf bir kaplama ile profesyonel görünümlü bir grid elde edeceksiniz.

## Yaygın Sorunlar ve İpuçları

- **Yanlış döşeme boyutu:** Brush için kullanılan `Rectangle2D` hedeflenen tekrar boyutuyla aynı olmalı; aksi takdirde desen uzayabilir.  
- **Opaklık uygulanmadı:** Şeffaf yapmak istediğiniz yola `setOpacity` çağrısını eklediğinizden emin olun; brush kendisi etkilenmez.  
- **Dosya kaydedilmiyor:** `dataDir` mevcut bir klasöre işaret ettiğini ve uygulamanızın yazma iznine sahip olduğunu kontrol edin.

## Sıkça Sorulan Sorular

**S: Aspose.Page profesyonel belge üretimi için uygun mu?**  
C: Evet, Aspose.Page Java’da yüksek‑kaliteli XPS ve PDF üretimi için tasarlanmış sağlam bir kütüphanedir.

**S: Grid renklerini Visual Brush ile özelleştirebilir miyim?**  
C: Kesinlikle! Brush’ın `setFill` çağrısındaki `createColor` parametrelerini istediğiniz RGBA değerlerine göre değiştirin.

**S: Aspose.Page için ek destek nereden bulabilirim?**  
C: Topluluk yardımı ve resmi yanıtlar için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Aspose.Page için ücretsiz deneme sürümü var mı?**  
C: Evet, satın almadan önce tüm özellikleri keşfedebileceğiniz bir [ücretsiz deneme](https://releases.aspose.com/) sunulmaktadır.

**S: Test amaçlı geçici bir lisans nasıl alınır?**  
C: Geliştirme ve değerlendirme için çalışan bir [geçici lisans](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

---

**Son Güncelleme:** 2025-12-18  
**Test Edilen Versiyon:** Aspose.Page for Java 23.12 (en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
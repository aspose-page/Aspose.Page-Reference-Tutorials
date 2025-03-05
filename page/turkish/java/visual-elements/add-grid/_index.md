---
title: Java'da Görsel Fırça kullanarak Izgara Ekleme
linktitle: Java'da Görsel Fırça kullanarak Izgara Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page ile Java belge görsellerini geliştirin! Adım adım Görsel Fırça kullanarak ızgara eklemeyi öğrenin. Uygulamanızın çekiciliğini zahmetsizce artırın.
type: docs
weight: 10
url: /tr/java/visual-elements/add-grid/
---
## giriiş
Aspose.Page'i kullanarak Java uygulamalarınızı görsel olarak çekici ızgaralarla geliştirmek mi istiyorsunuz? Bu eğitimde, Aspose.Page ile Java'da Visual Brush'ı kullanarak ızgara ekleme sürecinde size rehberlik edeceğiz. Görsel Fırça, belgelerinizde çarpıcı ızgara efektleri oluşturarak bir alanı görsel içerikle boyamanıza olanak tanır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel anlayışı.
-  Aspose.Page kütüphanesi kuruldu. adresinden indirebilirsiniz.[Java belgeleri için Aspose.Page](https://reference.aspose.com/page/java/).
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
## Paketleri İçe Aktar
Gerekli paketlerin Java projenize aktarıldığından emin olun:
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
Takip etmenizi kolaylaştırmak için süreci birden fazla adıma ayıralım.
## 1. Adım: Projenizi Kurun
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```
## Adım 2: Macenta Izgara Görsel Fırçası Oluşturun
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```
## Adım 3: Macenta Izgara Görsel Fırçası için Geometriyi Tanımlayın
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```
## Adım 4: Yeni Kanvas Oluşturun
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```
## Adım 5: Izgarayı Tuvale Ekleme
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```
## Adım 6: Kırmızı Şeffaf Dikdörtgen Ekleyin
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```
## Adım 7: Sonuçtaki XPS Belgesini Kaydedin
```java
doc.save(dataDir + "AddGrid_out.xps");
```
Bu adımları takip ettiğinizde Aspose.Page ile Java uygulamanızda Visual Brush'ı kullanarak görsel olarak çekici bir ızgarayı başarıyla ekleyeceksiniz.
## Çözüm
Tebrikler! Visual Brush'ı kullanarak ızgaralar eklemek için Aspose.Page for Java'dan nasıl yararlanacağınızı öğrendiniz. Bu güçlü özellikle belge görsellerinizi zahmetsizce geliştirin.
## Sıkça Sorulan Sorular
### Aspose.Page profesyonel belge oluşturmaya uygun mu?
Evet, Aspose.Page, Java'da profesyonel belge üretimi için tasarlanmış sağlam bir kütüphanedir.
### Izgara renklerini Visual Brush kullanarak özelleştirebilir miyim?
Kesinlikle! Görsel Fırça, çeşitli renklerle boyamanıza olanak tanıyarak özelleştirmede esneklik sağlar.
### Aspose.Page için ek desteği nerede bulabilirim?
 Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.
### Aspose.Page'in ücretsiz deneme sürümü var mı?
 Evet, erişebilirsiniz[ücretsiz deneme](https://releases.aspose.com/) Aspose.Page'in özelliklerini keşfetmek için.
### Aspose.Page için nasıl geçici lisans alabilirim?
 Bir satın al[geçici lisans](https://purchase.aspose.com/temporary-license/) test amaçlı.
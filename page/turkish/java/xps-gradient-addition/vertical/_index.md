---
title: Java XPS'de Dikey Degrade Ekleme
linktitle: Java XPS'de Dikey Degrade Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page ile Java XPS belgelerine nasıl dikey degrade ekleyeceğinizi öğrenin. Görsel çekiciliği zahmetsizce geliştirin. Adım adım kılavuz içeride.
weight: 12
url: /tr/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Dikey Degrade Ekleme

## giriiş
Bu eğitimde, Java XPS'de Aspose.Page for Java'yı kullanarak dikey degradenin nasıl ekleneceğini inceleyeceğiz. XPS belgelerinize degradeler eklemek, içeriğinizin görsel çekiciliğini artırarak onu daha ilgi çekici ve estetik açıdan hoş hale getirebilir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Çalışan bir Java geliştirme ortamı.
-  Aspose.Page Java kütüphanesi için. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/java/).
- Java programlamanın temel anlayışı.
## Paketleri İçe Aktar
Java projeniz için gerekli paketleri içe aktararak başlayın. Aspose.Page for Java kütüphanesini proje bağımlılıklarınıza eklediğinizden emin olun.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
        
// Java için Aspose.Page'i içe aktar
```
## 1. Adım: Belgeyi Başlatın
XPS belgesini başlatarak başlayın. Bu, belgenize yollar ve degradeler gibi öğeler eklemenin temelini oluşturur.
```java
// Belgeyi başlat
XpsDocument doc = new XpsDocument();
```
## Adım 2: Dikey Degradeli Bir Yol Oluşturun
Şimdi dikey degradeli bir yol oluşturalım. Bu, yol geometrisinin tanımlanmasını ve degrade duraklarının belirlenmesini içerir.
```java
// Geometriyle yol oluşturma
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Dikey degrade duraklarını tanımlayın
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Dikey degradeyi yola uygulama
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## 3. Adım: Belgeyi Kaydedin
Son olarak, XPS belgesini eklenmiş dikey degradeyle istediğiniz dizine kaydedin.
```java
// Belgeyi kaydet
doc.save(dataDir + "VerticalGradient.xps");
```
Tebrikler! Aspose.Page'i kullanarak Java XPS belgenize başarılı bir şekilde dikey degrade eklediniz.
## Çözüm
XPS belgelerinizi degradelerle geliştirmek, görsel çekiciliğini önemli ölçüde artırabilir. Aspose.Page for Java bu süreci basitleştirerek kolaylıkla çarpıcı belgeler oluşturmanıza olanak tanır.

### SSS
### Aspose.Page for Java'yı ticari projelerde kullanabilir miyim?
 Evet, Aspose.Page for Java ticari kullanıma açıktır. Satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### Aspose.Page for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Page for Java belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/page/java/).
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
### Yardıma mı ihtiyacınız var veya bir sorunuz mu var?
 Aspose.Page topluluğunu ziyaret edin[forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

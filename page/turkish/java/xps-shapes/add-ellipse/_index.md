---
title: Aspose.Page ile Radyal Degrade Elips Ekleme
linktitle: Java XPS'e Elips Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java'yı kullanarak Java XPS'de radyal degrade konturlu elips eklemeye ilişkin adım adım kılavuzu keşfedin. Belge oluşturma sürecinizi zahmetsizce geliştirin.
weight: 10
url: /tr/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile Radyal Degrade Elips Ekleme

## giriiş
Aspose.Page for Java kullanarak Java XPS'de elips eklemeye ilişkin adım adım kılavuzumuza hoş geldiniz. Aspose.Page, geliştiricilerin XPS belgeleriyle zahmetsizce çalışmasına olanak tanıyan güçlü bir Java kitaplığıdır. Bu öğreticide, radyal degrade konturlu elips oluşturma ve bunu bir XPS belgesi olarak kaydetme sürecinde size yol göstereceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Page for Java kütüphanesi indirildi. Alabilirsin[Burada](https://releases.aspose.com/page/java/).
- Java kodunu yazmak ve yürütmek için seçtiğiniz bir kod düzenleyici (Eclipse, IntelliJ, vb.).
## Paketleri İçe Aktar
Aspose.Page'i kullanmak için Java projenizde gerekli paketlerin içe aktarıldığından emin olun. Aşağıdaki içe aktarma ifadelerini Java dosyanızın üstüne ekleyin:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## 1. Adım: Belge Dizinini Ayarlayın
XPS belgesinin kaydedileceği belge dizininizin yolunu tanımlayın:
```java
String dataDir = "Your Document Directory";
```
## Adım 2: XPS Belgesi Oluşturun
Aşağıdaki kodu kullanarak yeni bir XPS belgesi başlatın:
```java
XpsDocument doc = new XpsDocument();
```
## Adım 3: Radyal Degrade Duraklarını Tanımlayın
Radyal degrade konturlu elips için degrade duraklarının bir listesini oluşturun:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Adım 4: Yol Geometrisi Oluşturun
Yol geometrisini kullanarak radyal degrade konturlu bir elips tanımlayın:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Adım 5: Kanvas ve Yol Ekle
Belgeye yeni bir tuval ekleyin ve tanımlanmış geometriye sahip yolu ekleyin:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Adım 6: Kontur ve Degradeyi Ayarlayın
Yolun konturunu radyal degrade fırçayla yapılandırın:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Adım 7: Kontur Kalınlığını Ayarlayın
Yolun kontur kalınlığını belirtin:
```java
path.setStrokeThickness(12f);
```
## Adım 8: Belgeyi Kaydedin
Ortaya çıkan XPS belgesini kaydedin:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Tebrikler! Aspose.Page for Java'yı kullanarak Java XPS'de radyal degrade konturlu elipsi başarıyla eklediniz.
## Çözüm
Bu eğitimde, görsel olarak çekici bir radyal degrade konturlu elips içeren bir XPS belgesi oluşturma adımlarını araştırdık. Aspose.Page for Java, XPS belgelerinin işlenmesini basitleştirerek geliştiricilere güçlü bir araç seti sağlar.
## Sıkça Sorulan Sorular
### Aspose.Page for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?
Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilebilir.
### Aspose.Page büyük ölçekli belge işlemeye uygun mu?
Kesinlikle! Aspose.Page, büyük ölçekli belge işlemeyi verimli bir şekilde gerçekleştirmek için tasarlanmıştır.
### Aspose.Page for Java için daha fazla eğitim ve örneği nerede bulabilirim?
 Ziyaret edin[Java belgeleri için Aspose.Page](https://reference.aspose.com/page/java/)Kapsamlı eğitimler ve örnekler için.
### Aspose.Page for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Page tartışmaları için topluluk forumları var mı?
 Evet, katıl[Aspose.Page topluluk forumu](https://forum.aspose.com/c/page/39) diğer geliştiricilerle iletişim kurmak ve yardım almak.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

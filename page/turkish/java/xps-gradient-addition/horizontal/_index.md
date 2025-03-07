---
title: Java XPS'de Yatay Degrade Ekleme
linktitle: Java XPS'de Yatay Degrade Ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page'i kullanarak Java'da XPS belgelerine nasıl çarpıcı bir yatay degrade ekleyeceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Yatay Degrade Ekleme

## giriiş
Aspose.Page for Java kullanarak Java XPS'de yatay degrade eklemeyi anlatan bu adım adım kılavuza hoş geldiniz. Aspose.Page for Java, geliştiricilerin XPS (XML Kağıt Belirtimi) belgeleriyle sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır.
Bu eğitimde, bir XPS belgesine yatay degrade eklemek için bir Java uygulaması oluşturma sürecinde size yol göstereceğiz. Bunu kolaylıkla başarmak için aşağıdaki adımları izleyin.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java'nın kurulu olduğundan emin olun. Değilse, Java'nın en son sürümünü adresinden indirip yükleyin.[java.com](https://www.java.com).
2.  Aspose.Page for Java Kütüphanesi: Aspose.Page for Java kütüphanesine sahip olmanız gerekir. adresinden indirebilirsiniz.[Java belgeleri için Aspose.Page](https://reference.aspose.com/page/java/).
## Paketleri İçe Aktar
Java uygulamanız için gerekli paketleri içe aktararak başlayın. Aspose.Page for Java kütüphanesini projenize ekleyin. Bunu aşağıdaki kod satırlarını ekleyerek yapabilirsiniz:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## 1. Adım: Belgeyi Başlatın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
//Belgeyi başlat
XpsDocument doc = new XpsDocument();
```
## Adım 2: Yatay Degrade Oluşturun
```java
// Yatay degrade
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## 3. Adım: Degradeli Yol Ekleme
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Adım 4: Belgeyi Kaydedin
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Parametreleri özel gereksinimlerinize göre ayarlayarak bu adımları gerektiği kadar tekrarlayın.
## Çözüm
Tebrikler! Aspose.Page for Java'yı kullanarak bir XPS belgesine başarıyla yatay degrade eklediniz. Bu eğitim, Java uygulamalarını degrade efektleriyle geliştirmek isteyen geliştiriciler için kapsamlı bir kılavuz sağladı.
## SSS
### S: Tek bir XPS belgesine birden fazla degrade uygulayabilir miyim?
Evet, karmaşık tasarımlar oluşturmak için farklı degradelere sahip birden fazla yol ekleyebilirsiniz.
### S: Aspose.Page en son Java sürümleriyle uyumlu mu?
Aspose.Page for Java, en yeni Java sürümleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir.
### S: Aspose.Page'de başka degrade türleri mevcut mu?
Evet, Aspose.Page, doğrusal degradelerin yanı sıra daha çeşitli efektler için radyal degradeleri de destekler.
### S: Degrade duraklarının renklerini ve konumlarını özelleştirebilir miyim?
Kesinlikle! Her degrade durağının renkleri ve konumları üzerinde tam kontrole sahipsiniz.
### S: Aspose.Page için yardım isteyebileceğim bir topluluk forumu var mı?
 Evet, ziyaret edebilirsiniz[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla bağlantı kurmak ve yardım almak için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

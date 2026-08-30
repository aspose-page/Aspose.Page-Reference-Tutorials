---
date: 2026-04-24
description: Java ile bir XPS belgesi oluşturmayı ve radyal degrade elips eklemeyi
  öğrenin. Bu adım adım kılavuz, Aspose.Page kullanarak çizgi kalınlığını ayarlamayı
  ve yol geometrisini tanımlamayı gösterir.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Java XPS'te Elips Ekle
second_title: Aspose.Page Java API
title: XPS Belgesi Oluşturma Java – Radial Gradyan Elips Ekle
url: /tr/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile Radial Gradient Elips Ekle

## Giriş
Bu öğreticide, Aspose.Page for Java kullanarak güzel bir radial gradient kenarlıklı elips ile **create XPS document Java** nasıl oluşturacağınızı öğreneceksiniz. Aspose.Page, düşük seviyeli XPS ayrıntılarını soyutlayan sağlam bir kütüphanedir; böylece dosya formatı inceliklerinden ziyade tasarıma odaklanabilirsiniz. Bu rehberin sonunda, raporlar, faturalar veya herhangi bir belge‑oluşturma iş akışına ekleyebileceğiniz kullanıma hazır bir XPS dosyanız olacak.

## Hızlı Yanıtlar
- **Bu kod ne üretir?** Çok renkli radial gradient ile kenarlıklı bir elips içeren tek sayfalık bir XPS dosyası.  
- **Hangi birincil API kullanılıyor?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, vb.).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Ayarladığımız ana özellikler nelerdir?** Çizgi fırçası (radial gradient), yayılma yöntemi, gradient durakları ve çizgi kalınlığı.  
- **Elips boyutunu değiştirebilir miyim?** Evet – yol geometrisi dizesini veya gradient fırça koordinatlarını değiştirin.

## “create XPS document Java” nedir?
Java’da XPS belgesi oluşturmak, XML Paper Specification (XPS) dosyasını—PDF’ye benzer sabit‑düzen bir belge formatı—doğrudan Java kodundan programlı olarak üretmek anlamına gelir. Aspose.Page, XML işaretlemesini soyutan yüksek‑seviye bir nesne modeli (`XpsDocument`, `XpsCanvas`, vb.) sağlar; bu sayede süreç standart Java nesneleriyle çalışmak kadar basittir.

## Neden radial gradient elips kullanmalı?
Radial gradient, üç boyutlu bir his verir ve raporlardaki görsel vurgular, logolar veya dekoratif öğeler için mükemmeldir. Tek renkli bir kenarlığa kıyasla, gradient dosya boyutunu önemli ölçüde artırmadan derinlik katar ve XPS formatı, ölçeklendirme sırasında vektör kalitesini korur.

## Ön Koşullar
Başlamadan önce, aşağıdaki ön koşulların karşılandığından emin olun:
- Makinenizde Java Development Kit (JDK) yüklü olmalı.
- Aspose.Page for Java kütüphanesini indirin. Bunu [buradan](https://releases.aspose.com/page/java/) alabilirsiniz.
- Java kodu yazmak ve çalıştırmak için tercih ettiğiniz bir kod editörü (Eclipse, IntelliJ vb.).

## Paketleri İçe Aktar
Aspose.Page'i kullanabilmek için Java projenizde gerekli paketlerin içe aktarıldığından emin olun. Aşağıdaki import ifadelerini Java dosyanızın en üstüne ekleyin:

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

## Adım 1: Belge Dizini Ayarla
XPS belgesinin kaydedileceği belge dizininin yolunu tanımlayın:

```java
String dataDir = "Your Document Directory";
```

## Adım 2: XPS Belgesi Oluştur
Aşağıdaki kodu kullanarak yeni bir XPS belgesi başlatın:

```java
XpsDocument doc = new XpsDocument();
```

## Adım 3: Radial Gradient Durduraklarını Tanımla
Radial gradient kenarlıklı elips için bir gradient durakları listesi oluşturun:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Adım 4: Yol Geometrisi Oluştur
Yol geometrisi kullanarak radial gradient kenarlıklı bir elips tanımlayın:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Adım 5: Kanvas ve Yol Ekle
Belgeye yeni bir kanvas ekleyin ve tanımlanan geometriyle yolu ekleyin:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Adım 6: Çizgiyi ve Gradient'i Ayarla
Yolun çizgisini radial gradient fırçası ile yapılandırın:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Adım 7: Çizgi Kalınlığını Ayarla
Yolun **çizgi kalınlığını ayarlayın**:

```java
path.setStrokeThickness(12f);
```

## Adım 8: Belgeyi Kaydet
Oluşturulan XPS belgesini kaydedin:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Tebrikler! Aspose.Page ile **create XPS document Java** yaparken radial gradient kenarlıklı bir elipsi başarıyla eklediniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Elips düz görünüyor** | `XpsSpreadMethod.Pad` yerine `Reflect` kullanılması | Adım 6'da gösterildiği gibi yayılma yöntemini `XpsSpreadMethod.Reflect` olarak değiştirin. |
| **Çıktı dosyası yok** | `dataDir` var olmayan bir klasöre işaret ediyor | Dizinin var olduğundan emin olun veya mutlak bir yol kullanın. |
| **Gradient renkleri hatalı** | Gradient duraklarının sırası yanlış | `offset` değerlerinin (0 → 1) artan bir sırada olduğundan emin olun. |
| **Derleme hataları** | Classpath'te Aspose.Page JAR dosyaları eksik | Proje bağımlılıklarınıza `aspose-page-xx.jar` ekleyin. |

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'ı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilebilir.

**S: Aspose.Page büyük ölçekli belge işleme için uygun mu?**  
C: Kesinlikle! Aspose.Page büyük ölçekli belge işleme görevlerini verimli bir şekilde gerçekleştirecek şekilde tasarlanmıştır.

**S: Aspose.Page for Java için daha fazla öğretici ve örnek nerede bulunabilir?**  
C: Kapsamlı öğreticiler ve örnekler için [Aspose.Page for Java belgelerine](https://reference.aspose.com/page/java/) göz atın.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S: Aspose.Page tartışmaları için topluluk forumları var mı?**  
C: Evet, diğer geliştiricilerle etkileşimde bulunmak ve yardım almak için [Aspose.Page topluluk forumuna](https://forum.aspose.com/c/page/39) katılabilirsiniz.

---

**Son Güncelleme:** 2026-04-24  
**Test Edilen:** Aspose.Page for Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
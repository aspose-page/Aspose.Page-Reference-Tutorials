---
date: 2025-12-25
description: Aspose.Page kullanarak Java XPS'te dikey degrade eklemeyi öğrenin. Belgenizin
  görsel çekiciliğini artırmak için bu adım adım kılavuzu izleyin.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPS'te Dikey Gradyan Nasıl Eklenir
url: /tr/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Dikey Degrade Nasıl Eklenir

## Giriş
Bu öğreticide **Java ile XPS belgelerine dikey degrade eklemeyi** keşfedeceksiniz. Dikey bir degrade, raporlarınızın, faturalarınızın veya herhangi bir yazdırılabilir içeriğin görsel etkisini büyük ölçüde artırabilir. Aspose.Page for Java kütüphanesini kullanarak projeyi kurmaktan son XPS dosyasını kaydetmeye kadar her adımı adım adım göstereceğiz.

## Hızlı Yanıtlar
- **Dikey degrade ne işe yarar?** Bir şeklin üstünden altına doğru pürüzsüz bir renk geçişi oluşturur.  
- **Hangi kütüphane gerekir?** Aspose.Page for Java (resmi siteden indirilebilir).  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Java 8+ ile uyumlu mu?** Evet, API Java 8 ve sonraki sürümleri destekler.  
- **Uygulama ne kadar sürer?** Ortam kurulduktan sonra genellikle 10 dakikadan az sürer.

## Önkoşullar
Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Çalışan bir Java geliştirme ortamı (JDK 8 veya daha yeni).  
- Aspose.Page for Java kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.  
- Java programlama kavramlarına temel bir anlayış.

## Paketleri İçe Aktarma
Java projeniz için gerekli paketleri içe aktararak başlayın. Aspose.Page for Java kütüphanesinin proje sınıf yoluna (classpath) eklendiğinden emin olun.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Adım 1: Belgeyi Başlatma
Yeni bir XPS belgesi oluşturun. Bu nesne, daha sonra ekleyeceğiniz tüm çizim öğelerini tutacaktır.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Adım 2: Dikey Degrade ile Bir Yol Oluşturma
Şimdi, dikey bir lineer degrade uygulayarak dikdörtgen bir yol tanımlayın. Degrade durakları, renkleri ve bu renklerin dikey eksen üzerindeki konumlarını belirler.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Adım 3: Belgeyi Kaydetme
Son olarak, XPS dosyasını diske yazın. Oluşan dosya, tanımladığınız dikey degrade ile doldurulmuş dikdörtgeni içerecektir.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Tebrikler! Aspose.Page kullanarak bir Java XPS belgesine **dikey degrade eklemeyi** başarıyla öğrendiniz.

## Neden Dikey Degrade Kullanmalı?
- **Gelişmiş estetik:** Degradeler, statik şekillere derinlik ve modern bir görünüm katar.  
- **Marka tutarlılığı:** Kurumsal renkleri sayfalar arasında sorunsuz bir şekilde eşleştirin.  
- **Kolay özelleştirme:** Grafik tasarımını yeniden yapmadan renkleri veya durak konumlarını değiştirin.

## Yaygın Sorunlar ve Çözüm Önerileri
- **Degrade görünmüyor:** `LinearGradientBrush` başlangıç ve bitiş noktalarının dikey yönde doğru ayarlandığını kontrol edin.  
- **Dosya kaydedilmiyor:** `dataDir`'in yazılabilir bir klasöre işaret ettiğinden ve dosya yazma izniniz olduğundan emin olun.  
- **Kütüphane bulunamadı:** Aspose.Page JAR dosyasının proje derleme yoluna (build path) eklendiğini iki kez kontrol edin.

## Sık Sorulan Sorular

**S: Aspose.Page for Java’yı ticari projelerde kullanabilir miyim?**  
C: Evet, Aspose.Page for Java ticari kullanım için mevcuttur. Satın almak için [buraya](https://purchase.aspose.com/buy) tıklayın.

**S: Aspose.Page for Java için ücretsiz deneme sürümü var mı?**  
C: Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Page for Java dokümantasyonunu nereden bulabilirim?**  
C: Dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aspose.Page for Java için geçici bir lisans alabilir miyim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

**S: Yardıma ihtiyacım var ya da sorularım var, ne yapmalıyım?**  
C: Aspose.Page topluluğu [forumuna](https://forum.aspose.com/c/page/39) göz atın.

---

**Son Güncelleme:** 2025-12-25  
**Test Edilen Sürüm:** Aspose.Page for Java 24.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
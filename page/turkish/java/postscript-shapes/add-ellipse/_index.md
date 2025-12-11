---
date: 2025-12-11
description: Aspose.Page kullanarak Java'da PostScript elipsi nasıl oluşturacağınızı
  öğrenin. Bu adım adım kılavuz, elipsi renkle doldurmayı ve Java kullanarak elips
  çizmeyi gösterir.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page ile Java’da PostScript elipsi nasıl oluşturulur
url: /tr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Page kullanarak PostScript elipsi oluşturma

## Giriş
Programlı olarak **PostScript elipsi** oluşturmak, raporlar, faturalar veya herhangi bir yazdırılabilir belgede vektör grafikler üzerinde ince ayarlı kontrol sağlar. Bu öğreticide, Aspose.Page for Java kütüphanesini kullanarak **PostScript elipsi** şekilleri oluşturmayı, bir elipsi renkle doldurmayı ve elipsin konturunu çizmeyi öğreneceksiniz. Sonunda, özel grafikleri doğrudan PostScript çıktınıza yerleştirmeye hazır olacaksınız.

## Hızlı Yanıtlar
- **Java'da PostScript grafikleri çizmek için en iyi kütüphane hangisidir?** Aspose.Page for Java.  
- **Bir elipsi katı bir renkle doldurabilir miyim?** Evet – `fill`'den önce `document.setPaint(Color.YOUR_COLOR)` kullanın.  
- **Sadece bir elipsin konturunu nasıl çizerim?** Boya ve çizgi kalınlığını ayarlayın, ardından `document.draw(...)` çağırın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; test için geçici bir lisans mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Mevcut Aspose.Page sürümüyle Java 8+ çalışma zamanı herhangi bir sürüm çalışır.

## PostScript elipsi nedir?
PostScript elipsi, sınırlayıcı bir dikdörtgenle tanımlanan bir vektör şeklidir. Raster görüntülerden farklı olarak, kalite kaybı olmadan ölçeklenir ve yüksek çözünürlüklü baskı ve PDF dönüşümü için idealdir.

## PostScript elipsi oluşturmak için neden Aspose.Page kullanmalı?
- **Tam kontrol** çizim temel öğeleri (çizgiler, eğriler, elipsler) üzerinde.  
- **Çapraz platform** – Windows, Linux ve macOS'ta çalışır.  
- **Harici bağımlılık yok** – saf Java API, yerel kod yok.  
- **Kolay entegrasyon** mevcut Java uygulamaları ve yapı araçlarıyla.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Fonksiyonel bir Java geliştirme ortamı (JDK 8 veya daha yenisi).  
2. Projenize eklenmiş Aspose.Page for Java kütüphanesi. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.

## Paketleri İçe Aktarma
Java kaynak dosyanızda, PostScript içeriğini çizmek ve kaydetmek için gereken sınıfları içe aktarın.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım adım kılavuz

### Adım 1: PostScript belgesini ayarlama
Bir çıktı akışı oluşturun, sayfa boyutunu yapılandırın ve bir `PsDocument` örneği oluşturun.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Adım 2: Elipsi renkle doldurma
Boyayı istediğiniz doldurma rengine ayarlayın ve bir `Ellipse2D` örneğiyle `fill` çağırın.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Adım 3: Elipsin konturunu çizecek çizgi kalınlığı ayarlama
Boyayı kontur rengine değiştirin, çizgi kalınlığı için bir `BasicStroke` tanımlayın ve elipsin konturunu çizin.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Adım 4: Belgeyi kapatıp kaydetme
Sayfayı sonlandırın ve PostScript dosyasını diske yazın.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Artık içinde iki elips bulunan bir PostScript dosyanız var—biri turuncu renkle doldurulmuş, diğeri kırmızı renkle konturlanmış. Tasarım ihtiyaçlarınıza uygun farklı koordinatlar, boyutlar ve renklerle denemeler yapmaktan çekinmeyin.

## Yaygın tuzaklar ve sorun giderme
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Lisans eksik** – Geçerli bir lisans olmadan, kütüphane değerlendirme modunda çalışır ve filigran ekleyebilir.  
- **Renk uygulanmadı** – Her `fill` veya `draw` çağrısından *önce* `document.setPaint(...)` ayarlamayı unutmayın; boya ayarı ayrı işlemler arasında otomatik olarak kalıcı değildir.

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz entegrasyon için tasarlanmıştır.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Test amaçları için **[buradan](https://purchase.aspose.com/temporary-license/)** geçici bir lisans edinin.

**S: Aspose.Page ticari projeler için uygun mu?**  
C: Kesinlikle! Ticari kullanım için lisans seçeneklerini keşfetmek üzere **[buradan](https://purchase.aspose.com/buy)** ziyaret edin.

**S: Aspose.Page ile ilgili sorular için nereden yardım alabilir veya tartışma yapabilirim?**  
C: Tartışmalar ve destek için **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** topluluğuna katılın.

**S: Aspose.Page for Java hakkında daha fazla öğrenmek için ücretsiz kaynaklar var mı?**  
C: **[Ücretsiz deneme](https://releases.aspose.com/)**'yi kullanın ve belgelerdeki örnekleri keşfedin.

## Sonuç
Aspose.Page for Java, basit bir doldurulmuş şekil ya da karmaşık bir konturlu şekil ihtiyacınız olsun, **PostScript elipsi** grafiklerini oluşturmayı kolaylaştırır. Yukarıdaki adımlarla herhangi bir yazdırılabilir belgeye profesyonel düzeyde vektör grafikleri hızlıca ekleyebilirsiniz. Daha derin keşifler için—birden fazla şekli birleştirme, degrade uygulama veya PDF'ye dönüştürme gibi—resmi **[belgelere](https://reference.aspose.com/page/java/)** bakın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-11  
**Test Edilen Versiyon:** Aspose.Page for Java 24.11  
**Yazar:** Aspose
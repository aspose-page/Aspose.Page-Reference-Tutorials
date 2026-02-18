---
date: 2026-02-18
description: Java'da Aspose.Page kullanarak boya rengini ayarlamayı ve bir PostScript
  elipsi oluşturmayı öğrenin. Bu kılavuz, elipsi Java'da doldurmayı, elipsin konturunu
  çizmeyi ve çizgi kalınlığını ayarlamayı gösterir.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Java'da PostScript elipsi çizmek için boya rengini ayarla
url: /tr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da PostScript elipsi çizmek için boya rengini ayarlama

## Giriş
Vektör grafikleri çizerken **boya rengini ayarlamanız** gerekiyorsa, Aspose.Page for Java kütüphanesi her bir çizgi ve dolgu üzerinde tam kontrol sağlar. Bu öğreticide **boya rengini ayarlamayı**, **Java'da elips doldurmayı** ve **elips konturunu çizmeyi** basit, adım adım bir yaklaşımla öğreneceksiniz. Sonunda, faturalar, raporlar veya herhangi bir yazdırılabilir belgeye yüksek kaliteli PostScript elipsleri ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Java'da PostScript grafikleri çizmek için en iyi kütüphane hangisidir?** Aspose.Page for Java.  
- **Bir elipsi katı bir renk ile doldurabilir miyim?** Evet – `fill`'den önce `document.setPaint(Color.YOUR_COLOR)` kullanın.  
- **Sadece bir elipsin konturunu nasıl çizerim?** Boya ve çizgi kalınlığını ayarlayın, ardından `document.draw(...)` çağırın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; test için geçici bir lisans mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Mevcut Aspose.Page sürümüyle Java 8+ çalışma zamanı herhangi bir sürüm çalışır.

## PostScript elipsi nedir?
PostScript elipsi, sınırlayıcı bir dikdörtgenle tanımlanan bir vektör şekildir. Raster görüntülerden farklı olarak kalite kaybı olmadan ölçeklenir, bu da yüksek çözünürlüklü baskı ve PDF dönüşümü için idealdir.

## PostScript elipsi oluşturmak için Aspose.Page'i neden kullanmalısınız?
- **Tam kontrol** çizim temel öğeleri (çizgiler, eğriler, elipsler) üzerinde.  
- **Çapraz platform** – Windows, Linux ve macOS'ta çalışır.  
- **Harici bağımlılık yok** – saf Java API, yerel kod yok.  
- **Kolay entegrasyon** mevcut Java uygulamaları ve yapı araçlarıyla.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Fonksiyonel bir Java geliştirme ortamı (JDK 8 veya üzeri).  
2. Projenize eklenmiş Aspose.Page for Java kütüphanesi. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  

## Paketleri İçe Aktarma
Java kaynak dosyanızda, PostScript içeriğini çizmek ve kaydetmek için gerekli sınıfları içe aktarın.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bir elips için boya rengini nasıl ayarlarsınız
Boya rengini ayarlamak, herhangi bir dolgu veya çizgi işlemi öncesinde ilk adımdır. `setPaint` metodu, bir sonraki çizim komutunda kullanılacak rengi belirler.

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

### Adım 2: Elipsi doldurmak – boya rengini kullanma
**Elipsi doldurmak** için, önce istediğiniz dolgu rengiyle `setPaint` çağırmalı, ardından bir `Ellipse2D` örneğiyle `fill` metodunu kullanmalısınız.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Adım 3: Elips konturunu çiz ve çizgi kalınlığını ayarla
Doldurduktan sonra, boya rengini farklı bir renge değiştirebilir, çizgi kalınlığını kontrol etmek için bir `BasicStroke` tanımlayabilir ve elips konturunu çizebilirsiniz.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Adım 4: Belgeyi kapat ve kaydet
Sayfayı sonlandırın ve PostScript dosyasını diske yazın.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Artık içinde iki elips bulunan bir PostScript dosyanız var—biri turuncu ile doldurulmuş, diğeri kırmızı konturlu. Tasarım ihtiyaçlarınıza uygun farklı koordinatlar, boyutlar ve renklerle denemeler yapmaktan çekinmeyin.

## Yaygın tuzaklar ve sorun giderme
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Lisans eksik** – Geçerli bir lisans olmadan, kütüphane değerlendirme modunda çalışır ve filigran ekleyebilir.  
- **Renk uygulanmadı** – Her `fill` veya `draw` çağrısından *önce* `document.setPaint(...)` ayarlamayı unutmayın; boya ayarı ayrı işlemler arasında otomatik olarak kalıcı olmaz.

## Sık Sorulan Sorular

**Q: Aspose.Page for Java'i diğer Java kütüphaneleriyle kullanabilir miyim?**  
A: Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz entegrasyon için tasarlanmıştır.

**Q: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
A: Test amaçlı geçici bir lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** edinebilirsiniz.

**Q: Aspose.Page ticari projeler için uygun mu?**  
A: Kesinlikle! Ticari kullanım için lisans seçeneklerini keşfetmek üzere **[burayı](https://purchase.aspose.com/buy)** ziyaret edin.

**Q: Aspose.Page ile ilgili sorular için nereden yardım alabilir veya tartışma yapabilirim?**  
A: Tartışmalar ve destek için **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** topluluğuna katılın.

**Q: Aspose.Page for Java hakkında daha fazla öğrenmek için ücretsiz kaynaklar var mı?**  
A: **[Ücretsiz deneme](https://releases.aspose.com/)**'yi kullanın ve belgelerdeki örnekleri inceleyin.

## Sonuç
Aspose.Page for Java, **boya rengini ayarlamayı**, **elips doldurmayı** ve **elips konturunu çizmeyi**—basit bir doldurulmuş şekle ya da karmaşık bir çizgi grafiğine ihtiyaç duyduğunuzda—kolaylaştırır. Yukarıdaki adımlarla herhangi bir yazdırılabilir belgeye profesyonel düzeyde vektör grafikleri hızlıca ekleyebilirsiniz. Daha derin keşifler için—birden fazla şekli birleştirme, degrade uygulama veya PDF'ye dönüştürme gibi—resmi **[belgelere](https://reference.aspose.com/page/java/)** bakın.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
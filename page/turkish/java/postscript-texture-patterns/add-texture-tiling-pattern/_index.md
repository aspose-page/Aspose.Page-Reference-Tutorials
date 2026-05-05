---
date: 2026-05-05
description: Aspose.Page for Java ile PostScript belgelerine doku döşeme desenleri
  eklemeyi öğrenin. Bu kılavuz, dokuyu verimli bir şekilde eklemeyi ve yaratıcı olasılıkları
  keşfetmeyi gösterir.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Java PostScript'te Doku Döşeme Deseni Ekle
second_title: Aspose.Page Java API
title: Java PostScript'te Doku Döşeme Deseni Nasıl Eklenir
url: /tr/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Doku Döşeme Deseni Nasıl Eklenir

## Giriş
Java geliştirme dünyasında, PostScript belgelerine **how to add texture** eklemeyi öğrenmek yaygın bir gereksinimdir. Aspose.Page for Java bu görevi basitleştirir, düşük seviyeli PostScript sözdizimi yerine tasarıma odaklanmanızı sağlar. Bu öğreticide, bir doku döşeme deseni eklemek, şekilleri doldurmak ve hatta bir Java PostScript belgesinde metni doku ile kaplamak için gereken tüm adımları göstereceğiz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java  
- **Bu kılavuzun hedeflediği birincil anahtar kelime nedir?** *how to add texture*  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü mevcuttur; üretim için bir lisans gereklidir.  
- **Desteklenen Java sürümü nedir?** Java 8 veya üzeri.  
- **Birden fazla şekil için doku fırçasını yeniden kullanabilir miyim?** Evet – `TexturePaint`'i bir kez oluşturup herhangi bir şekle uygulayabilirsiniz.  
- **Bir dikdörtgeni doku ile nasıl doldururum?** `TexturePaint`i geçerli boya olarak ayarladıktan sonra `document.fill(shape)` kullanın.

## Doku Döşeme Deseni Nedir?
Bir doku döşeme deseni, küçük bir görüntüyü (döşeme) daha büyük bir alana tekrar eder ve **fill shape with texture** ifadesini manuel olarak her döşemeyi çizmeye gerek kalmadan gerçekleştirmenizi sağlar. Bu teknik, PostScript'te arka planlar, doldurmalar ve dekoratif metin efektleri için idealdir.

## Neden Aspose.Page for Java Kullanmalı?
- **Zero‑dependency rendering** – harici PostScript yorumlayıcılarına ihtiyaç yok.  
- **Full control over graphics** – vektör şekilleri, metin ve bitmap dokuları birleştirin.  
- **Cross‑platform** – Java destekleyen herhangi bir işletim sisteminde çalışır.

## Önkoşullar
Öğreticiye başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java programlama diline temel bir anlayış.  
- PostScript belge yapısına aşinalık.  
- Aspose.Page for Java kütüphanesi yüklü. Bunu [burada](https://releases.aspose.com/page/java/) adresinden indirebilirsiniz.

## Paketleri İçe Aktar
Java projeniz için gerekli paketleri içe aktararak başlayın:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Java PostScript'te Doku Döşeme Deseni Nasıl Eklenir
Aşağıda adım adım bir kılavuz bulunmaktadır. Her adım kısa bir açıklama ve kopyalamanız gereken tam kodu içerir.

### Adım 1: PostScript Belgesi Oluştur
Yeni bir PostScript belgesi oluşturarak başlayın, çıktı akışını ve kaydetme seçeneklerini belirleyin. Gerekli yolların yapılandırıldığından emin olun.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Adım 2: Grafik Ortamını Kur
Kökeni uygun bir konuma taşıyın ve doku döşemesi olarak kullanılacak bitmap'i yükleyin.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### Adım 3: Doku Fırçası Oluştur
`TexturePaint`'i tanımlayın; bu, bitmap'i şeklin alanı boyunca tekrar eder. Döşemenin daha büyük veya daha küçük görünmesini istiyorsanız dikdörtgen boyutunu ayarlayın.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### Adım 4: Şekilleri Çiz ve Doldur
Bir dikdörtgen oluşturun ve fırçayı kullanarak **fill rectangle with texture** yapın. Ardından şeklin kenarını çizin, böylece sonuç görsel olarak belirgin olur.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### Adım 5: Metne Doku Deseni Ekle
Aynı dokuyu metin gliflerine de uygulayabilirsiniz. Bu, karakterlere **how to fill texture** uygulamayı gösterirken, aynı zamanda kenarlık ekleyebilmenizi sağlar.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### Adım 6: Kaydet ve Kapat
Son olarak, sayfayı kapatın, belgeyi kaydedin ve kaynakları serbest bırakın.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Yaygın Sorunlar ve İpuçları
- **Missing texture file** – `TestTexture.bmp` dosyasının yolunun doğru ve dosyanın erişilebilir olduğunu doğrulayın.  
- **Incorrect image dimensions** – Doku uzatılmış görünüyorsa, `imageArea`'yı orijinal görüntü boyutuna göre ayarlayın.  
- **Performance** – Gereksiz nesne oluşturmayı önlemek için aynı `TexturePaint` örneğini birden fazla şekil için yeniden kullanın.  
- **Pro tip:** Ölçeklendirildiğinde dokunun net kalması için döşeme için yüksek çözünürlüklü bir bitmap kullanın.

## Sıkça Sorulan Sorular

**Q:** Aspose.Page for Java yeni başlayanlar için uygun mu?  
**A:** Kesinlikle! Aspose.Page for Java kapsamlı belgeler sağlar, bu da tüm beceri seviyelerindeki geliştiriciler için erişilebilir olmasını sağlar.

**Q:** Aspose.Page for Java'ı mevcut Java projemle entegre edebilir miyim?  
**A:** Evet, sağlanan belgeleri [burada](https://reference.aspose.com/page/java/) izleyerek Aspose.Page for Java'ı projenize kolayca entegre edebilirsiniz.

**Q:** Destek bulabileceğim veya Aspose.Page ile ilgili soruları tartışabileceğim yer neresi?  
**A:** Toplulukla etkileşime geçmek ve yardım almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**Q:** Aspose.Page for Java için ücretsiz deneme sürümü mevcut mu?  
**A:** Evet, ücretsiz deneme sürümünü [burada](https://releases.aspose.com/) keşfedebilirsiniz.

**Q:** Aspose.Page for Java için geçici bir lisans nasıl alabilirim?  
**A:** Geçici lisans almak için [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak bir Java PostScript belgesine **how to add texture** döşeme desenleri eklemeyi başarıyla öğrendiniz. Farklı bitmap döşemeler, ölçek faktörleri ve birleşik işlemlerle denemeler yapmaktan çekinmeyin; böylece doku doldurmalarının tam yaratıcı potansiyelini ortaya çıkarabilirsiniz.

---

**Son Güncelleme:** 2026-05-05  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
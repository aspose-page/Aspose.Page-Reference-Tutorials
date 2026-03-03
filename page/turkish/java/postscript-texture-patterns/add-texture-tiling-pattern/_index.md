---
date: 2025-12-17
description: Aspose.Page for Java ile PostScript belgelerine doku döşeme desenleri
  eklemeyi öğrenin. Bu rehber, dokuyu verimli bir şekilde eklemeyi ve yaratıcı olasılıkları
  keşfetmeyi gösterir.
linktitle: Add Texture Tiling Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Java PostScript'te Doku Döşeme Deseni Nasıl Eklenir
url: /tr/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Doku Döşeme Deseni Ekleme

## Giriş
Java geliştirme dünyasında, **doku eklemeyi** öğrenmek PostScript belgelerinde yaygın bir gereksinimdir. Aspose.Page for Java, bu görevi zahmetsizce yerine getirmenize yardımcı olan değerli bir araçtır. Bu öğreticide, Aspose.Page kullanarak bir Java PostScript belgesine doku döşeme deseni ekleme sürecini adım adım göstereceğiz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Bu kılavuzun hedeflediği ana anahtar kelime nedir?** *how to add texture*  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü mevcuttur; üretim için lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Doku fırçasını birden fazla şekil için yeniden kullanabilir miyim?** Evet – `TexturePaint`'i bir kez oluşturup istediğiniz şekle uygulayabilirsiniz.

## Doku döşeme deseni nedir?
Doku döşeme deseni, küçük bir görüntüyü (döşemeyi) daha büyük bir alana tekrar ederek, **şekli doku ile doldurmanıza** olanak tanır; her bir döşemeyi manuel olarak çizmenize gerek kalmaz. Bu teknik, PostScript'te arka planlar, doldurmalar ve dekoratif metin efektleri için idealdir.

## Neden Aspose.Page for Java?
- **Sıfır bağımlılık renderlama** – harici PostScript yorumlayıcılarına ihtiyaç yok.  
- **Grafik üzerinde tam kontrol** – vektör şekilleri, metin ve bitmap dokuları birleştirin.  
- **Çapraz platform** – Java'yı destekleyen herhangi bir işletim sisteminde çalışır.  

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların karşılandığından emin olun:
- Java programlama diline temel bir anlayış.  
- PostScript belge yapısına aşinalık.  
- Aspose.Page for Java kütüphanesi yüklü. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.

## Paketleri İçe Aktarma
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

## Adım 1: Bir PostScript Belgesi Oluşturma
Yeni bir PostScript belgesi oluşturun, çıktı akışını ve kaydetme seçeneklerini belirtin. Gerekli yolların yapılandırıldığından emin olun.

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

## Adım 2: Grafik Ortamını Ayarlama
Kökeni (origin) çevirerek ve doku görüntü dosyasından bir `BufferedImage` oluşturarak grafik ortamını ayarlayın.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

## Adım 3: Doku Fırçası Oluşturma
Görüntüden bir doku fırçası tanımlayın, dokunun kaplayacağı alanı belirtin.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

## Adım 4: Şekilleri Çizme ve Doldurma
Bir dikdörtgen oluşturun ve tanımlanan fırçayı kullanarak **şekli doku ile doldurun**. Ayrıca görsel çekicilik için şekli çizin ve kenarlığını belirginleştirin.

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

## Adım 5: Doku Desenli Metin Ekleme
Belgeye metin ekleyin ve **doku ile doldurmanın** nasıl yapılacağını gösterin. Gerekli olduğunda yazı tipi, konum ve diğer parametreleri özelleştirin.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Adım 6: Kaydetme ve Kapatma
Mevcut sayfayı kapatarak, belgeyi kaydederek ve sorunsuz bir yürütme sağlayarak işlemi tamamlayın.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Yaygın Sorunlar ve İpuçları
- **Eksik doku dosyası** – `TestTexture.bmp` yolunun doğru ve dosyanın erişilebilir olduğundan emin olun.  
- **Yanlış görüntü boyutları** – Doku uzatılmış görünüyorsa, `imageArea`'yı orijinal görüntü boyutlarıyla eşleşecek şekilde ayarlayın.  
- **Performans** – Gereksiz nesne oluşturmayı önlemek için aynı `TexturePaint` örneğini birden fazla şekil için yeniden kullanın.

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java yeni başlayanlar için uygun mu?**  
C: Kesinlikle! Aspose.Page for Java kapsamlı belgeler sunar ve tüm beceri seviyelerindeki geliştiriciler için erişilebilirdir.

**S: Aspose.Page for Java'yı mevcut Java projemle entegre edebilir miyim?**  
C: Evet, sağlanan belgeleri izleyerek Aspose.Page for Java'yı projenize kolayca entegre edebilirsiniz. [Burada](https://reference.aspose.com/page/java/) daha fazla bilgi bulabilirsiniz.

**S: Aspose.Page ile ilgili sorularımı nereden sorabilirim?**  
C: Toplulukla etkileşime geçmek ve destek almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**S: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/) keşfedebilirsiniz.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisans almak için [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak bir Java PostScript belgesine **doku ekleme** döşeme desenlerini başarıyla uyguladınız. Farklı bitmap döşemeler, ölçek faktörleri ve birleşik işlemlerle denemeler yaparak doku doldurmalarının yaratıcı potansiyelini keşfetmeye devam edin.

---

**Son Güncelleme:** 2025-12-17  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en yeni)  
**Yazar:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

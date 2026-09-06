---
date: 2026-08-23
description: aspose.page image manipulation java'yı kullanarak PostScript dosyalarında
  resimleri gömmeyi ve döndürmeyi, net Java örnekleriyle öğrenin.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Java PostScript'te Resim Ekle
og_description: aspose.page image manipulation java'yı kullanarak PostScript dosyalarında
  resimleri gömmeyi ve döndürmeyi, adım adım Java kod örnekleriyle öğrenin.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: aspose.page image manipulation java kullanarak resim ekleme
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: aspose.page image manipulation java kullanarak resim ekleme
url: /tr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page görüntü işleme java'yı resim eklemek için nasıl kullanılır

## Giriş
Bu öğreticide, **aspose.page image manipulation java**'yı kullanarak PostScript dosyaları oluşturmayı, raster görüntüler eklemeyi ve çeviri‑ve‑dönme dönüşümlerini uygulamayı öğreneceksiniz. Kılavuzun sonunda, Java'dan piksel‑tam PostScript çıktısı üretebilecek, otomatik raporlama, baskı hatları veya PostScript belgesi içinde kesin görüntü yerleştirme gerektiren herhangi bir iş akışı için ideal bir çözüm elde edeceksiniz.

## Hızlı cevaplar
- **Hangi kütüphane gereklidir?** Aspose.Page for Java  
- **Birden fazla resim ekleyebilir miyim?** Evet – her resim için dönüşümü ve çizim adımlarını tekrarlayın  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme testi için çalışır; üretim için lisans gereklidir  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri  
- **Görüntü döndürme destekleniyor mu?** Kesinlikle – `AffineTransform.rotate()` kullanın  

## aspose.page image manipulation java nedir?
`aspose.page image manipulation java` Aspose.Page API'sidir ve Java kodundan PostScript belgeleri oluşturmanıza, düzenlemenize ve render etmenize olanak tanır; görüntü yerleştirme, ölçekleme ve döndürme üzerinde tam kontrol sağlar. Bu API sayesinde düşük seviyeli PostScript sözdiziminden kaçınır ve kütüphane format dönüşümünü ve gömmeyi dahili olarak yönetir.

## Neden aspose.page görüntü işleme için kullanmalı?
Aspose.Page **50+ görüntü formatı** (JPEG, PNG, BMP, TIFF dahil) sunar ve bunları PostScript'e belgeyi tamamen belleğe yüklemeden gömebilir; bu sayede yüzlerce sayfalı dosyaları işleyebilir ve tipik bir sunucuda bellek kullanımını 100 MB altında tutabilirsiniz. Yüksek seviyeli API, karmaşık PostScript komutlarını soyutlar, böylece ham PS operatörleri yerine özlü Java kodu yazarsınız.

## Önkoşullar
- Java Development Kit (JDK) 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Page for Java kütüphanesi – **[Aspose.Page for Java indirme sayfası](https://releases.aspose.com/page/java/)**'nden indirin.  
- Java sözdizimi ve nesne‑yönelimli programlamaya temel aşinalık.

## create postscript java nedir?
Java'dan bir PostScript dosyası oluşturmak, `.ps` uzantılı bir belgeyi programatik olarak üretmek anlamına gelir; bu belge sayfa düzeni, vektör grafikler ve raster görüntüler gibi öğeleri PostScript diliyle tanımlar. Aspose.Page, Java çağrılarınızı geçerli PostScript talimatlarına dönüştürerek ayrı bir PostScript yorumlayıcısına ihtiyaç duymadan baskıya hazır dosyalar üretmenizi sağlar.

## Çeviri ve döndürme adımlarıyla bir resmi nasıl eklenir

Resminizi yükleyin, bir `AffineTransform` uygulayın ve sayfaya çizin. Aşağıdaki adımlar izlemeniz gereken tam sıralamayı gösterir.

### Adım 1: grafik kaydet
Grafik durumunu kaydetmek, dönüşümlerinizi izole eder, böylece daha sonra geri dönebilirsiniz. Bu, ham PostScript'teki `gsave` operatörüne eşdeğerdir.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Adım 2: çevir ve dönüştür (resmi çevir ve döndür)
Öncelikle kaynak dosyadan bir `BufferedImage` oluşturun, ardından görüntüyü istenen koordinatlara taşıyan ve merkez etrafında döndüren bir `AffineTransform` oluşturun. `AffineTransform.rotate` bir açı bekler; dereceleri `Math.toRadians(degrees)` ile radyana çevirin.

**AffineTransform**, çeviri, döndürme, ölçekleme veya kaydırma gibi 2‑D afin dönüşümünü temsil eden bir Java sınıfıdır.  
**BufferedImage**, bir görüntüyü piksel rasteri olarak bellekte saklayan bir Java sınıfıdır.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Adım 3: belgeye resmi ekle
Dönüşümü yapılandırdıktan sonra, resmi mevcut sayfaya çizin. Kütüphane, `BufferedImage`'ı uygun bir PostScript görüntü akışına otomatik olarak dönüştürür.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Adım 4: grafik geri yükle
`grestore` çağrısı, grafik durumunu kaydetmeden önceki haline geri döndürür; böylece sonraki çizim komutları önceki dönüşümden etkilenmez.

```java
document.drawImage(image, transform, null);
```

### Adım 5: mevcut sayfayı kapat ve kaydet
Sayfayı tamamlayın, belgeyi kapatın ve çıktıyı diske yazın.

```java
document.writeGraphicsRestore();
```

Yukarıdaki diziyi tekrarlayarak ek görüntüler gömebilir, her seferinde çeviri koordinatlarını ve döndürme açısını ayarlayabilirsiniz.

## Yaygın sorunlar ve çözümler
- **FileNotFoundException:** `dataDir`'in bir dosya ayırıcı (`/` veya `\\`) ile bittiğini ve görüntü dosya adının tam olarak eşleştiğini doğrulayın.  
- **ImageIO.read null döndürüyor:** Görüntü formatının desteklenen listede (JPEG, PNG, BMP, GIF, TIFF) olduğundan emin olun.  
- **Yanlış döndürme açısı:** `AffineTransform.rotate` radyan ile çalışır; dereceden radyana dönüştürmek için `Math.toRadians(degrees)` kullanın.  
- **Büyük sayfalarda bellek dalgalanmaları:** Bellek kullanımını azaltmak için `Document.save` ile `saveOptions.setCompress(true)` kullanın.

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'yı diğer programlama dilleriyle kullanabilir miyim?**  
C: Çekirdek kütüphane yalnızca Java içindir, ancak Aspose .NET, C++ ve Python için eşdeğer API'ler sunar; her biri kendi platformuna göre uyarlanmıştır.

**S: Aspose.Page for Java için ücretsiz bir deneme mevcut mu?**  
C: Evet, ücretsiz deneme **[Aspose.Page ücretsiz deneme sayfası](https://releases.aspose.com/)** üzerinden erişilebilir.

**S: Aspose.Page for Java için geçici bir lisans nasıl alınır?**  
C: Geçici lisansı **[geçici lisans talep sayfası](https://purchase.aspose.com/temporary-license/)** üzerinden alabilirsiniz.

**S: Aspose.Page for Java ile ilgili topluluk desteği ve tartışmalara nereden ulaşabilirim?**  
C: Topluluk yardımı için **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**'u ziyaret edin.

**S: Aspose.Page for Java satın almak için ek kaynaklar var mı?**  
C: Kütüphaneyi **[Aspose.Page satın alma sayfası](https://purchase.aspose.com/buy)** üzerinden satın alabilirsiniz.

## Sonuç
Artık **aspose.page image manipulation java** kullanarak bir PostScript dosyası oluşturma, bir resmi çevirme ve döndürme ve sonucu kaydetme konusunda tam bir uçtan uca örneğe sahipsiniz. Gelişmiş özellikleri keşfetmek için tam **[belgelendirmeye](https://reference.aspose.com/page/java/)** göz atın; vektör grafikler, özel sayfa boyutları ve metin renderleme gibi konular mevcuttur.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## İlgili Öğreticiler

- [Aspose.Page Java API kullanarak PostScript'i PDF'ye Dönüştürme](/page/java/postscript-conversion/to-pdf/)
- [Java PostScript'te Çapraz Gradyan Ekleme: Aspose.Page Java kullanarak](/page/java/postscript-gradient-addition/diagonal/)
- [Java PostScript'te Tarama Deseni Ekleme Aspose.Page ile](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
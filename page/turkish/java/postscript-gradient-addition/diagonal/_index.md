---
date: 2025-12-07
description: Aspose.Page Java kullanarak Java PostScript belgelerinizi diyagonal degrade
  ile geliştirin. Java'da LinearGradientPaint ile degrade efektleri eklemeyi öğrenin
  ve canlı renk geçişlerini zahmetsizce oluşturun.
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java kullanarak Java PostScript'e Diyagonal Gradyan Ekle
url: /tr/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Kullanarak Java PostScript'te Diagonal Gradient Ekleme

## Giriş
PostScript dosyasını yumuşak bir diagonal renk geçişiyle zenginleştirmek istiyorsanız, **Aspose.Page Java** bunu şaşırtıcı derecede kolaylaştırıyor. Bu öğreticide, Java 2D'den `LinearGradientPaint` sınıfını kullanarak **gradient nasıl eklenir** adım adım inceleyeceğiz. Sonunda, canlı bir diagonal gradient içeren bir PostScript belgesi oluşturan, çalıştırmaya hazır bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for Java.  
- **Gradient'i oluşturan sınıf hangisidir?** `LinearGradientPaint`.  
- **Renkleri değiştirebilir miyim?** Evet – `Color[]` dizisini değiştirin.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Uygulama ne kadar sürer?** Temel bir gradient için yaklaşık 10 dakika.

## Aspose.Page Java Nedir?
Aspose.Page Java, geliştiricilerin dış bir yazılım gerektirmeden PostScript ve PDF dosyalarını oluşturmasını, düzenlemesini ve dönüştürmesini sağlayan güçlü bir API'dir. PostScript dilinin tam grafik yeteneklerini temiz, nesne‑yönelimli bir Java arayüzü üzerinden sunar.

## Neden diagonal gradient kullanmalı?
Diagonal gradient, grafiklere derinlik ve görsel ilgi katar; grafikler, afişler veya modern bir görünüme ihtiyaç duyan herhangi bir öğe için idealdir. Gradient bir köşeden karşı köşeye uzandığı için arka planlar, düğme kaplamaları ve süsleme şekilleri için çok uygundur.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java Development Kit (JDK) 8 veya üzeri.  
- Eclipse, IntelliJ IDEA veya VS Code gibi bir IDE.  
- **Aspose.Page for Java** kütüphanesi – en son sürümü [resmi indirme sayfasından](https://releases.aspose.com/page/java/) indirin.

## Paketleri İçe Aktarma
İlk olarak, ihtiyacınız olan Java 2D ve Aspose sınıflarını içe aktarın. Bu importlar, renk tanımlamaları, geometrik şekiller, gradient boyama ve PostScript belge API'sine erişim sağlar.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Adım 1: PostScript Belgesi için Çıktı Akışı Oluşturma
Dosyanın kaydedileceği klasörü tanımlayıp bir `FileOutputStream` açarak başlarız. Bu akış, oluşturulan PostScript verilerini alacaktır.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Adım 2: A4 Boyutlu Kaydetme Seçenekleri Oluşturma
`PsSaveOptions`, sayfa boyutu, çözünürlük ve diğer çıktı ayarlarını belirlemenizi sağlar. Burada varsayılan A4 boyutunu kullanıyoruz.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Adım 3: Yeni PS Belgesi Oluşturma
Çıktı akışı ve kaydetme seçenekleriyle bir `PsDocument` örneği oluşturun. `false` bayrağı, yapıcıya otomatik olarak yeni bir sayfa açmamasını söyler – bunu daha sonra yapacağız.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 4: Bir Dikdörtgen Oluşturma
Gradient doldurmasını alacak dikdörtgeni tanımlayın. Dikdörtgenin konumu (200, 100) ve boyutu (200 × 100), gradientin net görülmesini sağlar.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Adım 5: Gradient Dönüşümü Oluşturma
`AffineTransform`, gradienti dikdörtgen boyunca diagonal olarak çalışacak şekilde döndürmemizi, ölçeklememizi ve kaydırmamızı sağlar. Aşağıdaki matematik, hipotenüsü hesaplar ve ölçek oranını buna göre ayarlar.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Adım 6: Diagonal Lineer Gradient Boyası Oluşturma
İşte **gradient nasıl eklenir** sorusunun çekirdeği – daha önce tanımlanan dönüşümü kullanarak dikdörtgenin sol‑üst köşesinden sağ‑alt köşesine uzanan bir `LinearGradientPaint` oluşturuyoruz. `MultipleGradientPaint.CycleMethod.NO_CYCLE` gradientin tekrarlanmamasını sağlar.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Adım 7: Boyayı Ayarla ve Dikdörtgeni Doldur
Gradient boyasını belgeye uygulayın ve dikdörtgen şekliyle doldurun. Bu adım, diagonal renk geçişini PostScript sayfasına çizer.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Adım 8: Mevcut Sayfayı Kapat ve Belgeyi Kaydet
Son olarak, sayfayı kapatın, akışı boşaltın ve dosyayı kaydedin. Ortaya çıkan `DiagonalGradient_outPS.ps` dosyası herhangi bir PostScript görüntüleyiciyle açılabilir.

```java
// Close current page and save the document
document.closePage();
document.save();
```

Bu sekiz adımı izleyerek **Aspose.Page Java** kullanarak bir PostScript belgesine diagonal gradient başarıyla eklediniz. Farklı renkler, açı ve dikdörtgen boyutlarıyla deneyler yaparak özel görsel efektler oluşturabilirsiniz.

## Yaygın Sorunlar ve İpuçları
- **Gradient düz görünüyor** – dönüş açısını kontrol edin; 45° dönüş gerçek bir diagonal oluşturur.  
- **Renkler soluk görünüyor** – doğru renk işleme için `MultipleGradientPaint.ColorSpaceType.SRGB` kullandığınızdan emin olun.  
- **Dosya bulunamadı hatası** – `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanın yazma iznine sahip olduğunu doğrulayın.

## Sık Sorulan Sorular

**S: Bu kütüphaneyi Java'da başka grafik işlemleri için de kullanabilir miyim?**  
C: Evet, Aspose.Page for Java, tam bir çizim primi­tif seti, metin işleme ve görüntü yönetimi yetenekleri sunar.

**S: Aspose.Page Java için ücretsiz bir deneme sürümü mevcut mu?**  
C: Kesinlikle. Tam işlevsel bir deneme sürümünü [Aspose ücretsiz deneme sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Page Java dokümantasyonunu nerede bulabilirim?**  
C: Resmi API referansı [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aspose.Page Java için lisans nasıl satın alınır?**  
C: Lisanslar doğrudan [Aspose satın alma portalından](https://purchase.aspose.com/buy) alınabilir.

**S: Yardıma ihtiyacım var ya da sorularım var mı?**  
C: Hem Aspose mühendislerinden hem de topluluk geliştiricilerinden yardım almak için topluluk‑temelli [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

---

**Son Güncelleme:** 2025-12-07  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
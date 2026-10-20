---
date: 2026-10-20
description: Aspose.Page for Java ile dikdörtgeni nasıl ölçeklendireceğinizi, şekli
  nasıl çevireceğinizi ve PostScript belgeleri oluşturmak için affine transform'u
  nasıl uygulayacağınızı öğrenin.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java sayfa işleme içinde dönüşümler
og_description: Aspose.Page for Java kullanarak dikdörtgeni ölçeklendirme, şekli çevirme
  ve affine transform'u uygulayarak PostScript dosyalarını verimli bir şekilde oluşturmayı
  öğrenin.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Aspose.Page for Java ile dikdörtgeni ölçeklendirme – adım adım rehber
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Aspose.Page for Java ile Dikdörtgeni Ölçeklendirme
url: /tr/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java ile dikdörtgeni ölçeklendirme

## Giriş
Bu rehberde Aspose.Page for Java kullanarak **dikdörtgen nesnelerini nasıl ölçeklendireceğinizi** keşfedecek, şekil konumlarını nasıl çevireceğinizi, grafikleri nasıl döndüreceğinizi ve yüksek kaliteli PostScript çıktısı üretmek için afin dönüşüm işlemlerini nasıl uygulayacağınızı öğreneceksiniz. Bu teknikler, düşük seviyeli render kodu yazmadan cihaz bağımsız grafikler oluşturmanızı sağlar ve Java uygulamalarınızı daha güçlü ve sürdürülebilir kılar.

## Hızlı yanıtlar
`scale(sx, sy)` grafik bağlamını verilen yatay ve dikey faktörlerle ölçeklendirir.  

- **Java'da Aspose.Page ile bir dikdörtgeni nasıl ölçeklendirebilirim?** Dikdörtgeni çizmeye başlamadan önce grafik bağlamı üzerinde `scale(sx, sy)` metodunu çağırın.  
- **Diğer grafikleri etkilemeden bir şekli (çevirme) taşıyabilir miyim?** Evet—çevirme işlemini `writeGraphicsSave()` ve `writeGraphicsRestore()` çağrileri arasında sarın.  
- **Hangi sınıf bir PostScript dosyası oluşturur?** `PsDocument` sınıfını `PsSaveOptions` ile birlikte kullanın.  
- **Üretim kullanımında bir lisansa ihtiyacım var mı?** Ticari dağıtımlar için geçerli bir Aspose.Page lisansı gereklidir.  
- **Hangi Java sürümü destekleniyor?** Aspose.Page Java 8 ve üzeri sürümlerle çalışır.

## Önkoşullar
Başlamadan önce şunları doğrulayın:

- Temel Java sözdizimi ve nesne‑yönelimli kavramlara sağlam bir hakimiyet.  
- Aspose.Page for Java kütüphanesinin yüklü olması. [Aspose.Page for Java belgeleri](https://reference.aspose.com/page/java/) adresinden indirebilirsiniz.  
- Kütüphanenin JAR dosyalarını sınıf yoluna eklemiş bir Java IDE'si (IntelliJ IDEA, Eclipse veya VS Code).

## Paketleri içe aktar
`PsDocument` bir PostScript belgesi oluşturmak için kullanılan ana sınıftır ve `PsSaveOptions` belgenin nasıl kaydedileceğini yapılandırır.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## “how to scale rectangle” Aspose.Page'de ne anlama geliyor?
`scale(float sx, float sy)` metodu, mevcut grafik durumuna bir afin ölçekleme dönüşümü uygular ve sonraki çizimleri `sx` (yatay) ve `sy` (dikey) faktörleriyle yeniden boyutlandırır. Bu, **how to scale rectangle** anahtar kelimesinin temel işlemidir. Bu dönüşümü çizmeden önce uygulayarak, sonraki şekiller (örneğin dikdörtgenler) yeni boyutlarla, oranlarını koruyarak render edilir.

## Aspose.Page ile şekli nasıl çeviririm
`writeGraphicsSave()` mevcut grafik durumunu kaydeder ve `writeGraphicsRestore()` onu geri yükler, böylece dönüşümler yalnızca hedef şekli etkiler. Çevirme, koordinat sisteminin orijini nesne boyutlarını değiştirmeden yeniden konumlandırır. `translate(dx, dy)` metodunu `writeGraphicsSave()` / `writeGraphicsRestore()` arasında sararak, yalnızca istenen şeklin hareket ettiğinden ve diğer grafiklerin değişmediğinden emin olursunuz; bu, bireysel öğeler üzerinde hassas kontrol sağlar.

## Örnek 1: dönüşüm yok
İlk örnek, herhangi bir dönüşüm uygulanmadan bir dikdörtgen çizer ve sonraki örneklerle görsel karşılaştırma için bir temel oluşturur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Örnek 2: çevirme
Bu örnekte, ikinci bir dikdörtgen çizmeye başlamadan önce grafik bağlamını 250 birim sağa kaydırarak **how to translate shape** gösterilir.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Örnek 3: ölçekleme
Burada temel soruya yanıt veriyoruz: **how to scale rectangle**. Dikdörtgen, `scale(0.5f, 0.75f)` çağrısı ile orijinal genişliğinin %50'si ve yüksekliğinin %75'i kadar küçültülür.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Java'da şekli döndürme (rotate shape java)
`rotate(angle)` koordinat sistemini belirtilen açı (derece) kadar döndürür. `PsDocument` nesnenizi yükleyin, grafik durumunda `rotate(angle)` metodunu çağırın, şekli çizin ve ardından önceki duruma geri dönün. Bu desen, **rotate shape java** ve **how to rotate rectangle** ifadelerini tek, yeniden kullanılabilir bir blokta uygular ve grafikleri istediğiniz herhangi bir nokta etrafında döndürmenizi sağlar.

## Neden önemli – gerçek dünya faydaları
- **Cihaz‑bağımsız çıktı** – Aspose.Page, herhangi bir yazıcı veya görüntüleyicide aynı şekilde render edilen PostScript ve XPS dosyaları üretebilir, platform‑spesifik ayarlamaları ortadan kaldırır.  
- **İnce‑düzey kontrol** – Çevirme, ölçekleme, kaydırma ve döndürmeyi birleştirerek kesin yerleşim gereksinimlerini karşılayabilirsiniz; API sayfa başına 20’den fazla dönüşüm kombinasyonunu destekler.  
- **Performans‑odaklı işleme** – Kütüphane, tipik 100‑sayfalık raporlar için bellek ayak izini 10 MB’nin altında tutar, toplu işler hızlı ve ölçeklenebilir olur.

## Yaygın kullanım senaryoları
- **Yazdırılabilir faturalar** – Logoları, barkodları ve tabloları ölçekleme ve çevirme ile tam olarak konumlandırarak kurumsal marka yönergelerine uymak.  
- **Teknik diyagramlar** – Her bileşenin orantılı olarak yeniden boyutlandırılması ve konumlandırılması gereken şemalar oluşturmak.  
- **Otomatik çok‑sayfalı raporlar** – Mühendislik spesifikasyonları gibi sayfalar arasında tutarlı ölçekleme gerektiren PostScript raporları üretmek.

## Yaygın sorunlar ve çözümler
- **Dönüşüm sıfırlanmıyor** – Her zaman `writeGraphicsSave()` ile `writeGraphicsRestore()` eşleştirin; aksi takdirde sonraki çizimler istenmeyen dönüşümleri devralır.  
- **Beklenmeyen renkler** – Her dönüşümden sonra boya (renk) ayarlayın; çünkü grafik durumu bir geri yüklemeden sonra renk bilgisini korumaz.  
- **Dosya boyutu çok büyük** – `PsSaveOptions` içinde sıkıştırmayı etkinleştirin ve gömülü raster görüntü çözünürlüğünü sınırlayarak tipik 50‑sayfalık belgeler için nihai dosyayı 5 MB’nin altında tutun.

## SSS
### Aspose.Page for Java'yı başka belge formatları için kullanabilir miyim?
Aspose.Page öncelikle PostScript ve XPS formatları için sayfa manipülasyonuna odaklanır, ancak sınırlı PDF dışa aktarma yetenekleri de sunar.

### Aspose.Page for Java için daha fazla örnek ve belge nerede bulunabilir?
Kapsamlı kılavuzlar, API referansları ve örnek projeler için [Aspose.Page for Java belgeleri](https://reference.aspose.com/page/java/) adresini ziyaret edin.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, **Aspose ücretsiz deneme indirme** sayfası üzerinden ücretsiz bir deneme erişebilirsiniz: [Aspose ücretsiz deneme indirme](https://releases.aspose.com/).

### Aspose.Page for Java için geçici bir lisans nasıl alınır?
**Geçici lisans talep sayfası** üzerinden geçici bir lisans edinebilirsiniz: [geçici lisans talep sayfası](https://purchase.aspose.com/temporary-license/).

### Aspose.Page for Java hakkında topluluk desteği veya soru sorabileceğim yer neresi?
Topluluk tartışmaları, kod parçacıkları ve sorun giderme ipuçları için [Aspose.Page for Java forumu](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

## Sıkça sorulan sorular

**S: `translate` ve `scale` arasındaki fark nedir?**  
C: `translate` koordinat sisteminin orijini taşırken, `scale` X ve/veya Y ekseninde çizilen nesnelerin boyutunu değiştirir.

**S: Tek bir grafik durumunda birden fazla dönüşümü birleştirebilir miyim?**  
C: Evet—çizmeden önce `translate`, `scale`, `rotate` veya `shear` metodlarını sırasıyla çağırarak birleşik bir afin dönüşüm oluşturabilirsiniz.

**S: Bir şekli çizmeyi takiben dönüşümleri nasıl sıfırlarım?**  
C: Önceden kaydedilmiş grafik durumuna geri dönmek için `writeGraphicsRestore()` kullanın.

**S: Bir dikdörtgeni merkezine göre döndürebilir miyim?**  
C: Kesinlikle. Dikdörtgeni orijine taşıyın, `rotate(angle)` uygulayın, ardından tekrar orijinal konumuna geri taşıyarak çizin.

**S: Aspose.Page daha pürüzsüz grafikler için anti‑aliasing destekliyor mu?**  
C: Evet—anti‑aliasing'i etkinleştirmek için `PsSaveOptions` içinde uygun render seçeneklerini ayarlayın.

---

**Son Güncelleme:** 2026-10-20  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [Java PostScript'te Aspose.Page ile Dikdörtgen Çizme](/page/java/postscript-shapes/add-rectangle/)
- [Aspose.Page for Java ile PostScript'te Radyal Gradyan Oluşturma](/page/java/postscript-gradient-addition/)
- [Postscript Sayfa Manipülasyonu](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
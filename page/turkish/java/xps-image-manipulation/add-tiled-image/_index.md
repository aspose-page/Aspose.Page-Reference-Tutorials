---
date: 2026-05-30
description: Aspose.Page kullanarak Java'da XPS belgesi oluşturmayı ve döşeli görüntüyü
  zahmetsizce eklemeyi bu adım adım rehberle öğrenin. XPS dosyalarını hızlı bir şekilde
  nasıl oluşturacağınızı keşfedin.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Java XPS'de Döşeli Görüntü Ekle
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java'da Döşeli Görüntü ile XPS Belgesi Nasıl Oluşturulur
url: /tr/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Döşeli Görüntülü XPS Belgesi Nasıl Oluşturulur

## Giriş
XPS belgelerini programlı olarak oluşturmak, yazdırılabilir ve cihaz‑bağımsız çıktı ihtiyacı olan Java geliştiricileri için temel bir beceridir. **XPS nasıl oluşturulur** dosyalarını verimli bir şekilde oluşturma sorusuna, düşük seviyeli XML Paper Specification detaylarını soyutlayan ve görsel tasarıma odaklanmanızı sağlayan Aspose.Page for Java yanıt verir. Bu rehberde, bir XPS belgesi nasıl oluşturulur, arka plan veya desen olarak döşeli bir görüntü nasıl eklenir ve sonuç nasıl kaydedilir, tüm bunları kısa ve üretim‑hazır kodla göreceksiniz.

## Hızlı Yanıtlar
- **Aspose.Page ne yapar?** Java'da XPS belgeleri oluşturmak ve manipüle etmek için yüksek seviyeli bir API sağlar.  
- **Bir görüntüyü döşeyebilir miyim?** Evet – `XpsImageBrush` ile `XpsTileMode.Tile` kullanın.  
- **Lisans gerekir mi?** Üretim kullanımı için geçici veya ticari bir lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** JDK 8 ve üzeri tüm sürümler uyumludur.  
- **Uygulama ne kadar sürer?** Temel bir döşeli‑görüntü senaryosu için yaklaşık 10–15 dakika.

## “XPS belgesi oluşturma” nedir?
`XpsDocument`, Aspose.Page'in bellekte tek bir XPS dosyasını temsil eden üst‑seviye nesnesidir. Sayfaları, kaynakları ve meta verileri kapsar, böylece belgeyi programlı olarak oluşturabilirsiniz. XPS belgesi oluşturmak, bu sınıfın bir örneğini oluşturmak, görsel öğeler eklemek ve sonunda `save` metodunu çağırarak sabit‑düzen dosyasını diske yazmak anlamına gelir. Bu yaklaşım, manuel XML işlemlerini ortadan kaldırır ve XML Paper Specification'a uyumu garanti eder.

## Neden döşeli bir görüntü eklenir?
Döşeme, bir grafiği tanımlı bir alanda tekrar eder; bu, arka planlar, filigranlar veya desen doldurmaları için idealdir. `XpsTileMode.Tile` kullanarak görüntü, manuel çoğaltma olmadan otomatik olarak tekrar eder, geliştirme süresini tasarruf eder ve herhangi bir cihazda tutarlı render almayı sağlar. Döşeli görüntüler ayrıca aynı bitmap kaynağının birden çok kez gömülmesi yerine yeniden kullanılması sayesinde dosya boyutunu düşük tutar.

## Önkoşullar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm yüklü olmalıdır.  
2. **Aspose.Page for Java** – [web sitesinden](https://releases.aspose.com/page/java/) indirin.  
3. **Yazılabilir bir dizin** – oluşturulan XPS dosyasının kaydedileceği yer.

## Paketleri İçe Aktarma
Java projenizde gerekli sınıfları içe aktarın:

`XpsDocument` XPS dosyasını temsil eden ana nesnedir.  
`XpsImageBrush` şekilleri bir görüntü kaynağıyla doldurur.  
`XpsTileMode` bir görüntünün nasıl döşeneceğini belirler.  
`Rectangle2D` konumlandırma için dikdörtgen bir bölge tanımlar.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Adım‑Adım Kılavuz

### Adım 1: Projenizi Kurun
Aspose.Page JAR dosyalarını projenizin sınıf yoluna ekleyin ve içe aktarma ifadelerinin hatasız derlendiğini doğrulayın.

### Adım 2: XPS Belgesi Oluşturun
`XpsDocument`, sayfaları, yolları ve kaynakları tutan temel kapsayıcıdır. İstediğiniz sayfa boyutuyla bir örnek oluşturun, ardından grafik öğeler eklemeye başlayabilirsiniz.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Adım 3: Döşeli Görüntü Yolunu Tanımlayın
Döşemek istediğiniz görüntüyü (ör. `R08LN_NN.jpg`) `dataDir` tarafından referans verilen dizine yerleştirin. Görüntü bir fırça deseni olarak kullanılacak.

### Adım 4: Döşeli Görüntü Ekle
Bir dikdörtgen yol oluşturun ve onu bir `XpsImageBrush` ile doldurun. Döşeme modunu `Tile` olarak ayarlayarak görüntü dikdörtgen boyunca tekrar eder. Kaynak ve hedef dikdörtgenleri ayarlayarak döşeme boyutunu ve konumunu kontrol edin.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Adım 5: Belgeyi Kaydedin
XPS dosyasını diske kaydedin. Çıktı dosyası, az önce tanımladığınız döşeli görüntüyü içerecek ve herhangi bir XPS görüntüleyici ile açılabilir.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Aynı XPS belgesi içinde diğer sayfalara veya şekillere **döşeli görüntü ekle**meniz gerektiğinde bu adımları tekrarlayın.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| Görüntü görünmüyor | Dosya yolunun (`dataDir + "R08LN_NN.jpg"`) doğru ve görüntünün erişilebilir olduğunu doğrulayın. |
| Döşeme deseni uzamış görünüyor | Döşeme boyutunu kontrol etmek için kaynak ve hedef `Rectangle2D` değerlerini ayarlayın. |
| Opaklık etkisiz | Fırçanın opaklığının döşeme modu yapılandırmasından **sonra** ayarlandığından emin olun. |

## Sık Sorulan Sorular

**S:** Aspose.Page tüm Java sürümleriyle uyumlu mu?  
**C:** Aspose.Page, Java 8'den Java 21'e kadar destekler; tam uyumluluk matrisini [burada](https://reference.aspose.com/page/java/) bulabilirsiniz.

**S:** Aspose.Page'i ticari projelerde kullanabilir miyim?  
**C:** Evet, üretim kullanımı için ticari bir lisans gereklidir. Satın alma seçenekleri [burada](https://purchase.aspose.com/buy) listelenmiştir.

**S:** Ücretsiz deneme sürümü mevcut mu?  
**C:** Tam işlevsel bir ücretsiz deneme sürümü, Aspose sürüm sayfasından [burada](https://releases.aspose.com/) indirilebilir.

**S:** Topluluk desteği nereden alınabilir?  
**C:** Sorular sormak ve örnek paylaşmak için Aspose.Page topluluk forumuna [forum](https://forum.aspose.com/c/page/39) adresinden katılın.

**S:** Değerlendirme için geçici lisans nasıl alınır?  
**C:** Geçici lisanslar, Aspose portalı üzerinden istek üzerine [burada](https://purchase.aspose.com/temporary-license/) sağlanır.

## Sonuç
Artık Aspose.Page for Java kullanarak döşeli görüntülerle **XPS belgesi nasıl oluşturulur** konusunda eksiksiz, üretim‑hazır bir iş akışına sahipsiniz. `XpsImageBrush` ve `XpsTileMode.Tile`'ı kullanarak dosya boyutunu artırmadan zengin, tekrar edilebilir grafikler oluşturabilirsiniz. Farklı döşeme boyutları, opaklık seviyeleri ve şekillerle deneyler yaparak karmaşık belge düzenleri oluşturun. Bir sonraki adımda, XPS dosyalarınızı daha da zenginleştirmek için vektör şekilleri veya metin bindirmeleri eklemeyi keşfedin.

---

**Son Güncelleme:** 2026-05-30  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en son)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Java XPS Belgelerine Görüntü Ekleme – Aspose.Page ile Basit Bir Kılavuz](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - XPS'e Sayfa Ekleme Eğitimi](/page/java/xps-page-manipulation/add-page/)
- [Aspose.Page Java Kullanarak XPS'i PDF'e Dönüştürme](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
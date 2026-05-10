---
date: 2026-02-18
description: Aspose.Page kullanarak Java PostScript'te dikdörtgen şekilleri çizmeyi
  öğrenin. Bu adım adım kılavuz, boya ayarlamayı, Java'da dikdörtgen rengini belirlemeyi
  ve canlı grafikler oluşturmayı gösterirken, dikdörtgeni verimli bir şekilde nasıl
  çizeceğinizi açıklar.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page ile Java PostScript'te Dikdörtgen Nasıl Çizilir
url: /tr/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript'te Aspose.Page ile Dikdörtgen Çizme

## Giriş
Java PostScript dosyası içinde **dikdörtgen çizme** şekilleri eklemeniz gerekiyorsa doğru yere geldiniz. Bu öğreticide Aspose.Page for Java kullanarak renkli dikdörtgenler eklemeyi, doldurma ve kontur ayarlarını kontrol etmeyi ve sonucu bir PostScript belgesi olarak kaydetmeyi adım adım göstereceğiz. **Boyama ayarlama**, dikdörtgenin geometrisini tanımlama ve bu yaklaşımın programatik olarak yazdırılabilir grafikler üretmek için neden ideal olduğunu tam olarak göreceksiniz. Kılavuzun sonunda **draw rectangle java** tekniklerinin daha geniş bağlamını ve **java awt rectangle drawing** iş akışlarına nasıl uyduğunu da anlayacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Dikdörtgen renklerini değiştirebilir miyim?** Evet – herhangi bir `java.awt.Color` ile `setPaint` kullanın  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterli; üretim için lisans gereklidir  
- **Örnekte hangi sayfa boyutu kullanılıyor?** A4 (varsayılan `PsSaveOptions`)  
- **Kod Java 8+ ile uyumlu mu?** Kesinlikle – standart AWT sınıflarını kullanıyor  

## PostScript'te “How to Draw Rectangle” Nedir?
PostScript belgesinde bir dikdörtgen çizmek, bir dikdörtgen bölge tanımlamak ve ya doldurmak, konturunu çizmek ya da her ikisini yapmak anlamına gelir. Aspose.Page ile bunu tanıdık **java awt rectangle drawing** sınıflarını kullanarak yapabilirsiniz; bu da kodun okunmasını ve bakımını kolaylaştırır.

## Neden Dikdörtgen Grafikleri İçin Aspose.Page Kullanmalı?
- **Çapraz platform**: Her türlü yazıcıda çalışan standart PostScript üretir.  
- **İnce ayar kontrolü**: Doldurma renklerini, kontur renklerini ve çizgi kalınlıklarını bağımsız olarak ayarlayabilirsiniz.  
- **Harici bağımlılık yok**: Sadece yerleşik AWT geometri sınıflarını kullanır, ekstra grafik kütüphanesine ihtiyaç duymazsınız.  

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Java programlamaya temel bir anlayış.  
- Aspose.Page for Java kütüphanesi yüklü. Yüklü değilse, [Aspose.Page for Java belgelerinden](https://reference.aspose.com/page/java/) indirebilirsiniz.  
- Makinenizde bir Java geliştirme ortamı kurulu.  

## Paketleri İçe Aktarma
Java projenizde gerekli paketleri içe aktararak başlayın. Bu içe aktarmalar, AWT’nin `Color`, `BasicStroke` ve `Rectangle2D` sınıflarına ve Aspose.Page’in temel belge işleme sınıflarına erişim sağlar.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Java PostScript'te Dikdörtgen Çizmek İçin Adım Adım Kılavuz

### Adım 1: Dikdörtgeni Doldurmak İçin Boyama Ayarla  
**Boyama ayarlama** – ilk dikdörtgen için turuncu bir doldurma rengi seçiyoruz. Bu, **set rectangle color java** yeteneğini gösterir.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Adım 2: Dikdörtgeni Konturlamak İçin Boyama Ayarla  
**Set rectangle color java** – şimdi boyamayı kırmızıya değiştirip bir kontur kalınlığı tanımlıyoruz. Bu örnek kısmı, **draw rectangle java** işlemini özel bir çizgi kalınlığıyla nasıl yapacağınızı gösterir.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Adım 3: Mevcut Sayfayı Kapat ve Belgeyi Kaydet  
Çizim tamamlandıktan sonra sayfayı kapatıp dosyayı kalıcı hale getiriyoruz. Sayfayı kapatmak, tüm çizim komutlarının PostScript akışına gönderilmesini sağlar.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Dikdörtgen Çizme İçin Yaygın Kullanım Senaryoları
- **Fatura veya makbuz oluşturma** – dikdörtgenler kenarlık veya vurgulama bölümleri olarak kullanılır.  
- **Etiket oluşturma** – ürün bilgilerini ayırmak için renkli kutular çizin.  
- **Basit grafikler** – doldurulmuş dikdörtgenleri çubuk grafik elemanları olarak kullanın.  
- **Özel yazdırılabilir formlar** – dikdörtgenleri metinle birleştirerek form alanları oluşturun.  

## Yaygın Sorunlar ve İpuçları
- **Dosya yolu hataları** – `dataDir` değişkeninin bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Lisans istisnaları** – deneme sürümü bir filigran ekler; üretim kullanımı için tam lisans alın.  
- **Renk görünürlüğü** – bazı yazıcılar belirli RGB değerlerini farklı yorumlayabilir; önce basit bir siyah dikdörtgenle test edin.  
- **Bellek kullanımı** – büyük belgeler için her sayfadan sonra akışı boşaltmayı (`document.closePage()`) düşünün.  

## Sık Sorulan Sorular

**S:** *Aspose.Page for Java’yı başka programlama dilleriyle kullanabilir miyim?*  
**C:** Aspose.Page öncelikle Java’yı destekler, ancak diğer diller için benzer kütüphaneler mevcuttur.

**S:** *Aspose.Page for Java için bir deneme sürümü var mı?*  
**C:** Evet, [ücretsiz deneme sürümünü](https://releases.aspose.com/) inceleyebilirsiniz.

**S:** *Ek yardım ve tartışma platformları nerede?*  
**C:** Toplulukla etkileşimde bulunmak ve destek almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**S:** *Aspose.Page for Java için geçici bir lisans nasıl alınır?*  
**C:** Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S:** *Aspose.Page for Java’nın lisanslı sürümünü nereden satın alabilirim?*  
**C:** Lisanslı sürümü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Ek Soru‑Cevap**

**S:** *Dikdörtgen boyutunu dinamik olarak değiştirebilir miyim?*  
**C:** Evet – `fill` veya `draw` çağırmadan önce `Rectangle2D.Float(x, y, width, height)` parametrelerini istediğiniz gibi değiştirin.

**S:** *Dikdörtgenin içine metin eklemek mümkün mü?*  
**C:** Kesinlikle. Dikdörtgeni çektikten sonra istediğiniz font ve konumla `document.drawString(...)` kullanın.

**S:** *Aspose.Page da daire veya çokgen gibi diğer şekiller destekleniyor mu?*  
**C:** Evet, API `drawEllipse` ve `drawPolygon` gibi çeşitli vektör grafik metodları sunar.

## Sonuç
Bu rehberde **dikdörtgen çizme** işlemini Java PostScript belgesinde nasıl gerçekleştireceğinizi, **boyama ayarlama** yöntemlerini ve Aspose.Page kullanarak **set rectangle color java** nasıl yapılacağını gösterdik. Artık faturalar, etiketler veya özel formlar gibi canlı yazdırılabilir grafikler oluşturmak için sağlam bir temele sahipsiniz. Farklı renkler, çizgi stilleri ve ek AWT şekilleriyle denemeler yaparak çıktınızı zenginleştirmekten çekinmeyin.

---

**Son Güncelleme:** 2026-02-18  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en yeni)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-11
description: Java PostScript'te dikdörtgen şekilleri çizmeyi öğrenin. Bu adım adım
  kılavuz, boya ayarlamayı, dikdörtgen rengini java'da ayarlamayı ve canlı grafikler
  oluşturmayı gösterir.
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
Java PostScript dosyası içinde **how to draw rectangle** şekillerine ihtiyacınız varsa, doğru yerdesiniz. Bu öğreticide Aspose.Page for Java kullanarak renkli dikdörtgenler eklemeyi, dolgu ve kontur kontrolünü ve sonucu bir PostScript belgesi olarak kaydetmeyi adım adım göstereceğiz. **how to set paint**'i tam olarak nasıl yapacağınızı, dikdörtgenin geometrisini nasıl tanımlayacağınızı ve bu yaklaşımın programatik olarak yazdırılabilir grafikler üretmek için neden ideal olduğunu göreceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gereklidir?** Aspose.Page for Java  
- **Dikdörtgen renklerini değiştirebilir miyim?** Yes – use `setPaint` with any `java.awt.Color`  
- **Geliştirme için lisansa ihtiyacım var mı?** A free trial works for testing; a license is required for production  
- **Örnekte hangi sayfa boyutu kullanılıyor?** A4 (default `PsSaveOptions`)  
- **Kod Java 8+ ile uyumlu mu?** Absolutely – it uses standard AWT classes  

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:
- Java programlamaya temel bir anlayış.  
- Aspose.Page for Java kütüphanesi yüklü. Yüklü değilse, [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) adresinden indirin.  
- Makinenizde bir Java geliştirme ortamı kurulu.  

## Paketleri İçe Aktarma
Java projenizde, gerekli paketleri içe aktararak başlayın:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Java PostScript'te Dikdörtgen Çizme
Aşağıda, net adımlara bölünmüş tam iş akışı yer almaktadır. Her adım kısa bir açıklama ve ardından orijinal kod bloğu (değiştirilmemiş) içerir.

### Adım 1: Dikdörtgeni Doldurmak İçin Paint Ayarla  
**How to set paint** – ilk dikdörtgen için turuncu bir dolgu rengi seçiyoruz.

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

### Adım 2: Dikdörtgeni Çizmek İçin Paint Ayarla  
**Set rectangle color java** – şimdi paint'i kırmızıya değiştirip bir kontur genişliği tanımlıyoruz.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Adım 3: Mevcut Sayfayı Kapat ve Belgeyi Kaydet  
Çizimden sonra sayfayı kapatıp dosyayı kalıcı hâle getiriyoruz.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Neden Dikdörtgen Grafiklerinde Aspose.Page Kullanmalı?
- **Cross‑platform**: Her yazıcıda çalışan standart PostScript üretir.  
- **Fine‑grained control**: Dolgu renklerini, kontur renklerini ve çizgi kalınlıklarını bağımsız olarak ayarlayabilirsiniz.  
- **No external dependencies**: Yalnızca yerleşik AWT geometri sınıflarını kullanır.  

## Yaygın Sorunlar ve İpuçları
- **File path errors** – `dataDir`'in bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **License exceptions** – deneme sürümü bir filigran ekler; üretim kullanımı için tam lisans alın.  
- **Color visibility** – bazı yazıcılar belirli RGB değerlerini farklı yorumlayabilir; önce basit bir siyah dikdörtgenle test edin.  

## Sonuç
Bu rehberde Java PostScript belgesinde **how to draw rectangle** şekillerini nasıl çizeceğimizi gösterdik, **how to set paint** konusunu ele aldık ve Aspose.Page kullanarak **set rectangle color java**'yu nasıl yapacağınızı gösterdik. Raporlar, faturalar veya özel baskılar için zengin yazdırılabilir grafikler oluşturmak amacıyla farklı şekiller, renkler ve çizgi stilleriyle denemeler yapmaktan çekinmeyin.

## Sıkça Sorulan Sorular

### Aspose.Page for Java'yu diğer programlama dilleriyle kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak diğer diller için benzer kütüphaneler mevcuttur.

### Aspose.Page for Java için bir deneme sürümü mevcut mu?
Evet, Aspose.Page for Java özelliklerini [free trial version](https://releases.aspose.com/) ile keşfedebilirsiniz.

### Ek yardım ve tartışmaları nerede bulabilirim?
Toplulukla etkileşimde bulunmak ve yardım almak için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

### Aspose.Page for Java için geçici bir lisans nasıl alabilirim?
Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

### Aspose.Page for Java'nın lisanslı sürümünü nereden satın alabilirim?
Lisanslı bir sürümü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Ek Soru&Cevap**

**S:** *Dikdörtgen boyutunu dinamik olarak değiştirebilir miyim?*  
**C:** Evet – `fill` veya `draw` çağırmadan önce `Rectangle2D.Float(x, y, width, height)` parametrelerini değiştirmeniz yeterlidir.

**S:** *Dikdörtgenin içine metin eklemek mümkün mü?*  
**C:** Kesinlikle. Dikdörtgeni çektikten sonra istediğiniz yazı tipi ve konumla `document.drawString(...)` kullanın.

**S:** *Aspose.Page daireler veya çokgenler gibi diğer şekilleri destekliyor mu?*  
**C:** Evet, API `drawEllipse` ve `drawPolygon` gibi çeşitli vektör grafikler için yöntemler sunar.

---

**Son Güncelleme:** 2025-12-11  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
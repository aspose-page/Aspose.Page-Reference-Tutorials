---
date: 2026-02-07
description: Aspose.Page for Java ile bir dikdörtgeni nasıl ölçeklendireceğinizi,
  şekli nasıl çevireceğinizi ve PostScript belgeleri oluşturmak için afin dönüşümünü
  nasıl uygulayacağınızı öğrenin.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page for Java ile Dikdörtgeni Ölçeklendirme
url: /tr/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java ile Dikdörtgeni Ölçeklendirme

## Giriş
**Aspose.Page for Java**'in güçlü özelliklerini kullanarak çeşitli sayfa dönüşümlerini gerçekleştirmek için kapsamlı bir rehbere hoş geldiniz. Bu öğreticide **dikdörtgeni nasıl ölçeklendireceğinizi**, şekilleri nasıl çevireceğinizi, nesneleri nasıl döndüreceğinizi ve **affine transform** tekniklerini **PostScript belgesi** oluştururken nasıl uygulayacağınızı öğreneceksiniz. Bu yetenekler, düşük seviyeli render kodlarıyla uğraşmadan zengin, grafik‑ağır Java uygulamaları oluşturmanıza olanak tanır.

## Hızlı Yanıtlar
- **Java'da Aspose.Page ile bir dikdörtgeni nasıl ölçeklendirebilirim?** Şekli çizmeye başlamadan önce `document.scale()` metodunu kullanın.  
- **Bir şekli (çevirme) diğer grafiklerden etkilenmeden hareket ettirebilir miyim?** Evet—grafik durumunu kaydedin, `document.translate(x, y)` çağırın, çizin, ardından durumu geri yükleyin.  
- **PostScript dosyasını hangi sınıf oluşturur?** `PsDocument` ve `PsSaveOptions`.  
- **Üretim ortamında bir lisansa ihtiyacım var mı?** Ticari dağıtımlar için geçerli bir Aspose.Page lisansı gereklidir.  
- **Hangi Java sürümü destekleniyor?** Aspose.Page Java 8 ve üzeri sürümlerle çalışır.

## Önkoşullar
Adım‑adım kılavuza geçmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Java programlama temelleri.  
- Aspose.Page for Java kütüphanesi yüklü. İndirmek için [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) sayfasını ziyaret edebilirsiniz.  
- Makinenizde bir Java Entegre Geliştirme Ortamı (IDE) kurulu.

## Paketleri İçe Aktarma
Java projenizde Aspose.Page for Java'ı kullanmak için gerekli paketleri içe aktarın:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page'de “dikdörtgeni nasıl ölçeklendirebilirim” nedir?
Bir dikdörtgeni ölçeklendirmek, X ve Y eksenleri boyunca boyutunu değiştirirken şeklini korumasını sağlar. Aspose.Page, mevcut grafik durumuna **affine transform** uygulayan `scale(float sx, float sy)` metodunu sunar. Bu, **dikdörtgeni nasıl ölçeklendirebilirim** anahtar kelimesinin temel tekniğidir.

## Aspose.Page ile Şekli Nasıl Çevirirsiniz
Çevirme, bir şeklin boyutlarını değiştirmeden yeni bir konuma taşınmasını sağlar. Bu, **şekli nasıl çeviririm** ifadesinin özüdür. Grafik durumunu kaydedip `translate(dx, dy)` uygulayarak, şekli çizer ve ardından durumu geri yükleyerek diğer nesnelerin etkilenmemesini sağlarsınız.

## Örnek 1: Dönüşüm Yok
İlk örnek, hiçbir dönüşüm uygulanmadan basit bir dikdörtgen çizer. Bu, sonraki örneklerle karşılaştırma için bir temel oluşturur.

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

## Örnek 2: Çevirme
Burada **şekli nasıl çeviririm** örneğini gösteriyoruz; ikinci bir dikdörtgen çizmeye başlamadan önce grafik bağlamını 250 birim sağa kaydırıyoruz.

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

## Örnek 3: Ölçekleme
Bu örnek, temel soruya **dikdörtgeni nasıl ölçeklendirebilirim** yanıtını verir. Dikdörtgeni orijinal genişliğinin %50'si ve yüksekliğinin %75'i kadar küçültüyoruz.

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

## Şekli Döndürme Java (rotate shape java)
Döndürme, bir diğer yaygın affine işlemdir. Döndürme için kod parçacıkları burada verilmemiştir, ancak desen aynıdır: grafik durumunu kaydedin, `document.rotate(angle)` çağırın, şekli çizin, ardından durumu geri yükleyin. Bu, **rotate shape java** ve **dikdörtgeni nasıl döndürürüm** kavramlarını pratiğe döker.

## Neden Önemli – Gerçek Dünya Faydaları
- **Cihaz‑bağımsız çıktı** – Tek seferde yazın ve platform‑spesifik ayarlamalar yapmadan PostScript veya XPS oluşturun.  
- **İnce ayar kontrolü** – Tam yerleşim gereksinimlerini karşılamak için çevirme, ölçekleme, kaydırma ve döndürmeyi birleştirin.  
- **Performans‑odaklı** – Büyük ölçekli belgelerin toplu işlenmesi için düşük maliyetli API.

## Ortak Kullanım Senaryoları
- Yazdırılabilir faturalar üretmek – örneğin, logoları ve barkodları tam konumlandıran bir **printable invoice java** çözümü.  
- Hassas ölçekleme ve konumlandırmanın gerektiği teknik diyagramlar oluşturmak.  
- PostScript formatında çok sayfalı raporların otomatik üretimi.

## Yaygın Sorunlar ve Çözümler
- **Dönüşüm sıfırlanmıyor** – İstenmeyen kalıcı etkileri önlemek için `document.writeGraphicsSave()` ile `document.writeGraphicsRestore()` çiftini her zaman eşleştirin.  
- **Beklenmedik renkler** – Her dönüşümden sonra boya ayarını yeniden yapın; grafik durumu bir geri yüklemeden sonra önceki renk ayarlarını tutmaz.  
- **Dosya boyutu çok büyük** – Raster grafik eklerken sıkıştırmayı etkinleştirmek veya çözünürlüğü düşürmek için `PsSaveOptions` kullanın.

## SSS
### Aspose.Page for Java'ı başka belge formatları için kullanabilir miyim?
Aspose.Page öncelikle PostScript ve XPS formatları için sayfa manipülasyonuna odaklanır.

### Aspose.Page for Java için daha fazla örnek ve belge nerede bulunur?
Kapsamlı bilgi için [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) sayfasını ziyaret edin.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page for Java için geçici bir lisans nasıl alınır?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### Aspose.Page for Java hakkında topluluk desteği veya soru sorabileceğim yer neresi?
Topluluk tartışmaları için [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) sayfasını ziyaret edin.

## Sıkça Sorulan Sorular

**S: `translate` ve `scale` arasındaki fark nedir?**  
C: `translate` koordinat sisteminin orijini taşırken, `scale` çizilen nesnelerin X ve/veya Y eksenindeki boyutunu değiştirir.

**S: Tek bir grafik durumunda birden fazla dönüşümü birleştirebilir miyim?**  
C: Evet—çizmeden önce `translate`, `scale`, `rotate` veya `shear` metodlarını sırasıyla çağırarak birleşik bir affine dönüşüm oluşturabilirsiniz.

**S: Bir şekli çektikten sonra dönüşümleri nasıl sıfırlarım?**  
C: Önceden kaydedilmiş grafik durumuna geri dönmek için `document.writeGraphicsRestore()` kullanın.

**S: Bir dikdörtgeni merkezine göre döndürebilir miyim?**  
C: Kesinlikle. Dikdörtgeni orijine taşıyın, `rotate(angle)` uygulayın, ardından tekrar orijinal konumuna geri taşıyarak çizin.

**S: Aspose.Page daha yumuşak grafikler için anti‑aliasing destekliyor mu?**  
C: Evet—anti‑aliasing'i etkinleştirmek için `PsSaveOptions` içinde uygun render seçeneklerini ayarlayın.

---

**Son Güncelleme:** 2026-02-07  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
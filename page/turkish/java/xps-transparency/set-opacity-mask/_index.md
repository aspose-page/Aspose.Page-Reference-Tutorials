---
date: 2026-04-30
description: Aspose.Page Java kullanarak XPS belgesi oluşturmayı ve bir opaklık maskesi
  eklemeyi öğrenin. Kod örnekleriyle adım adım rehber.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Java XPS'te Opaklık Maskesini Ayarla
second_title: Aspose.Page Java API
title: XPS Belgesi Oluşturma Java – Aspose.Page ile Opaklık Maskesi Ayarlama
url: /tr/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'te Opaklık Maskesi Ayarlama Aspose.Page Java ile

## Giriş
Bu öğreticide **create XPS document Java** dosyaları oluşturacak ve grafiğinize cilalı, yarı‑saydam bir görünüm kazandıran bir opaklık maskesi uygulamayı öğreneceksiniz. Aspose.Page Java API'sını kullanarak tüm süreci adım adım inceleyeceğiz — bir XPS belgesi başlatmaktan, kanvas eklemeye, bir dikdörtgen çizmeye ve görüntü‑tabanlı bir opaklık maskesi eklemeye kadar. Sonunda, programlı olarak profesyonel XPS dosyaları üretebilecek ve maskeyi ihtiyacınız olan herhangi bir şekle yeniden kullanabileceksiniz.

## Hızlı Yanıtlar
- **Bir opaklık maskesi ne işe yarar?** Bir şeklin farklı şeffaflık seviyelerini tanımlar, altındaki içeriğin görünmesine izin verir.  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (aspose page java).  
- **Lisans gerekiyor mu?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Kaç satır kod?** Yaklaşık 20 satır Java kodu ve birkaç kurulum ifadesi.  
- **Maskeyi birden fazla şekle yeniden kullanabilir miyim?** Evet, aynı `ImageBrush`'ı birden fazla yola atayabilirsiniz.

## XPS'te Opaklık Maskesi Nedir?
Opaklık maskesi, bir şeklin her pikselinin alfa (şeffaflık) değerini kontrol eden bir bitmap veya vektördür. Bir dikdörtgene uygulandığında, dikdörtgenin bazı bölümleri tamamen opak, kısmen saydam veya tamamen şeffaf hâle gelir ve ek çizim katmanları olmadan karmaşık görsel efektler oluşturur.

## **create XPS document java** için Aspose.Page Java Neden Kullanılmalı?
- **Saf Java API** – Yerel bağımlılıkları yoktur, bu yüzden aynı kod Windows, Linux veya macOS'ta çalışır.  
- **Tam XPS spesifikasyon uyumu** – Maskeler XPS standardında tanımlandığı gibi render edilir.  
- **Nesne‑yönelimli tasarım** – .NET'e benzer, Aspose'u diğer dillerde kullandıysanız öğrenmesi kolaydır.  
- **Yüksek performans** – Büyük belgeler ve toplu işleme için optimize edilmiştir.

## Yaygın Kullanım Senaryoları
- **Filigranlama** – Sayfalar boyunca yarı‑saydam bir logo uygular.  
- **Dinamik temalandırma** – Oluşturulan raporlardaki UI öğelerinin görsel stilini değiştirir.  
- **Baskıya hazır ön izlemeler** – Tasarımın farklı opaklıklarla nasıl görüneceğini yazıcıya göndermeden önce gösterir.

## Önkoşullar
Başlamadan önce şunları temin edin:
- Java programlamaya temel bir anlayış.  
- Aspose.Page for Java kütüphanesi yüklü. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Aspose.Page için geçerli bir lisans. Yoksa, geçici bir lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** edinebilirsiniz.  
- Java uygulamalarını derleyip çalıştırabilecek bir geliştirme ortamı (ör. IntelliJ IDEA, Eclipse veya VS Code).

## Paketleri İçe Aktar
İlk olarak Aspose.Page kütüphanesinden gerekli sınıfları içe aktarın. Bu, API'nin projenizde kullanılabilir olmasını sağlar.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Adım‑Adım Kılavuz

### Adım 1: Yeni Bir XPS Belgesi Oluştur
İlk olarak, tüm grafikleri tutacak yeni bir XPS belgesi örneği oluşturun.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Adım 2: Bir Kanvas Ekleyin
Kanvas, XPS sayfası içinde bir çizim yüzeyi görevi görür.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Adım 3: Bir Dikdörtgen Ekleyin ve Katı Dolgu Uygulayın
Burada bir dikdörtgen yolu oluşturup ona katı kırmızı bir dolgu veriyoruz. Bu dikdörtgen daha sonra opaklık maskesini alacak.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Adım 4: ImageBrush Kullanarak Opaklık Maskesi Ekleyin
Bir TIFF görüntüsü yüklüyoruz, kaynak ve hedef dikdörtgenleri tanımlıyoruz ve fırçayı döşeme moduna ayarlıyoruz, böylece maske gerektiğinde tekrarlanır.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Adım 5: Oluşan XPS Belgesini Kaydedin
Son olarak, belgeyi diske kaydedin. Çıktı dosyası, uygulanan opaklık maskesiyle dikdörtgeni içerecek.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Bu adımları dikkatlice izleyerek **add opacity mask** işlevselliğini Aspose.Page kullanarak Java XPS belgenize dahil edin.

## Yaygın Sorunlar ve Çözümleme
- **Görüntü bulunamadı** – `dataDir`'in doğru klasöre işaret ettiğini ve `R08SY_NN.tif` dosyasının mevcut olduğunu doğrulayın.  
- **Maske katı görünüyor** – Kaynak görüntünün gerçekten değişen alfa değerleri içerdiğinden emin olun; tamamen opak bir görüntü şeffaflık göstermez.  
- **Döşeme modu uygulanmıyor** – Döşemenin fark edilmesi için hedef dikdörtgen, kaynak dikdörtgenden daha küçük olmalıdır.

## Sıkça Sorulan Sorular

**S: Aspose.Page tüm Java geliştirme ortamlarıyla uyumlu mu?**  
C: Evet, Aspose.Page çeşitli Java IDE'leri ve yapı araçlarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

**S: Aspose.Page'ı lisans olmadan kullanabilir miyim?**  
C: Kütüphaneyi geçici bir lisansla değerlendirebilirsiniz, ancak üretim kullanımı için tam lisans gereklidir.

**S: Deneme sürümünde herhangi bir sınırlama var mı?**  
C: Deneme sürümü boyut veya özellik kısıtlamaları getirebilir; ayrıntılar için resmi belgeleri inceleyin.

**S: Aspose.Page için nasıl destek alabilirim?**  
C: Topluluk yardımı için **[Aspose.Page forumunu](https://forum.aspose.com/c/page/39)** ziyaret edin veya premium destek için lisans satın alın.

**S: Aspose.Page için para iade garantisi var mı?**  
C: İade politikaları hakkında bilgi için **[satın alma sayfasına](https://purchase.aspose.com/buy)** bakın.

---

**Son Güncelleme:** 2026-04-30  
**Test Edilen Sürüm:** Aspose.Page Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
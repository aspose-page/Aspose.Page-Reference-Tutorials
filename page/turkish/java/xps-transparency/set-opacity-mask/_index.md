---
date: 2026-01-02
description: Aspose.Page Java ile XPS belgelerine opaklık maskesi eklemeyi öğrenin.
  Opaklık maskesi dikdörtgeni oluşturmak ve görsel kaliteyi artırmak için adım adım
  rehber.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Aspose.Page Java ile Java XPS'te Opaklık Maskesini Ayarlama
url: /tr/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS'de Opaklık Maskesini Ayarlama Aspose.Page Java Kullanarak

## Giriiş
**aspose page java** opaklık maskeleri üzerine kapsamlı rehberimize hoş geldiniz. Bu öğreticide bir XPS belgesi oluşturmayı, bir kanvas eklemeyi ve bir dikdörtgene opaklık paketi uygulamasını — tüm bunlar güçlü Aspose.Page Java API'si ile ilgili bilgileri içerir. Sonunda XPS dosyalarınıza cilalı, yarı‑saydam bir görünüm kazandıran opaklık maskeli dosyalar ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Bir opaklık maskesi ne yapar?** Bir şeklin açıklığının değişmesi, adı içeriğinin görünmesini sağlar.
- **Hangi kütüphanesi gereklidir?** Aspose.Page for Java (aspose page java).
- **Lisans gerekli mi?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.
- **Kaç satır kod?** Yaklaşık 20 satır Java kodu ve birkaç kurulum açıklaması.
- **Maskeyi birden fazla miktarda yeniden kullanabilir miyim?** Evet, aynı ImageBrush'ı anında çok yola atayabilirsiniz.

## XPS'de Opaklık Maskesi nedir?
Opaklık maskesi, bir şeklin her pikselinin alfa (şeffaflık) değerini kontrol eden bir bitmap veya vektördür. Bir dikdörtgenin açılışında, düzenlenirin bazı bölümleri tamamen opak, bazılarının şeffaf, bazılarının ise tamamen şeffaf hale getirilmesini sağlayan görsel efektler oluşturur.

## Opaklık Maskeleri için Neden Aspose.Page Java Kullanılmalı?
- **Java'da tam .NET‑stil API** – kişisel nesne modeli.
- **Harici ilişkiler yok** – saf Java ile çalışır.
- **Yüksek doğrulukta render** – maskelerin XPS spesifikasyonunda olduğu gibi render edilir.
- **Çapraz platformu** – Windows, Linux veya macOS'ta değişiklik yapılmadan çalıştırılır.

## Önkoşullar
Başlamadan önce gelişmelerin olduğundan emin olun:
- Java programlamaya temel bir anlayış.
- Aspose.Page for Java yükü yüklü. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.
- Aspose.Page için geçerli bir lisans. Yoksa **[buradan](https://purchase.aspose.com/temporary-license/)** geçici bir lisans belgesidir.
- Java'yı kaydedip çalıştırabilecek bir geliştirme ortamı (IntelliJ IDEA, Eclipse veya VS Code gibi).

## Paketleri İçe Aktar
Aspose.Page kütüphanesinden gerekli sınıfları içeri aktararak başlayın. Bu, API'nin projenizde kullanılabilir olmasını sağlar.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Adım Adım Kılavuz

### Adım 1: Yeni Bir XPS Belgesi Oluşturun
İlk olarak, tüm grafikleri tutacak yeni bir XPS belgesi örneği oluşturun.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Adım 2: Bir Tuval Ekleyin
Kanvas, XPS sayfası içinde bir çizim yüzeyi görevi görür.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Adım 3: Bir Dikdörtgen Ekleyin ve Düz Renk Dolgusu Uygulayın
Burada bir dikdörtgen yolu oluşturup ona katı kırmızı bir dolgu veriyoruz. Bu dikdörtgen daha sonra opaklık maskesi alacak.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Adım 4: Bir ImageBrush Kullanarak Opaklık Maskesi Ekleyin
Bir TIFF resmi yüklüyor, kaynak ve hedef dikdörtgenleri tanımlıyor ve fırçayı döşeme (tile) moduna ayarlıyoruz; böylece gerekirse maske tekrarlanır.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Adım 5: Oluşturulan XPS Belgesini Kaydedin
Son olarak belgeyi diske kaydedin. Çıktı dosyası, uygulanan opaklık maskesiyle birlikte dikdörtgeni içerecek.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Bu adımları dikkatle izleyerek **add opacity mask** işlevselliğini Java XPS belgenize Aspose.Page kullanarak ekleyebilirsiniz.

## Yaygın Sorunlar ve Sorun Giderme
- **Resim hatası oluştu** – `dataDir`'in doğru klasörde işaretlendiğini ve `R08SY_NN.tif` dosyalarının mevcut olup olmadığını doğrulayın.
- **Maske katı görünüyor** – Kaynak resminin gerçekten değişken alfa değerlerinin ortaya çıkmasından emin olun; tamamen opak bir resim şeffaflık göstermez.
- **Döşeme modu uygulanmıyor** – Döşemenin fark edilmesi için hedef dikdörtgen, kaynak kayıtlıdan daha küçük olmalıdır.

## Sıkça Sorulan Sorular

**S: Aspose.Page tüm Java geliştirme ortamlarıyla uyumlu mu?**
C: Evet, Aspose.Page çeşitli Java IDE'leri ve yapı araçlarıyla sorunsuz şekilde çalıştırılabilir şekilde tasarlanmıştır.

**S: Aspose.Page'i lisanssız kullanabilir miyim?**
C: Kütüphaneyi geçici bir lisansla değerlendirebilirsiniz, ancak üretim kullanımı için tam lisans gereklidir.

**S: Deneme sürümünde sınırlamalar var mı?**
C: Deneme bölüm boyutu veya özellik sınırlamaları yapılabilir; ayrıntılar için resmi dokümantasyona bakın.

**S: Aspose.Page için destek nasıl alınır?**
C: **[Aspose.Page forumu](https://forum.aspose.com/c/page/39)** üzerinden bölüm yardımı alabilir veya premium destek için lisans satın alabilirsiniz.

**S: Aspose.Page için para iade garantisi var mı?**
C: **[satın alma sayfası](https://purchase.aspose.com/buy)**'da iade politikaları hakkında bilgi bulabilirsiniz.

---

**Son Güncelleme:** 2026-01-02
**Test Edilenler:** Aspose.Page Java 24.11 (yazım anındaki en yeni sürüm)
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
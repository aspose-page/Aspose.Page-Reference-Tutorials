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

## Introduction
**aspose page java** opaklık maskeleri üzerine kapsamlı rehberimize hoş geldiniz. Bu öğreticide bir XPS belgesi oluşturmayı, bir kanvas eklemeyi ve bir dikdörtgene opaklık maskesi uygulamayı — tüm bunları güçlü Aspose.Page Java API'si ile öğreneceksiniz. Sonunda XPS dosyalarınıza cilalı, yarı‑saydam bir görünüm kazandıran opaklık maskeli dikdörtgenler ekleyebileceksiniz.

## Quick Answers
- **Bir opaklık maskesi ne yapar?** Bir şeklin şeffaflık seviyelerini değiştirir, altındaki içeriğin görünmesini sağlar.
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (aspose page java).
- **Lisans gerekli mi?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.
- **Kaç satır kod?** Yaklaşık 20 satır Java kodu ve birkaç kurulum ifadesi.
- **Maskeyi birden fazla şekle yeniden kullanabilir miyim?** Evet, aynı ImageBrush'ı birden çok yola atayabilirsiniz.

## What is an Opacity Mask in XPS?
Opaklık maskesi, bir şeklin her pikselinin alfa (şeffaflık) değerini kontrol eden bir bitmap veya vektördür. Bir dikdörtgene uygulandığında, dikdörtgenin bazı bölümleri tamamen opak, bazıları kısmen şeffaf, bazıları ise tamamen şeffaf hâle gelerek sofistike görsel efektler oluşturur.

## Why Use Aspose.Page Java for Opacity Masks?
- **Java'da tam .NET‑stil API** – sezgisel nesne modeli.
- **Harici bağımlılık yok** – saf Java ile çalışır.
- **Yüksek doğrulukta render** – maskeler XPS spesifikasyonunda olduğu gibi render edilir.
- **Çapraz platform** – Windows, Linux veya macOS'ta değişiklik yapmadan çalışır.

## Prerequisites
Başlamadan önce şunların olduğundan emin olun:
- Java programlamaya temel bir anlayış.  
- Aspose.Page for Java kütüphanesi yüklü. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Aspose.Page için geçerli bir lisans. Yoksa **[buradan](https://purchase.aspose.com/temporary-license/)** geçici bir lisans edinin.  
- Java uygulamalarını derleyip çalıştırabilecek bir geliştirme ortamı (IntelliJ IDEA, Eclipse veya VS Code gibi).

## Import Packages
Aspose.Page kütüphanesinden gerekli sınıfları içe aktararak başlayın. Bu, API'nin projenizde kullanılabilir olmasını sağlar.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Step‑by‑Step Guide

### Step 1: Create a New XPS Document
İlk olarak, tüm grafikleri tutacak yeni bir XPS belgesi örneği oluşturun.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Step 2: Add a Canvas
Kanvas, XPS sayfası içinde bir çizim yüzeyi görevi görür.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Step 3: Add a Rectangle and Apply a Solid Fill
Burada bir dikdörtgen yolu oluşturup ona katı kırmızı bir dolgu veriyoruz. Bu dikdörtgen daha sonra opaklık maskesi alacak.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Step 4: Add Opacity Mask Using an ImageBrush
Bir TIFF resmi yüklüyor, kaynak ve hedef dikdörtgenleri tanımlıyor ve fırçayı döşeme (tile) moduna ayarlıyoruz; böylece gerekirse maske tekrarlanır.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Step 5: Save the Resultant XPS Document
Son olarak belgeyi diske kaydedin. Çıktı dosyası, uygulanan opaklık maskesiyle birlikte dikdörtgeni içerecek.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Bu adımları dikkatle izleyerek **add opacity mask** işlevselliğini Java XPS belgenize Aspose.Page kullanarak ekleyebilirsiniz.

## Common Issues & Troubleshooting
- **Resim bulunamadı** – `dataDir`'in doğru klasöre işaret ettiğini ve `R08SY_NN.tif` dosyasının mevcut olduğunu doğrulayın.
- **Maske katı görünüyor** – Kaynak resmin gerçekten değişken alfa değerleri içerdiğinden emin olun; tamamen opak bir resim şeffaflık göstermez.
- **Tile modu uygulanmıyor** – Döşemenin fark edilmesi için hedef dikdörtgen, kaynak dikdörtgenden daha küçük olmalıdır.

## Frequently Asked Questions

**S: Aspose.Page tüm Java geliştirme ortamlarıyla uyumlu mu?**  
C: Evet, Aspose.Page çeşitli Java IDE'leri ve yapı araçlarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

**S: Aspose.Page'ı lisanssız kullanabilir miyim?**  
C: Kütüphaneyi geçici bir lisansla değerlendirebilirsiniz, ancak üretim kullanımı için tam lisans gereklidir.

**S: Deneme sürümünde sınırlamalar var mı?**  
C: Deneme sürümü boyut veya özellik kısıtlamaları getirebilir; ayrıntılar için resmi dokümantasyona bakın.

**S: Aspose.Page için destek nasıl alınır?**  
C: **[Aspose.Page forumu](https://forum.aspose.com/c/page/39)** üzerinden topluluk yardımı alabilir veya premium destek için lisans satın alabilirsiniz.

**S: Aspose.Page için para iade garantisi var mı?**  
C: **[satın alma sayfası](https://purchase.aspose.com/buy)**'da iade politikaları hakkında bilgi bulabilirsiniz.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page Java 24.11 (yazım anındaki en yeni sürüm)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
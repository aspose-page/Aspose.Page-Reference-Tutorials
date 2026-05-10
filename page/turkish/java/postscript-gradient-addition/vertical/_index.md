---
date: 2026-02-13
description: Aspose.Page kullanarak Java’da PostScript gradyanı nasıl oluşturacağınızı
  öğrenin. Bu adım adım rehber, PostScript belgelerinize dikey bir gradyanı zahmetsizce
  eklemenizi gösterir.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Java'da PostScript Gradyanı Oluştur – Dikey Gradyan Ekle
url: /tr/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java’da PostScript Gradient Oluşturma – Dikey Gradient Ekleme

## Introduction
Bu kapsamlı öğreticide, **Java’da PostScript gradient oluşturmayı** Aspose.Page for Java ile öğreneceksiniz. Dikey bir gradient eklemek, belgelerinizi daha canlı ve profesyonel gösterir; sadece birkaç satır kodla çarpıcı görsel efektler elde edebilirsiniz. Her adımı sizinle birlikte inceleyecek, her parçanın neden önemli olduğunu açıklayacak ve yaygın hatalardan kaçınmanız için pratik ipuçları vereceğiz. Bu rehberin sonunda, yumuşak ve göz alıcı dikey renk geçişlerine sahip PostScript dosyaları üretebileceksiniz.

## Quick Answers
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Renkleri özelleştirebilir miyim?** Evet, herhangi bir `java.awt.Color` kullanılabilir  
- **Döndürme destekleniyor mu?** Evet, gradienti bir `AffineTransform` ile döndürebilirsiniz  
- **Hangi çıktı formatı üretilir?** Standart bir PostScript (.ps) dosyası  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir  

## Why add a vertical gradient to a PostScript document?
Dikey gradientler, dosya boyutunu artırmadan sayfalarınıza derinlik katar. Şu durumlar için mükemmeldir:

* Rapor başlıkları veya altbilgileri için hafif bir arka plan efekti.  
* Teknik kılavuzlar veya beyaz kağıtlar içinde bölümleri vurgulamak.  
* Grafikler, diyagramlar veya tanıtım broşürleri için modern bir görünüm sağlamak.

Gradient vektörel biçimde tanımlandığı için, çıktı her çözünürlükte net kalır.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Makinenizde yüklü Java Development Kit (JDK).  
- Aspose.Page for Java kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.

## Import Packages
Java projenizde, işe başlamak için gerekli paketleri içe aktarın:
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

Şimdi, dikey bir gradient ekleme sürecini adım adım inceleyelim.

## How to create PostScript gradient in Java
Aşağıda, Aspose.Page API’sini kullanarak **Java’da PostScript gradient oluşturmayı** tam olarak gösteren adım‑adım bir rehber bulacaksınız.

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Tebrikler! Aspose.Page for Java kullanarak Java PostScript belgenize başarılı bir şekilde dikey gradient eklediniz.

## Common Issues and Solutions
- **Gradient düz görünüyor:** `AffineTransform` ölçeklemesinin dikdörtgen boyutlarıyla eşleştiğinden emin olun.  
- **Renkler soluk çıkıyor:** Doğru `ColorSpaceType` (SRGB) kullandığınızı ve kesirler dizisinin 0.0’dan 1.0’a sıralandığını kontrol edin.  
- **Dosya oluşturulmadı:** Çıktı dizini (`dataDir`) mevcut mu, uygulamanın yazma izni var mı kontrol edin.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz çalışacak şekilde tasarlanmıştır.

### Is there a free trial available for Aspose.Page for Java?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

### Where can I find additional documentation?
Detaylı dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

### How can I purchase Aspose.Page for Java?
Aspose.Page for Java’ı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Is there a forum for Aspose.Page discussions?
Evet, topluluk forumuna [buradan](https://forum.aspose.com/c/page/39) katılabilirsiniz.

## Additional Frequently Asked Questions

**S: Diğer gradient yönlerini (yatay, diyagonal) oluşturabilir miyim?**  
C: Kesinlikle. `LinearGradientPaint` içindeki başlangıç ve bitiş noktalarını ayarlayarak ve `AffineTransform`’deki dönüş açısını değiştirerek istediğiniz yönü elde edebilirsiniz.

**S: Bu PDF çıktısı için de çalışır mı?**  
C: Aynı gradient mantığını, `PsSaveOptions` yerine `PdfSaveOptions` kullanarak PDF’ye kaydederken de uygulayabilirsiniz.

**S: Gradient boyutunu dinamik olarak nasıl değiştiririm?**  
C: Çalışma zamanında dikdörtgen boyutlarını hesaplayıp bu değerleri hem `Rectangle2D` hem de `AffineTransform` yapıcılarına geçirin.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
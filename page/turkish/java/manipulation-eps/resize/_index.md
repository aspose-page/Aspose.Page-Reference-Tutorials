---
date: 2026-02-07
description: Java’da EPS dosyalarını yeniden boyutlandırmayı ve Aspose.Page kullanarak
  EPS boyutlarını değiştirmeyi öğrenin. Bu adım adım kılavuz, EPS’yi puan, inç, milimetre
  veya yüzde olarak nasıl yeniden boyutlandıracağınızı gösterir.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Aspose.Page ile Java'da EPS Dosyalarını Yeniden Boyutlandırma
url: /tr/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java’da Aspose.Page ile EPS Dosyalarını Yeniden Boyutlandırma

## Introduction
Programatik olarak **EPS dosyalarını yeniden boyutlandırma** konusunda güvenilir bir yol arıyorsanız, doğru yerdesiniz. Bu öğreticide Java’da Aspose.Page kütüphanesini kullanarak EPS görüntülerinin yeniden boyutlandırılmasını adım adım göstereceğiz. Boyutu iki katına çıkarmak, belirli bir ölçüye küçültmek ya da yüzde bazlı çalışmak ister misiniz, aşağıdaki adımlar çıktının boyutları üzerinde tam kontrol sağlar. **EPS nasıl yeniden boyutlandırılır** sorusunun cevabını bilmek, grafikleri farklı baskı düzenleri veya ekran çözünürlükleri için uyarlamanız gerektiğinde çok önemlidir.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I resize using points, inches, or millimeters?** Yes – the API supports all three units plus percentages.  
- **Do I need a license for development?** A free trial works for testing; a license is required for production.  
- **What Java version is required?** Java 8 or later.  
- **Is the code thread‑safe?** Each `PsDocument` instance is isolated, so you can process files in parallel.  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS), yayıncılık ve baskı alanında yaygın olarak kullanılan bir vektör grafik formatıdır. Bazen orijinal EPS dosyası, hedef çıktınızla eşleşmeyen bir boyutta oluşturulur – örneğin, 72 pt’de tasarlanmış bir logo, daha büyük bir broşür için 144 pt’ye ihtiyaç duyabilir. **EPS nasıl yeniden boyutlandırılır** bilgisini edinmek, vektör kalitesini korurken boyutları herhangi bir iş akışına uyarlamanızı sağlar.

## Why Use Aspose.Page for Resizing EPS?
- **Full‑control over units** – points, inches, millimeters, or percentages.  
- **No external dependencies** – pure Java API, no native libraries.  
- **High performance** – suitable for batch processing on servers.  
- **Preserves vector fidelity** – the output remains scalable without rasterization.

## Prerequisites
Kodlamaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde yüklü Java Development Kit (JDK).  
- Aspose.Page for Java kütüphanesi. **[buradan](https://releases.aspose.com/page/java/)** indirebilirsiniz.  
- Java programlamaya temel bir anlayış.

## Import Packages
Java projenizde Aspose.Page nesneleri ve standart I/O akışlarıyla çalışabilmek için gerekli importları ekleyin.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
Kütüphane, uygun `Units` enum değerini seçerek **eps boyutlarını değiştirmeyi** basit hale getirir. Aşağıda aynı beş adımlı deseni noktalar, inçler, milimetreler ve yüzde birimleri için nasıl uygulayacağınızı göreceksiniz. Tek değişen şey `resizeEps` metoduna gönderdiğiniz birimdir.

## How to Resize EPS Using Points
Aşağıda, EPS dosyasının boyutunu ölçüm birimi olarak nokta (points) kullanarak iki katına çıkaran eksiksiz bir örnek yer almaktadır.

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
Aynı beş adımlı desen geçerlidir; sadece `Units.Points` yerine `Units.Inches` kullanın ve ölçek faktörünü istediğiniz inç değerine göre ayarlayın.

## How to Resize EPS Using Millimeters
Yine aynı adımları izleyin, birimi `Units.Millimeters` olarak değiştirin. Bu, baskı iş akışları için metrik tabanlı boyutlar gerektiğinde oldukça kullanışlıdır.

## How to Resize EPS Using Percentages
Yüzde bazlı ölçeklendirme için birimi `Units.Percent` olarak bırakın. Orijinal genişlik ve yüksekliği istediğiniz yüzdeyle çarpın (örneğin, %50 küçültme için `0.5`).

## Common Pitfalls & Tips
- **Always close streams** – In production code, wrap streams in try‑with‑resources to avoid file locks.  
- **Preserve aspect ratio** – Multiply both width and height by the same factor unless you intentionally want distortion.  
- **Check DPI** – Resizing does not change the DPI; if you need a different DPI, adjust it separately after resizing.  
- **Thread safety** – Create a new `PsDocument` per thread; sharing the same instance can lead to unexpected results.  

## Frequently Asked Questions

**Q: Can I use this library for other image formats?**  
A: No, Aspose.Page is specialized for PostScript and EPS files only.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can explore the free trial **[here](https://releases.aspose.com/)**.

**Q: Where can I find additional help and discussions?**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** for community support.

**Q: How can I obtain a temporary license?**  
A: You can get a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Are there any example projects available?**  
A: Yes, check the documentation **[here](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
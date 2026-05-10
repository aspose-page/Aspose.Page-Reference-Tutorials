---
date: 2026-03-16
description: Aspose.Page kullanarak Java'da XPS belgelerine nasıl resim ekleneceğini
  öğrenin. Bu kılavuz, resimleri hızlı bir şekilde eklemenizi sağlar.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: asp asp – Aspose.Page ile Java XPS Belgelerine Resim Ekle
url: /tr/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp asp – Java XPS Belgelerine Görüntü Ekleme Aspose.Page

XPS dosyalarına görüntü eklemek, raporları, faturaları veya herhangi bir görsel belgeyi zenginleştirmek isteyen Java geliştiricileri için sık bir ihtiyaçtır. Bu öğreticide, güçlü Aspose.Page for Java kütüphanesini kullanarak bir XPS belgesine **görüntü eklemenin** nasıl yapılacağını öğrenecek ve **asp asp** yaklaşımının süreci neden güvenilir ve hızlı hâle getirdiğini göreceksiniz. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve yaygın hatalardan kaçınmanız için pratik ipuçları vereceğiz.

## Quick Answers
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Birden fazla görüntü ekleyebilir miyim?** Evet – her resim için görüntü‑ekleme adımlarını tekrarlayın  
- **Desteklenen görüntü formatları?** TIFF, JPEG, PNG, GIF (ve .NET tarafından desteklenen diğerleri)  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gerekir  
- **Tipik uygulama süresi?** Temel bir görüntü ekleme için yaklaşık 10‑15 dakika  

## asp asp: XPS Belgelerine Görüntü Ekleme
**asp asp** metodolojisi, belge oluşturma, yol tanımlama, bir görüntü fırçası uygulama ve kaydetme gibi basit, tekrarlanabilir bir desen etrafında döner. Bu desen kodunuzu temiz tutar ve ileride ek grafikler eklemeyi kolaylaştırır.

## What is Aspose.Page for Java?
Aspose.Page, Microsoft XPS Viewer’a ihtiyaç duymadan XPS (XML Paper Specification) belgeleri oluşturmanıza, düzenlemenize ve render etmenize olanak tanıyan özel bir API’dir. XPS işaretlemesinin düşük‑seviye ayrıntılarını soyutlayarak belgelerinizin görsel düzenine odaklanmanızı sağlar.

## Why add images to XPS?
- **Professional look:** Logolar, grafikler veya ürün fotoğrafları gibi görüntüler belgelerinize cilalı bir görünüm kazandırır.  
- **Brand consistency:** Şirket logonuzu gömmek, oluşturulan her fatura veya raporun markanızı taşımasını sağlar.  
- **Dynamic content:** Çalışma zamanında QR kodları, barkodlar veya kullanıcı‑tarafından oluşturulan grafikler programlı olarak ekleyebilirsiniz.

## Introduction
XPS belgelerine görüntü eklemek, rapor üretiminden belge işleme kadar birçok Java uygulamasında yaygın bir gereksinimdir. Aspose.Page for Java bu görevi basitleştirir, görüntüleri XPS dosyalarınıza sorunsuz bir şekilde entegre etmenizi sağlayan verimli yöntemler sunar. Bu öğreticide, Aspose.Page for Java kullanarak bir XPS belgesine nasıl görüntü ekleyeceğinizi göstereceğiz.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:
1. **Aspose.Page for Java Library** – Aspose.Page for Java kütüphanesini [website](https://releases.aspose.com/page/java/) adresinden indirin ve kurun.  
2. **Java Development Environment** – Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.

Şimdi sonraki adımlara geçelim.

## Import Packages
Java projenizde, gerekli sınıflara ve yöntemlere erişmek için Aspose.Page for Java paketlerini içe aktarın.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Step 1: Set Up Document Directory
XPS belgesi ve görüntü dosyalarının saklanacağı belge dizininizin yolunu tanımlayın.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document
Aşağıdaki kod parçacığını kullanarak yeni bir XPS belgesi başlatın:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Image to XPS Document
Bir görüntü eklemek için XPS belgesinde bir yol oluşturun ve sağlanan görüntü dosyası ile koordinatları kullanarak görüntü fırçasını ayarlayın.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Step 4: Save Resultant XPS Document
Değiştirilmiş XPS belgesini belirttiğiniz dizine kaydedin.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Projenizin gereksinimlerine göre daha fazla görüntü eklemek veya mevcut olanları özelleştirmek için bu adımları tekrarlayın.

## Common Issues and Solutions
- **Image appears stretched:** Kaynak dikdörtgenin (`new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f)`) görüntünüzün gerçek boyutlarıyla eşleştiğini doğrulayın. En‑boy oranını korumak için hedef dikdörtgeni ayarlayın.  
- **Watermark shows up:** Geçerli bir lisans olmadan kodu çalıştırırsanız Aspose bir filigran ekler. Bu durumu önlemek için lisansınızı uygulamanın erken aşamasında etkinleştirin.  
- **FileNotFoundException:** `dataDir` değişkeninin doğru klasöre işaret ettiğinden ve görüntü dosya adının (`QL_logo_color.tif`) diskteki dosyayla aynı olduğundan emin olun.

## Conclusion
Tebrikler! Aspose.Page for Java kullanarak bir XPS belgesine **görüntü eklemenin** nasıl yapılacağını başarıyla öğrendiniz. Bu beceri, Java uygulamalarınızın ve belgelerinizin görsel çekiciliğini artırmak için çok değerlidir. **asp asp** desenini izleyerek bu örneği kolayca genişletebilir, birden fazla grafik ekleyebilir, dinamik olarak ölçeklendirebilir veya anında grafikler oluşturabilirsiniz.

### Frequently Asked Questions
### Can I add multiple images to the same XPS document using Aspose.Page for Java?
Evet, bu öğreticideki adımları her görüntü için tekrarlayarak birden fazla görüntü ekleyebilirsiniz.

### What image formats are supported by Aspose.Page for Java?
Aspose.Page for Java, TIFF, JPEG, PNG ve GIF dahil olmak üzere çeşitli görüntü formatlarını destekler.

### Is there a trial version of Aspose.Page for Java available?
Evet, Aspose.Page for Java için ücretsiz bir deneme sürümünü [this link](https://releases.aspose.com/) adresinden edinebilirsiniz.

### How can I get a temporary license for Aspose.Page for Java?
Geçici bir lisansı [this link](https://purchase.aspose.com/temporary-license/) adresinden alabilirsiniz.

### Where can I find additional support or discuss issues related to Aspose.Page for Java?
Yardım almak, deneyimlerinizi paylaşmak ve Aspose.Page topluluğu ile iletişime geçmek için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
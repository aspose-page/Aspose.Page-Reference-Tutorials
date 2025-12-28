---
date: 2025-12-28
description: Aspose.Page kullanarak Java'da XPS belgelerine nasıl resim ekleneceğini
  öğrenin. Bu adım adım rehber, resimleri sorunsuz bir şekilde eklemenizi ve belge
  işleme süreçlerinizi geliştirmenizi gösterir.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Java XPS Belgelerine Görsel Ekleme – Aspose.Page ile Basit Bir Rehber
url: /tr/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java ile XPS Belgelerine Görüntü Ekleme

Görselleri XPS dosyalarına eklemek, raporları, faturaları veya herhangi bir görsel belgeyi zenginleştirmesi gereken Java geliştiricileri için yaygın bir gereksinimdir. Bu öğreticide **görsel ekleme** işlemini güçlü Aspose.Page for Java kütüphanesiyle nasıl yapacağınızı keşfedeceksiniz. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve tipik hatalardan kaçınmanız için ipuçları vereceğiz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Birden fazla görsel ekleyebilir miyim?** Evet – her resim için görsel ekleme adımlarını tekrarlayın  
- **Desteklenen görsel formatları?** TIFF, JPEG, PNG, GIF (ve .NET tarafından desteklenen diğerleri)  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gerekir  
- **Tipik uygulama süresi?** Temel bir görsel ekleme için yaklaşık 10‑15 dakika

## Giriş
Görselleri XPS belgelerine eklemek, rapor oluşturma ve belge işleme gibi birçok Java uygulamasında yaygın bir gereksinimdir. Aspose.Page for Java, bu görevi basitleştirir ve görselleri XPS dosyalarınıza sorunsuz bir şekilde entegre etmenizi sağlayan verimli yöntemler sunar. Bu öğreticide, Aspose.Page for Java kullanarak bir XPS belgesine nasıl görsel ekleyeceğinizi göstereceğiz.

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:
1. **Aspose.Page for Java Kütüphanesi** – [web sitesinden](https://releases.aspose.com/page/java/) Aspose.Page for Java kütüphanesini indirin ve kurun.  
2. **Java Geliştirme Ortamı** – Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.

Şimdi sonraki adımlara geçelim.

## Paketleri İçe Aktarma
Java projenizde, gerekli sınıflara ve yöntemlere erişmek için Aspose.Page for Java paketlerini içe aktarın.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Adım 1: Belge Dizinini Ayarlama
XPS belgesi ve görsel dosyalarının saklanacağı belge dizininin yolunu tanımlayın.

```java
String dataDir = "Your Document Directory";
```

## Adım 2: Yeni bir XPS Belgesi Oluşturma
Aşağıdaki kod parçacığını kullanarak yeni bir XPS belgesi başlatın:

```java
XpsDocument doc = new XpsDocument();
```

## Adım 3: XPS Belgesine Görsel Ekleme
Görsel eklemek için XPS belgesinde bir yol oluşturun ve sağlanan görsel dosyası ile koordinatları kullanarak görüntü fırçasını ayarlayın.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Adım 4: Oluşturulan XPS Belgesini Kaydetme
Değiştirilmiş XPS belgesini belirttiğiniz dizine kaydedin.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Bu adımları tekrarlayarak daha fazla görsel ekleyebilir veya mevcut görselleri projenizin gereksinimlerine göre özelleştirebilirsiniz.

## Sonuç
Tebrikler! Aspose.Page for Java kullanarak bir XPS belgesine **görsel ekleme** işlemini başarıyla öğrendiniz. Bu beceri, Java uygulamalarınızın ve belgelerinizin görsel çekiciliğini artırmak için çok değerlidir.

### Sıkça Sorulan Sorular
### Aspose.Page for Java ile aynı XPS belgesine birden fazla görsel ekleyebilir miyim?
Evet, her görsel için bu öğreticideki adımları tekrarlayarak birden fazla görsel ekleyebilirsiniz.

### Aspose.Page for Java hangi görsel formatlarını destekliyor?
Aspose.Page for Java, TIFF, JPEG, PNG ve GIF dahil olmak üzere çeşitli görsel formatlarını destekler.

### Aspose.Page for Java için bir deneme sürümü mevcut mu?
Evet, [bu bağlantıdan](https://releases.aspose.com/) Aspose.Page for Java ücretsiz deneme sürümünü edinebilirsiniz.

### Aspose.Page for Java için geçici bir lisans nasıl alınır?
Geçici lisansı [bu bağlantıdan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.Page for Java ile ilgili ek destek nereden bulunur veya sorunlar nasıl tartışılır?
Yardım almak, deneyimlerinizi paylaşmak ve Aspose.Page topluluğu ile iletişime geçmek için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Ek İpuçları ve Yaygın Tuzaklar
- **Yol Geometrisi Doğruluğu** – SVG‑stilindeki yol dizesinin görselinizin boyutlarıyla eşleştiğinden emin olun; aksi takdirde görsel gerilmiş veya kırpılmış görünebilir.  
- **Görsel Fırça Ölçeklendirme** – `createImageBrush` yöntemi kaynak ve hedef dikdörtgenleri alır; bu değerleri ayarlayarak konumlandırma ve ölçeklendirmeyi hassas bir şekilde kontrol edebilirsiniz.  
- **Lisans Aktivasyonu** – Kodu geçerli bir lisans olmadan çalıştırırsanız, Aspose oluşturulan XPS dosyasına bir filigran ekleyecektir.

---

**Son Güncelleme:** 2025-12-28  
**Test Edilen Versiyon:** Aspose.Page for Java 23.12 (yazım anındaki en yeni)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
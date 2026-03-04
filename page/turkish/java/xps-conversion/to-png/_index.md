---
date: 2025-12-23
description: Java'da Aspose.Page kullanarak XPS'i zahmetsizce **PNG'ye dönüştürün**.
  Bu kılavuz, XPS'i güvenilir, geliştirici‑dostu bir çözümle görüntü dosyalarına nasıl
  render edeceğinizi gösterir.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Java'da XPS'yi PNG'ye Dönüştür
url: /tr/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS'yi Java'da PNG'ye Dönüştür

## Giriş
Dinamik yazılım geliştirme dünyasında, **XPS'yi PNG'ye dönüştürme** (XML Paper Specification'dan Portable Network Graphics'e) ihtiyacı sıkça ortaya çıkar. Bu görevi Java'da sorunsuz bir şekilde gerçekleştirmek için Aspose.Page güçlü bir çözüm sunar. Bu öğreticide, Aspose.Page for Java kullanarak XPS'yi PNG'ye dönüştürme sürecini adım adım inceleyeceğiz.

## Hızlı Yanıtlar
- **Bu dönüşümü hangi kütüphane yönetir?** Aspose.Page for Java  
- **Hangi formatlar dahil?** XPS (kaynak) → PNG (çıktı)  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir  
- **Görüntü çözünürlüğünü ayarlayabilir miyim?** Evet, `PngSaveOptions.setResolution()` kullanarak  
- **Belirli sayfaları seçmek mümkün mü?** Kesinlikle – seçenek nesnesinde sayfa numaralarını sağlayın  

## XPS'yi PNG'ye Neden Dönüştürmeliyiz?
XPS'yi görüntü dosyalarına dönüştürmek, belgeleri web'de görüntülemek, raporlara yerleştirmek veya önizleme için küçük resimler oluşturmak istediğinizde faydalıdır. PNG, kayıpsız sıkıştırma ve geniş tarayıcı desteği sunar, bu da XPS içeriğinin yüksek kaliteli görsel temsilleri için ideal bir seçimdir.

## Önkoşullar
1. Java Development Kit (JDK): Sisteminizde JDK yüklü olduğundan emin olun.  
2. Aspose.Page for Java: Aspose.Page kütüphanesini indirin ve kurun. İndirme bağlantısını [burada](https://releases.aspose.com/page/java/) bulabilirsiniz.  
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi Java uyumlu bir IDE seçin.  

## Java'da XPS'yi PNG'ye Nasıl Dönüştürülür
Aşağıda, **XPS** belgelerini PNG görüntülerine dönüştürmeyi adım adım açıklayan bir kılavuz ve doğrudan projenize kopyalayabileceğiniz kod parçacıkları bulunmaktadır.

### Paketleri İçe Aktarma
Java projenizde Aspose.Page işlevselliğini kullanmak için gerekli paketleri içe aktarın. Java dosyanızın başına aşağıdaki import ifadelerini ekleyin:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Adım 1: Belge Dizini Ayarla
Kaynak XPS dosyanızın bulunduğu ve PNG dosyalarının kaydedileceği klasörü tanımlayın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Adım 2: XPS Belgesini Yükle
`XpsDocument` örneği oluşturarak kaynak XPS dosyasını yükleyin.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Adım 3: Seçenekleri Başlat
PNG çıktı seçeneklerini yapılandırın. Burada yumuşatma, çözünürlük ayarlayabilir ve hangi sayfaların render edileceğini belirtebilirsiniz.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Adım 4: Render Cihazı Oluştur
Render edilmiş görüntü verilerini tutacak bir `ImageDevice` oluşturun.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Adım 5: Kaydet ve Döngü
XPS belgesini render edin, ardından oluşturulan her PNG bayt dizisini diske bir dosya olarak yazın.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Bu adımları izleyerek, Aspose.Page for Java kullanarak XPS'yi PNG formatında **görüntü dosyalarına** sorunsuz bir şekilde render edebilirsiniz.

## Sonuç
Sonuç olarak, Aspose.Page for Java XPS'ten PNG'ye dönüşüm sürecini basitleştirir ve geliştiricilere güvenilir ve verimli bir araç sunar. Bu kütüphaneyi Java projelerinize entegre ederek belge manipülasyonu görevlerini kolaylaştırın.

## Ek Sıkça Sorulan Sorular

**Q: XPS dosyasının yalnızca seçili sayfalarını dönüştürebilir miyim?**  
A: Kesinlikle. Render etmek istediğiniz sayfaları belirtmek için `PngSaveOptions` içindeki `setPageNumbers` metodunu kullanın.

**Q: Yüksek kaliteli PNG'ler için önerilen görüntü çözünürlüğü nedir?**  
A: 300 dpi çözünürlük, kalite ve dosya boyutu arasında iyi bir denge sağlar, ancak `options.setResolution()` ile ayarlayabilirsiniz.

**Q: API büyük belgeler için çoklu iş parçacıklı dönüşümü destekliyor mu?**  
A: Evet, dönüşüm mantığını paralel iş parçacıklarında çalıştırabilirsiniz; her iş parçacığı farklı bir sayfa veya belge bölümüyle ilgilenir.

**Q: Çok büyük XPS dosyalarını dönüştürürken bellek kullanımını nasıl yönetirim?**  
A: Sayfaları sıralı olarak işleyin ve örnek kodda gösterildiği gibi her yazımdan sonra `FileOutputStream`'i serbest bırakın.

**Q: Oluşturulan PNG dosyalarına özel meta veriler eklemenin bir yolu var mı?**  
A: `PngSaveOptions` doğrudan meta veri alanlarını sunmasa da, standart görüntü kütüphanelerini kullanarak PNG'yi sonradan işleyip meta veri ekleyebilirsiniz.

---

**Son Güncelleme:** 2025-12-23  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
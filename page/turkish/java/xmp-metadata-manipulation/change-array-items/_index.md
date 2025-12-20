---
date: 2025-12-20
description: Aspose.Page for Java (aspose.page xmp java) kullanarak XMP'deki dizi
  öğelerini nasıl değiştireceğinizi öğrenin. Adım adım rehberimizle meta verileri
  zahmetsizce düzenleyin ve EPS belgelerinizi bugün geliştirin.
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: 'aspose.page xmp java: XMP''de Dizi Öğelerini Java ile Değiştir'
url: /tr/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: Java Kullanarak XMP'de Dizi Öğelerini Değiştirme

## Introduction
**Aspose.Page for Java** kullanarak XMP'de dizi öğelerini değiştirme konusunda kapsamlı rehberimize hoş geldiniz. **aspose.page xmp java** kütüphanesi, EPS dosyalarındaki XMP meta verileri üzerinde tam kontrol sağlar; başlıkları, oluşturucuları ve diğer özellikleri kolayca özelleştirmenize olanak tanır. Bu öğreticide, dizi öğelerini değiştirmek için gereken her adımı adım adım gösterecek ve EPS belgelerinizi güvenle geliştirebilmenizi ve kişiselleştirebilmenizi sağlayacağız.

## Quick Answers
- **aspose.page xmp java ne işe yarar?** Java üzerinden EPS dosyalarındaki XMP meta verilerini okur ve yazar.  
- **Denemek için lisansa ihtiyacım var mı?** Evet, ücretsiz bir deneme sürümü mevcuttur, ancak üretim kullanımı için lisans gereklidir.  
- **Hangi JDK sürümü destekleniyor?** Java 8 veya üzeri.  
- **Diğer meta veri alanlarını da değiştirebilir miyim?** Kesinlikle – herhangi bir XMP özelliği okunabilir veya güncellenebilir.  
- **API çoklu iş parçacığı (thread‑safe) mi?** Çoğu okuma/yazma işlemi, ayrı belge örnekleri üzerinde kullanıldığında güvenlidir.

## What is aspose.page xmp java?
`aspose.page xmp java`, Aspose.Page for Java paketinin XMP (Extensible Metadata Platform) işleme odaklı bir parçasıdır. Düşük seviyeli XMP yapısını basit Java nesnelerine dönüştürerek, diziler, çantalar (bags) ve yapılandırılmış özelliklerle ham XML ile uğraşmadan çalışmanıza olanak tanır.

## Why use aspose.page xmp java for EPS metadata?
- **Precision:** Belirli XMP dizi öğelerini doğrudan hedefleyin (ör. title, creator).  
- **Automation:** Meta veri güncellemelerini derleme hatlarına veya toplu işlemlere entegre edin.  
- **Compatibility:** XMP standardını izleyen herhangi bir EPS dosyasıyla çalışır.  

## Prerequisites
Kod kısmına geçmeden önce aşağıdakilerin kurulu olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.  
- Aspose.Page kütüphanesi for Java. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.  

## Import Packages
Başlamak için gerekli sınıfları Java projenize import edin. Aspose.Page JAR dosyasının proje sınıf yoluna (classpath) eklendiğinden emin olun.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## How to Change Array Items with aspose.page xmp java

### Step 1: Get XMP Metadata
İlk olarak EPS dosyanızdan XMP meta verisini alın. Dosyada XMP verisi yoksa, Aspose.Page mevcut PS yorumlarından (ör. %%Creator, %%Title) doldurulmuş yeni bir XMP bloğu oluşturur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Step 2: Set "dc:title" Array Item
Şimdi **dc:title** dizisinin ilk öğesini yeni bir başlık dizesiyle değiştirin.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Step 3: Set "dc:creator" Array Item
Benzer şekilde **dc:creator** dizisinin ilk öğesini güncelleyin.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Step 4: Initialize Output EPS File Stream
Değiştirilen meta verinin kaydedileceği çıktı EPS dosyası için bir akış (stream) hazırlayın.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### Step 5: Save Document with Changed XMP Metadata
Son olarak, belgeyi kaydederek değişiklikleri kalıcı hale getirin.

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Common Pitfalls & Tips
- **Index Out of Bounds:** Sağladığınız indeksin mevcut olduğundan emin olun; aksi takdirde Aspose bir istisna (exception) fırlatır.  
- **Stream Management:** Dosya kilitlenmelerini önlemek için akışları her zaman bir `finally` bloğunda kapatın.  
- **License Activation:** Geçerli bir lisans ayarlamayı unutmak, deneme modunda su işareti (watermark) eklenmiş çıktılar almanıza neden olabilir.

## Conclusion
Tebrikler! **aspose.page xmp java** kullanarak XMP'de dizi öğelerini nasıl değiştireceğinizi başarıyla öğrendiniz. Bu adım‑adım kılavuz, EPS meta verilerini programatik olarak değiştirmenizi sağlayarak otomatik belge iş akışları ve daha zengin içerik yönetimi için kapıyı açar.

## FAQs
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page öncelikle Java için tasarlanmıştır, ancak Aspose diğer diller için benzer kütüphaneler sunar.  
### Where can I find detailed documentation for Aspose.Page for Java?
Dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.  
### Is there a free trial available for Aspose.Page for Java?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.  
### How can I obtain a temporary license for Aspose.Page for Java?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.  
### Where can I purchase the full version of Aspose.Page for Java?
Tam sürümü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Additional Frequently Asked Questions
**Q: Can I update multiple array items in one call?**  
A: Her bir indeks için `setArrayItem` metodunu ayrı ayrı çağırmanız gerekir; toplu güncelleme yöntemi bulunmamaktadır.  

**Q: Does aspose.page xmp java support custom namespaces?**  
A: Evet, tam önekini (ör. `myNS:customProp`) sağlayarak herhangi bir kayıtlı XMP ad alanı ile çalışabilirsiniz.  

**Q: How do I verify that the metadata was updated correctly?**  
A: EPS dosyasını `PsDocument` ile yeniden yükleyip `getXmpMetadata()` metodunu çağırarak değerleri okuyabilir veya bir XMP görüntüleyicide dosyayı inceleyebilirsiniz.  

**Q: Is it possible to remove an array item entirely?**  
A: Belirli bir dizi öğesini silmek için `removeArrayItem(namespace, index)` metodunu kullanın.  

**Q: Will the changes affect the visual appearance of the EPS?**  
A: Hayır. XMP meta verileri görsel olmayan verilerdir; EPS dosyasının grafik içeriğini değiştirmez.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
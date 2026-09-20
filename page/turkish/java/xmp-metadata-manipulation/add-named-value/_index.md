---
date: 2026-09-19
description: Aspose.Page for Java kullanarak EPS dosyalarına XMP adlandırılmış değerleri
  eklemeyi öğrenin – adım adım kod örnekleriyle bir rehber.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Java ile XMP'de Adlandırılmış Değer Ekleme
og_description: Aspose.Page for Java kullanarak EPS dosyalarına XMP adlandırılmış
  değerleri ekleyin. Dakikalar içinde özel metadata eklemek için bu kısa rehberi izleyin.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Java kullanarak EPS dosyalarına XMP adlandırılmış değer ekleme
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Java kullanarak EPS dosyalarına XMP adlandırılmış değer ekleme
url: /tr/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP meta verisine adlandırılmış değer ekleme

## Giriş
Modern Java geliştirmesinde, **XMP eklemeyi** EPS dosyaları içinde öğrenmek, belge kökenini korumak ve aranabilirliği artırmak için gereklidir. **Aspose.Page for Java** ile, XMP paketine özel adlandırılmış değerleri zahmetsizce enjekte edebilirsiniz. Bu öğretici, tam kod parçacıklarıyla birlikte kesin adımları size gösterir; böylece bugün EPS belgelerinize XMP meta verisi eklemeye başlayabilirsiniz.

## Hızlı cevaplar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (Aspose)  
- **Hedef dosya türü?** XMP meta verisi içeren EPS dosyaları  
- **Ana kullanım durumu?** XMP'ye özel adlandırılmış değerler (ör. sayfa boyutu sınırlamaları) eklemek  
- **Önkoşullar?** JDK 8+ ve Aspose.Page for Java kütüphanesi  
- **Tipik uygulama süresi?** Kütüphane kurulduktan sonra 5–10 dakika  

## Asp nedir?
Aspose, dış yazılım gerektirmeden çeşitli belge formatlarını oluşturma, düzenleme, dönüştürme ve render etme imkanı sağlayan API'ler paketidir. Aspose.Page for Java bileşeni özellikle PostScript ve EPS işleme üzerine odaklanır; sayfa içeriği, grafikler ve XMP gibi meta verilere programatik erişim sunar.

## Neden XMP meta verisine adlandırılmış değerler eklenir?
Adlandırılmış değerler, XMP paketinin içinde doğrudan key‑value çiftleri saklamanızı sağlar ve bu değerler aşağı akış araçları tarafından anında okunabilir. Bu, arama motoru uyumluluğunu artırır, iş akışı otomasyonunu mümkün kılar ve düzenleyici bilgileri görsel içeriği değiştirmeden gömerek uyumluluk gereksinimlerini karşılar.

## Bunun önemi nedir?
Adlandırılmış değerler eklemek, tüm EPS dosyasını ayrıştırmadan okunabilen key‑value çiftlerini saklamanızı sağlar. Bu yetenek, otomatik yayınlama hatları, dijital varlık yönetim sistemleri ve meta verinin aşağı akış eylemlerini yönlendirdiği uyumluluk‑odaklı iş akışları için özellikle değerlidir.

## Önkoşullar
İlerlemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK):** Makinenizde yüklü bir JDK (8 veya üzeri).  
- **Aspose.Page for Java Library:** Resmi [Aspose.Page for Java download](https://releases.aspose.com/page/java/) adresinden indirin. JAR dosyasını projenizin sınıf yoluna ekleyin.  
- **Bir EPS dosyası** zaten XMP meta verisi içeren ya da otomatik olarak oluşturulacak.

## Paketleri içe aktar
Gerekli Java paketlerini içe aktararak başlayın. Bu importlar dosya akışlarına, EPS belge modeline ve XMP işleme sınıflarına erişim sağlar.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java kullanarak EPS dosyalarına XMP adlandırılmış değer ekleme
Adlandırılmış bir değer eklemek için EPS dosyasını bir `FileInputStream` ile yükleyin, `XmpMetadata` nesnesini alın veya oluşturun, uygun ad alanına istediğiniz `NamedValue`'yu ekleyin ve ardından `FileOutputStream` ile değiştirilmiş belgeyi yazın. Aspose.Page, eksikse XMP paketini otomatik olarak oluşturur ve yeni meta verinin doğru şekilde gömülmesini sağlar.

### Adım 1: Giriş EPS dosya akışını başlat
**FileInputStream** bir Java I/O sınıfıdır ve bir dosyadan ham baytları okur. Kaynak EPS dosyasını bir `FileInputStream` içine yükleyin. Bu akış, belgeyi Aspose API'sine besler.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro ipucu:** `dataDir` değişkenini yapılandırılabilir tutun, böylece aynı kod farklı ortamlar arasında çalışabilir.

### Adım 2: XMP meta verisini elde et
**XmpMetadata**, bir EPS belgesiyle ilişkili XMP paketini temsil eder. Mevcut XMP paketini alın; EPS dosyasında yoksa Aspose, PS yorumlarından doldurulmuş yeni bir XMP nesnesi oluşturur.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Adım 3: Adlandırılmış değer ekle
**NamedValue**, XMP meta veri ad alanı içinde saklanan bir key‑value çiftidir. XMP yapısına özel bir adlandırılmış değer ekleyin. Bu örnekte `xmpTPg:MaxPageSize` ad alanı altında yeni bir anahtar ekliyoruz.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Neden bu önemli:** Adlandırılmış değerler, aşağı akış uygulamalarının belgeyi tamamen ayrıştırmadan okuyabileceği key‑value çiftlerini saklamanızı sağlar.

### Adım 4: Çıkış EPS dosya akışını başlat
**FileOutputStream** bir Java I/O sınıfıdır ve ham baytları bir dosyaya yazar. Değiştirilmiş EPS'nin kaydedileceği bir `FileOutputStream` hazırlayın.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Adım 5: Belgeyi kaydet
`save` yöntemi değişiklikleri kalıcı hale getirir. Güncellenmiş XMP paketini EPS dosyasına yazar ve yeni adlandırılmış değerin belgenin meta verisinin bir parçası olmasını garanti eder.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Adım 6: Giriş EPS akışını kapat
Orijinal dosya tutamacını kapatmak kaynak sızıntılarını önler ve dosyanın sonraki işlemler için kilitlenmemesini sağlar.

```java
psStream.close();
```

Bu altı adımı izleyerek **Aspose.Page for Java** kullanarak **XMP meta verisine adlandırılmış bir değer eklemiş** oldunuz.

## Yaygın sorunlar ve çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS dosyasında XMP yok ve Aspose bir tane oluşturamadı | EPS'nin en az bir PS yorumu içerdiğinden emin olun veya manuel olarak yeni bir `XmpMetadata` örneği oluşturun. |
| Output file is empty | Çıktı akışı temizlenmemiş/kapatılmamış | `outPsStream.close()`'un bir `finally` bloğunda çağrıldığını doğrulayın (gösterildiği gibi). |
| Duplicate key error | Aynı adlandırılmış değer iki kez eklendi | Eklemeye çalışmadan önce `xmp.containsNamedValue(...)` ile anahtarın zaten mevcut olup olmadığını kontrol edin. |

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java'yi diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Page for Java diğer Java kütüphaneleriyle sorunsuz çalışacak şekilde tasarlanmıştır, geliştirme ortamınızda esneklik sağlar.

**S: Aspose.Page for Java için ücretsiz deneme mevcut mu?**  
C: Evet, Aspose.Page for Java ücretsiz denemesine resmi [Aspose releases page](https://releases.aspose.com/) üzerinden erişebilirsiniz.

**S: Aspose.Page for Java için geçici lisans nasıl alınır?**  
C: Geçici lisans sayfasını ziyaret edin: [temporary license page](https://purchase.aspose.com/temporary-license/) ve Aspose.Page for Java için geçici bir lisans edinin.

**S: Aspose.Page for Java için daha fazla öğretici ve örnek nerede bulunur?**  
C: Kapsamlı öğreticiler ve örnekler için [documentation](https://reference.aspose.com/page/java/) sayfasını keşfedin.

**S: Aspose.Page for Java büyük ölçekli projeler için uygun mu?**  
C: Kesinlikle, Aspose.Page for Java büyük ölçekli projeleri verimli bir şekilde yönetmek için tasarlanmıştır, sağlam belge işleme yetenekleri sunar.

## Sonuç
Bu rehberde **Aspose.Page for Java** kullanarak **EPS dosyalarında XMP meta verisine adlandırılmış değer eklemenin** ne kadar basit olduğunu gösterdik. Yukarıdaki adımlarla belgelerinizi özel meta verilerle zenginleştirebilir, aranabilirliği artırabilir ve daha akıllı aşağı akış işleme olanakları sağlayabilirsiniz.

---

**Last Updated:** 2026-09-19  
**Test Edildiği Versiyon:** Aspose.Page for Java 24.12 (yazım anındaki en son sürüm)  
**Author:** Aspose

## İlgili Öğreticiler

- [How to Add XMP Namespace in EPS Files Using Aspose.Page – Java Tutorial](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Add XMP Metadata to EPS Files Using Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Read XMP using Aspose.Page – Java Guide](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
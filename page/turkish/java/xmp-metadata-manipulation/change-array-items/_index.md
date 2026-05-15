---
date: 2026-05-15
description: aspose.page xmp öğreticisini Java için keşfedin—XMP meta verilerinde
  dizi öğelerini nasıl değiştireceğinizi, EPS başlıklarını, yaratıcıları ve daha fazlasını
  sadece birkaç satır kodla öğrenin.
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Java kullanarak XMP'de Dizi Öğelerini Değiştir
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp öğreticisi: Java kullanarak XMP''de Dizi Öğelerini Değiştir'
url: /tr/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp öğreticisi: XMP'de Dizi Öğelerini Java Kullanarak Değiştirme

## Giriş
Kapsamlı **aspose.page xmp tutorial**'ımıza hoş geldiniz. Bu rehberde, Aspose.Page for Java kullanarak EPS dosyalarındaki XMP meta verilerinde dizi öğelerini adım adım nasıl değiştireceğinizi göstereceğiz. Belge başlığını, yazar listesini veya başka herhangi bir XMP dizisini güncellemeniz gerekse de, süreç basittir, tamamen programatik olup Java 8 + ile çalışır.

## Hızlı Yanıtlar
- **aspose.page xmp java ne yapar?** EPS dosyalarında XMP meta verilerini doğrudan Java'dan okur ve yazar.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Evet—ücretsiz 30 günlük bir deneme mevcuttur; üretim için ticari bir lisans gereklidir.  
- **Hangi JDK sürümü destekleniyor?** Java 8 veya daha yenisi (Java 11, 17 ve 21 dahil).  
- **Diğer meta veri alanlarını değiştirebilir miyim?** Kesinlikle—özel ad alanları dahil herhangi bir XMP özelliği okunabilir veya güncellenebilir.  
- **API iş parçacığı‑güvenli mi?** Çoğu okuma/yazma işlemi, her iş parçacığının kendi `PsDocument` örneğiyle çalıştığında güvenlidir.

## aspose.page xmp java nedir?
`aspose.page xmp java`, Aspose.Page for Java'ın Extensible Metadata Platform (XMP)'yi kullanımı kolay Java nesnelerine soyutlayan bileşenidir. Ham XML ile uğraşmadan dizileri, çantaları ve yapılandırılmış özellikleri manipüle etmenizi sağlar. Pratikte, meta verileri anında düzenlemek için `setArrayItem` ve `removeArrayItem` gibi yüksek seviyeli yöntemlerle çalışırsınız.

## EPS meta verileri için aspose.page xmp java neden kullanılmalı?
Bu kütüphaneyi, ölçekli olarak EPS meta verileri üzerinde kesin ve otomatik kontrol gerektiğinde kullanmalısınız. Aspose.Page **30+ XMP şema alanını** destekler ve **500 MB**'a kadar dosyaları, tüm belgeyi belleğe yüklemeden işleyebilir; bu da size hız ve düşük bellek tüketimi sağlar. API ayrıca değişikliklerin orijinal grafikleri korumasını garanti eder, böylece görsel renderleme etkilenmez.

## Önkoşullar
- Java Development Kit (JDK) 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Page for Java kütüphanesi. En son JAR'ı [buradan](https://releases.aspose.com/page/java/) indirin.  
- Geçerli bir Aspose lisans dosyası (veya deneme lisansı) sınıf yoluna (classpath) yerleştirilmiş.

## aspose.page xmp java ile Dizi Öğelerini Nasıl Değiştirilir
Bu bölüm, tam iş akışını gösterir: EPS dosyasını açın, XMP meta veri nesnesini alın, belirli dizi girişlerini değiştirin ve sonunda güncellenmiş belgeyi diske yazın. Her adım, özlü Java kodlarıyla gösterilir ve kendi uygulamalarınıza entegre etmeyi kolaylaştırır.

### Adım 1: XMP Meta Verisini Al
`document.getXmpMetadata()` metodunu çağırarak EPS dosyasıyla ilişkili XMP meta veri nesnesini alın.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### Adım 2: "dc:title" Dizi Öğesini Ayarla
İlk başlık girişini değiştirmek için `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` kullanın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Adım 3: "dc:creator" Dizi Öğesini Ayarla
Benzer şekilde, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` ilk yaratıcı girişini günceller.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Adım 4: Çıktı EPS Dosya Akışını Başlat
Güncellenmiş belgeyi yazmak için hedef EPS dosyasına işaret eden bir `FileOutputStream` oluşturun.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Adım 5: Değiştirilen XMP Meta Verisiyle Belgeyi Kaydet
`PsDocument` sınıfı bir EPS belgesini temsil eder ve değişiklikleri bir akışa yazmak için `save` metodunu sağlar.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## Yaygın Tuzaklar ve İpuçları
- **Index Out of Bounds:** Hedef indeksin mevcut olduğunu doğrulayın; aksi takdirde Aspose `ArrayIndexOutOfBoundsException` hatası fırlatır.  
- **Stream Management:** Akışları her zaman bir `finally` bloğunda kapatın veya dosya kilitlenmelerini önlemek için try‑with‑resources kullanın.  
- **License Activation:** Geçerli bir lisans uygulamayı unutmak, deneme modunda su işareti (watermark) eklenmiş bir EPS ile sonuçlanır.  
- **Large Files:** 200 MB'den büyük EPS dosyaları için, bellek baskısını önlemek amacıyla JVM yığın boyutunu (`-Xmx2g`) artırmayı düşünün.

## Sıkça Sorulan Sorular

**Q: Tek bir çağrıda birden fazla dizi öğesini güncelleyebilir miyim?**  
A: Hayır. Değiştirmek istediğiniz her indeks için `setArrayItem` çağırmanız gerekir; API toplu güncelleme yöntemi sunmaz.

**Q: aspose.page xmp java özel ad alanlarını destekliyor mu?**  
A: Evet. `setArrayItem` veya `removeArrayItem` çağırırken tam önek (ör. `myNS:customProp`) sağlayın.

**Q: Meta verinin doğru şekilde güncellendiğini nasıl doğrularım?**  
A: EPS'yi `PsDocument` ile yeniden yükleyin, `getXmpMetadata()` çağırın ve dönen değerleri inceleyin veya dosyayı bir XMP görüntüleyicide açın.

**Q: Bir dizi öğesini tamamen kaldırmak mümkün mü?**  
A: Belirli bir XMP dizi girişini silmek için `removeArrayItem(namespace, index)` kullanın.

**Q: Değişiklikler EPS'nin görsel görünümünü etkiler mi?**  
A: Hayır. XMP meta verisi grafik içeriğinden ayrı depolanır ve EPS'nin nasıl render edildiğini değiştirmez.

## Sonuç
Artık Java için **aspose.page xmp tutorial**'ı ustalıkla kullanabiliyor ve EPS XMP meta verilerinde dizi öğelerini güvenle değiştirebiliyorsunuz. Bu yetenek, otomatik belge iş akışları, toplu meta veri güncellemeleri ve görsel veriye dokunmadan daha iyi varlık yönetimi sağlar.

---

**Son Güncelleme:** 2026-05-15  
**Test Edilen:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## İlgili Öğreticiler

- [Java Kullanarak XMP Meta Verisine Dizi Öğeleri Ekle](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp tutorial – Java Kullanarak XMP'de Adlandırılmış Değeri Değiştir](/page/java/xmp-metadata-manipulation/change-named-value/)
- [Java Kullanarak XMP Meta Verisini Okuma – Aspose.Page Kılavuzu](/page/java/xmp-metadata-manipulation/get-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
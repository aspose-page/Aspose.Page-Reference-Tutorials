---
date: 2025-12-20
description: Aspose.Page for Java (aspose.page xmp java) kullanarak XMP'deki dizi
  öğelerini nasıl değiştireceğinizi öğrenin. Adım adım rehberimizle meta verileri
  zahmetsizce düzenleyin ve EPS belgelerinizi bugün geliştirin.
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: 'aspose.page xmp java - XMP''de Dizi Öğelerini Java ile Değiştir'
url: /tr/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: Java Kullanarak XMP'de Dizi Öğelerini Değiştirme

## Giriiş
**Aspose.Page for Java** XMP'de dizini değiştirme konusunda özet rehberimizi kullanarak hoş geldiniz. **aspose.page xmp java** kütüphanesi, EPS dosyalarındaki XMP meta verileri üzerinde tam kontrol sağlar; karakterleri, oluşturucuları ve diğer özellikleri kolayca kişiselleştirmenize olanak tanır. Bu öğreticide, dizi öğelerini değiştirmek için gereken her adım adım adım atmanız ve EPS belgelerinizi kullanabilmenizi ve kişiselleştirebilmenizi sağlarsınız.

## Hızlı Yanıtlar
- **aspose.page xmp java'ya ne işe yarar?** Java üzerinden EPS dosyalarındaki XMP meta dosyalarındaki okur ve yazar.
- **Denemek için lisansa ihtiyacınız var mı?** Evet, ücretsiz bir deneme sürümü mevcuttur, ancak üretim kullanımı için lisans gereklidir.
- **Hangi JDK sürümü destekleniyor mu?** Java8 veya üzeri.
- **Diğer meta verilerinde ortaya çıkabilir mi?** kesinlikle – herhangi bir XMP özelliği okunabilir veya güncellenebilir.
- **API çoklu iş parçacığı (iş parçacığı güvenli) mi?** Çoğu okuma/yazma işlemi, ayrı belge örnekleri üzerinde güvenlidir.

## aspose.page xmp java nedir?
`aspose.page xmp java`, Aspose.Page for Java paketinin XMP (Extensible Metadata Platform) işleme odaklı bir parçasıdır. Düşük seviyede XMP protokolü basit Java ürünlerini dönüştürerek, diziler, çantalar (çantalar) ve teknolojik özelliklerle ve XML ile uğraşmadan çalışmanıza olanak tanır.

## EPS meta verileri için neden aspose.page xmp java kullanılmalı?
- **Precision:** esnek XMP dizisini doğrudan hedefleyin (ör. başlık, yaratıcı).
- **Otomasyon:** Meta veri güncellemelerini satırların bir araya getirilmesi veya toplu işlemlere entegre edin.
- **Uyumluluk:** XMP standardını takip eden herhangi bir EPS dosyasıyla çalışır.

## Önkoşullar
Kodun bölünmesinden önce aşağıdaki kuruluşunuzun olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Java için Aspose.Page kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.

## Paketleri İçe Aktar
Başlamak için gerekli sınıfları Java projenize import edin. Aspose.Page JAR dosyasının proje sınıf yoluna (classpath) eklendiğinden emin olun.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## aspose.page xmp java ile Dizi Öğelerini Değiştirme

### Adım 1: XMP Meta Verilerini Alın
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

### Adım 2: "dc:title" Dizi Öğesini Ayarlayın
Şimdi **dc:title** dizisinin ilk öğesini yeni bir başlık dizesiyle değiştirin.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Adım 3: "dc:creator" Dizi Öğesini Ayarlayın
Benzer şekilde **dc:creator** dizisinin ilk öğesini güncelleyin.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Adım 4: Çıktı EPS Dosya Akışını Başlatın
Değiştirilen meta verinin kaydedileceği çıktı EPS dosyası için bir akış (stream) hazırlayın.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### Adım 5: Değiştirilen XMP Meta Verileriyle Belgeyi Kaydedin
Son olarak, belgeyi kaydederek değişiklikleri kalıcı hale getirin.

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Yaygın Tuzaklar ve İpuçları
- **İndeks Sınır Dışı:** Sağladığınız indeksin mevcut olduğundan emin olun; Aksi takdirde bir istisna (istisna) fırlatır.
- **Akış Yönetimi:** Dosya kilitlenmelerini engellemek için depoları her zaman bir `sonunda` tükendiğinde kapatın.
- **Lisans Aktivasyonu:** geçerli bir lisans ayarlamayı unutmak, deneme modu su işareti (filigran) eklenmiş çıkışlar nedeniyle neden olabilir.

## Çözüm
Tebrikler! **aspose.page xmp java** kullanarak XMP'de yer alan dizini nasıl değiştireceğinizi başarıyla içeriğiniz. Bu adım‑adım yöneticisi, EPS meta yağsız programatik olarak veri aktarımını sağlayarak otomatik belge iş akışları ve daha zengin içerik yönetimi için kapıyı açar.

## Ek Sıkça Sorulan Sorular
**S: Tek çağrıda birden fazla dizi öğesini güncelleyebilir miyim?**
A: Her bir indeks için `setArrayItem` yöntemini ayrı ayrı çağırmanız gerekir; toplu güncelleme yöntemi bulunmamaktadır.

**S: aspose.page xmp Java özel ad alanlarını destekliyor mu?**
A: Evet, tam önekini (ör. `myNS:customProp`) sağlayarak herhangi bir kayıtlı XMP reklam alanı ile çalışabilirsiniz.

**S: Meta verilerin doğru şekilde güncellendiğini nasıl doğrularım?**
A: EPS parçaları `PsDocument` ile yeniden yükleyip `getXmpMetadata()` yöntemini çağırarak değerleri okunabilirir veya bir XMP görüntüleyicide görebilirsiniz.

**S: Bir dizi öğesini tamamen kaldırmak mümkün müdür?**
A: değişen bir diziyi silmek için `removeArrayItem(namespace, index)` yöntemini kullanın.

**S: Değişiklikler EPS'nin görsel görünümünü etkileyecek mi?**
C: Hayır. XMP meta verileri görsel olmayan verilerdir; EPS miktarının grafik özelliklerini değiştirmez.

---

**Son Güncelleme:** 2025-12-20
**Test Edildiği Sürüm:** Aspose.Page for Java 24.11 (yazım anındaki en güncel sürüm)
**Yazar:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-05
description: Aspose.Page for Java kullanarak EPS dosyalarının XMP meta verilerine
  dc:title dizi öğeleri eklemeyi öğrenin. Hızlı sonuçlar için bu adım adım kılavuzu
  izleyin.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Java ile XMP Metadata'ye dc:title Dizi Öğeleri Nasıl Eklenir
url: /tr/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Kullanarak XMP Metadata'ye Dizi Öğeleri Ekleme

## Giriş
Bu öğreticide **dc:title** (ve diğer dizi öğeleri) nasıl XMP metadata'ya EPS dosyası içinde Aspose.Page for Java ile eklenir keşfedeceksiniz. XMP metadata'yı güncellemek, başlıklar, oluşturucular veya anahtar kelimeler gibi aranabilir bilgileri doğrudan grafik dosyalarınıza gömmek istediğinizde faydalıdır. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve değişiklikleri nasıl doğrulayacağınızı göstereceğiz.

## Hızlı Yanıtlar
- **“dc:title” neyi temsil eder?** Dublin Core başlık özelliği olup bir XMP dizisi olarak depolanır.  
- **XMP metadata neden değiştirilir?** Daha iyi varlık yönetimi, aranabilirlik ve standartlara uyumluluk sağlar.  
- **Mevcut bir XMP bloğu gerekli mi?** Hayır—Aspose.Page eksikse PS yorumlarından bir XMP bloğu oluşturur.  
- **Hangi kütüphane sürümü gerekir?** En son 2026 yapısı dahil olmak üzere herhangi bir güncel Aspose.Page for Java sürümü.  
- **Diğer dizi özellikleri ekleyebilir miyim?** Evet—`dc:creator` gibi özellikler için aynı `addArrayItem` metodunu kullanın.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- Aspose.Page for Java kütüphanesi (JAR dosyasını projenizin sınıf yoluna ekleyin).  
- Temel Java geliştirme deneyimi (JDK 8+ önerilir).  
- XMP metadata içeren veya en azından PS metadata yorumları (`%%Title`, `%%Creator` gibi) bulunan bir EPS dosyası.  

## Paketleri İçe Aktarma
Okuma, manipülasyon ve EPS dosyalarını kaydetmek için gerekli sınıfları içe aktarın:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Adım 1: EPS Belgesini Yükleyin ve XMP Metadata'yı Alın
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Burada EPS dosyasını açıyor ve Aspose.Page'den XMP bloğunu istiyoruz. Dosyada XMP yoksa, kütüphane mevcut PS yorumlarını kullanarak otomatik olarak bir XMP bloğu oluşturur; böylece her zaman üzerinde çalışabileceğiniz bir metadata konteyneriniz olur.

## Adım 2: Yeni bir **dc:title** Dizi Öğesi Ekleyin  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Bu satır **dc:title** nasıl eklenir gösterir. `"NewTitle"` ifadesini gömmek istediğiniz gerçek başlıkla değiştirin. Metod, mevcut başlık dizisine değeri ekler ve önceki başlıkları korur.

## Adım 3: Yeni bir **dc:creator** Dizi Öğesi Ekleyin  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Benzer şekilde `dc:creator` özelliğini zenginleştirebilirsiniz. Birden fazla oluşturucu saklanabilir; her çağrı başka bir giriş ekler.

## Adım 4: Çıktı Akışını Hazırlayın  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Değiştirilmiş EPS dosyası için bir akış oluşturuyoruz. Farklı bir dosya adı (`xmp3_changed.eps`) kullanmak, orijinal dosyanın dokunulmaz kalmasını sağlar.

## Adım 5: Güncellenmiş XMP Metadata ile Belgeyi Kaydedin  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save` çağrısı EPS verisini güncellenmiş XMP bloğu ile birlikte yazar. `finally` bloğu, bir istisna oluşsa bile dosya tutamacının serbest bırakılmasını garanti eder.

## Neden Önemlidir
Doğru `dc:title` ve `dc:creator` değerlerini gömmek şunları iyileştirir:

- **Aranabilirlik** dijital varlık yönetim (DAM) sistemlerinde.  
- **Uyumluluk** metadata gerektiren yayın standartlarıyla.  
- **İş birliği**, ekip üyelerinin EPS'yi açmadan dosya içeriğini hızlıca tanımlamasını sağlar.

## Yaygın Tuzaklar ve İpuçları
- **Tuzak:** Mevcut dizi öğelerini istemeden üzerine yazmak.  
  **İpucu:** Yeni eklemeden önce mevcut değerleri görmek için `xmp.getArrayItems("dc:title")` kullanın.  
- **Tuzak:** Akışları kapatmayı unutmak, dosya kilitlenmelerine yol açar.  
  **İpucu:** I/O işlemlerini her zaman try‑with‑resources veya gösterildiği gibi bir `finally` bloğu içinde sarın.  
- **İpucu:** Birden fazla başlık veya oluşturucu eklemek için birden çok `addArrayItem` çağrısını zincirleyebilirsiniz.

## Sık Sorulan Sorular

### Aspose.Page for Java'ı diğer belge formatlarıyla kullanabilir miyim?
Evet, Aspose.Page EPS, PDF ve XPS dahil çeşitli belge formatlarını destekler.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page for Java dokümantasyonunu nerede bulabilirim?
Dokümantasyon [burada](https://reference.aspose.com/page/java/) mevcuttur.

### Aspose.Page for Java'ı nasıl satın alabilirim?
Ürünü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Aspose.Page for Java için geçici lisanslar mevcut mu?
Evet, geçici bir lisans alabilirsiniz [buradan](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
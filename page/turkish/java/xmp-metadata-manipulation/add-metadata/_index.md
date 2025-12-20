---
date: 2025-12-20
description: Aspose Page Java öğreticisiyle EPS dosyalarına XMP meta verisi eklemeyi
  öğrenin. Belge yönetiminizi geliştirmek için bu adım adım kılavuzu izleyin.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java Öğreticisi – EPS Dosyalarına XMP Meta Verisi Ekleme
url: /tr/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak XMP'de Meta Veri Ekleme

## Giriş
Bu **aspose page java tutorial** içinde, Java kullanarak belgenizin meta verisini XMP bilgisi ekleyerek nasıl geliştireceğinizi öğreneceksiniz. Bu adım‑adım kılavuz, mevcut bir EPS dosyasını okuma, XMP meta verisini çıkarma ve değişiklikleri Aspose.Page for Java kütüphanesiyle diske kaydetme süreçlerini size gösterir. Eğitim sonunda, herhangi bir EPS iş akışında XMP ile çalışmak için sağlam, yeniden kullanılabilir bir desen elde edeceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java  
- **Her EPS dosyasına XMP ekleyebilir miyim?** Evet – API, zaten mevcut değilse yeni bir XMP bloğu oluşturur.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve sonrası.  
- **Uygulama ne kadar sürer?** Temel bir meta veri güncellemesi için genellikle 10 dakikadan az.

## Aspose Page Java Eğitimine Genel Bakış
Bu eğitim, EPS dosyalarında XMP meta verisini manipüle etmek için gereken temel adımları gösterir. Bu adımları anlamak, meta veri işleme süreçlerini daha büyük belge‑işleme hatlarına entegre etmenize, aranabilirliği artırmanıza ve dijital varlık yönetimi için endüstri standartlarına uymanıza yardımcı olur.

## Önkoşullar
Eğitime başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
- Java programlama temellerine aşina olmak.  
- Aspose.Page for Java kütüphanesinin kurulu olması. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.  
- Değiştirmek istediğiniz bir EPS dosyası.

## Paketleri İçe Aktarma
İlk olarak, Java programınıza gerekli paketleri içe aktarın:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Adım 1: XMP Meta Verisini Alın
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

`"Your Document Directory"` ifadesini belgelerinizin bulunduğu gerçek yol ile değiştirin.

## Adım 2: CreatorTool Değerini Alın
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Adım 3: CreateDate Değerini Alın
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Adım 4: Title Değerini Alın
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Adım 5: Format Değerini Alın
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Adım 6: Creator Değerini Alın
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Adım 7: MetadataDate Değerini Alın
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Adım 8: Yeni XMP Meta Verisiyle Belgeyi Kaydedin
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Son olarak, giriş EPS akışını kapatmayı unutmayın:

```java
// Close input EPS stream
psStream.close();
```

Artık Aspose.Page for Java kullanarak EPS dosyanıza meta veri başarıyla eklediniz!

## Sonuç
Bu **aspose page java tutorial** içinde, Aspose.Page for Java kütüphanesini kullanarak bir EPS dosyasına XMP meta verisi eklemeyi inceledik. Bu güçlü API, belge meta verisini programlı olarak manipüle etmenizi sağlar ve varlıklarınızı düzenli ve aranabilir tutmanıza yardımcı olur.

## Sıkça Sorulan Sorular

**S: Aspose.Page for Java ücretsiz mi?**  
C: Aspose.Page for Java ticari bir üründür. Özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz [burada](https://releases.aspose.com/).

**S: Aspose.Page for Java belgelerine nereden ulaşabilirim?**  
C: Belgeler [burada](https://reference.aspose.com/page/java/) mevcuttur.

**S: Aspose.Page for Java için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Page for Java hangi dosya formatlarını destekliyor?**  
C: Aspose.Page for Java, EPS, PDF ve XPS dahil çeşitli formatları destekler.

**S: Aspose.Page for Java’yı satın alabilir miyim?**  
C: Evet, Aspose.Page for Java’yı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Meta veri eklerken büyük EPS dosyalarını nasıl yönetebilirim?**  
C: Bellek kullanımını düşük tutmak için dosyayı akış (stream) şeklinde işleyin (gösterildiği gibi) ve akışları hemen kapatın.

**S: Mevcut XMP alanlarını sadece okumak yerine değiştirebilir miyim?**  
C: Kesinlikle – `xmp.put(key, value)` kullanarak kaydetmeden önce yeni girişler ekleyebilir veya mevcutları güncelleyebilirsiniz.

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen Sürüm:** Aspose.Page for Java 24.12 (en yeni)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
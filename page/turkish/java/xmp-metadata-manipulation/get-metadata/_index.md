---
date: 2026-05-25
description: Java ile aspose.page kullanarak XMP nasıl okunur öğrenin. Bu adım adım
  rehber, XMP metadata, oluşturucu bilgisi, zaman damgaları, küçük resimler ve daha
  fazlasının çıkarılmasını gösterir.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Java ile XMP Metadata Okuma
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page ile XMP Okuma – Java Rehberi
url: /tr/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP'den Metaveri Almak Java Kullanarak

## Aspose.Page (Java) ile XMP Nasıl Okunur?

Load the EPS file with `new Document("file.eps")`—the `Document` class represents a loaded file. Call `getXmpMetadata()`, which extracts the XMP packet, and then query the returned `XmpMetadata` object—a map‑like interface for XMP properties—to retrieve the keys you need. This is all required to read XMP using Aspose.Page. The API abstracts the low‑level parsing, so you get a ready‑to‑use map of properties in just two lines of code.

Java ve Aspose.Page kütüphanesi ile **XMP** meta verilerini nasıl okuyacağınızı gösteren adım adım öğreticimize hoş geldiniz. XMP (Extensible Metadata Platform), belgeler içinde zengin meta verileri gömmek için yaygın olarak benimsenen bir standarttır. Bu kılavuzun sonunda belge formatı XMP'sini okuyabilecek, oluşturucu bilgilerini, zaman damgalarını, küçük resimleri ve daha fazlasını çekebilecek; böylece daha akıllı belge‑analiz çözümleri geliştirebileceksiniz.

## Hızlı Yanıtlar
- **“XMP okuma” ne demektir?** Bir dosyanın içinde saklanan XMP paketini programatik olarak çıkarmak anlamına gelir.  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java (resmi sayfadan [burada](https://releases.aspose.com/page/java/) indirebilirsiniz).  
- **Lisans gerekli mi?** Üretim ortamı için geçici ya da tam lisans gerekir; değerlendirme için ücretsiz deneme sürümü yeterlidir.  
- **Desteklenen Java sürümü nedir?** Java 8 ve üzeri.  
- **Diğer formatlardan XMP okunabilir mi?** Evet – Aspose.Page EPS, PDF, JPEG, PNG ve 20’den fazla diğer formattan XMP çıkarabilir.

## Önkoşullar
Kodlamaya başlamadan önce şunlara sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK)** – Java 8+ yüklü ve yapılandırılmış olmalı.  
- **Aspose.Page for Java** – Kütüphaneyi resmi siteden [burada](https://releases.aspose.com/page/java/) indirin.  
- XMP meta verisi içeren bir EPS dosyası (ör. `xmp1.eps`).  

## Paketleri İçe Aktarma
`XmpMetadata` sınıfı `com.aspose.page.xmp` ad alanında, `Document` sınıfı ise `com.aspose.page` içinde bulunur. EPS dosyası ve meta verileriyle çalışabilmek için her ikisini de içe aktarın.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Adım 1: Giriş EPS Dosya Akışını Başlatma
Belge dizininizin yolunu ayarlayın ve giriş EPS dosya akışını başlatın.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Adım 2: XMP Meta Verisini Alın
`XmpMetadata`, Aspose.Page'in bir belgeden çıkarılan XMP paketini tutan nesnesidir. `document.getXmpMetadata()` ile alın. Dosyada XMP yoksa, API mevcut PostScript yorumlarından minimal bir paket oluşturur.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 3: CreatorTool Bilgisini Çıkarma
`CreatorTool` anahtarı `xmp` ad alanı altında bulunur ve dosyayı oluşturan uygulamayı kaydeder. Varlığını kontrol edin ve değerini yazdırın.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Adım 4: CreateDate Bilgisini Çıkarma
`CreateDate`, belgenin ilk oluşturulduğu zaman damgasını saklar. Aynı `containsKey`/`get` desenini kullanarak okuyun.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Adım 5: Küçük Resim Genişliğini Alın
Küçük resimler mevcutsa, `xmp:Thumbnails` dizisi bir veya daha fazla giriş içerir. Her giriş `width`, `height` ve ikili veri içerir. Örnek, ilk küçük resmin genişliğini çıkarır.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Adım 6: Format Bilgisini Çıkarma
`format` anahtarı orijinal dosya formatını (ör. “application/postscript”) gösterir. Bu, kaynak tiplerini kaydetmek veya doğrulamak istediğinizde faydalıdır.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Adım 7: DocumentID'yi Alın
`DocumentID`, oluşturucu uygulama tarafından atanan benzersiz bir tanımlayıcıdır. Büyük varlık kütüphanelerinde yinelenenleri ayıklamak için kullanılabilir.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Neden Önemli
Aspose.Page **20+** dosya formatından XMP okuyabilir ve belgeyi belleğe tamamen yüklemeden **500 MB**'a kadar işleyebilir; bu da kritik meta verilere hızlı ve düşük maliyetli erişim sağlar. Bu yetenek, toplu işleme hatları, dijital varlık yönetim sistemleri ve aranabilir, makine‑okunur belge özelliklerine dayanan her çözüm için hayati öneme sahiptir.

## Yaygın Tuzaklar ve İpuçları
- **XMP eksik:** Bazı EPS dosyalarında XMP bulunmayabilir. `getXmpMetadata()` çağrısı mevcut PS yorumlarından minimal bir set oluşturur, ancak tam meta veri gömülü değilse elde edilemez.  
- **Küçük Resim Dizileri:** `xmp:Thumbnails` anahtarı birden çok giriş tutabilir. Örnek sadece ilkini çıkarır; tüm küçük resimleri istiyorsanız diziyi döngüyle işleyin.  
- **Ad Alanı Bilinci:** XMP anahtarları ad alanları kullanır (ör. `xmp:`, `dc:`). Tam anahtar adını referans aldığınızdan emin olun; aksi takdirde `containsKey` false döner.  

## Sık Sorulan Sorular
### Aspose.Page for Java'yı başka programlama dilleriyle kullanabilir miyim?
Evet, Aspose.Page Java, .NET ve birkaç diğer dili destekler. Tam listeyi [belgelendirmede](https://reference.aspose.com/page/java/) bulabilirsiniz.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page for Java için destek nereden alınır?
Topluluk yardımı ve resmi destek için [Aspose.Page forumuna](https://forum.aspose.com/c/page/39) göz atın.

### Aspose.Page for Java için geçici lisans nasıl alınır?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.Page for Java için ek kaynaklar var mı?
Tam [belgelendirmeyi](https://reference.aspose.com/page/java/) inceleyin ve kütüphaneyi [buradan](https://releases.aspose.com/page/java/) indirin.

## Ek SSS
**S: Bu yaklaşım XMP içeren PDF dosyalarında çalışır mı?**  
C: Evet, Aspose.Page PDF, EPS ve çeşitli görüntü formatlarından XMP okuyabilir.

**S: XMP meta verisini okuduktan sonra değiştirebilir miyim?**  
C: Kesinlikle. `XmpMetadata` nesnesi değiştirilebilir; anahtar ekleyebilir, güncelleyebilir veya kaldırabilir ve ardından belgeyi kaydedebilirsiniz.

**S: Yalnızca boyutlar değil, tüm küçük resim görüntülerini çıkarmanın bir yolu var mı?**  
C: Her küçük resim girişinin `xmpGImg:data` özelliğinden ikili veriyi alıp bir dosyaya yazabilirsiniz.

## Sonuç
Java ve Aspose.Page kullanarak **XMP meta verisini nasıl okuyacağınızı** artık biliyorsunuz. Bu adımları izleyerek oluşturucu araçları, zaman damgalarını, küçük resimleri, format bilgisini ve belge kimliklerini çıkarabilir; EPS dosyalarınızın gömülü meta verileri hakkında tam bir içgörü elde edebilirsiniz. Uygulamalarınız için daha zengin veri çekmek amacıyla ek XMP ad alanlarını keşfetmekten çekinmeyin.

---

**Son Güncelleme:** 2026-05-25  
**Test Edilen Versiyon:** Aspose.Page for Java 24.12 (en son)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose Page Java Öğreticisi – EPS Dosyalarına XMP Meta Verisi Ekle](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp öğreticisi – Java ile XMP'ye Ad Alanı Ekle](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp öğreticisi – Java ile XMP'de Adlandırılmış Değeri Değiştir](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
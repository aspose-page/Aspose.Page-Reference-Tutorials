---
date: 2025-12-21
description: Java ve Aspose.Page kullanarak XMP meta verilerini nasıl okuyacağınızı
  öğrenin. Bu adım adım kılavuz, belge formatı XMP'yi nasıl okuyacağınızı ve temel
  özellikleri nasıl çıkaracağınızı gösterir.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Java Kullanarak XMP Metaverisini Okuma – Aspose.Page Rehberi
url: /tr/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP'den Metaveri Almak Java ile

## Java Kullanarak XMP Metaverisini Okuma

Adım adım öğreticimize hoş geldiniz; bu öğretici **XMP'yi nasıl okuyacağınızı** Java ve Aspose.Page kütüphanesi ile gösterir. XMP (Extensible Metadata Platform), belgeler içinde zengin metaveri yerleştirmek için yaygın olarak benimsenen bir standarttır. Bu rehberin sonunda belge formatı XMP'yi okuyabilecek, oluşturucu bilgilerini, zaman damgalarını, küçük resimleri ve daha fazlasını çıkarabilecek ve daha akıllı belge‑analiz çözümleri oluşturabileceksiniz.

## Hızlı Yanıtlar
- **“how to read xmp” ne anlama geliyor?** Dosyalardan programlı olarak XMP metaverisi çıkarmak anlamına gelir.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for Java (Aspose indirme sayfasından temin edilebilir).  
- **Lisans gerekiyor mu?** Üretim kullanımı için geçici veya tam lisans gerekir; ücretsiz deneme mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya üzeri.  
- **XMP'yi diğer formatlardan okuyabilir miyim?** Evet, Aspose.Page EPS, PDF ve XMP gömen çeşitli görüntü türlerini işleyebilir.

## Önkoşullar
Before diving into the code, make sure you have:

- **Java Development Kit (JDK)** – Makinenizde Java 8+ yüklü ve yapılandırılmış.  
- **Aspose.Page for Java** – Kütüphaneyi resmi siteden [buradan](https://releases.aspose.com/page/java/) indirin.  
- XMP metaverisi içeren bir EPS dosyası (ör. `xmp1.eps`).  

## Paketleri İçe Aktarma
In your Java project, import the necessary packages:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Adım 1: Giriş EPS Dosya Akışını Başlatma
Begin by setting the path to your document directory and initializing the input EPS file stream.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Adım 2: XMP Metaverisini Alın
Retrieve XMP metadata from the EPS file. If the file lacks XMP metadata, a new one will be generated with values from PS metadata comments.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Adım 3: CreatorTool Bilgisini Çıkarın
Check and print the "CreatorTool" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Adım 4: CreateDate Bilgisini Çıkarın
Check and print the "CreateDate" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Adım 5: Küçük Resim Genişliğini Alın
If thumbnails exist, extract and print the width of the first thumbnail.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Adım 6: Format Bilgisini Çıkarın
Check and print the "format" value from the XMP metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Adım 7: DocumentID'yi Alın
Check and print the "DocumentID" value from the XMP metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Neden Önemli
XMP metaverisini okumak, bir belgeyi görüntüleyiciyle açmadan, kaynağını, oluşturulma tarihini ve diğer temel özelliklerini programlı olarak keşfetmenizi sağlar. Bu, toplu işleme, içerik yönetim sistemleri ve metaverinin indeksleme ve aramayı yönlendirdiği dijital varlık hatları için özellikle faydalıdır.

## Yaygın Tuzaklar ve İpuçları
- **XMP Eksikliği:** Bazı EPS dosyalarında XMP bulunmayabilir. `getXmpMetadata()` çağrısı mevcut PS yorumlarına dayanarak minimal bir set oluşturur, ancak gömülü olmadıkça tam metaveri elde edemezsiniz.  
- **Küçük Resim Dizileri:** `xmp:Thumbnails` anahtarı birden çok giriş tutabilir. Örnek sadece ilkini çıkarır; tüm küçük resimlere ihtiyacınız varsa diziyi döngüyle işleyin.  
- **Namespace Bilinci:** XMP anahtarları namespace kullanır (ör. `xmp:`, `dc:`). Tam anahtar adını kullandığınızdan emin olun; aksi takdirde `containsKey` false dönecektir.

## Sıkça Sorulan Sorular
### Aspose.Page for Java'ı diğer programlama dilleriyle kullanabilir miyim?
Evet, Aspose.Page Java, .NET ve daha fazlası dahil olmak üzere birden çok dili destekler. Detaylar için [belgelere](https://reference.aspose.com/page/java/) bakın.

### Aspose.Page for Java için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Page for Java için desteği nereden bulabilirim?
Topluluk desteği için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### Aspose.Page for Java için geçici lisans nasıl alabilirim?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

### Aspose.Page for Java için ek kaynaklar var mı?
Tam [belgelere](https://reference.aspose.com/page/java/) göz atın ve kütüphaneyi [buradan](https://releases.aspose.com/page/java/) indirin.

## Ek SSS
**S: Bu yöntem XMP içeren PDF dosyalarında çalışır mı?**  
C: Evet, Aspose.Page PDF, EPS ve çeşitli görüntü formatlarından XMP okuyabilir.

**S: XMP metaverisini okuduktan sonra değiştirebilir miyim?**  
C: Kesinlikle. `XmpMetadata` nesnesi değiştirilebilir; anahtar ekleyebilir, güncelleyebilir veya kaldırabilir ve ardından belgeyi kaydedebilirsiniz.

**S: Sadece boyutlar değil, tüm küçük resim görüntülerini çıkarmanın bir yolu var mı?**  
C: Her küçük resim girişinin `xmpGImg:data` özelliğinden ikili veriyi alabilir ve bir dosyaya yazabilirsiniz.

## Sonuç
Artık Java ve Aspose.Page kullanarak **XMP'yi nasıl okuyacağınızı** ustaca biliyorsunuz. Bu adımları izleyerek oluşturucu araçları, zaman damgalarını, küçük resimleri, format bilgilerini ve belge kimliklerini çıkarabilir; EPS dosyalarınızda gömülü metaveriye tam bir bakış elde edebilirsiniz. Uygulamalarınız için daha zengin veri elde etmek amacıyla ek XMP namespace'leriyle denemeler yapmaktan çekinmeyin.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

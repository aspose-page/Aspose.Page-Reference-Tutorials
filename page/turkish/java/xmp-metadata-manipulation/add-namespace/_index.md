---
date: 2026-03-08
description: Aspose.Page for Java ile EPS dosyalarına XMP ad alanı eklemeyi öğrenin
  – adım adım xmp ve xmp ad alanı ekleme öğreticisi java rehberi.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Aspose.Page Kullanarak EPS Dosyalarına XMP Ad Alanı Nasıl Eklenir – Java Öğreticisi
url: /tr/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

NamespaceURI` çağrısındaki önek ve URI'yi değiştirmeniz yeterlidir.

## XMP Namespace Nedir?

... etc.

Let's translate each paragraph.

I'll write full content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Kullanarak EPS Dosyalarına XMP Namespace Ekleme – Java Öğreticisi

## Hızlı Yanıtlar
- **Ana hedef nedir?** Bir EPS dosyasına özel bir XMP namespace ve özelliği eklemek.  
- **Hangi kütüphane gereklidir?** Aspose.Page for Java.  
- **Test için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Kaç kod değişikliği gerekiyor?** Her adım için bir olmak üzere sadece beş kısa kod parçacığı.  
- **Bu deseni diğer namespace'ler için yeniden kullanabilir miyim?** Evet, `registerNamespaceURI` çağrısındaki önek ve URI'yi değiştirmeniz yeterlidir.

## XMP Namespace Nedir?

XMP (Extensible Metadata Platform) namespace, ilgili metadata özelliklerini ortak bir URI altında gruplayan benzersiz bir tanımlayıcıdır. Bir namespace kaydetmek, mevcut standartlarla çakışmadan özel verileri (ör. şirket içi etiketler) depolamanızı sağlar.

## XMP Manipülasyonu İçin Aspose.Page Neden Kullanılmalı?

- **EPS ve PDF metadata üzerinde tam kontrol** sağlar, Adobe araçlarına ihtiyaç duymaz.  
- **XMP bloğu yoksa otomatik oluşturma**, PS yorumlarından yararlanır.  
- **Çapraz platform Java desteği**, mevcut iş akışlarına kolay entegrasyon imkanı verir.

## Ön Koşullar

- Aspose.Page for Java: Kütüphanenin kurulu olduğundan emin olun. İndirmek için [buraya](https://releases.aspose.com/page/java/) tıklayın.  
- Java Geliştirme Ortamı: Sisteminizde bir Java ortamı kurun.  
- Belge Dosyası: XMP metadata içeren bir EPS dosyanız olsun. Eğer XMP metadata içermiyorsa, kütüphane PS metadata yorumlarından bir tane oluşturur.

## Paketleri İçe Aktarma

Başlamak için gerekli paketleri Java projenize dahil edin:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Adım 1: XMP Metadata’yı Alın

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### Neden Önemli?
`XmpMetadata` nesnesini almak, belgenin metadata’sına canlı bir referans sağlar; böylece kaydetmeden önce okuyabilir, değiştirebilir veya genişletebilirsiniz.

## Adım 2: Yeni Namespace’i Kaydedin *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Açıklama
`registerNamespaceURI` metodu, kısa bir önek (`tmp`) ile tam bir URI’yi eşleştirir. Bu adım, XMP özelliklerinin kayıtlı bir namespace ile nitelendirilmesi gerektiği için sonraki işlem için zorunludur.

## Adım 3: Yeni Özellik Ekleyin

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### Ne Oluyor?
Burada `tmp:newKey` adında özel bir özellik oluşturup değerini `"NewValue"` olarak atıyoruz. İş mantığınıza uygun olarak anahtar ve değeri istediğiniz gibi değiştirebilirsiniz.

## Adım 4: Belgeyi Kaydedin

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### İpucu
`save` çağrısını her zaman bir `try/finally` bloğu içinde (veya `try‑with‑resources` kullanarak) sarmalayın; böylece bir istisna oluşsa bile çıktı akışı kapatılır.

## Adım 5: Akışları Kapatın

```java
// Close input EPS stream
psStream.close();
```

### En İyi Uygulama
Giriş akışını kapatmak, dosya tutamacını hemen serbest bırakır ve Windows sistemlerinde dosya kilitleme sorunlarını önler.

## Yaygın Sorunlar ve Çözümler

| Sorun | Muhtemel Neden | Çözüm |
|-------|----------------|------|
| Kaydedildikten sonra XMP bloğu görünmüyor | Orijinal EPS XMP içermiyor ve yorumlar yetersiz | EPS’nin standart PS yorumlarını (`%%Creator`, `%%Title` vb.) içerdiğinden emin olun veya bir namespace kaydetmeden önce boş bir `XmpMetadata` nesnesi oluşturun. |
| `registerNamespaceURI` bir istisna fırlatıyor | Önek zaten kullanılıyor | Benzersiz bir önek seçin veya mevcut namespace’leri `xmp.getRegisteredNamespaces()` ile kontrol edin. |
| Kaydedilen dosya bozuk | Çıktı akışı flush edilmemiş | `try‑with‑resources` kullanın veya kapatmadan önce `outPsStream.flush()` çağrısını ekleyin. |

## Sonuç

Bu **how to add xmp** öğreticisini izleyerek, Aspose.Page for Java kullanarak EPS dosyalarına özel namespace ve özellik eklemek için tekrar kullanılabilir bir yöntem elde ettiniz. Bu yetenek, iş akışı kimlikleri, şirket içi etiketler veya sonraki sistemler için entegrasyon verileri gibi daha zengin metadata stratejileri oluşturmanıza olanak tanır.

## SSS

### Aspose.Page for Java’yı başka programlama dilleriyle kullanabilir miyim?
Aspose.Page öncelikle Java’yı destekler, ancak .NET gibi diğer diller için de sürümleri mevcuttur.

### Ücretsiz deneme sürümü var mı?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) keşfedebilirsiniz.

### Kapsamlı belgeleri nereden bulabilirim?
Belgelere [buradan](https://reference.aspose.com/page/java/) ulaşabilirsiniz.

### Geçici bir lisans nasıl alınır?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.Page için topluluk forumları var mı?
Evet, toplulukla [Aspose.Page forumunda](https://forum.aspose.com/c/page/39) iletişime geçebilirsiniz.

---

**Son Güncelleme:** 2026-03-08  
**Test Edilen Sürüm:** Aspose.Page for Java 24.10 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
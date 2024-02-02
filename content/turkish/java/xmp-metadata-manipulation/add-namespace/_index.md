---
title: Java kullanarak XMP'ye Ad Alanı ekleme
linktitle: Java kullanarak XMP'ye Ad Alanı ekleme
second_title: Aspose.Page Java API'si
description: Aspose.Page for Java ile belge manipülasyonunun gücünün kilidini açın. Bu kapsamlı kılavuzda XMP ad alanlarını zahmetsizce eklemeyi öğrenin.
type: docs
weight: 13
url: /tr/java/xmp-metadata-manipulation/add-namespace/
---

## giriiş

Belge işleme alanında Aspose.Page for Java, çok çeşitli işlevler sunan güçlü bir araç olarak öne çıkıyor. Güçlü özelliklerden biri, Java kullanarak XMP'ye (Genişletilebilir Meta Veri Platformu) ad alanları ekleme yeteneğidir. Bu eğitim, süreci takip edilmesi kolay adımlara bölerek size süreç boyunca rehberlik edecektir.

## Önkoşullar

Öğreticiye başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for Java: Kütüphanenin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/page/java/).

- Java Geliştirme Ortamı: Sisteminizde bir Java ortamı kurun.

- Belge Dosyası: XMP meta verilerini içeren bir EPS dosyasına sahip olun. XMP meta verileri içermiyorsa kitaplık, PS meta veri yorumlarına dayalı olarak bir tane oluşturacaktır.

## Paketleri İçe Aktar

Başlamak için gerekli paketleri Java projenize aktarın:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 1. Adım: XMP Meta Verilerini Alın

```java

// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Giriş EPS dosya akışını başlat
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarındaki değerlerle dolu yeni bir tane oluşturun (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 2. Adım: Yeni Ad Alanını Kaydedin

```java
// "Tmp" ön ekiyle "http://www.some.org/schema/tmp#" yeni XML ad alanını ekleyin
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## 3. Adım: Yeni Mülk Ekle

```java
// Yeni XML ad alanına yeni "tmp:newKey" özelliğini ekleyin
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Adım 4: Belgeyi Kaydet

```java
// Çıkış EPS dosya akışını başlat
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Belgeyi değiştirilmiş XMP meta verileriyle kaydedin
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 5. Adım: Yayınları Kapatın

```java
// Giriş EPS akışını kapat
psStream.close();
```

Artık Aspose.Page for Java'yı kullanarak XMP'ye başarıyla bir ad alanı eklediniz. Daha fazla özelliği keşfetmekten ve bu kütüphanenin tüm potansiyelini ortaya çıkarmaktan çekinmeyin.

## Çözüm

Aspose.Page for Java, EPS dosyalarındaki XMP meta verilerinin işlenmesi gibi karmaşık bir görevi basitleştirir. Bu adım adım kılavuzu takip ederek belge işleme yeteneklerinizi geliştirecek değerli bir beceri elde ettiniz.

## SSS

### Aspose.Page for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Page öncelikle Java'yı destekler, ancak .NET gibi diğer diller için de versiyonlar mevcuttur.

### Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).

### Kapsamlı belgeleri nerede bulabilirim?
 Belgelere bakın[Burada](https://reference.aspose.com/page/java/).

### Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Page için topluluk forumları var mı?
 Evet, toplulukla etkileşime geçebilirsiniz[Aspose.Page forumu](https://forum.aspose.com/c/page/39).
---
title: Aspose.Page for .NET ile Değerleri Değiştirme
linktitle: Değişim değerleri
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile EPS dosya işleme konusunda uzmanlaşın. XMP meta veri değerlerini zahmetsizce değiştirin.
type: docs
weight: 17
url: /tr/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## giriiş

Belge işlemenin dinamik dünyasında Aspose.Page for .NET, geliştiricilere EPS dosyalarını zahmetsizce işleme yeteneği sunan güçlü bir araç olarak öne çıkıyor. Bu derste, Aspose.Page for .NET'i kullanarak EPS dosyalarındaki değerleri değiştirme sürecini ele alacağız. İster deneyimli bir geliştirici olun ister meraklı bir başlangıç seviyesinde olun, bu adım adım kılavuz sizi EPS dosyalarınızdaki XMP meta verilerini verimli bir şekilde değiştirmek için gereken becerilerle donatacaktır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

### 1. .NET Kütüphanesi için Aspose.Page

Geliştirme ortamınızda Aspose.Page for .NET kitaplığının kurulu olduğundan emin olun. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

### 2. Belge Dizini

Belgeleriniz için bir dizin oluşturun. Bu, EPS dosyalarınızın depolandığı konum olacaktır.

Artık önkoşullarımızı sıraladığımıza göre, bir sonraki önemli adımlara geçelim.

## Ad Alanlarını İçe Aktar

Herhangi bir .NET projesinde Aspose.Page'in işlevselliklerinden yararlanmak için gerekli ad alanlarının içe aktarılması önemlidir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 1. Adım: EPS dosyası giriş akışını başlatın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// EPS dosyası giriş akışını başlat
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## 2. Adım: Akıştan PsDocument örneği oluşturun

```csharp
//Akıştan PsDocument örneği oluşturun
PsDocument document = new PsDocument(psStream);
```

Artık aşamayı belirlediğimize göre, eğitimimizin özüne geçelim: EPS dosyasındaki XMP meta veri değerlerini değiştirme.

## 3. Adım: XMP meta verilerini alın

```csharp
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarından gelen değerlerle dolu yeni bir dosya alırız (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## 4. Adım: XMP meta veri değerlerini değiştirin

Şimdi XMP meta verilerindeki bazı anahtar değerleri değiştirelim:

### Adım 4.1: ModifyDate değerini değiştirin

```csharp
// ModifyDate değerini değiştir
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Adım 4.2: Yaratıcı değerini değiştirin

```csharp
// Yaratıcı değerini değiştir
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Adım 4.3: Başlık değerini değiştirin

```csharp
// Başlık değerini değiştir
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Bu değişiklikleri yaptıktan sonra son adıma geçelim - değiştirilen EPS dosyasını kaydetme.

## Adım 5: EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin

### Adım 5.1: Çıkış akışını oluşturun

```csharp
// Çıkış akışı oluştur
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Adım 5.2: EPS dosyasını kaydedin

```csharp
// EPS dosyasını kaydet
document.Save(outPsStream);
```

Son olarak giriş akışını kapatın:

```csharp
finally
{
    psStream.Close();
}
```

Tebrikler! Aspose.Page for .NET'i kullanarak bir EPS dosyasındaki XMP meta veri değerlerini başarıyla değiştirdiniz.

## Çözüm

Bu eğitimde, Aspose.Page for .NET'i kullanarak EPS dosyalarındaki değerleri değiştirmenin sorunsuz sürecini araştırdık. Bir geliştirici olarak artık etkili belge işleme için güçlü bir araca sahipsiniz.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer dosya formatlarıyla kullanabilir miyim?

Cevap1: Aspose.Page öncelikli olarak EPS dosya manipülasyonuna odaklanır. Diğer formatlar için Aspose'un geniş ürün yelpazesini keşfedin.

### S2: Deneme sürümü mevcut mu?

 Cevap2: Evet, Aspose.Page for .NET'i mevcut ücretsiz deneme sürümüyle deneyebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Ayrıntılı belgeleri nerede bulabilirim?

 A3: Kapsamlı belgeler bulunabilir[Burada](https://reference.aspose.com/page/net/).

### S4: Geçici lisansı nasıl edinebilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: .NET için Aspose.Page'i satın alabilir miyim?

 A5: Kesinlikle! Satın alma sayfasını ziyaret edin[Burada](https://purchase.aspose.com/buy) lisanslama seçenekleri için.
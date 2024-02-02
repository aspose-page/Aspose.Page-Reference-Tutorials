---
title: Aspose.Page for .NET ile Dizi Öğelerini Değiştirme
linktitle: Dizi Öğelerini Değiştir
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak EPS dosyalarındaki dizi öğelerini nasıl değiştireceğinizi öğrenin. Verimli meta veri manipülasyonu için adım adım kılavuzumuzu izleyin.
type: docs
weight: 15
url: /tr/net/eps-metadata-management/modify-eps-metadata-change-array-items/
---
## giriiş

Aspose.Page for .NET kullanarak dizi öğelerini değiştirmeye yönelik bu kapsamlı kılavuza hoş geldiniz! Aspose.Page, geliştiricilerin EPS dosyaları da dahil olmak üzere çeşitli belge formatlarıyla çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu eğitimde, özellikle dizi öğelerini değiştirerek, EPS dosyalarındaki XMP meta verilerini değiştirmeye odaklanacağız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Aspose.Page for .NET Library: Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

2. Geliştirme Ortamı: İster Visual Studio ister .NET geliştirmeyi destekleyen başka bir IDE olsun, tercih ettiğiniz geliştirme ortamını ayarlayın.

## Ad Alanlarını İçe Aktar

.NET uygulamanızda Aspose.Page işlevselliğine erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Sağlanan örneği birden çok adıma ayıralım:

## 1. Adım: EPS dosyası giriş akışını başlatın

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

 Bu adımda EPS dosyası giriş akışını başlatıyoruz ve bir`PsDocument` örnek ondan.

## 2. Adım: XMP meta verilerini alın

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

XMP meta verilerini EPS dosyasından alın. Dosya XMP meta verilerini içermiyorsa PS meta veri yorumlarından alınan değerlerle yeni bir dosya oluşturulur.

## 3. Adım: XMP meta veri değerlerini değiştirin

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

Burada, XMP meta verileri içindeki 0 dizinindeki başlığı ve yaratıcı öğelerini değiştiriyoruz.

## Adım 4: EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Bir çıktı akışı oluşturun ve EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak EPS dosyalarındaki dizi öğelerini nasıl değiştireceğinizi başarıyla öğrendiniz. Bu, belgelerinizdeki meta verileri özelleştirmek ve yönetmek için çok önemli bir adım olabilir.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?

Cevap1: Aspose.Page öncelikle EPS dosyalarıyla ilgilenir, ancak Aspose çeşitli belge formatlarıyla çalışmak için farklı kütüphaneler sağlar.

### S2: Ek belgeleri nerede bulabilirim?

 A2: adresindeki belgelere bakın.[.NET Belgeleri için Aspose.Page](https://reference.aspose.com/page/net/).

### S3: Ücretsiz deneme sürümü mevcut mu?

 C3: Evet, şu adresten ücretsiz deneme sürümünü edinebilirsiniz:[Burada](https://releases.aspose.com/).

### S4: Geçici lisansı nasıl alabilirim?

 Cevap4: Geçici bir lisans alın[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### S5: Nereden destek alabilirim veya toplulukla bağlantı kurabilirim?

 A5: ziyaret edin[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.
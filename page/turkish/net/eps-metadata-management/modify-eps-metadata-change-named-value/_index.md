---
title: Aspose.Page for .NET ile Adlandırılmış Değeri Değiştirme
linktitle: Adlandırılmış Değeri Değiştir
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak EPS dosyalarındaki adlandırılmış değerleri nasıl değiştireceğinizi öğrenin. Özel belge işleme için XMP meta verilerini zahmetsizce özelleştirin.
weight: 16
url: /tr/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile Adlandırılmış Değeri Değiştirme

## giriiş

Belge işleme dünyasında Aspose.Page for .NET, EPS dosyalarını işlemek için güçlü bir araç olarak öne çıkıyor. Sunduğu temel işlevlerden biri, XMP meta verileri içindeki adlandırılmış değerleri değiştirme yeteneğidir. Bu eğitim, Aspose.Page for .NET'i kullanarak adlandırılmış bir değeri değiştirme sürecinde size rehberlik edecek ve EPS dosyalarınızı özel ihtiyaçlarınıza göre özelleştirmenize olanak sağlayacaktır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET: Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

- Belge Dizini: EPS dosyalarınız için, adlandırılmış değer değişikliklerini gerçekleştirebileceğiniz belirlenmiş bir dizine sahip olun.

## Ad Alanlarını İçe Aktar

.NET projenizde Aspose.Page tarafından sağlanan işlevselliğe erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Aşağıdaki ad alanlarını kodunuza ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Şimdi, kapsamlı bir anlayış için kodu birden çok adıma ayıralım:

## 1. Adım: EPS Dosya Giriş Akışını Başlatın

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

Bu adımda değiştirmek istediğiniz EPS dosyası için giriş akışını ayarlıyoruz. "Belge Dizininiz"i, belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 2. Adım: XMP Meta Verilerini Alın

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Mevcut XMP meta verilerini EPS dosyasından alın. EPS dosyası XMP meta verilerini içermiyorsa PS meta veri yorumlarından alınan değerlerle yeni bir tane oluşturulacaktır.

## 3. Adım: XMP Meta Veri Değerlerini Değiştirin

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Burada "xmpTPg:MaxPageSize" yapısındaki iki adlandırılmış değerin değiştirildiğini gösteriyoruz. Bunu özel gereksinimlerinize göre özelleştirebilirsiniz.

## Adım 4: EPS Dosyasını Değiştirilmiş XMP Meta Verileriyle Kaydetme

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Değiştirilen EPS dosyasını çıkış akışına kaydedin. Dosya artık XMP meta verilerinde yapılan değişiklikleri yansıtacaktır.

## Çözüm

Bu eğitimde, EPS dosyalarındaki XMP meta verileri içindeki adlandırılmış değerleri değiştirmek için Aspose.Page for .NET'ten nasıl yararlanacağınızı öğrendiniz. Bu işlevsellik, belgelerinizi belirli gereksinimleri karşılayacak şekilde özelleştirmek ve uyarlamak için bir dünya olasılıklar dünyasının kapılarını açar.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?

Cevap1: Evet, Aspose.Page, EPS, XPS ve PDF dahil olmak üzere çeşitli belge formatlarını destekler.

### S2: Aspose.Page for .NET'in deneme sürümü mevcut mu?

 C2: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.Page for .NET hakkında daha fazla belgeyi nerede bulabilirim?

 A3: Belgelere bakın[Burada](https://reference.aspose.com/page/net/).

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Page for .NET kullanıcıları için hangi destek seçenekleri mevcut?

 A5: Topluluk forumunu ziyaret edin[Burada](https://forum.aspose.com/c/page/39) Destek ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

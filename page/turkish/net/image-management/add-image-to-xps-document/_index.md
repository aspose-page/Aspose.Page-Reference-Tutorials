---
title: Aspose.Page for .NET ile XPS Belgesine Görüntü Ekleme
linktitle: XPS Belgesine Resim Ekle
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile görüntülerin XPS belgelerine kusursuz entegrasyonunu keşfedin. Sorunsuz bir geliştirme deneyimi için adım adım kılavuzumuzu izleyin.
type: docs
weight: 11
url: /tr/net/image-management/add-image-to-xps-document/
---
## giriiş

.NET geliştirme dünyasında görüntülerin XPS belgelerine dahil edilmesi yaygın bir gerekliliktir. Aspose.Page for .NET, XPS belgelerini zahmetsizce işlemek ve geliştirmek için güçlü bir araç seti sunarak bu süreci basitleştirir. Bu eğitim, Aspose.Page for .NET kullanarak bir XPS belgesine görüntü ekleme adımlarında size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Page for .NET Library: Kütüphaneyi şu adresten indirip yükleyin:[Aspose.Page .NET Belgeleri](https://reference.aspose.com/page/net/).

2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.

3. Örnek Resim: XPS belgesine eklemek istediğiniz örnek bir resim dosyasına (örneğin, "QL_logo_color.tif") sahip olun.

## Ad Alanlarını İçe Aktar

Gerekli ad alanlarını .NET projenize aktararak başlayın. Bu ad alanları Aspose.Page for .NET tarafından sağlanan özelliklerin kullanılması açısından hayati öneme sahiptir.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. Adım: Belge Dizinini Ayarlayın

Belge dizininizin yolunu belirterek başlayın. Bu adım, projenizin dosyaları nerede bulacağını ve kaydedeceğini bilmesini sağlar.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

## Adım 2: XPS Belgesi Oluşturun

Aspose.Page for .NET'i kullanarak yeni bir XPS belgesi oluşturun.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

## 3. Adım: XPS Belgesine Görüntü Ekleme

Şimdi görüntüyü XPS belgesine ekleyelim. Bu örnekte "QL_logo_color.tif" adlı örnek bir görsel kullanacağız.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

## Adım 4: Sonuçtaki XPS Belgesini Kaydetme

XPS belgesini eklenen görüntüyle birlikte kaydedin.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Artık Aspose.Page for .NET'i kullanarak bir XPS belgesine başarıyla görüntü eklediniz!

## Çözüm

Bu eğitimde, görüntüleri XPS belgelerine sorunsuz bir şekilde dahil etmek için Aspose.Page for .NET'ten nasıl yararlanılacağını araştırdık. Bu adım adım kılavuz, .NET geliştirme yeteneklerinizi geliştirerek sorunsuz bir entegrasyon süreci sağlar.

## SSS'ler

### S1: Aspose.Page for .NET en son .NET framework sürümleriyle uyumlu mu?

 Cevap1: Aspose.Page for .NET, en son sürümler de dahil olmak üzere çok çeşitli .NET framework sürümleriyle uyumlu olacak şekilde tasarlanmıştır. Bakın[dokümantasyon](https://reference.aspose.com/page/net/) özel ayrıntılar için.

### S2: Aspose.Page for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?

C2: Evet, Aspose.Page for .NET platformdan bağımsız olduğundan hem Windows hem de Linux ortamlarında kullanıma uygundur.

### S3: Aspose.Page for .NET için herhangi bir lisanslama seçeneği var mı?

 C3: Evet, lisanslama seçeneklerini keşfedebilir ve satın alma işlemi gerçekleştirebilirsiniz[Burada](https://purchase.aspose.com/buy).

### S4: Aspose.Page for .NET'in ücretsiz deneme sürümü mevcut mu?

 Cevap4: Evet, Aspose.Page for .NET'i ücretsiz olarak deneyebilirsiniz.[ücretsiz deneme](https://releases.aspose.com/).

### S5: Aspose.Page for .NET için nereden yardım alabilirim veya toplulukla etkileşime geçebilirim?

 A5: ziyaret edin[.NET forumu için Aspose.Page](https://forum.aspose.com/c/page/39) toplulukla bağlantı kurmak ve destek almak için.
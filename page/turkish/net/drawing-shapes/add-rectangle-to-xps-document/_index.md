---
title: Aspose.Page for .NET ile XPS Belgesine Dikdörtgen Ekleme
linktitle: XPS Belgesine Dikdörtgen Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile belge oluşturmayı geliştirin. Bu adım adım eğitimde XPS belgelerine nasıl dikdörtgen ekleyeceğinizi öğrenin.
weight: 13
url: /tr/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesine Dikdörtgen Ekleme

## giriiş

Aspose.Page for .NET, .NET uygulamalarında XPS (XML Kağıt Belirtimi) belgeleriyle çalışmak için çeşitli özellikler sağlayan güçlü bir kitaplıktır. Bu eğitimde Aspose.Page for .NET kullanarak XPS belgesine dikdörtgen eklemeye odaklanacağız. Belge oluşturma sürecinizi geliştirmek için bu adım adım kılavuzu izleyin.

## Önkoşullar

Bu eğitime başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/page/net/).

2. Belge Dizini: XPS belgelerinizi depolamak istediğiniz bir dizin ayarlayın.

## Ad Alanlarını İçe Aktar

.NET uygulamanıza Aspose.Page işlevlerini kullanmak için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
// ExStart:3
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2. Adım: Yeni Bir XPS Belgesi Oluşturun

```csharp
// ExStart:4
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
// ExBitiş:4
```

## 3. Adım: Dikdörtgen Ekleme

```csharp
// ExStart:5
// Sol altta CMYK (mavi) düz renkli konturlu dikdörtgen
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExBitiş:5
```

## Adım 4: Belgeyi Kaydedin

```csharp
// ExStart:6
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExBitiş:6
```

Tebrikler! Aspose.Page for .NET'i kullanarak XPS belgesine başarıyla dikdörtgen eklediniz.

## Çözüm

Aspose.Page for .NET, belge düzenleme görevlerini basitleştirerek geliştiricilerin XPS belgelerini zahmetsizce oluşturmasına ve değiştirmesine olanak tanır. Bu adım adım kılavuz, XPS belgenize nasıl dikdörtgen ekleyeceğinizi göstererek daha fazla araştırma için sağlam bir temel sağlar.

## SSS'ler

### S1: Aspose.Page tüm .NET uygulamalarıyla uyumlu mudur?

C1: Evet, Aspose.Page tüm .NET uygulamalarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

### S2: Aspose.Page for .NET belgelerini nerede bulabilirim?

 A2: Belgeler mevcut[Burada](https://reference.aspose.com/page/net/).

### S3: Satın almadan önce Aspose.Page for .NET'i ücretsiz deneyebilir miyim?

 A3: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 A4: Ziyaret edin[bu bağlantı](https://purchase.aspose.com/temporary-license/) geçici lisans almak için.

### S5: Aspose.Page for .NET ile ilgili topluluk desteğini nereden alabilirim veya soru sorabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Aspose.Page for .NET ile XPS'ye Dikey Degrade ekleyin
linktitle: XPS'ye Dikey Degrade Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak XPS belgelerini dikey degradelerle nasıl geliştireceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 15
url: /tr/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS'ye Dikey Degrade ekleyin

## giriiş

Aspose.Page for .NET kullanarak bir XPS belgesine nasıl dikey degrade ekleyeceğinizi anlatan bu adım adım eğitime hoş geldiniz. Aspose.Page, .NET uygulamalarınızda XPS (XML Kağıt Belirtimi) dosyalarıyla çalışmanıza olanak tanıyan güçlü bir API'dir. Bu öğreticide, yeni bir XPS belgesi oluşturma, yola dikey degrade ekleme ve sonucu kaydetme sürecinde size rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/page/net/).

- Geliştirme Ortamı: Tercih ettiğiniz IDE ile Visual Studio gibi bir .NET geliştirme ortamı kurun.

Şimdi Aspose.Page for .NET'i kullanarak XPS belgesine dikey degrade eklemeye başlayalım.

## Ad Alanlarını İçe Aktar

.NET uygulamanıza Aspose.Page sınıflarına ve yöntemlerine erişmek için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 1. Adım: Belge Dizininizi Kurun

Başlamadan önce, elde edilen XPS belgesini kaydetmek istediğiniz belge dizininizin yolunu ayarlayın.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2. Adım: Yeni Bir XPS Belgesi Oluşturun

Aşağıdaki kodu kullanarak yeni bir XPS belgesi başlatın:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExBitiş:4
```

## Adım 3: Gradyan Duraklarını Tanımlayın

Her durağın rengini ve konumunu belirterek degrade duraklarının bir listesini oluşturun. Bu örnekte beş duraklı dikey bir degrade tanımlıyoruz.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExBitiş:5
```

## 4. Adım: Degradeli Bir Yol Oluşturun

Geometrisini belirterek bir yol tanımlayın ve ona doğrusal bir degrade fırçası uygulayın.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExBitiş:6
```

## Adım 5: Ortaya Çıkan XPS Belgesini Kaydedin

Değiştirilen XPS belgesini belirttiğiniz dizine kaydedin.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExBitiş:7
```

Tebrikler! Aspose.Page for .NET'i kullanarak bir XPS belgesine başarıyla dikey degrade eklediniz.

## Çözüm

Bu eğitimde, XPS belgelerini dikey degradelerle geliştirmek için Aspose.Page for .NET'ten nasıl yararlanılacağını araştırdık. Aspose.Page karmaşık görevleri basitleştirerek geliştiricilere .NET uygulamalarında XPS dosyalarını yönetmeleri için kusursuz bir yol sunar.

## SSS'ler

### S1: Aspose.Page Visual Studio 2019 ile uyumlu mu?

Cevap1: Evet, Aspose.Page, Visual Studio 2019 ile uyumludur. Kütüphanenin doğru sürümünün kurulu olduğundan emin olun.

### S2: Aspose.Page'i ticari projeler için kullanabilir miyim?

 C2: Evet, Aspose.Page ticari projeler için kullanılabilir. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) Lisanslama seçeneklerini keşfetmek için.

### S3: Ücretsiz deneme sürümü mevcut mu?

 Cevap3: Evet, Aspose.Page'in ücretsiz deneme sürümünü edinebilirsiniz[Burada](https://releases.aspose.com/).

### S4: Aspose.Page belgelerini nerede bulabilirim?

 A4: Belgeler mevcut[Burada](https://reference.aspose.com/page/net/).

### S5: Nasıl destek alabilirim veya soru sorabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

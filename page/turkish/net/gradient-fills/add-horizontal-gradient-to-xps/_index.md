---
title: Aspose.Page for .NET ile XPS'ye Yatay Degrade ekleyin
linktitle: XPS'ye Yatay Degrade Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak XPS belgelerinize nasıl çarpıcı yatay degradeler ekleyeceğinizi öğrenin. Görsel çekiciliği zahmetsizce artırın.
weight: 13
url: /tr/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS'ye Yatay Degrade ekleyin

## giriiş

Bu eğitimde, Aspose.Page for .NET'i kullanarak yatay degrade ekleyerek XPS belgelerini nasıl geliştirebileceğimizi keşfedeceğiz. Aspose.Page for .NET, .NET uygulamalarında XPS (XML Kağıt Belirtimi) belgelerinin kusursuz şekilde işlenmesini sağlayan güçlü bir kitaplıktır. Degradeler eklemek, belgelerinize görsel çekicilik katabilir ve bu kılavuz, süreç boyunca size adım adım yol gösterecektir.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[.NET Belgeleri için Aspose.Page](https://reference.aspose.com/page/net/).

2. Geliştirme Ortamı: Visual Studio gibi bir kod düzenleyici de dahil olmak üzere uygun bir geliştirme ortamı kurun.

## Ad Alanlarını İçe Aktar

Gerekli ad alanlarını projenize aktararak başlayın. Bu ad alanları Aspose.Page for .NET ile çalışmak için gereklidir:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Şimdi verilen örneği birden çok adıma ayıralım.

## 1. Adım: Belge Dizini Yolunu Ayarlayın

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

## 3. Adım: Gradyan Duraklarını Başlatın

```csharp
// ExStart:5
// XpsGradientStop Listesini Başlat
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExBitiş:5
```

## Adım 4: Yeni Bir Yol Oluşturun

```csharp
// ExStart:6
//Kısaltma formunda geometriyi tanımlayarak yeni yol oluşturun
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExBitiş:6
```

## Adım 5: Ortaya Çıkan XPS Belgesini Kaydedin

```csharp
// ExStart:7
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExBitiş:7
```

Artık Aspose.Page for .NET'i kullanarak XPS belgenize başarıyla yatay degrade eklediniz.

## Çözüm

XPS belgelerinizi degradelerle geliştirmek yalnızca görsel çekiciliğini artırmakla kalmaz, aynı zamanda daha ilgi çekici bir kullanıcı deneyimi de sağlar. Aspose.Page for .NET bu süreci basitleştirerek profesyonel sonuçlara zahmetsizce ulaşmanızı sağlar.

## SSS'ler

### S1: Aspose.Page for .NET belgelerini nerede bulabilirim?

 A1: Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/page/net/).

### S2: Aspose.Page for .NET'i nasıl indirebilirim?

 Cevap2: Kitaplığı şuradan indirebilirsiniz:[Aspose.Page for .NET indirme sayfası](https://releases.aspose.com/page/net/).

### S3: Aspose.Page for .NET'i nereden satın alabilirim?

 Cevap3: Aspose.Page for .NET'i şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).

### S4: Ücretsiz deneme sürümü mevcut mu?

 C4: Evet, şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.aspose.com/).

### S5: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap5: Geçici lisansı şu adresten alabilirsiniz:[bu bağlantı](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

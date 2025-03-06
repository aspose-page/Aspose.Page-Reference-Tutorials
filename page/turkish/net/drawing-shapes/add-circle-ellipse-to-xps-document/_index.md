---
title: Aspose.Page for .NET ile XPS Belgesine Circle Ellipse ekleme
linktitle: XPS Belgesine Daire Elipsi Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak XPS belgelerini canlı radyal degradelerle geliştirin. Çarpıcı görsel efektler için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesine Circle Ellipse ekleme

## giriiş

Görsel olarak çekici XPS belgeleri oluşturmak, çeşitli uygulamalarda ortak bir gereksinimdir. Aspose.Page for .NET, XPS belgelerini verimli bir şekilde yönetmek için güçlü bir dizi özellik sunar. Bu eğitimde Aspose.Page for .NET kullanarak bir XPS belgesine daire elipsi eklemeye odaklanacağız. XPS belgelerinizi canlı radyal degradelerle geliştirmek için aşağıdaki adımları izleyin.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).
- Bir geliştirme ortamı, tercihen Visual Studio veya başka herhangi bir .NET geliştirme aracı.
- Temel C# programlama bilgisi.

## Ad Alanlarını İçe Aktar

Başlamak için C# kodunuza gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Şimdi örneği birden çok adıma ayıralım:

## 1. Adım: Belgeyi Ayarlayın

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```

Burada Aspose.Page for .NET'i kullanarak yeni bir XPS belgesi başlatıyoruz.

## Adım 2: Radyal Degrade Elipsini Tanımlayın

```csharp
// Sol altta radyal degrade konturlu elips
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Bu adım, çeşitli renk duraklarına sahip bir radyal degrade elips tanımlamayı içerir.

## Adım 3: Radyal Degrade Fırçasını Ayarlayın

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Burada elipsin konturunu radyal degrade bir fırçaya ayarlayarak ona gerekli parametreleri sağlıyoruz.

## 4. Adım: Kontur Kalınlığını Ayarlayın

```csharp
path.StrokeThickness = 12f;
```

Bu adım, daha iyi görselleştirme için konturun kalınlığının ayarlanmasını içerir.

## Adım 5: Ortaya Çıkan XPS Belgesini Kaydedin

```csharp
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Son olarak değiştirilen XPS belgesini istediğiniz konuma kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak XPS belgenize radyal degradelere sahip bir daire elipsi başarıyla eklediniz. Belgelerinizde istediğiniz görsel efektleri elde etmek için farklı parametreler ve renklerle denemeler yapın.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?

Cevap1: Aspose.Page for .NET özellikle XPS belge manipülasyonuyla ilgilenir. Diğer formatlar için ilgili Aspose kütüphanelerini kullanmayı düşünün.

### S2: Test amaçlı olarak geçici bir lisans mevcut mu?

 C2: Evet, adresini ziyaret ederek test için geçici bir lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### S3: Ek yardım ve tartışmaları nerede bulabilirim?

 A3: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.

### S4: Referans için herhangi bir örnek belge var mı?

 A4: Keşfedin[dokümantasyon](https://reference.aspose.com/page/net/) Kapsamlı örnekler ve yönergeler için.

### S5: .NET için Aspose.Page'i satın alabilir miyim?

 Cevap5: Evet, kütüphaneyi satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

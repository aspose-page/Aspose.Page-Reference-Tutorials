---
title: Aspose.Page for .NET ile XPS Belgesine Döşenmiş Görüntü Ekleme
linktitle: XPS Belgesine Döşenmiş Görüntü Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile XPS belgelerine döşemeli görüntüleri zahmetsizce eklemeyi keşfedin. Görsel çekiciliği artırın ve çarpıcı belgeler oluşturun.
weight: 12
url: /tr/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesine Döşenmiş Görüntü Ekleme

## giriiş

Görsel olarak çekici döşemeli görüntüler ekleyerek XPS belgelerinizi geliştirmek mi istiyorsunuz? Aspose.Page for .NET, geliştiricilerin bunu sorunsuz bir şekilde başarmalarını sağlar. Bu adım adım kılavuzda, Aspose.Page for .NET kullanarak bir XPS belgesine döşenmiş bir görüntü ekleme sürecinde size yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. Ayrıntılı belgeleri bulabilir ve kütüphaneyi indirebilirsiniz.[Burada](https://reference.aspose.com/page/net/).
- Geliştirme Ortamı: Visual Studio gibi tercih ettiğiniz .NET geliştirme ortamını kurun.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını projenize aktarın. Bu, Aspose.Page ile çalışmak için gereken sınıflara ve yöntemlere erişiminizi sağlar. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi örneği birden çok adıma ayıralım.

## Adım 1: Belge Dizinini Tanımlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```

"Belge Dizininiz"i, XPS belgenizi kaydetmek istediğiniz asıl yolla değiştirdiğinizden emin olun.

## 2. Adım: Yeni Bir XPS Belgesi Oluşturun

```csharp
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```

 kullanarak yeni bir XPS belgesi oluşturun.`XpsDocument` sınıf.

## 3. Adım: Döşenmiş Görüntü Ekleme

```csharp
// Döşeme resmi
// ImageBrush dolgulu dikdörtgen aşağıda sağ üstte
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Bu adım, XPS belgesine döşenmiş bir görüntü ekler. Koordinatları ve görüntü dosyası yolunu gereksinimlerinize göre ayarlayın.

## 4. Adım: Ortaya Çıkan XPS Belgesini Kaydedin

```csharp
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Değiştirilen XPS belgesini belirtilen dizine kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak XPS belgesine döşemeli bir görüntünün nasıl ekleneceğini başarıyla öğrendiniz. Bu basit ama güçlü özellik, belgelerinizin görsel çekiciliğini zahmetsizce geliştirmenize olanak tanır.

## SSS'ler

### S1: Aspose.Page tüm .NET geliştirme ortamlarıyla uyumlu mudur?

C1: Evet, Aspose.Page, Visual Studio da dahil olmak üzere çeşitli .NET geliştirme ortamlarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

### S2: Döşenmiş görüntünün opaklığını ayarlayabilir miyim?

Cevap2: Elbette, örnekte gösterildiği gibi, doldurulmuş dikdörtgenin opaklığını aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`Opacity` mülk.

### S3: Aspose.Page for .NET'te başka döşeme modları mevcut mu?

 Cevap3: Evet, Aspose.Page farklı döşeme modları sağlar. Bu eğitimde şunları kullandık:`XpsTileMode.Tile`, ancak belgelerdeki diğer seçenekleri keşfedebilirsiniz.

### S4: Aspose.Page'in geçici lisanslarını nasıl halledebilirim?

 A4: Bkz.[geçici lisans](https://purchase.aspose.com/temporary-license/) Geçici lisansların alınması ve uygulanması konusunda rehberlik için Aspose web sitesindeki sayfa.

### S5: Nereden yardım alabilirim veya Aspose.Page topluluğuyla bağlantı kurabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla etkileşime geçmek, sorular sormak ve çözümler bulmak.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

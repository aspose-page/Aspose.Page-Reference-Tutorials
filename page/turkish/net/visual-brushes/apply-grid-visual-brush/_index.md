---
title: Aspose.Page for .NET ile Izgara Görsel Fırçasını Uygulayın
linktitle: Izgara Görsel Fırçasını Uygula
second_title: Aspose.Page .NET API'si
description: Aspose.Page ile .NET'te belge işlemenin dinamik dünyasını keşfedin. Görsel açıdan etkileyici belgeler için Izgara Görsel Fırçasını nasıl uygulayacağınızı öğrenin.
weight: 10
url: /tr/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile Izgara Görsel Fırçasını Uygulayın

## giriiş

.NET geliştirme dünyasında Aspose.Page, belge işleme görevlerini yerine getirmek için güçlü bir araç olarak öne çıkıyor. Sunduğu büyüleyici özelliklerden biri, belgelerinize yeni bir boyut kazandıran Izgara Görsel Fırçası uygulama yeteneğidir. Bu eğitim, Aspose.Page for .NET'i kullanarak Macenta Grid Visual Brush'ı adım adım uygulama sürecinde size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Page for .NET: Kitaplığın .NET ortamınıza yüklendiğinden ve kurulduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/page/net/).

- Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamına ve temel C# programlama anlayışına sahip olun.

- Belge Dizini: Belgeleriniz için işlenen dosyaların kaydedileceği bir dizin oluşturun.

## Ad Alanlarını İçe Aktar

Aspose.Page özelliklerini etkili bir şekilde kullanmak için C# kodunuzda gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi örneği birden çok adıma ayıralım.

## 1. Adım: XpsDocument'i başlatın

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

 Burada bir örneğini oluşturuyoruz`XpsDocument` XPS belgeleriyle çalışmak için.

## Adım 2: Macenta Izgara Geometrisi Oluşturun

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExBitiş:4
```

Bu adım, macenta ızgarası için bir yol geometrisi oluşturmayı içerir.

## Adım 3: Macenta Grid VisualBrush'ı Tasarlayın

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExBitiş:5
```

Burada vektör grafiklerini kullanarak macenta ızgaranın görsel yönünü tasarlıyoruz.

## Adım 4: VisualBrush'ı Izgaraya Uygulayın

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExBitiş:6
```

Görsel fırçayı ızgara yoluna uygulayarak uygun şekilde döşenmesini sağlayın.

## Adım 5: Izgarayı Tuvale Ekleme

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExBitiş:7
```

Gereken dönüşümleri belirterek ızgarayı tuvale ekleyin.

## Adım 6: Kırmızı Dikdörtgenle Geliştirin

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// ExBitiş:8
```

Kırmızı şeffaf bir dikdörtgen ekleyerek görsel çekiciliği artırın.

## Adım 7: Belgeyi Kaydedin

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExBitiş:9
```

Ortaya çıkan XPS belgesini belirttiğiniz dizine kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak belgenize Grid Görsel Fırçasını başarıyla uyguladınız. Bu teknik, belgelerinizin görsel öğelerini önemli ölçüde geliştirerek dinamik ve ilgi çekici bir kullanıcı deneyimi sağlayabilir.

## SSS'ler

### S1: Aspose.Page for .NET'i hem web hem de masaüstü uygulamalarında kullanabilir miyim?

Cevap1: Evet, Aspose.Page for .NET çok yönlüdür ve çeşitli uygulama türlerinde kullanılabilir.

### S2: Satın almadan önce deneme sürümü mevcut mu?

 Cevap2: Kesinlikle ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Ek desteği veya topluluk tartışmalarını nerede bulabilirim?

 A3: Ziyaret edin[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) Tartışma ve destek için.

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Page for .NET için başka hangi belgeler mevcut?

 Cevap5: Kapsamlı belgeleri inceleyin[Burada](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

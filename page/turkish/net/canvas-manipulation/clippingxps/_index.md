---
title: .NET için Aspose.Page ile XPS'yi kırpma
linktitle: XPS'yi kırpma
second_title: Aspose.Page .NET API'si
description: XPS belgelerini kırpmaya ilişkin bu adım adım kılavuzla Aspose.Page for .NET'in gücünü keşfedin. XPS dosyalarını zahmetsizce oluşturun, yönetin ve kaydedin.
weight: 11
url: /tr/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET için Aspose.Page ile XPS'yi kırpma

## giriiş

Aspose.Page for .NET kullanarak XPS'yi kırpma hakkındaki bu kapsamlı eğitime hoş geldiniz! Bu kılavuzda, Aspose.Page for .NET'i kullanarak XPS belgelerini oluşturma, değiştirme ve kaydetme sürecinde size yol göstereceğiz. XPS veya XML Kağıt Belirtimi, standartlaştırılmış ve açık bir belge formatıdır ve Aspose.Page for .NET, .NET uygulamalarınızda XPS belgeleriyle çalışmak için güçlü araçlar sağlar.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Makinenizde Visual Studio yüklü.
-  Aspose.Page for .NET kütüphanesi projenize eklendi. İndirebilirsin[Burada](https://releases.aspose.com/page/net/).
- Temel C# programlama dili bilgisi.

## Ad Alanlarını İçe Aktar

Aspose.Page for .NET işlevlerini kullanabilmek için gerekli ad alanlarını projenize aktarmanız gerekir. Bu adımları takip et:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi sağladığınız örnek kodu birden fazla adıma ayıralım.

## Adım 1: Belge dizini yolunu ayarlayın.

```csharp
string dataDir = "Your Document Directory";
```

"Belge Dizininiz"i belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 2: Yeni bir XPS Belgesi oluşturun.

```csharp
XpsDocument doc = new XpsDocument();
```

Bu, üzerinde çalışacağınız yeni bir XPS belgesi oluşturur.

## Adım 3: Ana tuvali oluşturun.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Bu adım, tüm sayfa öğeleri için ortak olan ana tuvali oluşturur.

## Adım 4: Ana tuvalde sol ve üst uzaklıkları ayarlayın.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Sol ve üst ofsetleri ihtiyaçlarınıza göre ayarlayın.

## Adım 5: Dikdörtgen bir yol geometrisi oluşturun.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Bu, bir dikdörtgen için bir yol geometrisi oluşturur.

## Adım 6: Dikdörtgenler için dolgu oluşturun.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Dikdörtgenlerin dolgu rengini tanımlayın.

## Adım 7: Ana tuvale klipli başka bir tuval ekleyin.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Bu adım, ana tuvale başka bir tuval ekler.

## Adım 8: Klip için bir daire geometrisi oluşturun.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Bu, dairesel bir klip geometrisi oluşturur ve bunu ikinci tuvale uygular.

## Adım 9: İkinci tuvalde bir dikdörtgen oluşturun ve içini doldurun.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Bu adım, ikinci tuvalde bir dikdörtgen oluşturur ve onu doldurur.

## Adım 10: Konturlu dikdörtgen içeren ikinci tuvali ana tuvale ekleyin.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Bu, ana tuvale başka bir tuval ekler.

## Adım 11: Üçüncü tuvalde bir dikdörtgen oluşturun ve onu konturlayın.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Bu, üçüncü tuvalde bir dikdörtgen oluşturur ve ona bir kontur uygular.

## Adım 12: Ortaya çıkan XPS belgesini kaydedin.

```csharp
doc.Save(dataDir + "output2.xps");
```

Bu, XPS belgesini belirtilen dizine kaydeder.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak XPS'yi nasıl kırpacağınızı başarıyla öğrendiniz. Bu kılavuz, süreçte yer alan adımların ayrıntılı bir açıklamasını sağlamıştır.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?

Cevap1: Aspose.Page for .NET öncelikle XPS belgelerine odaklanır, ancak Aspose çeşitli belge formatları için başka kütüphaneler de sağlar.

### S2: Aspose.Page for .NET yeni başlayanlar için uygun mudur?

C2: Evet, Aspose.Page for .NET kullanıcı dostu olacak şekilde tasarlanmıştır ve yeni başlayanlar, uygun belgelerle onun işlevlerini hızlı bir şekilde kavrayabilirler.

### S3: Daha fazla örneği ve kaynağı nerede bulabilirim?

 A3: Ziyaret edin[dokümantasyon](https://reference.aspose.com/page/net/) Ve[Aspose.Page forumu](https://forum.aspose.com/c/page/39) Kapsamlı kaynaklar ve örnekler için.

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Page for .NET'in ücretsiz deneme sürümü mevcut mu?

 A5: Evet, ücretsiz denemeyi keşfedebilirsiniz[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

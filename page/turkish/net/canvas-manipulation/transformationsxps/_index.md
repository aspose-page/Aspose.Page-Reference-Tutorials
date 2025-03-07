---
title: .NET için Aspose.Page ile XPS Dönüşümleri
linktitle: Dönüşümler XPS
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile XPS belgelerini zahmetsizce dönüştürün. Sorunsuz dönüşümler için adım adım kılavuzumuzu izleyin.
weight: 13
url: /tr/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET için Aspose.Page ile XPS Dönüşümleri

## giriiş

XPS belgelerinde çeşitli dönüşümleri zahmetsizce gerçekleştirmenizi sağlayan güçlü bir kütüphane olan Aspose.Page for .NET dünyasına hoş geldiniz. Bu eğitimde, Aspose.Page for .NET'i kullanarak XPS belgelerini dönüştürme sürecini ele alacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz her adımda size yol gösterecek ve kavramları kolayca kavramanızı sağlayacaktır.

## Önkoşullar

Başlamadan önce aşağıdakilerin yerinde olduğundan emin olun:

-  Aspose.Page for .NET Library: Kütüphaneyi şu adresten indirip yükleyin:[.NET Belgeleri için Aspose.Page](https://reference.aspose.com/page/net/).

- Geliştirme Ortamı: Visual Studio veya başka herhangi bir .NET geliştirme aracı gibi uyumlu bir geliştirme ortamı kurun.

- Belge Dizininiz: Koddaki yer tutucuyu, belge dizininizin gerçek yoluyla değiştirin.

Şimdi öğreticiye geçelim!

## Ad Alanlarını İçe Aktar

İlk olarak, Aspose.Page for .NET işlevlerini kodunuzda kullanılabilir hale getirmek için gerekli ad alanlarını içe aktardığınızdan emin olun. Komut dosyanızın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. Adım: Yeni Bir XPS Belgesi Oluşturun

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";

// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```

## Adım 2: Ana Kanvas Oluşturun

```csharp
// Tüm sayfa öğeleri için ortak olan ana tuvali oluşturun
XpsCanvas canvas1 = doc.AddCanvas();

// Ana tuvalde sol ve üst ofsetleri yapın
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Adım 3: Dikdörtgen Yol Geometrisi Oluşturun

```csharp
// Dikdörtgen yol geometrisi oluşturma
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Adım 4: Dikdörtgenler İçin Dolgu Ekleme

```csharp
// Dikdörtgenler için dolgu oluşturma
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Adım 5: Dönüşümler Olmadan Yeni Bir Kanvas Ekleme

```csharp
// Ana tuvale herhangi bir değişiklik yapmadan yeni tuval ekleyin
XpsCanvas canvas2 = canvas1.AddCanvas();

// Bu tuvalde dikdörtgen oluşturun ve içini doldurun
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 6. Adım: Çeviri Dönüşümüyle Yeni Bir Kanvas Ekleme

```csharp
// Ana tuvale çeviri dönüşümünü içeren yeni tuval ekleyin
XpsCanvas canvas3 = canvas1.AddCanvas();

// Önceki dikdörtgenin altına yeni bir dikdörtgen yerleştirmek için bu tuvali çevirin
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Bu tuvali sayfanın sağ tarafına çevirin
canvas3.RenderTransform.Translate(500, 0);

// Bu tuvalde dikdörtgen oluşturun ve içini doldurun
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Adım 7: Çift Ölçekli Dönüşümle Yeni Bir Kanvas Ekleme

```csharp
//Ana tuvale çift ölçekli dönüşümle yeni tuval ekleyin
XpsCanvas canvas4 = canvas1.AddCanvas();

// Önceki dikdörtgenin altına yeni bir dikdörtgen yerleştirmek için bu tuvali çevirin
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Bu tuvali ölçeklendir
canvas4.RenderTransform.Scale(2, 2);

// Bu tuvalde dikdörtgen oluşturun ve içini doldurun
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Adım 8: Bir Nokta Dönüşümü Etrafında Döndürmeyle Yeni Bir Kanvas Ekleme

```csharp
// Ana tuvale bir nokta dönüşümü etrafında rotasyonla yeni tuval ekleyin
XpsCanvas canvas5 = canvas1.AddCanvas();

// Önceki dikdörtgenin altına yeni bir dikdörtgen yerleştirmek için bu tuvali çevirin
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Bu tuvali 45 derecelik bir nokta etrafında döndürün
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Bu tuvalde dikdörtgen oluşturun ve içini doldurun
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Adım 9: Sonuçtaki XPS Belgesini Kaydedin

```csharp
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak bir XPS belgesini başarıyla dönüştürdünüz. Bu kılavuz, önkoşulların ayarlanmasından çeşitli dönüşümlerin gerçekleştirilmesine kadar temel adımları kapsıyordu. Bu teknikleri deneyin ve projelerinizde Aspose.Page for .NET'in tüm potansiyelini ortaya çıkarın.

## SSS'ler

### S1: Aspose.Page for .NET tüm .NET geliştirme ortamlarıyla uyumlu mudur?

C1: Evet, Aspose.Page for .NET, Visual Studio da dahil olmak üzere çeşitli .NET geliştirme ortamlarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

### S2: Aspose.Page for .NET için ek örnekleri ve belgeleri nerede bulabilirim?

 A2: Ziyaret edin[.NET Belgeleri için Aspose.Page](https://reference.aspose.com/page/net/) Kapsamlı belgeler ve örnekler için.

### S3: Satın almadan önce Aspose.Page for .NET'i deneyebilir miyim?

 C3: Evet, adresini ziyaret ederek ücretsiz deneme sürümünü keşfedebilirsiniz.[Aspose.Page Ücretsiz Deneme](https://releases.aspose.com/).

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap4: Ziyaret ederek geçici bir lisans alın[Geçici Lisans](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Page for .NET'i nereden satın alabilirim?

 Cevap5: .NET için Aspose.Page'i şu adresten satın alın:[Aspose.Page Satın Al](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-01-05
description: Aspose.Page for .NET kullanarak XPS belgelerini nasıl kırpacağınızı öğrenin.
  Bu adım adım kılavuz, XPS dosyalarını verimli bir şekilde oluşturmayı, düzenlemeyi
  ve kaydetmeyi gösterir.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Nasıl Kırpılır
url: /tr/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Nasıl Kesilir

## Giriş

Aspose.Page for .NET kullanarak **XPS nasıl kesilir** konusundaki bu kapsamlı öğreticiye hoş geldiniz! Bu rehberde, kütüphane ile XPS belgelerini oluşturma, manipüle etme ve kaydetme sürecini adım adım anlatacağız. XPS, yani XML Paper Specification, standartlaştırılmış ve açık bir belge formatıdır ve Aspose.Page for .NET, .NET uygulamalarınızda XPS belgeleriyle çalışmak için güçlü araçlar sunar.

## Hızlı Yanıtlar
- **XPS kesme nedir?** XPS kanvas öğelerinin görünür alanını sınırlamak için geometrik bir maske (clip) uygulamaktır.  
- **Bu iş için en iyi kütüphane hangisidir?** Aspose.Page for .NET, XPS oluşturma ve kesme için tam özellikli bir API sunar.  
- **Önkoşullar?** Visual Studio, .NET çalışma zamanı ve Aspose.Page for .NET kütüphanesi.  
- **Uygulama ne kadar sürer?** Temel bir kesme senaryosu için yaklaşık 10‑15 dakika.  
- **Bunu üretimde kullanabilir miyim?** Evet, geçerli bir Aspose lisansı (deneme sürümü mevcut) ile.

## “XPS nasıl kesilir” nedir?
XPS’te kesme, bir **clip geometrisi** (örneğin bir daire veya dikdörtgen) tanımlanıp kanvasa atanmasıyla çalışır. Bu geometrinin dışına çizilen her şey render edilmez; bu sayede maskelenmiş görseller, özel şekiller veya odaklanmış içerik alanları gibi gelişmiş sayfa düzenleri oluşturabilirsiniz.

## XPS kesmek için Aspose.Page for .NET neden kullanılmalı?
- **Kanvas dönüşümleri, yol geometrileri ve fırçalar üzerinde tam kontrol**.  
- **Harici bağımlılık yok** – her şey .NET uygulamanız içinde çalışır.  
- **Çapraz‑platform** desteği .NET Framework, .NET Core ve .NET 5/6+ için.  
- **Yüksek performans** – geçerli XPS dosyaları üreten hafif bir API.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde Visual Studio yüklü olmalıdır.  
- Projenize Aspose.Page for .NET kütüphanesini ekleyin. **[Buradan](https://releases.aspose.com/page/net/)** indirebilirsiniz.  
- C# programlama diline temel bilgi.

## Ad Alanlarını İçe Aktarma

Aspose.Page for .NET işlevlerini kullanabilmek için gerekli ad alanlarını projenize dahil etmeniz gerekir. Aşağıdaki adımları izleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi, sağladığınız örnek kodu birden fazla adıma ayıralım.

## Adım 1: Belge dizini yolunu ayarlayın.

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini, belge dizininizin gerçek yolu ile değiştirin.

## Adım 2: Yeni bir XPS Belgesi oluşturun.

```csharp
XpsDocument doc = new XpsDocument();
```

Bu, üzerinde çalışacağınız yeni XPS belgesini oluşturur.

## Adım 3: Ana kanvası oluşturun.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Bu adım, tüm sayfa öğeleri için ortak olan ana kanvası oluşturur.

## Adım 4: Ana kanvasta sol ve üst ofsetleri ayarlayın.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Sol ve üst ofsetleri gereksinimlerinize göre ayarlayın.

## Adım 5: Dikdörtgen yol geometrisi oluşturun.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Bu, bir dikdörtgen için yol geometrisi oluşturur.

## Adım 6: Dikdörtgenler için dolgu oluşturun.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Dikdörtgenlerin dolgu rengini tanımlayın.

## Adım 7: Ana kanvasa clip ile başka bir kanvas ekleyin.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Bu adım, ana kanvasa başka bir kanvas ekler.

## Adım 8: Clip için dairesel bir geometri oluşturun.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Bu, ikinci kanvasa uygulanacak dairesel bir clip geometrisi oluşturur.

## Adım 9: İkinci kanvasta bir dikdörtgen oluşturun ve doldurun.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Bu adım, ikinci kanvasta bir dikdörtgen oluşturur ve doldurur.

## Adım 10: Ana kanvasa strokeli bir dikdörtgenle ikinci kanvası ekleyin.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Bu, ana kanvasa başka bir kanvas ekler.

## Adım 11: Üçüncü kanvasta bir dikdörtgen oluşturun ve strokleyin.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Bu, üçüncü kanvasta bir dikdörtgen oluşturur ve ona bir çizgi (stroke) uygular.

## Adım 12: Sonuç XPS belgesini kaydedin.

```csharp
doc.Save(dataDir + "output2.xps");
```

Bu, XPS belgesini belirtilen dizine kaydeder.

## Yaygın Sorunlar ve Çözümler
- **Geçersiz yol** – `dataDir` değişkeninin sonunda ters eğik çizgi (`\\`) olduğundan emin olun veya `Path.Combine` kullanın.  
- **Clip uygulanmadı** – Clip geometri dizesinin doğru biçimlendirildiğini kontrol edin; eksik bir boşluk clip’in göz ardı edilmesine neden olabilir.  
- **Lisans istisnası** – Değerlendirme dışı bir derlemede, belgeyi oluşturmadan önce geçerli bir Aspose lisansı ekleyerek çalışma zamanı istisnalarını önleyin.

## Sıkça Sorulan Sorular

### S1: Aspose.Page for .NET başka belge formatlarıyla da kullanılabilir mi?

C1: Aspose.Page for .NET öncelikle XPS belgelerine odaklanır, ancak Aspose farklı belge formatları için başka kütüphaneler sunar.

### S2: Aspose.Page for .NET yeni başlayanlar için uygun mu?

C2: Evet, Aspose.Page for .NET kullanıcı dostu olacak şekilde tasarlanmıştır ve yeni başlayanlar doğru dokümantasyonla işlevlerini hızlıca kavrayabilir.

### S3: Daha fazla örnek ve kaynak nereden bulunur?

C3: Geniş kaynak ve örnekler için [dokümantasyonu](https://reference.aspose.com/page/net/) ve [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### S4: Aspose.Page for .NET için geçici bir lisans nasıl alınır?

C4: Geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** alabilirsiniz.

### S5: Aspose.Page for .NET için ücretsiz deneme sürümü var mı?

C5: Evet, ücretsiz deneme sürümünü **[buradan](https://releases.aspose.com/)** keşfedebilirsiniz.

## Ek Sıkça Sorulan Sorular

**S: Tek bir kanvasa birden fazla clip geometrisi ekleyebilir miyim?**  
C: Evet, `Clip` özelliğine birden fazla alt‑yolu içeren karmaşık bir `PathGeometry` atayarak katmanlı maskeler oluşturabilirsiniz.

**S: Kesme, PDF dönüşümünü etkiler mi?**  
C: XPS’i Aspose.PDF ile PDF’ye dönüştürdüğünüzde clip geometrisi korunur; görsel sonuç aynı kalır.

**S: XPS’te clipping animasyonu mümkün mü?**  
C: XPS kendisi animasyonu desteklemez; ancak farklı clip şekilleriyle bir dizi XPS sayfası üreterek hareketi taklit edebilirsiniz.

**Son Güncelleme:** 2026-01-05  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
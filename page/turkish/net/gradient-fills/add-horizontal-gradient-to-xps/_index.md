---
date: 2026-02-25
description: Aspose.Page for .NET kullanarak yatay dolgu ile XPS degrade oluşturmayı
  öğrenin. Belgelerinizde görsel çekiciliği zahmetsizce artırın.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS Gradyanı Oluştur: Aspose.Page for .NET ile Yatay Doldurma'
url: /tr/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

Issue | Reason | Fix" translate to "Sorun | Sebep | Çözüm". Ensure markdown table alignment.

Also ensure we keep code placeholders unchanged.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Gradient Oluşturma – Aspose.Page for .NET ile XPS'e Yatay Gradient Ekleme

## Giriş

Bu öğreticide, sayfalarınız boyunca yatay olarak akan **XPS gradient** doldurmaları oluşturacaksınız. Yatay bir gradient eklemek, özellikle raporlar, broşürler veya görsel‑ağırlıklı çıktılar için bir XPS belgesini anında daha cilalı ve çekici hale getirebilir. Ortamı kurmaktan son XPS dosyasını kaydetmeye kadar Aspose.Page for .NET kullanarak tam süreci adım adım göstereceğiz.

## Hızlı Yanıtlar
- **Bu öğreticide ne ele alınıyor?** Aspose.Page for .NET ile bir XPS belgesine yatay gradient ekleme.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET (herhangi bir son sürüm).  
- **Lisans gerekiyor mu?** Geliştirme için deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel bir gradient için yaklaşık 5–10 dakika.  
- **Gradient yönünü değiştirebilir miyim?** Evet – `LinearGradientBrush`'ın başlangıç/bitiş noktalarını değiştirin.

## Aspose.Page for .NET ile XPS gradient nasıl oluşturulur

Aşağıda, kodun her satırının **neden** var olduğunu, sadece **ne** yaptığını açıklayan adım adım bir rehber bulacaksınız. Visual Studio’da ya da tercih ettiğiniz .NET editöründe rahatlıkla takip edebilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınıza Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) adresinden indirebilirsiniz.
2. Geliştirme Ortamı: Visual Studio gibi bir kod editörü dahil olmak üzere uygun bir geliştirme ortamı kurun.

## Ad Alanlarını İçe Aktarın

Projenize gerekli ad alanlarını içe aktararak başlayın. Bu ad alanları, Aspose.Page for .NET ile çalışmak için gereklidir:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Şimdi, verilen örneği birden fazla adıma ayıralım.

## Adım 1: Belge Dizini Yolunu Ayarlama

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Adım 2: Yeni Bir XPS Belgesi Oluşturma

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Adım 3: Gradient Durdurucuları Başlatma

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Adım 4: Yeni Bir Yol Oluşturma

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Adım 5: Oluşan XPS Belgesini Kaydetme

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Artık Aspose.Page for .NET kullanarak XPS belgenize yatay bir gradient başarıyla eklediniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Gradient tek renk gibi görünüyor | Gradient durdurucuları doğru eklenmemiş | Fırça ayarlandıktan sonra `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` kodunun çalıştığından emin olun. |
| Kaydedilen dosya boş | `dataDir` mevcut olmayan bir klasöre işaret ediyor | Klasörün varlığını doğrulayın veya mutlak bir yol kullanın. |
| `PointF` üzerinde derleme hatası | `System.Drawing` referansı eksik | `System.Drawing.Common` referansını ekleyin ( .NET Core/5+ için). |

## SSS'ler

### Q1: Aspose.Page for .NET dokümantasyonunu nerede bulabilirim?

A1: Dokümantasyonu [burada](https://reference.aspose.com/page/net/) bulabilirsiniz.

### Q2: Aspose.Page for .NET'i nasıl indirebilirim?

A2: Kütüphaneyi [Aspose.Page for .NET indirme sayfasından](https://releases.aspose.com/page/net/) indirebilirsiniz.

### Q3: Aspose.Page for .NET'i nereden satın alabilirim?

A3: Aspose.Page for .NET'i [satın alma sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Q4: Ücretsiz deneme mevcut mu?

A4: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/) alabilirsiniz.

### Q5: Aspose.Page for .NET için geçici lisans nasıl alınır?

A5: Geçici bir lisansı [bu bağlantıdan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sıkça Sorulan Sorular

**S: Bu gradient tekniğini zaten resim içeren XPS belgelerinde kullanabilir miyim?**  
C: Kesinlikle. Gradient bir yol katmanına uygulanır, bu yüzden mevcut resimler dokunulmaz kalır.

**S: Bunun yerine dikey bir gradient oluşturmak mümkün mü?**  
C: Evet. `LinearGradientBrush`'ın başlangıç ve bitiş noktalarını X sabit kalırken farklı Y koordinatları olacak şekilde değiştirin.

**S: Aspose.Page .NET Core'u destekliyor mu?**  
C: Kütüphane .NET Core, .NET 5 ve sonraki sürümlerle tam uyumludur.

**S: Aynı gradient'i birden fazla sayfada nasıl tekrar kullanabilirim?**  
C: `XpsLinearGradientBrush`'ı bir kez oluşturun, bir değişkende saklayın ve her sayfadaki yollara atayın.

## Sonuç

XPS belgelerinizi gradientlerle geliştirmek yalnızca görsel çekiciliği artırmakla kalmaz, aynı zamanda daha etkileyici bir kullanıcı deneyimi sunar. Aspose.Page for .NET ile **XPS gradient** doldurmalarını hızlı ve güvenilir bir şekilde oluşturabilir, raporlarınıza, broşürlerinize veya e‑kitaplarınıza profesyonel bir parlaklık kazandırabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-02-25  
**Test Edilen:** Aspose.Page for .NET 24.11  
**Yazar:** Aspose
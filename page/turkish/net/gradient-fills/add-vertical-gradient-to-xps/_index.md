---
date: 2026-02-25
description: Aspose.Page for .NET ile XPS belgesi oluşturmayı ve lineer degrade uygulamayı
  öğrenin. XPS dosyasını kaydetmek için adım adım rehberimizi izleyin.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page kullanarak Dikey Gradyanlı XPS Belgesi Oluşturun
url: /tr/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 placeholders: they are not fenced code blocks, but just placeholders. Keep them as is.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS'e Dikey Degrade Ekleyin Aspose.Page for .NET ile

## Giriş

Bu öğreticide **XPS belgesi** oluşturacaksınız ve bu belgeye düzgün bir dikey degrade ekleyeceksiniz. Degradeler, XPS dosyalarını daha profesyonel göstermek için yaygın bir yoldur—raporlar, broşürler veya herhangi bir yazdırılabilir grafik için mükemmeldir. Projeyi kurmaktan son XPS dosyasını kaydetmeye kadar her adımı adım adım göstereceğiz, böylece herhangi bir yola lineer bir degrade kolayca uygulayabilirsiniz.

## Hızlı Yanıtlar
- **Bu öğreticide ne anlatılıyor?** XPS belgesindeki bir yola dikey lineer degrade eklemek.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.  
- **Sonucu XPS dosyası olarak kaydedebilir miyim?** Evet, `Save` metodu dosyayı diske yazar.

## XPS'te dikey degrade nedir?

Dikey degrade, bir şeklin üstünden altına doğru renk geçişi yapan bir renk değişimidir. XPS'te bu, **lineer degrade fırçası** (linear gradient brush) ile sağlanır; başlangıç ve bitiş noktaları ile belirli konumlardaki renkleri tanımlayan degrade durakları (gradient stops) koleksiyonu içerir.

## Neden Aspose.Page ile degrade içeren XPS belgesi oluşturmalıyım?

- **Tam .NET entegrasyonu** – .NET Framework, .NET Core ve .NET 5/6+ ile çalışır.  
- **Harici bağımlılık yok** – tüm render işlemleri kütüphane tarafından yapılır.  
- **Yüksek doğruluk** – degradeler, XPS spesifikasyonuna tam uyumlu olarak render edilir.  
- **Kolay bakım** – yollar, fırçalar ve renkler için net bir nesne modeli sunar.

## Önkoşullar

- Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. İndirmek için [buraya](https://releases.aspose.com/page/net/) tıklayın.  
- Geliştirme Ortamı: Visual Studio gibi tercih ettiğiniz IDE ile bir .NET geliştirme ortamı kurun.

Her şey hazır olduğuna göre, koda geçelim.

## Ad Alanlarını İçe Aktarın

.NET uygulamanızda Aspose.Page sınıflarına ve metodlarına erişmek için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Adım 1: Belge Dizininizi Ayarlayın

Oluşturulacak XPS dosyasının kaydedileceği klasörü tanımlayın.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Adım 2: Yeni Bir XPS Belgesi Oluşturun

Daha sonra degrade‑dolgu bir yol ekleyeceğimiz yeni bir XPS belgesi örneği oluşturun.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Adım 3: Degrade Duraklarını Tanımlayın

Degrade durakları, renkleri ve bu renklerin degrade çizgisi üzerindeki konumlarını belirler. Burada, yumuşak bir dikey geçiş elde etmek için beş durak oluşturuyoruz.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Adım 4: Degrade ile Bir Yol Oluşturun

Bir dikdörtgen şekli çizer ve **lineer degrade fırçası**nı (linear gradient brush) (10, 110) noktasından (10, 200) noktasına dikey olarak çalışacak şekilde uygularız. Fırça, önceki adımda tanımlanan degrade duraklarını alır.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Adım 5: Sonuç XPS Belgesini Kaydedin

Son olarak XPS belgesini diske yazın. Bu **XPS dosyasını kaydet** adımı, belirttiğiniz klasörde `AddVerticalGradient_outXPS.xps` dosyasını oluşturur.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**İpucu:** Çıktıyı Windows XPS Viewer veya herhangi bir üçüncü‑taraf görüntüleyicide açarak degrade’nin beklendiği gibi göründüğünden emin olun.

## Yaygın Sorunlar ve Çözüm Önerileri

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| Degrade tek renk olarak görünüyor | Degrade durakları fırçaya eklenmemiş | `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` satırının çalıştığından emin olun. |
| Kaydetme sırasında dosya bulunamadı | `dataDir` mevcut olmayan bir klasöre işaret ediyor | Önce klasörü oluşturun veya mutlak bir yol kullanın. |
| Renkler farklı görünüyor | Renk değerleri ARGB sırasına göre; kanal sırasını kontrol edin | `CreateColor(alpha, red, green, blue)` metodunu doğru şekilde kullanın. |

## Sık Sorulan Sorular

**S: Aspose.Page Visual Studio 2019 ile uyumlu mu?**  
C: Evet, Aspose.Page Visual Studio 2019 ile uyumludur. Doğru kütüphane sürümünün kurulu olduğundan emin olun.

**S: Aspose.Page'i ticari projelerde kullanabilir miyim?**  
C: Evet, Aspose.Page ticari projelerde kullanılabilir. Lisans seçeneklerini incelemek için [buraya](https://purchase.aspose.com/buy) bakın.

**S: Ücretsiz deneme mevcut mu?**  
C: Evet, Aspose.Page'in ücretsiz denemesini [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Page dokümantasyonunu nereden bulabilirim?**  
C: Dokümantasyon [burada](https://reference.aspose.com/page/net/) mevcuttur.

**S: Destek alabilir ya da soru sorabilir miyim?**  
C: Topluluk desteği için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Sonuç

Artık **XPS belgesi oluşturma**, **lineer degrade uygulama** ve **XPS dosyasını kaydetme** işlemlerini Aspose.Page for .NET ile nasıl yapacağınızı biliyorsunuz. Bu yöntem, XPS çıktılarınızda görsel stil üzerinde tam kontrol sağlar ve yazdırılabilir belgelerinizin öne çıkmasını sağlar.

---  

**Son Güncelleme:** 2026-02-25  
**Test Edilen Sürüm:** Aspose.Page for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
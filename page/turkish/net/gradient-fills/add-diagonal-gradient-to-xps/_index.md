---
date: 2026-02-23
description: Aspose.Page for .NET'i kullanarak diyagonal degrade XPS belgeleri oluşturmayı
  öğrenin ve görsel sunumlarınızı zahmetsizce yükseltin.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile Diyagonal Gradyan XPS Oluşturma
url: /tr/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

Probably translate "Last Updated:" => "Son Güncelleme:" etc.

But they are plain text lines; we can translate.

Now produce final output.

Check for any stray spaces.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile Diyagonal Gradyan XPS Oluşturma

## Giriş

Eğer **diyagonal gradyan XPS** dosyaları oluşturmak istiyorsanız, Aspose.Page for .NET bu süreci oldukça basitleştirir. Bu öğreticide, Aspose.Page API'sini kullanarak bir XPS belgesine adım adım diyagonal gradyan eklemeyi öğreneceksiniz. Sonunda, herhangi bir şekil veya renk şemasına uyarlayabileceğiniz yeniden kullanılabilir bir desen elde edeceksiniz.

## Hızlı Yanıtlar
- **API yöntemi ne yapar?** Bir yolu boyunca diyagonal olarak uzanan lineer gradyan fırçası oluşturur.  
- **XPS belgesini temsil eden sınıf hangisidir?** `XpsDocument`.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için lisans gereklidir.  
- **Gradyan yönünü değiştirebilir miyim?** Evet—başlangıç ve bitiş `PointF` değerlerini ayarlayın.  
- **.NET sürümleri hangileri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## **create diagonal gradient xps** nedir?
Diyagonal gradyan, bir şeklin bir köşesinden karşı köşesine doğru yumuşak bir renk geçişidir. XPS'de bu etki, bir yolun doldurma özelliğine `LinearGradientBrush` uygulanarak elde edilir. Aspose.Page kütüphanesi düşük seviyeli XPS işaretlemesini soyutlayarak, renkler ve geometri üzerine odaklanmanızı sağlar.

## Neden Aspose.Page'i diyagonal gradyanlar için kullanmalısınız?
- **Yüksek doğrulukta render** – çıktı XPS spesifikasyonuna tam olarak uyar.  
- **Tam .NET entegrasyonu** – C#, VB.NET ve herhangi bir .NET diliyle çalışır.  
- **Harici bağımlılık yok** – her şey aynı süreç içinde yönetilir, COM veya Office gerekmez.  
- **Karmaşık belgelere ölçeklenebilir** – aynı sayfada birden fazla gradyan, resim ve metni birleştirebilirsiniz.

## Önkoşullar

1. **Aspose.Page for .NET Kütüphanesi** – [buradan](https://releases.aspose.com/page/net/) indirin.  
2. **Geliştirme Ortamı** – Visual Studio, Rider veya .NET projelerini destekleyen herhangi bir editör.  

Şimdi koda dalalım.

## Ad Alanlarını İçe Aktarın

.NET projenizde, gerekli sınıflara ve yöntemlere erişmek için Aspose.Page kütüphanesinden ilgili ad alanlarını ekleyin. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Adım 1: Belge Dizinini Ayarlayın

Diyagonal gradyanlı XPS belgesinin kaydedileceği dizini belirleyerek başlayın.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Adım 2: Yeni Bir XPS Belgesi Oluşturun

Aspose.Page kütüphanesini kullanarak yeni bir `XpsDocument` başlatın.

```csharp
XpsDocument doc = new XpsDocument();
```

## Adım 3: Gradyan Renklerini Tanımlayın

Diyagonal gradyanda yer alacak renkleri temsil eden `XpsGradientStop` nesnelerinin bir listesini oluşturun.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Adım 4: Bir Yola Diyagonal Gradyan Ekleyin

Tanımlı bir geometriye sahip yeni bir yol oluşturun ve ona diyagonal gradyanı uygulayın. Gerekirse render dönüşümünü ve doldurma özelliklerini ayarlayın.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Adım 5: Oluşturulan XPS Belgesini Kaydedin

Son olarak, değiştirilmiş XPS belgesini belirttiğiniz dizine kaydedin.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Artık başarılı bir şekilde **diyagonal gradyan XPS** dosyası oluşturdunuz. Farklı renk durakları, geometri dizgileri veya dönüşüm matrisleriyle deneyler yaparak çeşitli görsel efektler elde edebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Gradyan görünmüyor** – Yol geometrisinin kapalı olduğundan ve fırçanın başlangıç/bitiş noktalarının yol sınırları içinde olduğundan emin olun.  
- **Yanlış renkler** – `CreateColor` metodunu doğru ARGB değerleriyle kullandığınızdan; metodun 0‑255 aralığında değerler beklediğinden emin olun.  
- **Dosya kaydedilmiyor** – `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanın yazma iznine sahip olduğunu kontrol edin.

## Sık Sorulan Sorular

**S: Belgenin farklı bölümlerine birden fazla gradyan uygulayabilir miyim?**  
C: Evet, birden fazla yol oluşturup her birine ayrı gradyanlar atayabilirsiniz.

**S: Önceden tanımlı gradyan stilleri mevcut mu?**  
C: Aspose.Page özelleştirilebilir gradyanlar sunar; renk geçişleri üzerinde tam kontrol sağlar.

**S: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?**  
C: Aspose.Page öncelikli olarak XPS belge manipülasyonuna odaklanır.

**S: Belge işleme ile ilgili hataları nasıl yönetebilirim?**  
C: Hata yönetimi en iyi uygulamaları için [belgelere](https://reference.aspose.com/page/net/) bakın.

**S: Satın almadan önce deneme sürümü var mı?**  
C: Evet, Aspose.Page for .NET'i deneyimlemek için [ücretsiz deneme](https://releases.aspose.com/) sürümünü keşfedebilirsiniz.

**S: Gradyan yönünü dikey veya yatay olarak nasıl değiştiririm?**  
C: `CreateLinearGradientBrush` içindeki `PointF` argümanlarını yeni başlangıç ve bitiş noktalarına göre değiştirin.

**S: Kütüphane gradyanlarda şeffaflığı destekliyor mu?**  
C: Evet—`CreateColor` ile renk oluştururken alfa değerini dahil edin.

## Sonuç

Aspose.Page for .NET, XPS belgelerine diyagonal gradyan ekleme sürecini basitleştirir. Bu kılavuz, önkoşulları kurmaktan son dosyayı kaydetmeye kadar her adımı size gösterdi. XPS raporlarınızı, broşürlerinizi veya faturalarınızı gerçekten öne çıkarmak için farklı şekiller ve renk paletleriyle denemeler yapmaya devam edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

---
---
date: 2026-02-25
description: C# lineer gradient fırçasını kullanarak PS dosyalarına degrade eklemeyi
  ve Aspose.Page for .NET ile bir dikdörtgeni degrade ile doldurmayı öğrenin.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Lineer Gradyan Fırçası – Aspose.Page ile PostScript (PS)'e Dikey Gradyan
  Ekle
url: /tr/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 keep code block placeholders unchanged.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Aspose.Page ile PostScript (PS) Dosyasına Dikey Degrade Ekle

## Giriş

Belge manipülasyonu ve oluşturma alanında, **Aspose.Page for .NET** geliştiriciler için güçlü bir araç olarak öne çıkıyor. Bu rehberde **PS** dosyalarına **gradient eklemeyi** **C# linear gradient brush** kullanarak **dikdörtgeni gradient ile doldurmayı** keşfedeceksiniz. Bu öğreticinin sonunda, gerekli kodu ve bu tekniğin PostScript çıktınızda sorunsuz bir dikey degrade üretmesinin nedenlerini adım adım anlayacaksınız.

## Hızlı Yanıtlar
- **C# linear gradient brush ne yapar?** Bir şekil üzerinde birden fazla renk arasında yumuşak bir geçiş oluşturur.
- **Herhangi bir .NET sürümüyle kullanabilir miyim?** Evet, Aspose.Page .NET Framework 4.5+ ve .NET Core/5+ sürümlerini destekler.
- **Üretim için lisansa ihtiyacım var mı?** Değerlendirme dışı sürümler için ticari bir lisans gereklidir.
- **Degrade gerçekten dikey mi?** Fırça 90° döndürülür, bu da dikey bir akış sağlar.
- **Çıktı nerede kaydedilir?** `dataDir` içinde belirttiğiniz yola (ör. `VerticalGradient_outPS.ps`) kaydedilir.

## C# Linear Gradient Brush Nedir?
**C# linear gradient brush**, tanımlı noktalar arasında doğrusal bir renk geçişi çizen bir GDI+ nesnesidir (`LinearGradientBrush`). Aspose.Page’in çizim API’siyle birleştirildiğinde, doğrudan bir PostScript (PS) belgesine karmaşık degradeler render etmenizi sağlar.

## PostScript İçin Neden Linear Gradient Brush Kullanmalı?
- **Yüksek kalite çıktı:** Degradeler yazıcı seviyesinde render edilir, doğruluk korunur.
- **Tam kontrol:** Özel renk durakları, dönüş ve ölçekleme ayarlayabilirsiniz.
- **Yeniden kullanılabilir kod:** Aynı fırça mantığı PDF, SVG ve Aspose.Page tarafından desteklenen diğer formatlarda da çalışır.

## Önkoşullar

Öğreticiye başlamadan önce aşağıdakilerin hazır olduğundan emin olun:

- Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. Gerekli kaynakları ve belgeleri [burada](https://reference.aspose.com/page/net/) bulabilirsiniz.
- Geliştirme Ortamı: .NET geliştirme için bir Entegre Geliştirme Ortamı (IDE) dahil uygun bir geliştirme ortamı kurun.
- Temel Anlayış: Akışlar, grafik yolları ve renk manipülasyonu gibi .NET geliştirme temellerine aşina olun.

## Ad Alanlarını İçe Aktarın

C# projenizde, kod dosyanızın başında gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: Belge Dizinini Ayarlayın

İlk olarak belge dizininizin yolunu belirtin. Bu, PS belgenizin kaydedileceği konumdur.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: PostScript Belgesi İçin Çıktı Akışı Oluşturun

`FileStream` sınıfını kullanarak PostScript belgesi için bir çıktı akışı oluşturun.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Adım 3: Kaydetme Seçeneklerini ve PS Belgesini Oluşturun

A4 boyutunda kaydetme seçenekleri oluşturun ve yeni bir sayfalı PS belgesi başlatın.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 4: Dikdörtgen Boyutlarını Tanımlayın

Dikey degrade uygulanacak dikdörtgenin boyutlarını ve konumunu belirtin.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Adım 5: Grafik Yolu Oluşturun

Tanımlanan dikdörtgenden bir grafik yolu oluşturun.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Adım 6: İnterpolasyon Renklerini Tanımlayın

Degrade için bir interpolasyon renkleri ve konumları dizisi oluşturun.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Adım 7: Linear Gradient Brush Oluşturun

Dikdörtgeni sınır olarak, başlangıç ve bitiş renkleriyle bir linear gradient brush oluşturun.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Adım 8: Fırça Dönüşümünü Ayarlayın

Fırça için bir dönüşüm belirleyin, X ve Y ölçek bileşenlerinin dikdörtgenin genişliği ve yüksekliğiyle eşleştiğinden emin olun.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Adım 9: Boyamayı Ayarlayın ve Dikdörtgeni Doldurun

Belge için boyamayı ayarlayın ve önceden tanımlanan yolu kullanarak **fill rectangle with gradient** işlemini gerçekleştirin.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Adım 10: Mevcut Sayfayı Kapatın ve Belgeyi Kaydedin

Mevcut sayfayı kapatın ve PostScript belgesini kaydedin.

```csharp
document.ClosePage();
document.Save();
```

Tebrikler! Aspose.Page for .NET ile **C# linear gradient brush** kullanarak bir **PostScript belgesine dikey degrade eklediniz**. Belgelerinizde çeşitli görsel etkiler elde etmek için farklı parametreler ve renklerle deney yapın.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Nasıl Düzeltilir |
|-------|----------------|------------|
| Degrade yatay görünüyor | Fırça dönüşü uygulanmadı | `brushTransform.Rotate(90);` ifadesinin `brush.Transform`'a atanmasından önce çağrıldığından emin olun. |
| Renkler soluk görünüyor | Düşük çözünürlüklü çıktı akışı | Daha yüksek çözünürlüklü bir `PsSaveOptions` kullanın veya belge boyutunu artırın. |
| Çıktı dosyası boş | Akış temizlenmedi | `document.Save();` ifadesinin `using` bloğunun dışında çağrıldığını doğrulayın. |

## Sıkça Sorulan Sorular

**S1: Aynı belgenin farklı bölgelerine birden fazla degrade uygulayabilir miyim?**  
C: Evet, uygulayabilirsiniz. Her bölge için belirli boyut ve renk şemasıyla adımları tekrarlamanız yeterlidir.

**S2: Bu kodu mevcut .NET projemle nasıl entegre edebilirim?**  
C: Kodu proje dosyanıza kopyalayıp yapıştırın ve Aspose.Page kütüphanesinin referans olarak eklendiğinden emin olun.

**S3: Aspose.Page for .NET'te başka degrade türleri mevcut mu?**  
C: Aspose.Page, radyal ve yol degradeleri dahil çeşitli degrade türlerini destekler. Daha fazla ayrıntı için belgelere bakın.

**S4: Aspose.Page'i ticari projelerde kullanabilir miyim?**  
C: Evet, kullanabilirsiniz. Lisans seçeneklerini incelemek için [burayı](https://purchase.aspose.com/buy) ziyaret edin.

**S5: Aspose.Page için yardım alabileceğim bir topluluk forumu var mı?**  
C: Elbette! Diğer geliştiricilerle bağlantı kurmak ve yardım almak için [Aspose.Page forumuna](https://forum.aspose.com/c/page/39) gidin.

---

**Son Güncelleme:** 2026-02-25  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
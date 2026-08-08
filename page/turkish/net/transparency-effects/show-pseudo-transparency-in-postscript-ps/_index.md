---
date: 2026-03-29
description: Aspose.Page for .NET ile PostScript'te sahte şeffaflık oluşturmak için
  C#'ta lineer degrade fırçasının nasıl kullanılacağını öğrenin.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: PS'de Pseudo-Şeffaflık için C# Lineer Gradyan Fırçası
url: /tr/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) İçin Pseudo-Şeffaflıkta Linear Gradient Brush C#

## Giriş

PostScript (PS) dosyalarınıza ince bir geçiş efekti eklemeniz gerekiyorsa, **linear gradient brush C#** mükemmel araçtır. Aspose.Page for .NET, opak ve yarı saydam degrade dolgu ile dikdörtgenler çizmeyi kolaylaştırır ve belgelerinize modern, katmanlı bir görünüm kazandırır. Bu öğreticide, C#'ta bir linear gradient brush kullanarak pseudo‑şeffaflık oluşturmak için gereken adımları adım adım göstereceğiz.

## Hızlı Yanıtlar
- **Linear gradient brush'ı sağlayan kütüphane nedir?** Aspose.Page for .NET
- **Hangi grafik sınıfı degrade oluşturur?** `LinearGradientBrush`
- **Renk başına opaklığı kontrol edebilir miyim?** Evet, `Color.FromArgb(alpha, …)` kullanarak
- **Üretim için lisansa ihtiyacım var mı?** Geçerli bir Aspose.Page lisansı gereklidir
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Linear Gradient Brush C# Nedir?

`LinearGradientBrush`, iki renk arasında düz bir çizgi boyunca yumuşak bir geçiş çizen bir GDI+ nesnesidir. Her renk için alfa kanalını (0‑255) belirttiğinizde, yarı saydam degrade oluşturabilirsiniz—tam da PostScript'te pseudo‑şeffaflık için ihtiyacımız olan şey.

## Pseudo‑Şeffaflık İçin Linear Gradient Brush C# Neden Kullanılır?

- **İnce ayarlı opaklık kontrolü:** İstenen geçiş seviyesini elde etmek için her rengin alfasını ayarlayın.  
- **Cihaz bağımsız renderleme:** Fırça ekran, PDF, EPS ve PS çıktılarında aynı şekilde çalışır.  
- **Basit API:** Birkaç C# satırı profesyonel düzeyde görsel efektler üretir.

## Önkoşullar

Kodun içine dalmadan önce şunların yüklü olduğundan emin olun:

- Aspose.Page for .NET yüklü. [Aspose.Page documentation](https://reference.aspose.com/page/net/) adresinden indirebilirsiniz.
- Oluşturulan PostScript belgesinin kaydedileceği yazılabilir bir klasör.

Gerekli araçlara sahip olduğunuza göre, pseudo‑şeffaf dikdörtgenleri oluşturmaya başlayalım.

## Ad Alanlarını İçe Aktarın

Başlamadan önce, kullanacağımız sınıfları içeren ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: PostScript Belgesi İçin Çıktı Akışını Oluşturun

Sonuç PS dosyasını tutacak bir dosya akışı oluşturup ardından `PsDocument`'i başlatıyoruz.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 2: **Opak** Degrade Dolgulu Bir Dikdörtgen Oluşturun

Burada renkleri tamamen opak (alpha = 255) olan bir `LinearGradientBrush` oluşturuyoruz. Bu dikdörtgen arka plan katmanı olarak hizmet verecek.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Adım 3: **Yarı Saydam** Degrade Dolgulu Bir Dikdörtgen Oluşturun

Şimdi alfa değerleri 255'ten düşük (ör. 150 ve 50) olan bir **linear gradient brush C#** kullanıyoruz. Bu, dikdörtgeni kısmen şeffaf yapar ve pseudo‑şeffaflık etkisini elde eder.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Adım 4: Sayfayı Kapatın ve Belgeyi Kaydedin

Son olarak sayfayı bitirip PS dosyasını diske yazıyoruz.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Bu dört adımı izleyerek opak ve yarı saydam dikdörtgenleri sorunsuz bir şekilde birleştirebilir, herhangi bir PostScript çıktısında ikna edici bir pseudo‑şeffaflık efekti oluşturabilirsiniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| Renkler tamamen opak görünüyor | Alfa değeri yanlışlıkla 255 olarak ayarlandı | `alpha` < 255 olacak şekilde `Color.FromArgb(alpha, …)` kullanın |
| Degrade yanlış şekilde gerilmiş | Yanlış dönüşüm matrisi | Matris parametrelerinin dikdörtgen boyutlarıyla eşleştiğini doğrulayın |
| Çıktı dosyası boş | Akış kapatılmadı veya `Save()` çağrılmadı | `document.ClosePage()` ve `document.Save()`'in `using` bloğu içinde çalıştırıldığından emin olun |

## Sıkça Sorulan Sorular

**S: Aspose.Page tüm .NET sürümleriyle uyumlu mu?**  
C: Aspose.Page for .NET, .NET framework'ün çeşitli sürümleriyle uyumludur, esneklik ve entegrasyon kolaylığı sağlar.

**S: Pseudo‑şeffaflığı sadece dikdörtgenler dışında diğer şekillere de uygulayabilir miyim?**  
C: Evet, aynı prensipleri `GraphicsPath`'i uygun şekilde ayarlayarak herhangi bir şekle uygulayabilirsiniz.

**S: Ek örnekler ve belgeler nerede bulunabilir?**  
C: Kapsamlı örnekler ve detaylı API referansları için [Aspose.Page documentation](https://reference.aspose.com/page/net/) adresini inceleyin.

**S: Aspose.Page için ücretsiz deneme mevcut mu?**  
C: Evet, [bu linkten](https://releases.aspose.com/) Aspose.Page'in ücretsiz denemesine erişebilirsiniz.

**S: Aspose.Page için geçici bir lisans nasıl alabilirim?**  
C: Aspose.Page için geçici lisans almak üzere [bu linki](https://purchase.aspose.com/temporary-license/) ziyaret edin.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
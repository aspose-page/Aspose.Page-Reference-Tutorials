---
title: Aspose.Page ile PostScript'te (PS) Sahte Şeffaflığı Göster
linktitle: PostScript'te (PS) Sahte Şeffaflığı Göster
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile PostScript'te sözde şeffaflığın gücünü keşfedin. Görsel olarak etkileyici belgeler için adım adım kılavuzumuzu izleyin.
type: docs
weight: 13
url: /tr/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## giriiş

Sahte şeffaflık ekleyerek PostScript (PS) belgelerinizin görsel çekiciliğini arttırmayı mı istiyorsunuz? Aspose.Page for .NET, bu etkiyi zahmetsizce elde etmek için güçlü bir çözüm sunar. Bu adım adım eğitimde, Aspose.Page'i kullanarak PostScript'te sahte şeffaflık gösterme sürecinde size rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Aspose.Page for .NET: Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Page belgeleri](https://reference.aspose.com/page/net/).

- Belge Dizini: PostScript belgelerinizi depolamak için bir dizin ayarlayın.

Artık gerekli araçlara sahip olduğunuza göre, Aspose.Page kullanarak PostScript'te sahte şeffaflığın nasıl sergileneceğini keşfedelim.

## Ad Alanlarını İçe Aktar

Örneği derinlemesine incelemeden önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. Adım: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
//PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//A4 boyutunda kaydetme seçenekleri oluşturun
	PsSaveOptions options = new PsSaveOptions();

	// Yeni 1 sayfalık PS Belgesi oluştur
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 2: Opak Degrade Dolguyla Dikdörtgen Oluşturun

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

## Adım 3: Yarı Saydam Degrade Dolguyla Dikdörtgen Oluşturun

```csharp
	offsetX = 350;

	//İlk dikdörtgenden grafik yolu oluşturun
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Şeffaflığı 255 değil 150 ve 50 olan doğrusal degrade fırça renkleri oluşturun. Yani yarı saydamdır.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Adım 4: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Bu adımları izleyerek, Aspose.Page for .NET'i kullanarak sözde şeffaflığı PostScript belgelerinize sorunsuz bir şekilde entegre edebilirsiniz.

## Çözüm

Sonuç olarak Aspose.Page for .NET, PostScript belgelerinizin görsel öğelerini geliştirmenin basit ve etkili bir yolunu sunar. Yukarıda özetlenen adımlar, sözde şeffaflığı dahil etmek için açık bir yol sağlayarak görsel olarak etkileyici çıktılar oluşturmanıza olanak tanır.

## SSS'ler

### S1: Aspose.Page, .NET'in tüm sürümleriyle uyumlu mudur?

Cevap1: Aspose.Page for .NET, .NET framework'ün çeşitli versiyonlarıyla uyumludur, esneklik ve entegrasyon kolaylığı sağlar.

### S2: Dikdörtgenlerin yanı sıra diğer şekillere de sözde şeffaflık uygulayabilir miyim?

C2: Evet, GraphicsPath uygun şekilde ayarlanarak aynı prensipler diğer şekillere de uygulanabilir.

### S3: Ek örnekleri ve belgeleri nerede bulabilirim?

 A3: Keşfedin[Aspose.Page belgeleri](https://reference.aspose.com/page/net/) Kapsamlı örnekler ve ayrıntılı belgeler için.

### S4: Aspose.Page'in ücretsiz deneme sürümü mevcut mu?

 Cevap4: Evet, Aspose.Page'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[bu bağlantı](https://releases.aspose.com/).

### S5: Aspose.Page için nasıl geçici lisans alabilirim?

 A5: Ziyaret edin[bu bağlantı](https://purchase.aspose.com/temporary-license/) Aspose.Page için geçici bir lisans almak için.
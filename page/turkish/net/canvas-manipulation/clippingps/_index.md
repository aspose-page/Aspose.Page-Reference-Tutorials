---
title: .NET için Aspose.Page ile PS'yi kırpma
linktitle: PS'yi kırpma
second_title: Aspose.Page .NET API'si
description: PostScript belgelerini kırpmaya ilişkin bu adım adım eğitimle Aspose.Page for .NET'in gücünü keşfedin. Belge işleme yeteneklerinizi zahmetsizce geliştirmeyi öğrenin.
weight: 10
url: /tr/net/canvas-manipulation/clippingps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET için Aspose.Page ile PS'yi kırpma

## giriiş

PostScript (PS) belgelerinde kırpma uygulamak için Aspose.Page for .NET'in kullanımına ilişkin kapsamlı eğitime hoş geldiniz. Bu eğitim, .NET uygulamalarında çeşitli belge formatlarıyla çalışmak için güçlü bir kütüphane olan Aspose.Page'i kullanarak PS belgelerini kırpma sürecinde size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- C# programlama dili hakkında çalışma bilgisi.
-  Aspose.Page for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/page/net/).
- Visual Studio gibi entegre bir geliştirme ortamı (IDE).

## Ad Alanlarını İçe Aktar

Gerekli ad alanlarını C# kodunuza aktararak başlayın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi örneği birden çok adıma ayıralım:

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
// PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## 3. Adım: Kaydetme Seçenekleri Oluşturun

```csharp
// Varsayılan değerlerle kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();
```

## 4. Adım: 1 Sayfalık Yeni Bir PS Belgesi Oluşturun

```csharp
// Yeni 1 sayfalık PS Belgesi oluştur
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 5: Dikdörtgenden Grafik Yolu Oluşturun

```csharp
// Dikdörtgenden grafik yolu oluşturun
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## Adım 6: Şekle Göre Kırpma

```csharp
// Dönüşümden sonra bu duruma geri dönmek için grafik durumunu kaydedin
document.WriteGraphicsSave();

//Geçerli grafik durumunu 100 nokta sağa ve 100 nokta aşağıya kaydır.
document.Translate(100, 100);

// Çemberden grafik yolu oluştur
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Mevcut grafik durumuna daire şeklinde kırpma ekleme
document.Clip(circlePath);

// Boyayı geçerli grafik durumunda ayarla
document.SetPaint(new SolidBrush(Color.Blue));

// Dikdörtgeni mevcut grafik durumunda doldurun (kırpma ile)
document.Fill(rectanglePath);

// Grafik durumunu önceki (üst) seviyeye geri yükleyin
document.WriteGraphicsRestore();
```

## Adım 7: Üst Düzey Grafik Durumunu Değiştirin

```csharp
// Üst düzey grafik durumunu 100 nokta sağa ve 100 nokta alta kaydırın.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Dikdörtgeni, kırpılan dikdörtgenin üzerine geçerli grafik durumunda (kırpılma olmadan) çizin
document.Draw(rectanglePath);
```

## Adım 8: Belgeyi Kapatın ve Kaydedin

```csharp
// Geçerli sayfayı kapat
document.ClosePage();

// Belgeyi kaydet
document.Save();
```

Artık Aspose.Page for .NET'i kullanarak PostScript belgesinde kırpmayı başarıyla uyguladınız.

## Çözüm

Bu eğitimde, PostScript belgelerinde kırpma uygulamak için Aspose.Page for .NET'i nasıl kullanacağınızı öğrendiniz. Bu güçlü kitaplık, .NET uygulamalarınızda çeşitli belge formatlarını işlemek için kusursuz ve etkili bir yol sağlar.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?

Cevap1: Aspose.Page öncelikle .NET uygulamaları için tasarlanmıştır. Ancak Aspose diğer programlama dilleri için de benzer kütüphaneler sağlar.

### S2: Aspose.Page for .NET için ek örnekleri ve belgeleri nerede bulabilirim?

 Cevap2: Daha fazla örneği ve ayrıntılı belgeleri inceleyebilirsiniz.[Aspose.Page belgeleri](https://reference.aspose.com/page/net/).

### S3: Aspose.Page for .NET'in ücretsiz deneme sürümü mevcut mu?

 Cevap3: Evet, Aspose.Page for .NET'in ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S4: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Nereden destek alabilirim veya Aspose.Page ile ilgili soruları tartışabilirim?

 A5: ziyaret edin[Aspose.Page forumları](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

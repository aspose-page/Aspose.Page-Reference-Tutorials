---
title: Aspose.Page for .NET ile PostScript'e (PS) Dikdörtgen Ekleme
linktitle: PostScript'e (PS) Dikdörtgen Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page ile .NET'te belge oluşturmayı geliştirin. PostScript (PS) dosyalarına adım adım dikdörtgen eklemeyi öğrenin.
type: docs
weight: 12
url: /tr/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## giriiş

.NET'te belge oluşturma yeteneklerinizi geliştirmek istiyorsanız Aspose.Page, PostScript belgelerinin işlenmesi için güçlü bir çözüm sunar. Bu eğitimde, Aspose.Page for .NET'i kullanarak PostScript belgesine dikdörtgen ekleme sürecinde size rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET Kütüphanesi: Aspose.Page for .NET kütüphanesini şuradan indirip yükleyin:[Burada](https://releases.aspose.com/page/net/).

- Geliştirme Ortamı: Makinenizde bir .NET geliştirme ortamının kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi örneği birden çok adıma ayıralım:

## 1. Adım: Belge Dizininizi Kurun

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```

Bu adımda, "Belge Dizininiz"i PostScript belgenizi kaydetmek istediğiniz yolla değiştirin.

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
//PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Burada PostScript belgesi için bir çıktı akışı oluşturuyoruz ve dosya adını belirtiyoruz ("AddRectangle_outPS.ps"). Dosya adını ve konumunu tercihlerinize göre ayarlayın.

## 3. Adım: Kaydetme Seçeneklerini Ayarlayın ve PS Belgesi Oluşturun

```csharp
//A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();

// Yeni 1 sayfalık PS Belgesi oluştur
PsDocument document = new PsDocument(outPsStream, options, false);
```

İstediğiniz sayfa boyutunu (bu durumda A4) belirterek kaydetme seçeneklerini ayarlayın. Ardından yeni bir tek sayfalı PostScript belgesi oluşturun.

## Adım 4: Dikdörtgen Ekle ve Doldur

```csharp
//İlk dikdörtgenden grafik yolu oluşturun
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Boyayı ayarla
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Dikdörtgeni doldur
document.Fill(path);
```

Burada ilk dikdörtgeni temsil eden bir grafik yolu oluşturuyoruz, boya rengini ayarlıyoruz (bu durumda turuncu) ve dikdörtgeni dolduruyoruz.

## Adım 5: Başka Bir Dikdörtgen ve Kontur Ekleyin

```csharp
//İkinci dikdörtgenden grafik yolu oluşturun
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Konturu ayarla
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Dikdörtgenin konturunu (ana hatlarını) çizin
document.Draw(path);
```

Önceki adıma benzer şekilde, ikinci dikdörtgen için bir grafik yolu oluşturuyoruz, kontur rengini ayarlıyoruz (3 kalınlığında kırmızı) ve dikdörtgenin ana hatlarını çiziyoruz.

## Adım 6: Sayfayı Kapatın ve Belgeyi Kaydedin

```csharp
//Geçerli sayfayı kapat
document.ClosePage();

//Belgeyi kaydet
document.Save();
```

Son olarak geçerli sayfayı kapatın ve belgenin tamamını kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak PostScript belgesine başarıyla dikdörtgenler eklediniz. Bu eğitim, geliştirme ortamınızı kurmaktan son belgeyi kaydetmeye kadar temel adımları kapsıyordu.

## SSS'ler

### S1: Dikdörtgenlerin renklerini özelleştirebilir miyim?

A1: Evet, parametreleri ayarlayarak renkleri özelleştirebilirsiniz.`SolidBrush` Ve`Pen` sınıflar.

### S2: Aspose.Page diğer belge formatlarıyla uyumlu mudur?

Cevap2: Evet, Aspose.Page, XPS ve PostScript dahil çeşitli belge formatlarını destekler.

### S3: Belgeye nasıl metin ekleyebilirim?

 A3: kullanabilirsiniz`TextFragment` Belgenize metin eklemek için Aspose.Page'deki class'ı kullanın.

### S4: Ek örnekleri ve belgeleri nerede bulabilirim?

 Cevap4: Belgeleri inceleyin[Burada](https://reference.aspose.com/page/net/) ve ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.

### S5: Satın almadan önce Aspose.Page'i deneyebilir miyim?

 A5: Evet, ücretsiz deneme sürümünü alabilirsiniz[Burada](https://releases.aspose.com/) ve uzun süreli kullanım için, bir[geçici lisans](https://purchase.aspose.com/temporary-license/).

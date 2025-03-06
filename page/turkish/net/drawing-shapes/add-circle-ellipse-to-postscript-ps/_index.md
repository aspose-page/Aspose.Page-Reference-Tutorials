---
title: Aspose.Page ile PostScript'e (PS) Circle Ellipse ekleme
linktitle: PostScript'e Daire Elipsi Ekleme (PS)
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak PostScript (PS) belgelerine zahmetsizce daire elipsleri nasıl ekleyeceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 10
url: /tr/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript'e (PS) Circle Ellipse ekleme

## giriiş

Aspose.Page for .NET kullanarak PostScript (PS) belgelerine daire elipsleri eklemeyi konu alan bu kapsamlı eğitime hoş geldiniz. Aspose.Page, geliştiricilerin PostScript ve diğer belge formatlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu kılavuzda daire elipslerini PS belgelerinize kolaylıkla dahil etme sürecinde size yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Page for .NET Kütüphanesi: Aspose.Page for .NET kütüphanesini şuradan indirip yükleyin:[Burada](https://releases.aspose.com/page/net/).

2. Geliştirme Ortamı: Makinenizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun.

Şimdi adım adım kılavuza başlayalım.

## Ad Alanlarını İçe Aktar

İlk adımda, Aspose.Page işlevselliğini kodunuzda kullanılabilir hale getirmek için gerekli ad alanlarını içe aktarmanız gerekir.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi, bir PostScript belgesine daire elipsleri ekleme sürecinde size yol göstermesi için verilen örneği birden çok adıma ayıralım.

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```

"Belge Dizininiz"i, belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
//PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Burada PostScript belgesini yazmak için bir FileStream oluşturulur ve dosya modu yeni bir dosya oluşturacak şekilde ayarlanır.

## 3. Adım: Kaydetme Seçenekleri ve PS Belgesi Oluşturun

```csharp
//A4 boyutunda kaydetme seçenekleri oluşturun
PsSaveOptions options = new PsSaveOptions();

// Yeni 1 sayfalık PS Belgesi oluştur
PsDocument document = new PsDocument(outPsStream, options, false);
```

Bu adım, A4 boyutunda kaydetme seçenekleri oluşturmayı ve yeni bir 1 sayfalık PS Belgesinin başlatılmasını içerir.

## Adım 4: İlk Elips için Grafik Yolu Oluşturun

```csharp
//İlk elipsten grafik yolu oluşturun
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

İlk elips için konumunu ve boyutlarını belirten bir grafik yolu oluşturulur.

## Adım 5: Boyayı Ayarlayın ve Elipsi Doldurun

```csharp
//Boyayı ayarla
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Elipsi doldur
document.Fill(path);
```

Burada boya ayarlanır ve ilk elips belirtilen renkle doldurulur.

## Adım 6: İkinci Elips için Grafik Yolu Oluşturun

```csharp
//İkinci elipsten grafik yolu oluşturun
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Benzer şekilde, ikinci elips için konumunu ve boyutlarını tanımlayan bir grafik yolu oluşturulur.

## Adım 7: Konturu Ayarlayın ve Elipsi Çizin

```csharp
//Konturu ayarla
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Elipsi konturlayın (ana hatlarını çizin)
document.Draw(path);
```

Bu adımda kontur ayarlanır ve ikinci elips belirtilen renk ve çizgi kalınlığıyla ana hatlarıyla belirtilir.

## Adım 8: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin

```csharp
//Geçerli sayfayı kapat
document.ClosePage();

//Belgeyi kaydet
document.Save();
```

Son olarak mevcut sayfa kapatılır ve belgenin tamamı kaydedilerek işlem tamamlanır.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak PostScript belgelerine daire elipslerinin nasıl ekleneceğini başarıyla öğrendiniz. Bu eğitimde, bu işlevselliği projelerinize sorunsuz bir şekilde entegre etmenize yardımcı olacak ayrıntılı, adım adım bir kılavuz sağlanmıştır.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?

 Cevap1: Aspose.Page öncelikle PostScript'e odaklanır, ancak Aspose çeşitli belge formatları için başka kütüphaneler de sağlar. Kontrol edin[Belgeleri sunun](https://reference.aspose.com/page/net/) daha fazla ayrıntı için.

### S2: Ek desteği ve topluluk tartışmalarını nerede bulabilirim?

 A2: Ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) Topluluk tartışmaları ve desteği için.

### S3: Aspose.Page for .NET'in ücretsiz deneme sürümü mevcut mu?

 A3: Evet, erişebilirsiniz[ücretsiz deneme](https://releases.aspose.com/)Aspose.Page for .NET'in özelliklerini keşfetmek için.

### S4: Aspose.Page için nasıl geçici lisans alabilirim?

 Cevap4: Geçici bir lisans edinin[Burada](https://purchase.aspose.com/temporary-license/) test ve değerlendirme amaçlıdır.

### S5: Aspose.Page for .NET'i nereden satın alabilirim?

 Cevap5: .NET için Aspose.Page'i şu adresten satın alın:[satın alma sayfası](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

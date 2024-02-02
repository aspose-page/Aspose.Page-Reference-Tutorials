---
title: Aspose.Page for .NET ile EPS Görüntülerini Kırpın
linktitle: EPS Görüntülerini Kırp
second_title: Aspose.Page .NET API'si
description: Aspose.Page ile .NET'te EPS görüntü işlemenin kusursuz dünyasını keşfedin. Çarpıcı sonuçlar için görüntüleri zahmetsizce kırpın ve yeniden boyutlandırın.
type: docs
weight: 10
url: /tr/net/image-manipulation/crop-eps-images/
---
## giriiş

.NET uygulamalarınızda EPS görüntülerini değiştirmekte zorlanıyor musunuz? Başka yerde arama! Bu eğitimde, güçlü Aspose.Page for .NET kitaplığını kullanarak EPS görüntülerini kırpma sürecinde size rehberlik edeceğiz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, bu adım adım kılavuz, hassas görüntü kırpma işlemini zahmetsizce gerçekleştirmenize yardımcı olacaktır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- .NET geliştirme konusunda çalışma bilgisi.
-  Aspose.Page for .NET kütüphanesi kuruldu. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).
- Örnek bir EPS görüntüsü (koddaki "input.eps" ifadesini gerçek dosyanızla değiştirin).

## Ad Alanlarını İçe Aktar

Kodumuzun sorunsuz çalışması için gerekli ad alanlarını içe aktararak başlayalım. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Şimdi öğreticiyi birden fazla adıma ayıralım.

## 1. Adım: PsDocument'i başlatın

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Bir başlat`PsDocument` giriş EPS akışına sahip nesne.

## Adım 2: Sınırlayıcı Kutuyu Çıkarın

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

EPS görüntüsünün ilk sınırlayıcı kutusunu alın.

## 3. Adım: Çıktı Akışı Oluşturun

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Kırpılan EPS görüntüsü için bir çıktı akışı oluşturun.

## Adım 4: Yeni Sınırlayıcı Kutuyu Tanımlayın

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Kırpma için yeni bir sınırlayıcı kutu tanımlayın. Yeni değerlerin ilk sınırlayıcı kutunun içinde olduğundan emin olun.

## Adım 5: Kırpın ve Kaydedin

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Yeni sınırlayıcı kutuyu kullanarak EPS görüntüsünü kırpın ve çıktı akışına kaydedin.

Farklı yeniden boyutlandırma senaryoları için bu adımları tekrarlayın.

## EPS Görüntülerini Yeniden Boyutlandırma

### İnç Olarak Yeniden Boyutlandır

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

EPS görüntüsünü yeniden boyutlandırın ve inç cinsinden belirtilen boyutlarla kaydedin.

### Milimetre Olarak Yeniden Boyutlandır

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

EPS görüntüsünü yeniden boyutlandırın ve belirtilen boyutlarla milimetre cinsinden kaydedin.

### Yüzde Olarak Yeniden Boyutlandır

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

EPS görüntüsünü yeniden boyutlandırın ve belirtilen boyutlarla yüzde olarak kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak EPS görüntülerini nasıl kırpacağınızı ve yeniden boyutlandıracağınızı başarıyla öğrendiniz. Şimdi görüntü işleme yeteneklerinizi geliştirin ve .NET uygulamalarınızı bir sonraki seviyeye taşıyın.

## SSS

### S1: Aspose.Page for .NET'i diğer görüntü formatlarıyla kullanabilir miyim?

Cevap1: Aspose.Page öncelikle EPS görüntülerine odaklanır, ancak Aspose farklı formatlar için çeşitli kütüphaneler sağlar. Belirli formatlar için belgelerine bakın.

### S2: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 A2: Ziyaret edin[bu bağlantı](https://purchase.aspose.com/temporary-license/) Test için geçici bir lisans almak için.

### S3: Aspose.Page for .NET ile işleyebileceğim görüntü boyutunda herhangi bir sınırlama var mı?

Cevap3: Aspose.Page çeşitli boyutlardaki görselleri işleyecek şekilde tasarlanmıştır. Ancak performans, görüntünün karmaşıklığına bağlı olarak değişebilir.

### S4: Aspose.Page tartışmaları için bir topluluk forumu var mı?

 Cevap4: Evet, Aspose.Page topluluğuyla etkileşime geçebilirsiniz[Burada](https://forum.aspose.com/c/page/39).

### S5: Aspose.Page for .NET'in ayrıntılı belgelerini nerede bulabilirim?

 A5: Belgelere bakın[Burada](https://reference.aspose.com/page/net/).
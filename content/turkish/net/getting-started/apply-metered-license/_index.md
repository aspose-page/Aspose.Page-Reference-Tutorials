---
title: Aspose.Page for .NET ile Ölçülü Lisans Uygulayın
linktitle: Ölçülü Lisansı Uygula
second_title: Aspose.Page .NET API'si
description: Ölçülü lisans uygulamasına ilişkin bu adım adım kılavuzla Aspose.Page for .NET'in kusursuz entegrasyonunu keşfedin. Belge işlemeyi zahmetsizce optimize edin.
type: docs
weight: 10
url: /tr/net/getting-started/apply-metered-license/
---
## giriiş

Ölçülü bir lisans uygulayarak Aspose.Page for .NET'in tüm potansiyelini ortaya çıkarın. Bu eğitim, bu güçlü .NET kitaplığının sorunsuz ve optimize edilmiş kullanımını sağlayarak, ölçülü lisansı kurma ve uygulama sürecinde size rehberlik edecektir.

## Önkoşullar

Adımlara dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Geçerli bir Aspose.Page for .NET lisansı: Bunu şu adresten edinebilirsiniz:[satın alma.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page kütüphanesi kuruldu: Bkz.[dokümantasyon](https://reference.aspose.com/page/net/) Kurulum talimatları için.
- .NET geliştirme ortamı: Makinenizde çalışan bir .NET ortamının kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktar

Aspose.Page işlevlerine erişmek için .NET projenize gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## 1. Adım: Ölçülen Genel ve Özel Anahtarları Ayarlayın

 Başlat`Aspose.Page.Metered` sınıflandırın ve ölçülü genel ve özel anahtarları ayarlayın. Yer değiştirmek`<type public key here>` Ve`<type private key here>` gerçek anahtarlarınızla.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Adım 2: EPS Dosyasını Yükleyin ve Belge Oluşturun

 EPS dosyanızın yolunu belirtin ve içeriğini okumak için bir akış oluşturun. Ardından, bir örneğini oluşturun`PsDocument` akıştan sınıf.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Adım 3: EPS'yi PNG Görüntüsüne Dönüştürün

 Oluşturduğunuz bir`ImageDevice` EPS dosyasını PNG görüntüsüne dönüştürmek için. EPS dosyasını kullanarak resim olarak kaydedin.`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Adım 4: Görüntü Baytlarını Alın

Her bayt dizisinin bir sayfayı temsil ettiği görüntü baytlarını alın. Bu durumda bir sayfamız var.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Adım 5: Görüntü Baytlarını Dosyaya Kaydetme

EPS'den PNG'ye başarılı bir dönüşüm sağlayarak görüntü baytlarını bir dosyaya kaydedin.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## 6. Adım: Ölçülü Lisansı Doğrulayın

Ölçülü lisansın başarıyla uygulanıp uygulanmadığını görsel olarak kontrol edin. Ortaya çıkan görüntü kırmızı değerlendirme mesajını içermiyorsa bu, ölçülü lisansın herhangi bir sorun olmadan uygulandığını gösterir.

Artık Aspose.Page for .NET'in tüm özelliklerinden ölçülü lisansla yararlanmaya hazırsınız!

## Çözüm

Bu adım adım kılavuz, Aspose.Page for .NET'i kullanarak ölçülü bir lisansı sorunsuz bir şekilde uygulayabilmeniz için sizi bilgiyle donattı. Belge işleme yeteneklerinizi geliştirin ve bu güçlü kitaplığın sunduğu geniş özellikleri keşfedin.

## SSS'ler

### S1: Aspose.Page for .NET için ölçülü lisansı nasıl edinebilirim?

 A1: Ziyaret edin[satın alma.aspose.com](https://purchase.aspose.com/buy) Geçerli bir lisans almak için.

### S2: Aspose.Page for .NET belgelerini nerede bulabilirim?

 A2: Bkz.[Aspose.Page .NET](https://reference.aspose.com/page/net/) kapsamlı belgeler için.

### S3: Aspose.Page tartışmaları ve desteği için bir forum var mı?

 A3: Evet, ziyaret edin[forum](https://forum.aspose.com/c/page/39) toplulukla etkileşime geçmek ve yardım istemek.

### S4: Satın almadan önce Aspose.Page for .NET'i deneyebilir miyim?

 Cevap4: Kesinlikle! Ücretsiz denemeye şuradan erişin:[Burada](https://releases.aspose.com/).

### S5: Aspose.Page for .NET için nasıl geçici lisans alabilirim?

 A5: Ziyaret edin[geçici lisans/](https://purchase.aspose.com/temporary-license/) geçici lisans almak için.
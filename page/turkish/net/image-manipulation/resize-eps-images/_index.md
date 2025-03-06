---
title: EPS Görüntülerini Aspose.Page for .NET ile yeniden boyutlandırın
linktitle: EPS Görüntülerini Yeniden Boyutlandır
second_title: Aspose.Page .NET API'si
description: Aspose.Page'i kullanarak .NET'te EPS görüntülerini yeniden boyutlandırmanın kusursuz sürecini keşfedin. Zahmetsizce nokta, inç, milimetre ve yüzde hassasiyetine ulaşın.
weight: 11
url: /tr/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS Görüntülerini Aspose.Page for .NET ile yeniden boyutlandırın

## giriiş

Aspose.Page for .NET'i kullanarak EPS görüntülerini sorunsuz bir şekilde yeniden boyutlandırmak mı istiyorsunuz? Bu eğitim, EPS görüntülerinin boyutunu nokta, inç, milimetre ve yüzde gibi çeşitli birimlerle zahmetsizce değiştirmek için kapsamlı kılavuzunuzdur. Aspose.Page for .NET güçlü bir araç seti sunar ve bu eğitimde size süreci adım adım anlatacağız.

## Önkoşullar

Yeniden boyutlandırma büyüsüne dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET Library: Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

- Belge Dizini: Giriş EPS dosyanızı ve yeniden boyutlandırılmış çıktı dosyalarınızı saklayacağınız bir dizin oluşturun.

Artık her şeyi ayarladığınıza göre, gerekli ad alanlarını içe aktarmaya devam edelim ve adım adım kılavuzu inceleyelim.

## Ad Alanlarını İçe Aktar

.NET projenize Aspose.Page ile çalışmak için gerekli ad alanlarını içe aktararak başlayın. Dosyanızın başına aşağıdaki kodu ekleyin:

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

## 1. Adım: Noktalarda Yeniden Boyutlandırma

Bir EPS görüntüsünü noktalar halinde yeniden boyutlandırarak başlayalım. Noktalar baskı endüstrisinde standart bir ölçü birimidir.

```csharp
public static void ResizeInPoints()
{
    // Belge Dizininiz
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Adım 2: İnç Cinsinden Yeniden Boyutlandırma

Şimdi bir EPS görüntüsünü grafik tasarımda yaygın olarak kullanılan bir birim olan inç cinsinden yeniden boyutlandıralım.

```csharp
public static void ResizeInInches()
{
    // Belge Dizininiz
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Adım 3: Milimetre cinsinden yeniden boyutlandırma

Şimdi bir EPS görüntüsünü, tasarım ve baskıda yaygın olarak kullanılan bir diğer birim olan milimetre cinsinden yeniden boyutlandıralım.

```csharp
public static void ResizeInMillimeters()
{
    // Belge Dizininiz
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Adım 4: Yüzde Olarak Yeniden Boyutlandırma

Son olarak, görüntü boyutunu ayarlamak için esnek bir yaklaşım sağlayarak, yüzdeleri kullanarak bir EPS görüntüsünü yeniden boyutlandıralım.

```csharp
public static void ResizeInPercents()
{
    // Belge Dizininiz
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Bu yöntemleri projenize entegre etmekten çekinmeyin; EPS görüntülerini zahmetsizce yeniden boyutlandıracaksınız. İstenilen boyutlara ulaşmak için farklı birimlerle denemeler yapın.

## Çözüm

Tebrikler! Aspose.Page for .NET ile EPS görüntülerini yeniden boyutlandırma sanatında ustalaştınız. Bu güçlü kütüphane, vektör grafiklerini değiştirmek için bir olasılıklar dünyasının kapılarını açar. İster basılı ister dijital medya için tasarım yapıyor olun, Aspose.Page hassas ve özelleştirilmiş sonuçlar elde etmenizi sağlar.

## SSS'ler

### S1: Birden fazla EPS görüntüsünü aynı anda yeniden boyutlandırabilir miyim?

Cevap1: Evet, yeniden boyutlandırma yöntemlerini uygun şekilde uygulayarak bir EPS dosyaları koleksiyonunda dolaşabilirsiniz.

### S2: Aspose.Page diğer görüntü formatlarıyla uyumlu mudur?

Cevap2: Aspose.Page öncelikli olarak PostScript ve EPS formatlarına odaklanır. Diğer görüntü formatları için Aspose.Imaging'i kullanmayı düşünün.

### S3: Ticari projeler için lisanslamayla ilgili hususlar var mı?

 C3: Evet, geçerli bir lisansınız olduğundan emin olun. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) lisans ayrıntıları için.

### S4: Satın almadan önce Aspose.Page'i deneyebilir miyim?

 Cevap4: Kesinlikle! Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/).

### S5: Nereden ek yardım alabilirim veya sorunları tartışabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) toplulukla bağlantı kurmak ve yardım almak için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

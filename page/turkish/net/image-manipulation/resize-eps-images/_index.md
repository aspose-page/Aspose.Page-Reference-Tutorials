---
date: 2026-03-03
description: Aspose.Page ile .NET’te EPS görüntülerini yeniden boyutlandırmayı öğrenin
  – puan, inç, milimetre veya yüzde kullanarak EPS’yi yeniden boyutlandırma konusunda
  adım adım bir rehber.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile EPS Görüntülerini Yeniden Boyutlandırma
url: /tr/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile EPS Görüntülerini Yeniden Boyutlandırma

## Giriş

Aspose.Page for .NET kullanarak **EPS görüntülerini nasıl yeniden boyutlandıracağınızı** sorunsuz bir şekilde mi arıyorsunuz? Bu öğretici, EPS görüntülerinin boyutunu noktalar, inçler, milimetreler ve yüzde gibi çeşitli birimlerde zahmetsizce manipüle etmeniz için kapsamlı bir rehberdir. Aspose.Page for .NET güçlü bir araç seti sunar ve bu öğreticide, süreci adım adım sizinle birlikte ele alacağız.

## Hızlı Yanıtlar
- **EPS yeniden boyutlandırmayı hangi kütüphane yönetir?** Aspose.Page for .NET  
- **Hangi birimler desteklenir?** Noktalar, İnçler, Milimetreler ve Yüzdeler  
- **Üretim için lisansa ihtiyacım var mı?** Evet – ticari bir lisans gereklidir  
- **Birden fazla dosyayı aynı anda yeniden boyutlandırabilir miyim?** Kesinlikle – sadece dosyalar arasında döngü yapın  
- **.NET Core destekleniyor mu?** Evet, API .NET Framework ve .NET Core ile çalışır  

## EPS Yeniden Boyutlandırma Nedir?
Encapsulated PostScript (EPS), baskı ve tasarım iş akışlarında yaygın olarak kullanılan vektör tabanlı bir grafik formatıdır. Bir EPS dosyasının yeniden boyutlandırılması, sanat eserini rasterleştirmeden sınırlama kutusunu değiştirir ve herhangi bir ölçekte netliği korur.

## EPS Görüntülerini Neden Yeniden Boyutlandırmalısınız?
- **Baskı Kalitesini Koruyun:** Vektör ölçeklendirme kenarları keskin tutar.  
- **Düzen Gereksinimlerine Uyun:** Boyutları sayfa veya tuval boyutlarıyla eşleyecek şekilde ayarlayın.  
- **Toplu İşleri Otomatikleştirin:** Programlı olarak dakikalar içinde onlarca dosyayı yeniden boyutlandırın.  

## Ön Koşullar

Yeniden boyutlandırma sihrine dalmadan önce, aşağıdaki ön koşulların yerine getirildiğinden emin olun:

- Aspose.Page for .NET Kütüphanesi: Aspose.Page for .NET kütüphanesinin yüklü olduğundan emin olun. [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.

- Belge Dizini: Giriş EPS dosyanızı ve çıktı yeniden boyutlandırılmış dosyalarınızı saklayacağınız bir dizin oluşturun.

Artık her şey hazır olduğuna göre, gerekli ad alanlarını içe aktarmaya devam edelim ve adım adım kılavuza dalalım.

## Ad Alanlarını İçe Aktarma

.NET projenizde, Aspose.Page ile çalışmak için gerekli ad alanlarını içe aktararak başlayın. Dosyanızın başına aşağıdaki kodu ekleyin:

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

## EPS'i Noktalarla Yeniden Boyutlandırma

Noktalar, baskı endüstrisinde standart bir ölçü birimidir. Aşağıdaki örnek, orijinal genişlik ve yüksekliği iki katına çıkarır.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## EPS'i İnçlerle Yeniden Boyutlandırma

İnçler, grafik tasarımcıların baskı için varlıkları hazırlarken sıkça kullandığı bir birimdir.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## EPS'i Milimetrelerle Yeniden Boyutlandırma

Milimetreler, metrik sistemi kullanan bölgelerde yaygındır.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## EPS'i Yüzde Kullanarak Yeniden Boyutlandırma

Yüzde tabanlı yeniden boyutlandırma, görüntüyü orijinal boyutuna göre ölçeklendirmenizi sağlar.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Bu yöntemleri projenize entegre etmekten çekinmeyin, böylece EPS görüntülerini zahmetsizce yeniden boyutlandırabilirsiniz. İstediğiniz boyutları elde etmek için farklı birimlerle denemeler yapın.

## Yaygın Sorunlar ve Çözümler
- **Dosya bulunamadı:** `dataDir`'in doğru klasöre işaret ettiğini ve `input.eps` dosyasının mevcut olduğunu doğrulayın.  
- **Beklenmeyen boyut:** `Units.Percents` değerinin orijinal boyutun %150'si için 150 gibi bir değer beklediğini unutmayın.  
- **Lisans istisnası:** Lisans hatası görürseniz, `PsDocument` oluşturulmadan önce geçerli bir Aspose.Page lisans dosyasının yüklendiğinden emin olun.  

## Sonuç

Tebrikler! Aspose.Page for .NET ile **EPS görüntülerini nasıl yeniden boyutlandıracağınızı** ustaca öğrendiniz. Bu güçlü kütüphane, vektör grafiklerini manipüle etmek için bir dizi olasılık sunar. Baskı ya da dijital medya tasarımı yapıyor olun, Aspose.Page size kesin ve özelleştirilmiş sonuçlar elde etme gücü verir.

## SSS'ler

### S1: Birden fazla EPS görüntüsünü aynı anda yeniden boyutlandırabilir miyim?
A1: Evet, EPS dosyalarının bir koleksiyonunda döngü yaparak, yeniden boyutlandırma yöntemlerini buna göre uygulayabilirsiniz.

### S2: Aspose.Page diğer görüntü formatlarıyla uyumlu mu?
A2: Aspose.Page öncelikle PostScript ve EPS formatlarına odaklanır. Diğer görüntü formatları için Aspose.Imaging kullanmayı düşünün.

### S3: Ticari projeler için lisans konuları var mı?
A3: Evet, geçerli bir lisansa sahip olduğunuzdan emin olun. Lisans detayları için [burayı](https://purchase.aspose.com/buy) ziyaret edin.

### S4: Satın almadan önce Aspose.Page'i deneyebilir miyim?
A4: Kesinlikle! Ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

### S5: Ek yardım almak ya da sorunları tartışmak için nereden ulaşabilirim?
A5: Toplulukla bağlantı kurmak ve yardım almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

## Sık Sorulan Sorular

**S: Bu kod .NET Core 6 ile çalışıyor mu?**  
C: Evet. API .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ ve .NET 6+ ile uyumludur.

**S: Orijinal renk profilini nasıl koruyabilirim?**  
C: `ResizeEps` yöntemi renk verisini değiştirmez; yalnızca sınırlama kutusunu değiştirir.

**S: Bir EPS dosyasını belleğe tamamen yüklemeden yeniden boyutlandırmak mümkün mü?**  
C: Gösterildiği gibi bir akış kullanmak bellek kullanımını düşük tutar; belge anlık olarak işlenir.

**S: Birden fazla yeniden boyutlandırma işlemini zincirleme yapabilir miyim?**  
C: Kesinlikle. Aynı `PsDocument` örneği üzerinde `ResizeEps` metodunu sırasıyla çağırın.

**S: EPS içindeki gömülü görüntülere ne olur?**  
C: Vektör içeriğiyle orantılı olarak ölçeklendirilirler ve kalite korunur.

---

**Son Güncelleme:** 2026-03-03  
**Test Edilen Versiyon:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
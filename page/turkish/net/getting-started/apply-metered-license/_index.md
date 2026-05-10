---
date: 2026-01-28
description: Aspose.Page for .NET kullanarak EPS'yi PNG'ye nasıl dönüştüreceğinizi
  öğrenin ve sorunsuz belge işleme için ölçülü bir lisans uygulayın.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile EPS'yi PNG'ye Dönüştürün ve Ölçülü Lisansı Uygulayın
url: /tr/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS'yi PNG'ye Dönüştürme ve Aspose.Page for .NET ile Ölçülen Lisans Uygulama

## Giriş

Aspose.Page for .NET'in **EPS'yi PNG'ye dönüştürme** ve ölçülen lisans uygulama yeteneklerini tam anlamıyla kullanın. Bu öğretici, bir EPS dosyasını yüklemekten PNG görüntüsü olarak kaydetmeye kadar tüm adımları size gösterir; böylece belgeleri verimli bir şekilde işleyebilir ve değerlendirme filigranlarından kurtulabilirsiniz.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** EPS dosyalarını PNG görüntülerine dönüştürme ve Aspose.Page for .NET ile ölçülen lisans uygulama.  
- **Lisans gerekir mi?** Evet, üretim kullanımı için ölçülen bir lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Uygulama ne kadar sürer?** Temel bir dönüşüm için yaklaşık 10–15 dakika.  
- **Bunu Linux/macOS'ta çalıştırabilir miyim?** Kesinlikle—Aspose.Page çapraz platformdur.

## “EPS'yi PNG'ye dönüştürmek” nedir?
EPS'yi PNG'ye dönüştürmek, vektör tabanlı Encapsulated PostScript (EPS) dosyasını bitmap PNG görüntüsüne rasterleştirmek anlamına gelir. Bu, EPS'yi desteklemeyen web sayfaları, raporlar veya UI bileşenlerinde grafik göstermek veya gömmek istediğinizde faydalıdır.

## EPS'den görüntüye dönüşümde ölçülen lisans neden kullanılmalı?
Ölçülen lisans, işlediğiniz sayfalar için yalnızca kullandıkça ödeme yapmanızı sağlar; değişken hacimli iş yükleri için idealdir. Ayrıca ücretsiz deneme sürümünde görülen kırmızı değerlendirme bannerını ortadan kaldırarak son kullanıcılarınız için temiz bir çıktı sunar.

## Ön Koşullar

Adımlara geçmeden önce aşağıdaki ön koşulların sağlandığından emin olun:

- Geçerli bir Aspose.Page for .NET lisansı: Lisansı [purchase.aspose.com](https://purchase.aspose.com/buy) adresinden temin edebilirsiniz.  
- Aspose.Page kütüphanesi yüklü: Kurulum talimatları için [documentation](https://reference.aspose.com/page/net/) sayfasına bakın.  
- .NET geliştirme ortamı: Makinenizde çalışan bir .NET ortamının kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktarma

.NET projenizde Aspose.Page işlevlerine erişmek için gerekli ad alanlarını içe aktarın:

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

## Ölçülen lisans ile EPS'yi PNG'ye nasıl dönüştürülür?

Aşağıda bilmeniz gereken her şeyi kapsayan adım‑adım bir rehber bulacaksınız.

### Adım 1: Ölçülen Genel ve Özel Anahtarları Ayarlama

`Aspose.Page.Metered` sınıfını başlatın ve ölçülen genel ve özel anahtarları ayarlayın. `<type public key here>` ve `<type private key here>` yerlerine kendi anahtarlarınızı girin.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Adım 2: EPS Dosyasını Yükleme ve Belge Oluşturma

EPS dosyanızın yolunu belirtin ve içeriğini okumak için bir akış oluşturun. Ardından, akıştan bir `PsDocument` örneği oluşturun.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Adım 3: EPS'yi PNG Görüntüsüne Dönüştürme

EPS dosyasını PNG görüntüsüne dönüştürmek için bir `ImageDevice` oluşturun. `ImageSaveOptions` kullanarak EPS dosyasını bir görüntü olarak kaydedin.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Adım 4: Görüntü Baytlarını Alma

Her bayt dizisinin bir sayfayı temsil ettiği görüntü baytlarını alın. Bu örnekte tek bir sayfamız var.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Adım 5: Görüntü Baytlarını Dosyaya Kaydetme

Görüntü baytlarını bir dosyaya kaydedin; böylece EPS'den PNG'ye başarılı bir dönüşüm elde etmiş olursunuz.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Adım 6: Ölçülen Lisansı Doğrulama

Lisansın başarıyla uygulandığını görsel olarak kontrol edin. Oluşan görüntü kırmızı değerlendirme mesajı içermiyorsa, ölçülen lisans sorunsuz bir şekilde uygulanmıştır.

Artık ölçülen lisans ile Aspose.Page for .NET'in tam yeteneklerini kullanmaya hazırsınız!

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Kırmızı değerlendirme bannerı hâlâ görünüyor | Lisans ayarlanmamış veya anahtarlar hatalı | Genel/özel anahtarları iki kez kontrol edin ve `SetMeteredKey` metodunun belge işleme öncesinde çağrıldığından emin olun |
| Çıktı dosyası oluşturulmadı | `dataDir` yolu hatalı veya dosya izinleri yetersiz | Dizin varlığını doğrulayın ve uygulamanın yazma iznine sahip olduğundan emin olun |
| Birden fazla sayfa kaydedilmiyor | Sadece ilk sayfa yazılıyor | `imagesBytes` üzerinde döngü kurarak her diziye ayrı bir PNG dosyası yazın |

## Sık Sorulan Sorular

**S: Ölçülen lisansı CI/CD boru hattında kullanabilir miyim?**  
C: Evet, anahtarları güvenli bir şekilde (ör. ortam değişkenleri) saklayabilir ve derleme sürecinde `SetMeteredKey` metodunu çağırabilirsiniz.

**S: Aspose.Page PNG'ye dönüştürürken renk profili korumasını destekliyor mu?**  
C: PNG çıktısı orijinal renk bilgisini korur, ancak `ImageSaveOptions` aracılığıyla daha da özelleştirilebilir.

**S: EPS'yi diğer raster formatlarına (JPEG, BMP) dönüştürmek mümkün mü?**  
C: Kesinlikle—`ImageSaveOptions`'ı istediğiniz formata değiştirmeniz yeterlidir.

**S: Desteklenen maksimum EPS dosya boyutu nedir?**  
C: Aspose.Page büyük dosyaları işleyebilir, ancak bellek tüketimi görüntü çözünürlüğüyle artar. Çok büyük belgeler için sayfaları tek tek işlemek akıllıca olur.

**S: EPS dosyasındaki sayfa sayısını programlı olarak nasıl alabilirim?**  
C: `PsDocument` yüklendikten sonra `document.PagesCount` özelliğini kullanın.

## SSS'ler

### S1: Aspose.Page for .NET için ölçülen lisansı nasıl temin ederim?

C1: Geçerli bir lisans almak için [purchase.aspose.com](https://purchase.aspose.com/buy) adresini ziyaret edin.

### S2: Aspose.Page for .NET dokümantasyonunu nerede bulabilirim?

C2: Kapsamlı dokümantasyon için [Aspose.Page .NET](https://reference.aspose.com/page/net/) sayfasına bakın.

### S3: Aspose.Page tartışma ve destek forumu var mı?

C3: Evet, toplulukla etkileşime geçmek ve yardım almak için [forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

### S4: Aspose.Page for .NET'i satın almadan denemek mümkün mü?

C4: Kesinlikle! Ücretsiz deneme sürümüne [here](https://releases.aspose.com/) üzerinden ulaşabilirsiniz.

### S5: Aspose.Page for .NET için geçici bir lisans nasıl alınır?

C5: Geçici lisans için [temporary license/](https://purchase.aspose.com/temporary-license/) adresini ziyaret edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Son Güncelleme:** 2026-01-28  
**Test Edilen Versiyon:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}
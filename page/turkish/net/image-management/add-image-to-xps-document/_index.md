---
date: 2026-02-28
description: Aspose.Page for .NET kullanarak XPS belgesi oluşturmayı ve görüntü eklemeyi
  öğrenin. Sorunsuz bir geliştirme deneyimi için bu adım adım kılavuzu izleyin.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: XPS Belgesi Oluştur .NET – Aspose.Page ile Görsel Ekle
url: /tr/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesine Görüntü Ekleme

Bu öğreticide, güçlü Aspose.Page kütüphanesini kullanarak **create XPS document .NET** nasıl oluşturacağınızı ve bir görüntüyü nasıl gömeceğinizi öğreneceksiniz. Raporlar, faturalar veya özel grafikler oluşturuyor olun, XPS dosyalarına görsel öğeler eklemek .NET geliştiricileri için sık bir gereksinimdir.

## Giriş

.NET geliştirme dünyasında, XPS belgelerine görüntü eklemek yaygın bir gereksinimdir. Aspose.Page for .NET bu süreci basitleştirir ve XPS belgelerini zahmetsizce manipüle edip geliştirebileceğiniz güçlü bir araç seti sunar. Bu öğretici, Aspose.Page for .NET kullanarak bir XPS belgesine görüntü ekleme adımlarını size gösterecek.

## Hızlı Yanıtlar
- **Bu öğreticinin kapsamı nedir?** Aspose.Page for .NET ile bir XPS belgesine görüntü ekleme.  
- **Hedeflenen birincil anahtar kelime nedir?** *create xps document .net*  
- **Lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim için bir lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 ile çalışır.  
- **Uygulama ne kadar sürer?** Temel bir görüntü ekleme için yaklaşık 5‑10 dakika.

## “create XPS document .NET” nedir?
.NET içinde bir XPS belgesi oluşturmak, C# veya VB.NET kullanarak XML Paper Specification (XPS) dosyasını programlı olarak üretmek anlamına gelir — sabit‑düzen bir belge formatı. Aspose.Page, düşük‑seviye ayrıntıları soyutlayan akıcı bir API sunar ve metin, şekil ve görüntü gibi içeriklere odaklanmanızı sağlar.

## Neden Aspose.Page ile görüntü eklemelisiniz?
- **Tam kontrol** görüntülerin konumlandırılması, ölçeklendirilmesi ve kırpılması üzerinde.  
- **Harici bağımlılık yok** — kütüphane görüntü çözümlemesini dahili olarak gerçekleştirir.  
- **Çapraz‑platform** desteği Windows ve Linux ortamları için.  
- **Yüksek doğruluk** renderlama, son XPS dosyasında görüntü kalitesini korur.

## Ön Koşullar

Öğreticiye başlamadan önce aşağıdaki ön koşulların karşılandığından emin olun:

1. Aspose.Page for .NET Kütüphanesi: Kütüphaneyi [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/) adresinden indirin ve kurun.

2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.

3. Örnek Görüntü: XPS belgesine eklemek istediğiniz örnek bir görüntü dosyanız (ör. "QL_logo_color.tif") olsun.

## Ad Alanlarını (Namespaces) İçe Aktarın

.NET projenize gerekli ad alanlarını (namespaces) ekleyerek başlayın. Bu ad alanları, Aspose.Page for .NET tarafından sağlanan özellikleri kullanmanız için kritiktir.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page ile XPS Belgesine Görüntü Ekleme

Aşağıda **create XPS document .NET** oluşturmak ve bir görüntü gömmek için gereken adımları adım adım inceleyeceğiz.

### Adım 1: Belge Dizini Ayarla

Belge dizininizin yolunu belirterek başlayın. Bu adım, projenizin dosyaları nereden bulup nereye kaydedeceğini bilmesini sağlar.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Adım 2: XPS Belgesi Oluştur

Aspose.Page for .NET kullanarak yeni bir XPS belgesi oluşturun.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Adım 3: XPS Belgesine Görüntü Ekle

Şimdi görüntüyü XPS belgesine ekleyelim. Bu örnekte "QL_logo_color.tif" adlı örnek bir görüntü kullanacağız.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Adım 4: Oluşturulan XPS Belgesini Kaydet

Eklenen görüntüyle XPS belgesini kaydedin.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Artık Aspose.Page for .NET kullanarak bir XPS belgesine başarıyla görüntü eklediniz!

## Yaygın Sorunlar ve Çözümler

- **File not found error** – `dataDir` değişkeninin doğru klasöre işaret ettiğinden ve görüntü dosya adının tam olarak eşleştiğinden emin olun; Linux'ta büyük/küçük harf duyarlılığına dikkat edin.  
- **Image appears distorted** – `CreateMatrix` ölçekleme faktörlerini veya `RectangleF` parametrelerini ayarlayarak boyut ve en‑boy oranını kontrol edin.  
- **Unsupported image format** – Aspose.Page yaygın raster formatlarını (PNG, JPEG, TIFF) destekler. Desteklenmeyen formatları `CreateImageBrush` kullanmadan önce dönüştürün.

## Sıkça Sorulan Sorular

### S1: Aspose.Page for .NET en son .NET framework sürümleriyle uyumlu mu?

A1: Aspose.Page for .NET, en son sürümler de dahil olmak üzere geniş bir .NET framework sürüm yelpazesiyle uyumlu olacak şekilde tasarlanmıştır. Ayrıntılı bilgi için [documentation](https://reference.aspose.com/page/net/) sayfasına bakın.

### S2: Aspose.Page for .NET hem Windows hem de Linux ortamlarında kullanılabilir mi?

A2: Evet, Aspose.Page for .NET platform‑bağımsızdır ve hem Windows hem de Linux ortamlarında kullanılabilir.

### S3: Aspose.Page for .NET için lisans seçenekleri nelerdir?

A3: Evet, lisans seçeneklerini inceleyebilir ve satın alabilirsiniz. Detaylar için [here](https://purchase.aspose.com/buy) adresini ziyaret edin.

### S4: Aspose.Page for .NET için ücretsiz bir deneme mevcut mu?

A4: Evet, [free trial](https://releases.aspose.com/) sayfasına erişerek Aspose.Page for .NET'i ücretsiz deneyebilirsiniz.

### S5: Aspose.Page for .NET ile ilgili destek almak veya toplulukla etkileşime geçmek için nereden ulaşabilirim?

A5: Topluluk ve destek için [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) sayfasını ziyaret edin.

## Sonuç

Bu öğreticide, Aspose.Page for .NET'i kullanarak XPS belgelerine sorunsuz bir şekilde görüntü eklemeyi inceledik. Bu adım‑adım kılavuz, entegrasyon sürecinizi sorunsuz hâle getirerek .NET geliştirme yeteneklerinizi artırır ve **create XPS document .NET** çözümlerinizde görsel zenginlik sağlar.

---

**Son Güncelleme:** 2026-02-28  
**Test Edilen Versiyon:** Aspose.Page for .NET 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
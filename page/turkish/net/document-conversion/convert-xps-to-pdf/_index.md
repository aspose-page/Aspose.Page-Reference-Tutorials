---
title: Aspose.Page for .NET ile XPS'yi PDF'ye dönüştürün
linktitle: XPS'yi PDF'ye dönüştür
second_title: Aspose.Page .NET API'si
description: Aspose.Page ile XPS'yi zahmetsizce .NET'te PDF'ye dönüştürün. Kitaplığı indirin, belgeleri inceleyin ve ücretsiz deneme sürümünü edinin.
weight: 11
url: /tr/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS'yi PDF'ye dönüştürün

## giriiş

Bu eğitimde, güçlü Aspose.Page for .NET kitaplığını kullanarak XPS (XML Kağıt Belirtimi) belgelerini PDF'ye (Taşınabilir Belge Formatı) dönüştürme sürecini derinlemesine inceleyeceğiz. Aspose.Page for .NET, XPS dosyalarıyla çalışmak için güçlü bir dizi özellik sunarak geliştiricilerin çeşitli özelleştirme seçenekleriyle bunları sorunsuz bir şekilde PDF formatına dönüştürmesine olanak tanır.

## Önkoşullar

Bu dönüşüm yolculuğuna çıkmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Page belgeleri](https://reference.aspose.com/page/net/).

- Geliştirme Ortamı: Visual Studio veya başka bir uyumlu IDE ile bir .NET geliştirme ortamı kurun.

- XPS Belgesi: PDF'ye dönüştürmek istediğiniz XPS belgesini hazırlayın. Bu, belirlenmiş bir dizinde saklanan örnek XPS dosyanız olabilir.

## Ad Alanlarını İçe Aktar

Kodun derinliklerine dalmadan önce, Aspose.Page for .NET işlevlerinin kodumuzda erişilebilir olmasını sağlamak için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Page.XPS;
```

## 1. Adım: Belge Dizinini Başlatın

```csharp
string dataDir = "Your Document Directory";
```

"Belge Dizininiz"i, XPS belgenizi içeren dizinin yolu ile değiştirin.

## 2. Adım: PDF ve XPS Akışlarını Başlatın

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Hem çıktı PDF dosyası hem de giriş XPS dosyası için akışları açın. Uygun dosya yollarının ayarlandığından emin olun.

## 3. Adım: XPS Belgesini Yükleyin

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Aspose.Page for .NET kitaplığını kullanarak XPS belgesini yükleyin.

## 4. Adım: PDF Kaydetme Seçeneklerini Başlatın

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

JPEG kalite düzeyi, görüntü sıkıştırma, metin sıkıştırma ve eklenecek belirli sayfa numaraları gibi parametreler de dahil olmak üzere PDF kaydetme seçeneklerini ayarlayın.

## Adım 5: PDF İşleme Cihazı Oluşturun

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Aspose.Page for .NET kitaplığını kullanarak PDF formatı için bir işleme cihazı oluşturun.

## Adım 6: Belgeyi PDF'ye Kaydetme

```csharp
document.Save(device, options);
```

Belirtilen işleme aygıtını ve seçeneklerini kullanarak XPS belgesini PDF'ye kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak bir XPS belgesini başarıyla PDF'ye dönüştürdünüz. Bu çok yönlü kitaplık, geliştiricilere çeşitli belge formatlarını zahmetsizce kullanmaları için güçlü bir araç seti sağlar.

## SSS'ler

### S1: Aspose.Page for .NET'i kullanarak birden fazla XPS dosyasını tek bir PDF'ye dönüştürebilir miyim?

Cevap1: Evet, birden fazla XPS dosyası arasında geçiş yapabilir ve bunları tek bir PDF'de birleştirmek için aynı adımları uygulayabilirsiniz.

### S2: Aspose.Page for .NET tarafından desteklenen başka çıktı formatları var mı?

C2: Evet, Aspose.Page for .NET TIFF, JPEG, PNG ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler.

### S3: Dönüştürülen PDF belgesinin görünümünü nasıl özelleştirebilirim?

Cevap3: İstediğiniz görünümü elde etmek için görüntü sıkıştırma ve metin sıkıştırma gibi seçenek nesnesi parametrelerinde ince ayar yapabilirsiniz.

### S4: Aspose.Page for .NET'in deneme sürümü mevcut mu?

 C4: Evet, Aspose.Page for .NET'in yeteneklerini aşağıdaki adresten ücretsiz deneme sürümünü edinerek keşfedebilirsiniz.[Burada](https://releases.aspose.com/).

### S5: Aspose.Page for .NET için topluluk desteğini nereden alabilirim?

 A5: ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) Topluluk tartışmaları ve desteği için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

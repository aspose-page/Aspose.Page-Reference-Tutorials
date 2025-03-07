---
title: Aspose.Page ile PostScript'e (PS) Unicode Dizeli Metin Ekleme
linktitle: PostScript'e (PS) Unicode Dizeli Metin Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak PostScript dosyalarına Unicode metin eklemeyi öğrenin. Belge işlemeyi kolaylıkla geliştirin.
weight: 11
url: /tr/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript'e (PS) Unicode Dizeli Metin Ekleme

## giriiş

Belge işleme alanında Aspose.Page for .NET, geliştiricilerin çeşitli belge formatlarını oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplık olarak öne çıkıyor. Güçlü özelliklerinden biri, PostScript (PS) dosyalarına Unicode dizeleri kullanarak metin ekleme yeteneğidir. Bu eğitimde, Aspose.Page ile çalışan geliştiricilere kusursuz bir deneyim sunarak bu görevi gerçekleştirmeye yönelik adım adım bir kılavuzu inceleyeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında çalışma bilgisi.
-  Aspose.Page for .NET kütüphanesi kuruldu. adresinden indirebilirsiniz.[.NET belgeleri için Aspose.Page](https://reference.aspose.com/page/net/).
- Gerekli yapılandırmalarla oluşturulmuş bir geliştirme ortamı.

## Ad Alanlarını İçe Aktar

Aspose.Page for .NET işlevlerini kullanmak için gerekli ad alanlarını C# kodunuzda içe aktarın:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. Adım: Belge Dizinini ve Yazı Tipleri Klasörünü Ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // A4 boyutunda kaydetme seçenekleri oluşturun
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Ek seçenekler buradan ayarlanabilir)
    
    // Yeni 1 sayfalık PS Belgesi oluştur
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Diğer adımlar aşağıda açıklanacaktır)
    
    // Belgeyi kaydet
    document.Save();
}
```

## 3. Adım: Özel Yazı Tipiyle Unicode Metin Ekleme

```csharp
string str = "試してみます.";  // Unicode metin
int fontSize = 48;

// Metni doldurmak için özel yazı tipi kullanma
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Adım 4: Geçerli Sayfayı Kapatın

```csharp
document.ClosePage();
```

## Adım 5: Belgeyi Sonlandırın ve Kaydedin

```csharp
document.Save();
```

## Çözüm

Bu eğitimde, Aspose.Page for .NET kullanarak bir PostScript belgesine Unicode metin ekleme sürecini anlattık. Geliştiriciler, güçlü yeteneklerinden yararlanarak belge işleme iş akışlarını geliştirerek esneklik ve hassasiyet sağlayabilirler.

## SSS'ler

### S1: Aspose.Page for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?

Cevap1: Aspose.Page öncelikli olarak .NET için tasarlanmıştır ancak Java'nın başka sürümleri de mevcuttur.

### S2: Aspose.Page for .NET için geçici lisansı nasıl edinebilirim?

 A2: Ziyaret edin[Geçici Lisans](https://purchase.aspose.com/temporary-license/) Geçici lisans almak için.

### S3: Aspose.Page tartışmaları için bir topluluk forumu var mı?

 A3: Evet, ziyaret edin[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği için.

### S4: Aspose.Page for .NET hangi formatlarla çalışabilir?

Cevap4: Aspose.Page, XPS, PS, EPS, PDF ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

### S5: Eklenen metnin görünümünü özelleştirebilir miyim?

Cevap5: Evet, Aspose.Page'de metnin yazı tipini, boyutunu, rengini ve diğer özelliklerini özelleştirebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

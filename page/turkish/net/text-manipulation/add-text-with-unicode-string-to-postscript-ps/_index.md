---
date: 2026-03-21
description: Aspose.Page for .NET kullanarak Unicode metinli C# PostScript belgesi
  oluşturmayı öğrenin – belge manipülasyonunu geliştirmek için hızlı bir yol.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Unicode metinle C#’ta PostScript belgesi oluşturma – Aspose.Page
url: /tr/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) Belgesine Unicode Dizesi ile Metin Ekleme Aspose.Page ile

## Giriş

Eğer **C# ile bir PostScript belgesi oluşturmanız** ve Unicode karakterler eklemeniz gerekiyorsa, Aspose.Page for .NET bu süreci basitleştirir. Bu öğreticide, bir PS dosyasına Japonca metin (veya herhangi bir Unicode dizesi) eklemeyi, özel bir yazı tipi seçmeyi ve sonucu kaydetmeyi gösteren eksiksiz, uygulamalı bir örnek üzerinden adım adım ilerleyeceğiz. Sonunda, herhangi bir C# projesine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Bu öğreticinin kapsamı nedir?** Aspose.Page kullanarak C# içinde bir PostScript dosyasına Unicode metin ekleme.
- **Hangi kütüphane gereklidir?** Aspose.Page for .NET (en son sürüm).
- **Özel bir yazı tipine ihtiyacım var mı?** İstenen Unicode aralığını destekleyen herhangi bir TrueType/OpenType yazı tipi, ör. *Arial Unicode MS*.
- **Kaç satır kod?** Yaklaşık 30 satır, net adımlara bölünmüş.
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterli; üretim için tam lisans gereklidir.

## “create postscript document c#” nedir?
C# içinde bir PostScript belgesi oluşturmak, PostScript dilinin spesifikasyonlarına uygun bir .ps dosyasını programlı olarak üretmek anlamına gelir. Aspose.Page düşük seviyeli detayları soyutlayarak, metin, grafik ve yazı tipleri gibi içeriğe odaklanmanızı sağlar.

## Unicode metin için neden Aspose.Page kullanmalı?
- **Tam Unicode desteği** – manuel kodlama yapmadan herhangi bir dilden karakterleri render eder.
- **Cihaz bağımsız** – aynı kod PS, EPS ve PDF çıktıları için çalışır.
- **Harici bağımlılık yok** – kütüphane yazı tipi yüklemeyi ve glif eşlemesini dahili olarak yönetir.

## Önkoşullar

- C# ve .NET geliştirme konusunda temel bilgi.
- Aspose.Page for .NET kütüphanesi kurulu. [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) adresinden indirebilirsiniz.
- Kullanmayı planladığınız yazı tiplerini içeren bir klasör (ör. *Arial Unicode MS*).

## Ad Alanlarını İçe Aktar

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: Belge Dizini ve Yazı Tipi Klasörünü Ayarla

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluştur

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Adım 3: Özel Yazı Tipi ile Unicode Metin Ekle

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Adım 4: Mevcut Sayfayı Kapat

```csharp
document.ClosePage();
```

## Adım 5: Belgeyi Tamamla ve Kaydet

```csharp
document.Save();
```

## Yaygın Sorunlar ve Çözümleri

- **Yazı tipi bulunamadı** – `AdditionalFontsFolders` yolunun .ttf/.otf dosyalarını içeren klasöre işaret ettiğinden ve yazı tipi adının tam olarak eşleştiğinden emin olun.
- **Bozuk karakterler** – kaynak dizenizin C# kaynak dosyanızda UTF‑8 olarak kodlandığını doğrulayın (gerekirse `#pragma warning disable 1591` kullanın).
- **Dosya oluşturulmadı** – `dataDir` üzerindeki yazma izinlerini ve akışın doğru şekilde serbest bırakıldığını kontrol edin (`using` bloğu bunu yönetir).

## Sık Sorulan Sorular

**S: Aspose.Page for .NET'i başka programlama dilleriyle kullanabilir miyim?**  
C: Aspose.Page öncelikle .NET için tasarlanmıştır, ancak Java eşdeğerleri mevcuttur.

**S: Aspose.Page for .NET için geçici lisans nasıl alınır?**  
C: Geçici lisans almak için [Temporary License](https://purchase.aspose.com/temporary-license/) adresini ziyaret edin.

**S: Aspose.Page tartışmaları için bir topluluk forumu var mı?**  
C: Evet, topluluk desteği için [Aspose.Page forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Aspose.Page for .NET hangi formatlarla çalışabilir?**  
C: Aspose.Page XPS, PS, EPS, PDF ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

**S: Eklenen metnin görünümünü özelleştirebilir miyim?**  
C: Evet, Aspose.Page içinde metnin yazı tipi, boyutu, rengi ve diğer özelliklerini özelleştirebilirsiniz.

## Sonuç

Bu öğreticide, **C# ile bir PostScript belgesi oluşturmayı** ve Aspose.Page kullanarak Unicode metin eklemeyi gösterdik. Yukarıdaki adımları izleyerek çok dilli metin render'ını herhangi bir .NET uygulamasına hızlıca entegre edebilir, belge oluşturma ve düzenleme üzerinde tam kontrol sahibi olabilirsiniz.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
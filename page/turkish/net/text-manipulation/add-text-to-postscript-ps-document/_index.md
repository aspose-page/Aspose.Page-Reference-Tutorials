---
date: 2026-03-21
description: Aspose.Page for .NET kullanarak PS belgelerine metin doldurmayı ve metin
  eklemeyi öğrenin. Kod örnekleriyle adım adım rehber.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page ile PostScript (PS) Belgelerinde Metni Nasıl Doldurulur
url: /tr/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) Belgelerinde Metin Doldurma (Fill Text) Nasıl Yapılır – Aspose.Page

## Giriş

PostScript (PS) dosyası içinde **metni doldurmak (fill text)** istiyorsanız, Aspose.Page for .NET bu işlemi çok basitleştirir. Rapor, fatura ya da özel grafikler oluşturuyor olun, metin ekleme ve biçimlendirme temel bir gereksinimdir. Bu öğreticide ortamı kurmaktan son PS belgesini kaydetmeye kadar tüm süreci adım adım göstereceğiz; böylece .NET uygulamalarınızda PS dosyalarına güvenle metin ekleyebileceksiniz.

## Hızlı Yanıtlar
- **“Metni doldurmak” ne demektir?** Karakterleri katı bir fırça ile çizer, glifleri doğrudan sayfaya boyar.  
- **Özel yazı tipleri kullanabilir miyim?** Evet—Aspose.Page, `add custom font ps` özelliği sayesinde özel yazı tiplerini destekler.  
- **PS belgesini nasıl kaydederim?** Sayfayı kapattıktan sonra `document.Save()` çağırın; bu dosyayı diske yazar (`save ps document`).  
- **“Metni doldur ve kenarlıkla (stroke) çizmek” destekleniyor mu?** Kesinlikle; hem doldurma hem de dış hat için `FillAndStrokeText` kullanın.  
- **Hangi .NET sürümleri gereklidir?** .NET Framework 4.5+ veya .NET Core/5/6+ çalışma zamanı yeterlidir.

## PS belgesinde “metni doldurmak” (how to fill text) nedir?

Metni doldurmak, karakterleri bir kenarlık olmadan katı bir renk (veya fırça) ile boyamaktır. PostScript’te bu, `fill` operatörüne eşdeğerdir. Aspose.Page, bu işlemi `FillText` ve `FillAndStrokeText` gibi kullanımı kolay metodlarla soyutlar.

## Neden özel yazı tipi ps eklemek için Aspose.Page kullanmalıyım?

- **Tam yazı tipi desteği** – sistem yazı tipleri ve harici TrueType/OpenType yazı tipleri kutudan çıkar çıkmaz çalışır.  
- **Hassas konumlandırma** – X/Y koordinatlarını, boyutu ve stili siz kontrol edersiniz.  
- **Zengin biçimlendirme** – doldurma, kenarlık ve kalemleri birleştirerek “fill and stroke text” gibi efektler oluşturabilirsiniz.  
- **Çapraz platform** – aynı API ile Windows, Linux ve macOS’ta çalışır.

## Ön Koşullar

Başlamadan önce şunların kurulu olduğundan emin olun:

- **Aspose.Page for .NET** – kütüphaneyi [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) adresinden indirin.  
- **Belge Dizini** – kaynak ve çıktı PS dosyalarının bulunacağı makinenizdeki klasör (*Your Document Directory* kod içinde referans verilen).  
- **Yazı Tipi Klasörü** – kullanmayı planladığınız özel yazı tiplerini içeren bir alt klasör.

## Ad Alanlarını (Namespaces) İçe Aktarma

Derleyicinin sınıfları nereden bulacağını bilmesi için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım Adım Kılavuz

### Adım 1: PS Belgesi için Çıktı Akışı Oluşturma  

Oluşturulacak PS dosyasını tutacak bir `FileStream` açın, `PsSaveOptions`’ı özel yazı tipleri klasörüne yönlendirin ve bir `PsDocument` örneği oluşturun.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **İpucu:** `using` bloğunu tutarak akışın otomatik olarak kapanmasını sağlayın; bu aynı zamanda PS dosyasını (`save ps document`) sonlandırır.

### Adım 2: Sistem Yazı Tipi ile Metni Doldurma  

Yerleşik *Times New Roman* yazı tipini kullanarak temel **metni doldurma (how to fill text)** işlemini gösteriyoruz.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Adım 3: Özel Yazı Tipi ile Metni Doldurma  

Belirli bir görünüm istiyorsanız, `ExternalFontCache.FetchDrFont` ile yazı tipleri klasöründen özel bir yazı tipi yükleyin. Bu, **add custom font ps** gereksinimini karşılar.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Adım 4: Sistem Yazı Tipi ile Metni Kenarlıkla (Stroke) Çizme  

Kenarlık, glifin konturunu çizer. Bunu bir doldurma ile birleştirerek “fill and stroke” etkisi elde edebilirsiniz.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Neden önemli?** `FillAndStrokeText` çağrısı, tek adımda **fill and stroke text** yapmanızı gösterir ve tipografik kontrolünüzü zenginleştirir.

### Adım 5: Özel Yazı Tipi ile Metni Kenarlıkla (Stroke) Çizme  

Aynı kenarlık tekniği, yüklediğiniz herhangi bir özel yazı tipiyle de çalışır.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Adım 6: Sayfayı Kapat ve Belgeyi Kaydet  

İşlemi tamamlamak çok basit: geçerli sayfayı kapatın ve `Save()` çağırarak PS dosyasını diske yazın.

```csharp
document.ClosePage();
document.Save();
}
```

> **Sonuç:** *Your Document Directory* içinde `AddText_outPS.ps` dosyasını bulacaksınız; bu dosya sistem ve özel yazı tipleriyle doldurulmuş ve kenarlıklı metinleri içerir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Çözüm |
|-------|----------|
| **Özel yazı tipi bulunamadı** | `AdditionalFontsFolders` ile işaretlenen klasörde yazı tipi dosyasının (.ttf/.otf) mevcut olduğunu doğrulayın. |
| **Metin yanlış konumda görünüyor** | `FillText`/`OutlineText` metodlarına verilen X/Y koordinatlarını ayarlayın. PostScript birimleri puandır (1/72 inç). |
| **Renkler farklı görünüyor** | Doğru `Color` değerlerine sahip `SolidBrush` veya `Pen` kullandığınızdan emin olun. |
| **Belge kaydedilmiyor** | `using` bloğunun istisna atmadan tamamlandığını ve uygulamanın hedef klasöre yazma izni olduğunu kontrol edin. |

## Sık Sorulan Sorular

**S: Aspose.Page’i diğer .NET kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Page diğer .NET bileşenleriyle sorunsuz entegre olur; aynı çözüm içinde PDF, görüntü veya grafik kütüphanelerini birleştirebilirsiniz.

**S: Bu süreçte özel yazı tipleri zorunlu mu?**  
C: Sistem yazı tipleri de çalışır, ancak özel yazı tipleri tam tasarım özgürlüğü sağlar ve marka‑özel tipografi gerektiğinde faydalıdır.

**S: Aspose.Page büyük ölçekli belge işleme için uygun mu?**  
C: Kesinlikle. Kütüphane yüksek verimlilik senaryoları için optimize edilmiştir ve binlerce PS dosyasını verimli bir şekilde işleyebilir.

**S: PS belgesindeki metnin konumunu değiştirebilir miyim?**  
C: Tabii—`FillText` veya `OutlineText` çağrılarındaki sayısal X/Y değerlerini değiştirmeniz yeterlidir.

**S: Aspose.Page‑ile ilgili sorular için nereden destek alabilirim?**  
C: Topluluk ve uzman yardımı için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-21  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose
---
date: 2026-06-30
description: Aspose.Page for .NET kullanarak postscript belge .NET oluşturmayı ve
  dikdörtgen eklemeyi öğrenin. Adım adım rehber ve code samples.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: PostScript (PS) İçin Dikdörtgen Ekle
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript Belgesi .NET Oluşturma – Aspose.Page ile Dikdörtgen Ekle
url: /tr/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile PostScript (PS) Belgesine Dikdörtgen Ekle

## Giriş

Aspose.Page for .NET, PostScript, EPS ve XPS dosyalarını programlı olarak oluşturmanıza ve manipüle etmenize olanak sağlayan bir kütüphanedir. **create postscript document .net** oluşturmak istiyorsanız, bu öğretici Aspose.Page kullanarak bir PostScript belgesine dikdörtgen eklemeyi adım adım gösterir ve daha zengin grafik oluşturma için sağlam bir temel sağlar.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET.  
- **Sıfırdan bir PostScript belgesi oluşturabilir miyim?** Evet – API, PS dosyalarını programlı olarak oluşturmanıza olanak tanır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme test için çalışır; üretim için lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel şekiller için genellikle 10 dakikadan az.

## postscript belgesi .net oluşturma nedir?
.NET'te bir PostScript belgesi oluşturmak, Aspose.Page API'sini kullanarak sayfa içeriğini—metin, grafik veya şekiller—tanımlayan bir `.ps` dosyasını programlı olarak üretmek anlamına gelir. Bu yaklaşım, sunucu tarafı grafik üretimi, otomatik rapor oluşturma veya çıktı formatı üzerinde hassas kontrol gerektiği her senaryo için idealdir.

## Aspose.Page for .NET neden kullanılmalı?
Aspose.Page, **30+ grafik ilkel** destekler ve belgeyi belleğe tamamen yüklemeden **500 MB**'a kadar dosyalar oluşturabilir, Windows, Linux ve macOS'ta yüksek performanslı render sağlar. Şekiller, renkler ve çizgiler üzerinde tam kontrol sunar ve düşük seviyeli PostScript kodu yazma ihtiyacını ortadan kaldırır.

- **Grafikler üzerinde tam kontrol** – düşük seviyeli PS sözdizimiyle uğraşmadan şekiller çizin, renkleri ayarlayın ve çizgileri uygulayın.  
- **Çapraz platform** – Windows, Linux ve macOS çalışma zamanlarında çalışır.  
- **Harici bağımlılık yok** – kütüphane tüm PS üretimini dahili olarak yönetir.  
- **Zengin dokümantasyon ve örnekler** – hızlıca başlayabilirsiniz.

## Önkoşullar

- **Aspose.Page for .NET Kütüphanesi** – [buradan](https://releases.aspose.com/page/net/) indirip kurun.  
- **Geliştirme Ortamı** – Visual Studio, VS Code veya herhangi bir .NET uyumlu IDE.

## Ad Alanlarını İçe Aktarma

`Aspose.Page` ad alanı, `Document`, `Page`, `SolidBrush` ve `Pen` gibi ihtiyaç duyacağınız temel sınıfları sunar. Kodlamaya başlamadan önce içe aktarın.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi örneği net, numaralı adımlara bölelim.

## Adım 1: Belge Dizinini Ayarlayın

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini, oluşturulan PS dosyasının kaydedileceği klasörle değiştirin.

## Adım 2: PostScript Belgesi için Çıktı Akışı Oluşturun

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Bu akış **AddRectangle_outPS.ps** dosyasına işaret eder. Gerektiği gibi dosyanın adını değiştirebilir veya konumunu değiştirebilirsiniz.

## Adım 3: Kaydetme Seçeneklerini Ayarlayın ve PS Belgesini Oluşturun

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Burada Aspose.Page'e A4 sayfa boyutu kullanmasını ve tek sayfalı bir belge oluşturmasını söylüyoruz.

## Adım 4: Dolu Bir Dikdörtgen Ekleyin

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

(250, 100) konumunda, genişliği 150 ve yüksekliği 100 olan bir dikdörtgen tanımlıyoruz, turuncu bir fırça ayarlıyor ve şekli dolduruyoruz.

## Adım 5: Çerçeveli Bir Dikdörtgen Ekleyin

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Sayfanın daha alt kısmında ikinci bir dikdörtgen oluşturulur, bu sefer kırmızı 3‑nokta kalınlığında bir çizgiyle.

## Adım 6: Sayfayı Kapatın ve Belgeyi Kaydedin

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Sayfayı kapatmak çizimi sonlandırır ve `Save()` PS dosyasını diske yazar.

## postscript belgesi .net nasıl oluşturulur?
`Document`, Aspose.Page'de bir PostScript dosyasını temsil eden ana sınıftır. `SaveOptions`, belge için sayfa boyutu ve çıktı formatı gibi ayarları belirler. `Document` nesnesini yükleyin, A4 sayfa için `SaveOptions`'ı yapılandırın, şekillerinizi `SolidBrush` veya `Pen` ile çizin, ardından `document.Save()`'ı çağırın — tüm iş akışı sadece birkaç kod satırı gerektirir ve desteklenen herhangi bir .NET çalışma zamanında çalışır. Bu desen, ham PS sözdizimine dokunmadan tam uyumlu PostScript dosyaları üretmenizi sağlar.

## Postscript dosyası nasıl oluşturulur
Çıktı formatını PostScript (`SaveFormat.PS`) olarak belirtmek için Aspose.Page'in `SaveOptions` sınıfını kullanın. Kütüphane içeriği doğrudan bir dosyaya veya bellek akışına gönderir, böylece aşırı bellek tüketimi olmadan büyük belgeler verimli bir şekilde oluşturabilirsiniz.

## Yaygın Sorunlar ve İpuçları

- **Yanlış dosya yolu** – `dataDir`'in bir yol ayırıcı (`\\` veya `/`) ile bittiğinden emin olun veya `Path.Combine` kullanın.  
- **Lisans eksik** – Üretim ortamında, belgeyi oluşturmadan önce Aspose lisansınızı uygulayarak değerlendirme filigranlarından kaçının.  
- **Renk görünürlüğü** – Dikdörtgen boş görünüyorsa, fırça veya kalem renklerinin sayfa arka planına zıt olduğundan emin olun.

## Sık Sorulan Sorular

**S:** Dikdörtgenlerin renklerini özelleştirebilir miyim?  
**C:** Kesinlikle. `SolidBrush` ve `Pen` yapıcılarındaki `Color.Orange` veya `Color.Red` değerlerini istediğiniz herhangi bir `System.Drawing.Color` ile değiştirin.

**S:** Aspose.Page diğer belge formatlarıyla uyumlu mu?  
**C:** Evet. PostScript'in yanı sıra Aspose.Page XPS ve EPS üretimini de destekler.

**S:** Aynı belgeye nasıl metin ekleyebilirim?  
**C:** İstenilen koordinatlara metin yerleştirmek için `TextFragment` sınıfını kullanın, ardından `document.Draw(textFragment)`'ı çağırın.

**S:** Ek örnekler ve tam API referansını nerede bulabilirim?  
**C:** Dokümantasyonu [buradan](https://reference.aspose.com/page/net/) inceleyin ve topluluğa [Aspose.Page forumu](https://forum.aspose.com/c/page/39) üzerinden katılın.

**S:** Aspose.Page'i satın almadan deneyebilir miyim?  
**C:** Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz. Uzun vadeli değerlendirme için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) düşünün.

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Page for .NET ile PostScript Belgesi Oluşturma](/page/net/document-creation/create-postscript-document/)
- [Aspose.Page ile PostScript (PS) Belgesine Resim Ekleme](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Aspose.Page ile PostScript (PS) Belgesine Metin Ekleme](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
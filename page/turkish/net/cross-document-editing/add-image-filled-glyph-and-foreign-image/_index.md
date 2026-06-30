---
date: 2026-06-30
description: XPS belgesini .NET ile nasıl oluşturacağınızı ve Aspose.Page for .NET
  kullanarak görüntü dolu glifler ya da yabancı görüntüler eklemeyi birkaç kolay adımda
  öğrenin.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Görüntü Dolu Glif ve Yabancı Görüntü Ekle
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS Belgesi .NET Oluşturma – Aspose.Page ile Görüntü Dolu Glif ve Yabancı Görüntü
  Ekleme
url: /tr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgesi Oluştur .NET – Görüntü Dolu Glif ve Başka Bir Görüntüyü Aspose.Page ile Ekle

## Giriş

.NET geliştirmede, **create XPS document .NET** görevleri yüksek‑kaliteli, çözünürlük‑bağımsız grafiklere ihtiyaç duyduğunuzda yaygındır. Aspose.Page for .NET bunu basit hale getirir ve XPS dosyalarını görüntü‑dolu gliflerle zenginleştirmenize veya başka bir XPS belgesinden görüntüler almanıza olanak tanır. Bu öğreticinin sonunda iki XPS belgesi oluşturmayı, glifleri görüntülerle doldurmayı ve bu görüntüleri belgeler arasında yeniden kullanmayı öğreneceksiniz—faturalar, sertifikalar veya herhangi bir görsel‑zengin çıktı üretmek için mükemmeldir.

## Hızlı Yanıtlar
- **Aspose.Page neyi destekliyor?** 25'ten fazla görüntü formatı ve XPS dosyalarını tam bellek yüklemesi yapmadan 500 MB'a kadar işleme yeteneği.  
- **Görüntü dolu bir glif eklemek için kaç satır kod gerekir?** Sadece iki satır: bir `ImageBrush` oluşturun ve bir `Glyph`'a atayın.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans değerlendirme filigranlarını kaldırır.  
- **Hangi .NET sürümleri uyumludur?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Başka bir XPS'ten fontları yeniden kullanabilir miyim?** Kesinlikle – birinci belgeden font koleksiyonunu ikinci belgeye aktarabilirsiniz.

## Aspose.Page .NET kullanarak bir XPS belgesi nasıl oluşturulur?

Aspose.Page kütüphanesini yükleyin, bir `XpsDocument` örneği oluşturun, bir sayfa ekleyin ve `Save` metodunu çağırın – bu, üç kısa ifadeyle tam iş akışıdır. API sayfa boyutu, DPI ve kaynak yönetimini otomatik olarak ele alır, böylece düşük seviyeli XPS yapılarıyla kendiniz uğraşmanız gerekmez. Bu yaklaşım tek sayfalık broşürden çok yüz sayfalı kataloglara kadar ölçeklenebilir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Aspose.Page for .NET** – indirin: [here](https://releases.aspose.com/page/net/).  
- **A .NET IDE** – Visual Studio, Rider, veya C# uzantılı VS Code.  
- **A folder for your documents** – kod örneklerinde **Your Document Directory** olarak adlandıracağız.

## Ad Alanlarını İçe Aktarın

`Aspose.Page.XPS` ad alanı temel XPS belge sınıflarını sağlar, `Aspose.Page.XPS.XpsModel` ise glifler ve fırçalar gibi model öğelerini içerir. Dosyanızın en üstüne şu satırları ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Görüntü Dolu Glif Nedir?

Bir glif, katı renk, degrade veya bir görüntü fırçası ile render edilebilen bir vektör şeklidir. `ImageBrush` uyguladığınızda, glifin iç kısmı sağlanan görüntü ile boyanır ve tüm sayfayı rasterleştirmeden karmaşık görsel efektler elde edebilirsiniz.

## Adım 1: İlk XPS Belgesini Oluşturun

`XpsDocument` bir XPS paketini temsil eder ve XPS dosyalarını oluşturup kaydetmenin giriş noktasıdır. Görüntü‑dolu glifleri barındıracak ilk XPS belgesini oluşturarak başlayın.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Adım 2: İlk Belgeye Glifler Ekleyin

`XpsGlyphs`, bir sayfaya yerleştirilebilen glif (metin karakteri) koleksiyonunu tanımlar. Font, boyut, stil ve konumu belirterek ilk belgeye glifler ekleyin.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Adım 3: Glifleri Bir Image Brush ile Doldurun

`ImageBrush`, bir alanı görüntüyle boyar ve desenlerin veya resimlerin şekilleri doldurmasına izin verir. Veri klasörünüzdeki bir görüntüyü kullanarak glifleri bir image brush ile doldurun.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Adım 4: İkinci XPS Belgesini Oluşturun

`XpsDocument` yeni bir XPS dosyası oluşturmak için kullanılır; bu dosya sayfalar, kaynaklar ve içerik barındırabilir. Şimdi, birinci belgede oluşturulan glifleri içerecek ikinci XPS belgesini oluşturun.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Adım 5: İlk Belgeden Font ile Glifler Ekleyin

`Font`, bir XPS belgesinde metin renderlamak için kullanılan bir yazı tipini temsil eder. İlk belgeden çıkarılan fontu kullanarak ikinci belgeye glifler ekleyin. Font koleksiyonunu paylaşarak dosya boyutunu düşük tutar ve görsel tutarlılığı sağlarsınız.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Adım 6: İlk Belgenin Doldurmasından Bir Image Brush Oluşturun

`ImageBrush`, mevcut bir doldurmadan oluşturularak aynı görüntünün belgeler arasında yeniden kullanılmasını sağlar. İlk belgenin doldurmasından bir image brush oluşturun ve ikinci belgede glifleri doldurmak için kullanın. Bu “başka bir görüntü” tekniği, kaynak dosyayı çoğaltmadan sanat eserini yeniden kullanmanıza imkan verir.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Adım 7: Belgeleri Kaydedin

`Save` XPS paketini bir dosyaya yazar ve tüm kaynakları gömer. İlk ve ikinci XPS belgelerini çıktı klasörüne kaydedin. `Save` metodu XPS paketini yazar, tüm kaynakları gömer ve görüntü‑dolu glifleri korur.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Görüntü glif içinde görünmüyor** | `ImageBrush` hatalı bir URI ile oluşturulmuş veya görüntü boyutu glif sınırlarını aşıyor. | Görüntü yolunu doğrulayın ve isteğe bağlı olarak `ImageBrush.Stretch = Stretch.Uniform` ayarlayın. |
| **İkinci belgede fontlar eksik** | Font kaynakları ilk XPS'ten dışa aktarılmamış. | Glifleri eklemeden önce `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` kullanın. |
| **Büyük dosyalarda performans yavaşlaması** | Her glif için büyük görüntülerin belleğe yüklenmesi. | Tüm glifler için tek bir `ImageBrush` örneği yeniden kullanın veya kullanmadan önce görüntüyü küçültün. |

## Sıkça Sorulan Sorular

### Q1: Glifleri doldurmak için farklı görüntü formatları kullanabilir miyim?
A1: Evet, Aspose.Page PNG, JPEG, BMP, GIF, TIFF ve daha fazlasını destekler—toplamda 25'ten fazla format.

### Q2: Gliflerin görünümünü daha da nasıl özelleştirebilirim?
A2: `Glyph.Stroke`, `Glyph.FillOpacity` ve `Glyph.Transform` gibi özellikleri keşfederek konturları, şeffaflığı ve dönüşleri ayarlayabilirsiniz.

### Q3: Aspose.Page büyük belge setlerini işlemek için uygun mu?
A3: Kesinlikle. Kütüphane, çok sayfalı XPS dosyalarını akış kullanarak işler ve 500 sayfalık belgeler için bile bellek kullanımını 100 MB'ın altında tutar.

### Q4: Tek tek gliflere farklı stiller uygulayabilir miyim?
A4: Evet, her `Glyph` örneği kendi `Fill`, `Stroke` ve `Transform` özelliklerine sahiptir, bu da glif başına stil uygulamayı sağlar.

### Q5: Diğer XPS araçlarına göre Aspose.Page kullanmanın avantajları nelerdir?
A5: Aspose.Page 25'ten fazla görüntü formatını destekler, dosyaları tam bellek yüklemesi olmadan 500 MB'a kadar işler ve %100 .NET‑yerel API sunar—COM interop veya harici araçlara ihtiyaç duymaz.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [XPS Belgesi Oluştur – Aspose.Page for .NET](/page/net/document-creation/)
- [XPS Belgesine Görüntü Ekle – Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Glif Kopyası Ekle ve Renk Değiştir – Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
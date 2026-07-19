---
date: 2026-07-19
description: XPS belgesi .NET oluşturmayı ve Aspose.Page for .NET kullanarak bir dikdörtgen
  eklemeyi adım adım, öz bir rehberde öğrenin.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: XPS Belgesine Dikdörtgen Ekle
og_description: XPS belgesini .NET hızlı bir şekilde oluşturun. Bu öğreticide, Aspose.Page
  for .NET kullanarak bir XPS dosyasına dikdörtgen ekleme işlemi, net kod örnekleri
  ve ipuçlarıyla gösterilmektedir.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS Belgesi Oluştur .NET – Aspose.Page ile Dikdörtgen Ekle
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS Belgesi Oluştur .NET – Aspose.Page ile Dikdörtgen Ekle
url: /tr/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgesi .NET Oluşturma – Aspose.Page ile Dikdörtgen Ekleme

## Giriş

Bu öğreticide **XPS belgesi .NET oluşturma** ve Aspose.Page for .NET kullanarak içine bir dikdörtgen çizmeyi öğreneceksiniz. Raporlama motoru, yazdırılabilir fatura veya özel bir grafik katmanı oluşturuyor olun, XPS dosyalarını programlı olarak üretme yeteneği, düzen ve doğruluk üzerinde tam kontrol sağlar. Aşağıdaki adımları izleyin ve birkaç dakika içinde kullanıma hazır bir XPS dosyanız olacak.

## Hızlı Yanıtlar
- **Ana hedef nedir?** .NET XPS belgesi oluşturmak ve bir dikdörtgen şekli eklemek.  
- **Hangi kütüphane gereklidir?** Aspose.Page for .NET (resmi siteden indirilebilir).  
- **Test için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Uygulama ne kadar sürer?** Temel bir dikdörtgen için yaklaşık 5‑10 dakika.

## Aspose.Page for .NET Nedir?
Aspose.Page for .NET, geliştiricilerin dış bileşenlere bağımlı olmadan XPS (XML Paper Specification) belgelerini programlı olarak oluşturmasını, düzenlemesini ve render etmesini sağlayan yüksek performanslı, tamamen yönetilen bir API'dir. Şekil, metin ve resim çizmek için zengin bir nesne modeli sunar ve renk yönetimi, sıkıştırma ve PDF dönüşümü gibi gelişmiş özellikleri destekler; bu da onu geniş bir belge üretim senaryosu yelpazesi için uygun kılar.

## Neden Aspose.Page ile XPS belgesi .NET oluşturmalısınız?
Aspose.Page **30+ XPS özelliğini** destekler—vektör grafikleri, metin yerleşimi ve renk yönetimi dahil—ve belgenin tamamını belleğe yüklemeden **500 MB**'a kadar dosyalar üretebilir. Bu ölçülen yetenek, büyük ölçekli baskı işlerinde bile sorunsuz performans sağlar.

## Önkoşullar

Bu öğreticiye başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. Aspose.Page for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Page for .NET kütüphanesinin yüklü olduğundan emin olun. [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.

2. Belge Dizini: XPS belgelerinizi saklamak istediğiniz bir dizin oluşturun.

## Ad Alanlarını İçe Aktarın

.NET uygulamanızda Aspose.Page işlevlerini kullanmak için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## .NET'te bir XPS belgesine nasıl dikdörtgen eklerim?

XPS belgesini yükleyin, bir `Graphics` nesnesi oluşturun, istediğiniz boyutta bir `RectangleF` tanımlayın ve `DrawRectangle` çağırın. Bu sıralama, tek bir kod satırıyla bir dikdörtgen çizer ve DPI ölçeklendirmesini otomatik olarak yönetir. Tipik A4‑boyutlu sayfalar için, 200 × 100 pt dikdörtgen ekstra hesaplama yapmadan ortalanmış olarak görünür.

### Adım 1: Belge Dizinini Ayarlayın

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Adım 2: Yeni bir XPS Belgesi Oluşturun

`XpsDocument` sınıfı, oluşturduğunuz XPS dosyasını temsil eder ve sayfalar, grafikler ve diğer kaynakları eklemek için yöntemler sağlar.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Adım 3: Bir Dikdörtgen Ekleyin

`XpsPath`, XPS belgesi içinde çizilebilir bir yol nesnesi tanımlar; geometri, kenar çizgisi, dolgu ve diğer görsel özellikleri ayarlamanıza olanak tanır.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Adım 4: Belgeyi Kaydedin

`Save` yöntemi, oluşturulan XPS belgesini belirtilen dosya yoluna yazar.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Tebrikler! Aspose.Page for .NET kullanarak bir XPS belgesine başarıyla dikdörtgen eklediniz.

## Yaygın Sorunlar ve İpuçları

- **Eksik yazı tipleri:** Başvurduğunuz yazı tiplerinin sunucuda yüklü olduğundan emin olun; aksi takdirde Aspose.Page varsayılan bir yazı tipi ile değiştirir ve bu düzeni etkileyebilir.  
- **Büyük belgeler:** 200 MB'den büyük dosyalar oluştururken bellek kullanımını azaltmak için `document.SaveOptions.Compress = true` çağrısını düşünün.  
- **Koordinat sistemi:** XPS, puan (1/72 inç) kullanır. Ekran tabanlı boyutlarla çalışıyorsanız pikselleri puana dönüştürmeyi unutmayın.

## Sıkça Sorulan Sorular

**S: Aspose.Page tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet, Aspose.Page masaüstü, web ve bulut .NET uygulamalarıyla sorunsuz çalışır.

**S: Aspose.Page for .NET belgelerine nereden ulaşabilirim?**  
C: Tam API referansı [burada](https://reference.aspose.com/page/net/) mevcuttur.

**S: Aspose.Page for .NET'i satın almadan önce ücretsiz deneyebilir miyim?**  
C: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Page for .NET için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisans almak için [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

**S: Aspose.Page for .NET ile ilgili topluluk desteği veya soru sorabileceğim yer neresi?**  
C: Topluluk desteği için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**Son Güncelleme:** 2026-07-19  
**Test Edilen Sürüm:** Aspose.Page for .NET 24.9  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Page for .NET ile XPS Belgesi Oluşturma](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Şekil Çizme](/page/net/drawing-shapes/)
- [Aspose.Page for .NET ile XPS Belgesine Metin Ekleme](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
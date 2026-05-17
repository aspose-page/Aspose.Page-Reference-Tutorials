---
date: 2026-02-25
description: Aspose.Page for .NET kullanarak PostScript belgelerini lineer degrade
  dikdörtgen ekleyerek geliştirin. Degrade dolgu metni ve metin konturu degrade hakkında
  bilgi edinmek için adım adım rehberimizi izleyin.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page ile PostScript (PS)'ye Lineer Gradyan Dikdörtgen Ekle
url: /tr/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 formatting exactly.

Let's write final.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript (PS) Belgesine Lineer Gradyan Dikdörtgen Ekleme

## Giriş

Bu kapsamlı öğreticiye hoş geldiniz. Aspose.Page for .NET kullanarak PostScript (PS) belgelerine **lineer gradyan dikdörtgen** eklemeyi öğreneceksiniz. Aspose.Page, çeşitli formatlarda belge oluşturmanıza, değiştirmenize ve render etmenize olanak tanıyan güçlü bir kütüphanedir ve bugün PS dosyalarınıza göz alıcı gradyanlar getirmeye odaklanacağız.

### Hızlı Yanıtlar
- **Lineer gradyan dikdörtgen ne yapar?** Bir kenardan diğerine düzgün bir renk geçişiyle dikdörtgen bir alanı doldurur.  
- **Hangi API gradyan dolgu metnini yönetir?** `LinearGradientBrush` ile `SetPaint` ve `FillAndStrokeText`.  
- **Metni gradyan ile kenarlayabilir miyim?** Evet—`SetStroke` ile bir gradyan fırçası kullanın ve `OutlineText` çağırın.  
- **Üretim için lisansa ihtiyacım var mı?** Değerlendirme dışı kullanım için ticari bir Aspose.Page lisansı gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Önkoşullar

İlerlemeye başlamadan önce şunların olduğundan emin olun:

- Aspose.Page for .NET Kütüphanesi: Kütüphanenin projenizde referans edildiğinden emin olun. İndirmek için [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) adresini ziyaret edebilirsiniz.  
- Belge Dizini: Oluşturulan PS dosyasının kaydedileceği bir klasör oluşturun ve kodda **“Your Document Directory”** ifadesini bu yol ile değiştirin.

## Ad Alanlarını İçe Aktarma

Başlamak için çizim ve PS‑özel sınıflarına erişmenizi sağlayacak ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Lineer Gradyan Dikdörtgen Nedir?

Bir **lineer gradyan dikdörtgen**, iç kısmı lineer bir gradyanla boyanmış dikdörtgen bir şekildir—renkler, genellikle soldan sağa (yatay) veya üstten alta (dikey) doğru düz bir çizgi boyunca sorunsuz bir şekilde geçiş yapar. Aspose.Page’de bunu, dikdörtgeni tanımlayan bir `GraphicsPath` ile renk geçişini tanımlayan bir `LinearGradientBrush` kombinasyonu ile elde edersiniz.

## Neden Gradyan Dolgu Metni ve Kenarlık Metni Gradyanı Kullanmalı?

- **Görsel Çekicilik:** Gradyan dolgu metin, raporlar, faturalar veya tanıtım materyallerine derinlik ve modern bir stil kazandırır.  
- **Marka Tutarlılığı:** Kurumsal renkleri kesin ARGB değerleriyle eşleştirin.  
- **Çok Yönlülük:** Aynı fırça, şekil dolguları, metin dolguları ve kenarlık gradyanları için yeniden kullanılabilir, kod tekrarını azaltır.

## Adım 1: Belgeyi Kurma

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 2: Gradyan Dikdörtgen ve Renkleri Tanımlama

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Adım 3: Fırça İçin Dönüşüm Ayarlama

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Adım 4: Boyayı Ayarla ve Dikdörtgeni Doldur

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Gradyan Dolgu Metni Nasıl Uygulanır

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Kenarlık Metni Gradyanı Kullanma

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Adım 7: Mevcut Sayfayı Kapat ve Belgeyi Kaydet

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Tebrikler! Bir PostScript belgesine **lineer gradyan dikdörtgen** başarıyla eklediniz ve aynı fırçayı **gradyan dolgu metni** ve **kenarlık metni gradyanı** için kullandınız.

## Yaygın Kullanım Senaryoları ve İpuçları

- **Rapor Başlıkları:** Bölüm başlıklarını vurgulamak için büyük metin bloklarını gradyanlarla doldurun.  
- **Marka Logoları:** Tutarlı bir marka kimliği için logo şekillerini gradyan dolgu şekilleriyle yeniden oluşturun.  
- **Pro İpucu:** Renklerin şekiller ve metinler arasında mükemmel hizalanmasını sağlamak için aynı `LinearGradientBrush` örneğini birden fazla çizim çağrısında yeniden kullanın.

## Sıkça Sorulan Sorular

### S1: Dikdörtgen dışındaki diğer şekillere gradyan uygulayabilir miyim?
**A:** Evet, `GraphicsPath` ile tanımlanan herhangi bir şekle gradyan uygulayabilirsiniz. `document.Fill(path)` çağırmadan önce daireler, çokgenler veya özel yollar ekleyin.

### S2: Gradyan renklerini nasıl değiştirebilirim?
**A:** `LinearGradientBrush` oluştururken `Color.FromArgb` değerlerini değiştirin. İlk renk başlangıç, ikinci renk ise gradyanın sonudur.

### S3: Aspose.Page farklı belge formatlarıyla uyumlu mu?
**A:** Kesinlikle. Aspose.Page XPS, PS, PDF ve çeşitli diğer vektör formatlarını destekler. Tam liste için resmi dokümantasyona bakın.

### S4: Aspose.Page'i ticari projelerde kullanabilir miyim?
**A:** Evet, ticari lisanslama mevcuttur. Detaylar için satın alma sayfasına bakın: [here](https://purchase.aspose.com/buy).

### S5: Topluluk desteğini nereden bulabilirim?
**A:** Aspose.Page topluluk forumuna katılın: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-05
description: Aspose.Page for .NET kullanarak PostScript'te kırpma yolu eklemeyi öğrenin
  – fırça ayarlama ve kesikli dikdörtgen çizme teknikleriyle adım adım rehber.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile PS'ye Kırpma Yolu Ekle
url: /tr/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile PS'ye Kırpma Yolu Ekleme

## Giriş

Bu kapsamlı öğreticide, Aspose.Page for .NET kullanarak bir PostScript (PS) belgesine **kırpma yolu eklemeyi** keşfedeceksiniz. Her adımı adım adım gösterecek, **boyama fırçasını nasıl ayarlayacağınızı** ve kırpılmış içeriğin etrafına **kesikli dikdörtgen nasıl çizeceğinizi** anlatacağız. Sonunda, şekle göre kırpma gösteren tam işlevsel bir PS dosyanız olacak ve grafikleriniz daha dinamik ve profesyonel görünecek.

## Hızlı Yanıtlar
- **“kırpma yolu eklemek” ne yapar?** Çizim işlemlerini tanımlı bir şekle sınırlar, o şeklin dışındaki her şeyi gizler.  
- **.NET’te kırpma işlemini hangi kütüphane yönetir?** Aspose.Page for .NET, PS/EPS manipülasyonu için zengin bir API sunar.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Fırça rengini değiştirebilir miyim?** Evet, istediğiniz `SolidBrush` veya degrade ile `SetPaint` kullanabilirsiniz.  
- **Kesikli bir dikdörtgen çizmek mümkün mü?** Kesinlikle – `DashStyle.Dash` ile bir `Pen` oluşturup `Draw` metodunu kullanın.  

## PostScript’te kırpma yolu nedir?
Kırpma yolu, sonraki çizim komutlarının görünür bölgesini tanımlar. Yolun dışına çizilen her şey yok sayılır; bu sayede orijinal içeriği değiştirmeden karmaşık maskeli grafikler oluşturabilirsiniz.

## Aspose.Page’i kırpma için neden kullanmalısınız?
- **Harici bağımlılık yok** – saf .NET kütüphanesi.  
- **Grafik durumunun tam kontrolü** (save/restore, translate, rotate).  
- **Zengin çizim primitive’leri**; `SetPaint`, `Clip` ve özelleştirilebilir kalem ve fırçalarla `Draw`.  

## Önkoşullar

- C# programlama temelleri.  
- Aspose.Page for .NET kütüphanesi yüklü – [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- Visual Studio veya tercih ettiğiniz .NET IDE.  

## Ad Alanlarını İçe Aktarma

İlk olarak, grafik manipülasyonu için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi örneği net, numaralı adımlara ayıralım.

### Adım 1: Belge Dizinini Ayarla

Kaynak ve çıktı dosyalarının bulunacağı klasörü tanımlayın.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Adım 2: PostScript Belgesi İçin Çıktı Akışı Oluştur

Oluşturulacak PS dosyasını tutacak yazılabilir bir akış yaratın.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Adım 3: Kaydetme Seçeneklerini Oluştur

`PsSaveOptions` nesnesini varsayılan ayarlarla örnekleyin. İsterseniz daha sonra özelleştirebilirsiniz.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Adım 4: Yeni 1‑Sayfalı PS Belgesi Oluştur

PS dosyanızı temsil edecek `PsDocument` nesnesini başlatın.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Adım 5: Dikdörtgenden Grafik Yolu Oluştur

Daha sonra kırpılacak temel şekil olarak bir dikdörtgen kullanacağız.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Adım 6: Şekle Göre Kırpma

Burada bir daire kullanarak **kırpma yolu ekliyor**, **boyama fırçasını** maviye **ayar**lıyor ve kırpılmış bölge içinde dikdörtgeni dolduruyoruz.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Adım 7: Üst Düzey Grafik Durumunu Değiştir ve Kesikli Dikdörtgen Çiz

Önceki durumu geri yükledikten sonra grafik imlecini tekrar hareket ettiriyor, **kesikli bir dikdörtgen çiziyor** ve mavi bir kontur uyguluyoruz.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Adım 8: Belgeyi Kapat ve Kaydet

Sayfayı sonlandırın ve PS dosyasını diske yazın.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Artık **kırpma yolu eklediniz**, özel bir boyama fırçası ayarladınız ve Aspose.Page for .NET ile grafiklerinizin etrafına kesikli bir dikdörtgen çizmeyi başardınız.

## Yaygın Sorunlar ve Çözümler

- **Kırpma görünmüyor:** `WriteGraphicsSave()` çağrısını çevirme işleminden önce ve `WriteGraphicsRestore()` çağrısını doldurmadan sonra yaptığınızdan emin olun.  
- **Yanlış renkler:** `SetPaint`'in `Clip` sonrası ve `Fill` öncesinde çağrıldığını kontrol edin.  
- **Kesikli çizgiler düz görünüyor:** `Pen` nesnesinin `DashStyle` özelliğinin `DashStyle.Dash` olarak ayarlandığından emin olun.  

## Sık Sorulan Sorular

### S1: Aspose.Page for .NET’i başka programlama dilleriyle kullanabilir miyim?
Cevap: Aspose.Page öncelikle .NET uygulamaları için tasarlanmıştır. Ancak Aspose, diğer programlama dilleri için benzer kütüphaneler de sunar.

### S2: Aspose.Page for .NET için ek örnekler ve belgeler nerede bulunur?
Cevap: Daha fazla örnek ve ayrıntılı belgeyi [Aspose.Page belgeleri](https://reference.aspose.com/page/net/) sayfasında inceleyebilirsiniz.

### S3: Aspose.Page for .NET için ücretsiz deneme mevcut mu?
Cevap: Evet, Aspose.Page for .NET’in ücretsiz denemesine [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### S4: Aspose.Page for .NET için geçici bir lisans nasıl alınır?
Cevap: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### S5: Aspose.Page ile ilgili destek veya tartışma platformları nerede?
Cevap: Topluluk desteği ve tartışmalar için [Aspose.Page forumlarını](https://forum.aspose.com/c/page/39) ziyaret edin.

---

**Son Güncelleme:** 2026-01-05  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-26
description: Aspose.Page kullanarak .NET’te doku döşeme desenleriyle PostScript belgesi
  oluşturmayı öğrenin. PS dosyalarınıza zengin dokular eklemek için adım adım rehberimizi
  izleyin.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Doku Döşemeli PostScript .NET Belgesi Oluştur
url: /tr/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Doku Döşeme ile PostScript .NET Belgesi Oluşturma

## Doku döşeme ile PostScript belgesi .NET nasıl oluşturulur

Bu öğreticide **PostScript belge .NET** oluşturmayı ve Aspose.Page kütüphanesini kullanarak bir doku döşeme deseniyle zenginleştirmeyi öğreneceksiniz. Projenizi kurmaktan, metni doku fırçası ile doldurup kenarlığını çizmeye kadar her adımı adım adım göstereceğiz, böylece dakikalar içinde görsel açıdan çekici PS dosyaları üretebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Page for .NET  
- **.NET Core kullanabilir miyim?** Evet, kütüphane .NET Core ve .NET 5/6’yı destekler  
- **Doku için hangi görüntü formatları çalışır?** System.Drawing tarafından desteklenen herhangi bir format (BMP, PNG, JPEG vb.)  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika  
- **Lisans gerekli mi?** Test için ücretsiz deneme sürümü yeterlidir; üretim için lisans gerekir  

## Önkoşullar

- Makinenizde yüklü [Visual Studio](https://visualstudio.microsoft.com/)  
- C# programlamaya temel aşinalık  
- [Aspose.Page for .NET kütüphanesini](https://releases.aspose.com/page/net/) indirin ve kurun  
- Doku deseni için bir görüntü dosyası (ör. **TestTexture.bmp**)  

## Ad Alanlarını İçe Aktarın

C# dosyanızda, kullanacağımız türlerin nerede bulunduğunu derleyicinin bilmesi için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: Belge Dizinini Ayarlayın

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

**Your Document Directory** ifadesini, oluşturulan PS dosyasının kaydedileceği klasörle değiştirin.

## Adım 2: PS Belgesi İçin Çıktı Akışı Oluşturun

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Bu blok bir dosya akışı açar, sayfa boyutunu (varsayılan A4) yapılandırır ve üzerine çizeceğimiz yeni bir **PsDocument** örneği oluşturur.

## Adım 3: Doku Döşeme Deseni Uygulayın

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Burada bitmap’i yüklüyor, bir **TextureBrush** içine sarıyor, isteğe bağlı olarak yatayda geriyor ve **PsDocument**’e sonraki çizim işlemleri için bu fırçayı kullanmasını söylüyoruz.

## Adım 4: Dikdörtgen Yolu Oluşturun ve Doldurun

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Basit bir dikdörtgen tanımlanır ve önceki adımda ayarladığımız doku fırçası ile doldurulur.

## Adım 5: Çizgi Ayarla ve Çiz

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Mevcut boya (doku fırçası) alınır, kenar için kırmızı bir kalem oluşturulur ve dikdörtgenin çerçevesi çizilir.

## Adım 6: Metni Doku Deseniyle Doldur ve Çiz

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Bu adım **metni doldur ve çiz** yeteneğini gösterir: “ABC” karakterleri doku fırçası ile doldurulur ve ardından kenarlığı çizilir, çarpıcı bir görsel etki elde edilir.

## Adım 7: Belgeyi Kaydet ve Kapat

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Sayfanın kapatılması çizim komutlarını sonlandırır ve `Save()` PostScript dosyasını diske yazar.

## Yaygın Sorunlar ve Çözümler

- **Doku yanlış şekilde gerilmiş görünüyor** – Ölçeklemeyi X/Y yönlerinde kontrol etmek için `Matrix` değerlerini ayarlayın.  
- **Görüntü bulunamadı** – `dataDir` değişkeninin doğru klasöre işaret ettiğinden ve dosya adının büyük/küçük harf duyarlılığıyla tam eşleştiğinden emin olun.  
- **Renkler doğru çıkmıyor** – PostScript cihaz‑bağımsız bir renk uzayı kullanır; doğru eşleşen `Color` nesneleri kullandığınızdan emin olun.  

## Sık Sorulan Sorular

**S:** Doku deseni için başka görüntü formatları kullanabilir miyim?  
**C:** Evet, `System.Drawing.Bitmap` tarafından desteklenen herhangi bir format (BMP, PNG, JPEG, GIF vb.) çalışır.

**S:** Aspose.Page .NET Core ile uyumlu mu?  
**C:** Kesinlikle. Kütüphane .NET Framework, .NET Core ve .NET 5/6 üzerinde çalışır.

**S:** Dokulu dikdörtgenin boyutunu nasıl değiştiririm?  
**C:** Dikdörtgen oluşturma adımındaki `RectangleF` değerlerini değiştirin (ör. `new RectangleF(0, 0, 300, 150)`).

**S:** Tek bir belgede birden fazla doku deseni uygulayabilir miyim?  
**C:** Evet. Farklı bir görüntü ile yeni bir `TextureBrush` oluşturun ve bir sonraki şekil ya da metni çizmeye başlamadan önce tekrar `SetPaint` çağırın.

**S:** Daha fazla örnek ve API referansına nereden ulaşabilirim?  
**C:** Topluluk desteği için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) ve ayrıntılı API kullanımı için resmi [dökümantasyon](https://reference.aspose.com/page/net/) sayfalarını ziyaret edin.

## Sonuç

Artık **PostScript belge .NET** oluşturmayı ve doku döşeme deseni uygulamayı, ayrıca **metni doku ile doldurup çizmeyi** biliyorsunuz. Farklı görüntüler, ölçekleme matrisleri ve çizim primitive’leriyle deneyler yaparak raporlar, broşürler veya grafik‑ağır çıktılar için özel stillerde PS dosyaları üretebilirsiniz.

---

**Son Güncelleme:** 2026-03-26  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
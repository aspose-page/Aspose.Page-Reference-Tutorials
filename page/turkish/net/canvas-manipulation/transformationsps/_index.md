---
date: 2026-01-12
description: Aspose.Page for .NET kullanarak PostScript dosyasını nasıl kaydedeceğinizi
  ve PostScript belgesi oluşturacağınızı öğrenin ve dinamik grafikler için birden
  fazla dönüşüm uygulayın.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Aspose.Page Dönüşümleri (.NET) ile PostScript dosyasını kaydet
url: /tr/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Dönüşümleriyle PostScript Dosyası Kaydetme (.NET)

## Giriş

Bu öğreticide, Aspose.Page for .NET ile çalışırken **PostScript dosyasını kaydetmeyi** keşfedeceksiniz. Bir PostScript belgesi oluşturmayı, öteleme, ölçekleme, döndürme ve kaydırma gibi birden çok dönüşümü uygulamayı ve sonunda sonucu kaydetmeyi adım adım inceleyeceğiz. Sonunda, dinamik grafikleri programlı olarak oluşturma konusunda rahat olacak ve her dönüşümü grafik durumunda tam olarak nerede konumlandırmanız gerektiğini bileceksiniz.

## Hızlı Yanıtlar
- **Ne oluşturabilirim?** Dönüştürülmüş grafiklere sahip tam özellikli bir PostScript belgesi.  
- **Hangi kütüphane gerekiyor?** Aspose.Page for .NET (resmi siteden indirilebilir).  
- **Dosyayı nasıl kaydederim?** Grafik durumlarını yapılandırdıktan sonra `PsDocument.Save()` kullanın.  
- **Birden fazla dönüşüm uygulayabilir miyim?** Evet – `Transform` ile birleştirebilir veya ardışık çağrılar yapabilirsiniz.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.

## “PostScript dosyası kaydet” işlemi nedir?

PostScript dosyasını kaydetmek, bellekte oluşturduğunuz çizim komutlarını bir `.ps` dosyasına kalıcı olarak yazmak anlamına gelir. Dosya, herhangi bir PostScript yorumlayıcısı, yazıcı veya görüntüleyici tarafından işlenebilir.

## PostScript belgesi oluşturmak için .NET için Aspose.Page'i neden kullanmalıyım?

Aspose.Page, düşük seviyeli PostScript sözdizimini soyutlayan yüksek seviyeli, cihaz bağımsız bir API sunar. Şunları elde edersiniz:

- Yollar, fırçalar ve dönüşümler için güçlü tipli C# nesneleri.  
- Grafik durum yığını (save/restore) otomatik yönetimi.  
- Manuel hesaplamalar gerektirmeden karmaşık dönüşüm matrisleri için tam destek.  

## Önkoşullar

Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

- **Aspose.Page for .NET** kütüphanesini projenize entegre edin. [İndirme bağlantısı](https://releases.aspose.com/page/net/) üzerinden alın.  
- Oluşturulan `.ps` dosyasının kaydedileceği yazılabilir bir klasör. Koddaki yer tutucu yolu gerçek dizininizle değiştirin.

## Ad Alanlarını İçe Aktarın

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Şimdi her dönüşüm adımını tek tek inceleyelim.

## Dönüşüm Yok

### Adım 1: Çıktı Akışını Oluştur

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Bu kod parçacığı, tek bir turuncu dikdörtgen içeren bir **PostScript belgesi** oluşturur ve **PostScript dosyasını** herhangi bir dönüşüm uygulamadan kaydeder.

## Öteleme

### Adım 1: Grafik Durumunu Kaydet

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Grafik durumunu kaydetmek, nesneleri hareket ettirdikten sonra eski konuma geri dönmenizi sağlar.

### Adım 2: Grafik Durumunu Ötele

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Bu öteleme, bu çağrıdan sonra çizilen her şeyi 250 birim sağa kaydırır.

### Adım 3: Öteleme Dönüşümüyle Dikdörtgeni Doldur

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Şimdi mavi bir dikdörtgen, turuncu olanın 250 birim sağında görünecek.

### Adım 4: Grafik Durumunu Geri Yükle

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Geri yükleme, koordinat sistemini orijinal konumuna döndürür; böylece sonraki çizimler ötelemeden etkilenmez.

## Ölçekleme

> *Aynı deseni izleyebilirsiniz—durumu kaydedin, `Scale` uygulayın, çizin, ardından geri yükleyin.*  
> **İpucu:** Nesneleri yalnızca bir yönde uzatmak için tekdüz olmayan ölçekleme (`Scale(sx, sy)`) kullanın.

## Döndürme

> *`Rotate(angle)` kullanarak orijine ya da özel bir dönme noktasına göre döndürün.*  
> **İpucu:** Belirli bir nokta etrafında döndürmek için döndürmeden önce `Translate` uygulayın.

## Kaydırma

> *Kaydırma dönüşümleri (`Shear(shx, shy)`) şekilleri eğer, italik etkileri için kullanışlıdır.*  

## Karmaşık Dönüşümler

> *Gelişmiş senaryolar için özel bir `Matrix` oluşturun ve `Transform(matrix)` metoduna geçirin.*  
> Bu, **birden fazla dönüşümü** tek bir adımda **uyguladığınız** yerdir.

## Sonuç

Aspose.Page for .NET kullanarak **PostScript dosyasını kaydetmeyi**, **PostScript belgesi oluşturmayı** ve **birden çok dönüşüm uygulamayı** öğrendiniz. Farklı dönüşüm sıralarıyla deney yapın, birleştirin ve grafiğin nasıl evrildiğini izleyin.

## Sık Sorulan Sorular

**S: Tek bir nesneye birden fazla dönüşüm nasıl uygulanır?**  
C: İhtiyacınız olan sırada öteleme, ölçekleme, döndürme veya kaydırma içeren özel bir `Matrix` oluşturup `Transform` metoduyla kullanın.

**S: Belgeyi kaydetmeden önce dönüşümleri önizleyebilir miyim?**  
C: Evet—`PsDocument`i bir görüntüye render edebilir veya bir PostScript görüntüleyici ile çıktıyı `Save()` çağrısından önce inceleyebilirsiniz.

**S: Belgedeki belirli öğelere dönüşüm uygulamak mümkün mü?**  
C: Kesinlikle. Öğeyi çizmeye başlamadan önce grafik durumunu kaydedin, istediğiniz dönüşümü uygulayın, çizin, ardından durumu geri yükleyin.

**S: Karmaşık dönüşümlerde performans kaygıları var mı?**  
C: Karmaşık matrisler CPU yükünü artırır. Dönüşümleri mümkün olduğunca basit tutun ve benzer nesneleri çizerken kaydedilmiş durumları yeniden kullanın.

**S: Aspose.Page ile ilgili sorular için destek nasıl alınır?**  
C: Topluluk yardımı için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin veya doğrudan Aspose desteğiyle iletişime geçin.

---

**Son Güncelleme:** 2026-01-12  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
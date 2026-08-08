---
date: 2026-04-03
description: Aspose.Page kullanarak .NET’te şeffaf bir dikdörtgen eklemeyi ve bir
  Grid Visual Brush uygulamayı öğrenin; çarpıcı XPS belgeleri oluşturun.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Izgara Görsel Fırçasını Uygula
second_title: Aspose.Page .NET API
title: Grid Visual Brush (.NET) kullanarak Şeffaf Dikdörtgen Ekle
url: /tr/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Şeffaf Dikdörtgen Ekleme Grid Görsel Fırçası ile (.NET)

## Giriş

Eğer bir XPS belgesine **şeffaf bir dikdörtgen** eklemek ve aynı zamanda şık bir Grid Visual Brush uygulamak istiyorsanız, doğru yerdesiniz. Bu öğreticide Aspose.Page for .NET ile gerekli adımları adım adım göstereceğiz, böylece öne çıkan görsel açıdan zengin belgeler oluşturabilirsiniz. Sonunda, her iki tekniği tek bir, kolay takip edilebilir iş akışında gösteren tam, çalıştırılabilir bir örnek elde edeceksiniz.

## Hızlı Yanıtlar
- **Şeffaf bir dikdörtgen ne yapar?** Arka plan içeriğinin görünmesini sağlayan yarı saydam bir kaplama ekler.  
- **Hangi API fırçayı oluşturur?** `XpsDocument.CreateVisualBrush` Grid Visual Brush'ı oluşturur.  
- **Lisans gerekli mi?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.

## XPS'de Şeffaf Dikdörtgen Nedir?
Şeffaf bir dikdörtgen, doldurma renginin alfa bileşeni 1.0'dan düşük olan bir şekildir; bu sayede alttaki grafikler kısmen görünür. Bu, arka planı tamamen gizlemeden bölümleri vurgulamak için mükemmeldir.

## Neden Grid Visual Brush Kullanılır?
Grid Visual Brush, küçük bir vektör grafiğini daha büyük bir alana döşemenizi sağlar ve ızgaralar, taramalar veya özel dokular gibi desenler oluşturur. Bunu şeffaf bir dikdörtgenle birleştirerek hafif ve çözünürlük bağımsız katmanlı görsel efektler elde edersiniz.

## Ön Koşullar

Koda geçmeden önce şunların olduğundan emin olun:

- **Aspose.Page for .NET** – bunu [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.
- .NET geliştirme ortamı (Visual Studio, VS Code veya tercih ettiğiniz herhangi bir IDE).
- Oluşturulan XPS dosyalarının kaydedileceği bir klasör.

## Ad Alanlarını İçe Aktarın

C# dosyanızda gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Şimdi çözümü net, numaralı adımlara ayıralım.

## Adım 1: XpsDocument Başlatma

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

`XpsDocument` örneği oluşturularak başlarız; bu örnek sonraki tüm çizim işlemlerini tutacaktır.

## Adım 2: Magenta Izgara Geometrisini Oluşturma

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Bu geometri, görsel fırçanın dolduracağı ızgaranın ana hatlarını tanımlar.

## Adım 3: Magenta Izgara VisualBrush Tasarımı

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Burada, ızgara boyunca tekrarlanacak küçük bir magenta döşeme çizeriz.

## Adım 4: VisualBrush'ı Izgaraya Uygulama

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` çağrısı, magenta döşemeyi ızgara geometrisine bağlar ve döşemeyi etkinleştirir.

## Adım 5: Izgarayı Kanvasa Ekleme

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Döşenen ızgarayı bir kanvasa yerleştirir ve istenen konumda görünmesi için bir çeviri dönüşümü uygularız.

## Adım 6: Şeffaf Dikdörtgen Ekleme

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Bu adımda **şeffaf bir dikdörtgen** ekliyoruz (`Opacity = 0.7f` ile kırmızı şekil). Dikdörtgenin ne kadar şeffaf olduğunu kontrol etmek için opaklık değerini ayarlayın.

## Adım 7: Belgeyi Kaydetme

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS dosyası, daha önce belirttiğiniz klasöre yazılır.

## Yaygın Kullanım Senaryoları

- **Rapor Vurgulama:** Bir grafiği veya tabloyu vurgulamak için yarı saydam bir dikdörtgen üstüne bindirin.  
- **Filigran Efektleri:** Hafif bir marka izi için döşenen ızgarayı şeffaf bir kaplamayla birleştirin.  
- **Etkileşimli PDF/XPS:** Kullanıcı arayüzünü okunabilir tutarken form alanları için deseni arka plan olarak kullanın.

## Sorun Giderme İpuçları

- **Opaklık Görünmüyor mu?** Görüntüleyicinizin XPS şeffaflığını desteklediğinden emin olun; bazı eski görüntüleyiciler `Opacity` özelliğini görmezden gelebilir.  
- **Yanlış Döşeme Boyutu?** Kaynak dikdörtgenin (`new RectangleF(0f, 0f, 10f, 10f)`) vektör döşemenin boyutlarıyla eşleştiğini doğrulayın.  
- **Dosya Kaydedilmedi mi?** `dataDir`'in mevcut ve yazılabilir bir dizine işaret ettiğini iki kez kontrol edin.

## Sıkça Sorulan Sorular

**S: Aspose.Page for .NET'i hem web hem de masaüstü uygulamalarında kullanabilir miyim?**  
C: Evet, kütüphane tüm .NET uygulama türlerinde çalışır.

**S: Satın almadan önce deneme sürümü mevcut mu?**  
C: Kesinlikle, ücretsiz denemeye [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Ek destek veya topluluk tartışmalarını nerede bulabilirim?**  
C: Topluluk ve Aspose mühendislerinden yardım almak için [Aspose.Page Forum](https://forum.aspose.com/c/page/39) adresini ziyaret edin.

**S: Değerlendirme için geçici bir lisans nasıl alabilirim?**  
C: Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Page for .NET için başka hangi belgeler mevcut?**  
C: Kapsamlı belgeleri [buradan](https://reference.aspose.com/page/net/) inceleyin.

---

**Son Güncelleme:** 2026-04-03  
**Test Edilen Versiyon:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
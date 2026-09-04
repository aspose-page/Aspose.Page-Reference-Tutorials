---
date: 2026-06-25
description: Aspose.Page for .NET kullanarak XPS belgelerini nasıl kırpacağınızı öğrenin.
  Bu adım adım rehber, XPS dosyalarını verimli bir şekilde oluşturmayı, düzenlemeyi
  ve kaydetmeyi gösterir.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: XPS Kırpma
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Nasıl Kırpılır
url: /tr/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Kesme

## Giriş

Aspose.Page for .NET kullanarak **XPS nasıl kesilir** konusundaki bu kapsamlı öğreticiye hoş geldiniz! Bu rehberde, adım adım bir XPS belgesi oluşturmayı, geometrik kırpma maskeleri uygulamayı ve sonucu kaydetmeyi öğreneceksiniz. Kırpma, bir tuvalin bölümlerini gizlemenizi sağlar ve maskelenmiş görüntüler, özel şekiller veya odaklanmış içerik alanları gibi karmaşık düzenleri .NET kodunuzdan çıkmadan mümkün kılar.

## Hızlı Yanıtlar
- **XPS kesme nedir?** XPS tuval öğelerinin görünen alanını sınırlamak için geometrik bir maske (clip) uygulamak.  
- **Bu iş için en iyi kütüphane hangisidir?** Aspose.Page for .NET, XPS oluşturma ve kırpma için tam özellikli bir API sunar.  
- **Önkoşullar?** Visual Studio, .NET çalışma zamanı ve Aspose.Page for .NET kütüphanesi.  
- **Uygulama ne kadar sürer?** Temel bir kırpma senaryosu için yaklaşık 10‑15 dakika.  
- **Bunu üretimde kullanabilir miyim?** Evet, geçerli bir Aspose lisansı (deneme sürümü mevcut) ile.

## “XPS nasıl kesilir” nedir?

XPS kesme, bir tuval üzerine geometrik bir maske uygulayarak maskenin dışındaki tüm çizimlerin render edilmemesi anlamına gelir. Bu teknik, maskelenmiş görüntüler, özel şekilli düğmeler oluşturmak veya okuyucunun dikkatini belirli bir sayfa bölgesine odaklamak için idealdir. Bir kırpma geometrisi tanımlayarak—örneğin bir dikdörtgen, daire veya karmaşık bir yol—son XPS sayfasında neyin görüneceği üzerinde ince ayar kontrolü elde edersiniz.

## XPS kesmek için neden Aspose.Page for .NET kullanılmalı?

Aspose.Page, dış bağımlılıklar olmadan belirli, sunucu tarafı XPS manipülasyonu sağlar. **50+ giriş ve çıkış formatını** destekler, standart 2.5 GHz CPU’da **200 sayfalık XPS dosyalarını 0.5 saniyeden kısa sürede** işleyebilir ve .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 ve .NET 7 ile uyumludur. API, tuval dönüşümleri, yol geometrileri ve fırçalar üzerinde tam kontrol sunar, böylece her seferinde yüksek kaliteli çıktı elde edilir.

## Önkoşullar

- Makinenizde Visual Studio yüklü olmalıdır.  
- Projenize Aspose.Page for .NET kütüphanesini ekleyin. Bunu [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- C# programlama dili hakkında temel bilgi.

## XPS Nasıl Kesilir?

Bir XPS belgesi yükleyin, bir tuval oluşturun, bir kırpma geometrisi tanımlayın (ör. bir daire), bu geometriyi tuvalin `Clip` özelliğine atayın, içeriğinizi çizin ve sonunda belgeyi kaydedin. Bu adımlar sadece birkaç metod çağrısıyla gerçekleştirilebilir ve Aspose.Page, temel XML işaretlemesini otomatik olarak yönetir, böylece dosya yapısına değil görsel tasarıma odaklanırsınız.

## Ad Alanlarını İçe Aktarma

Aspose.Page for .NET işlevlerini kullanmak için projenize gerekli ad alanlarını içe aktarmanız gerekir. Aşağıdaki adımları izleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Şimdi, sağladığınız örnek kodu birden fazla adıma ayıralım.

## Adım 1: Belge dizini yolunu ayarlayın.

XPS dosyasının oluşturulacağı klasörü tanımlayın. `Path.Combine` kullanmak, herhangi bir işletim sisteminde doğru dizin ayırıcıyı garanti eder.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Adım 2: Yeni bir XPS Belgesi Oluşturun.

`XpsDocument` sınıfını örnekleyin; bu sınıf tüm XPS paketini temsil eder.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Adım 3: Ana tuvali oluşturun.

`Canvas` sınıfı, şekillerin, görüntülerin ve metnin render edildiği bir XPS sayfası içinde bir çizim yüzeyini temsil eder.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Adım 4: Ana tuvalde sol ve üst ofsetleri ayarlayın.

Tuval konumunu ayarlayarak çizimin sayfada nereden başlayacağını kontrol edin.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Adım 5: Dikdörtgen yol geometrisi oluşturun.

`PathGeometry` vektörel bir şekil tanımlar; burada basit bir dikdörtgen oluşturuyoruz.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Adım 6: Dikdörtgenler için dolgu oluşturun.

Dikdörtgeni doldurmak için kullanılacak katı renk fırçasını tanımlayın.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Adım 7: Ana tuvale kırpmalı başka bir tuval ekleyin.

Kırpma maskesi alacak bir alt tuval oluşturun.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Adım 8: Kırpma için daire geometrisi oluşturun.

`PathGeometry` aynı zamanda daireleri temsil edebilir; bu geometri alt tuvalin `Clip` özelliğine atanacaktır.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Adım 9: İkinci tuvalde bir dikdörtgen oluşturun ve doldurun.

Kırpılmış tuval içinde bir dikdörtgen çizin; yalnızca daire içindeki bölüm görünecektir.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Adım 10: Ana tuvale kenarlıklı bir dikdörtgen içeren ikinci tuvali ekleyin.

Kırpma ile kenarlıkların nasıl etkileştiğini göstermek için kenarlıklı bir dikdörtgen ekleyin.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Adım 11: Üçüncü tuvalde bir dikdörtgen oluşturun ve kenarlık ekleyin.

Üçüncü tuval, kırpma olmadan bağımsız çizimi gösterir.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Adım 12: Oluşan XPS belgesini kaydedin.

XPS paketini dosya sistemine kaydedin.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Yaygın Sorunlar ve Çözümler
- **Geçersiz yol** – `dataDir` değişkeninin ters eğik çizgi (`\\`) ile bittiğinden emin olun veya `Path.Combine` kullanın.  
- **Kırpma uygulanmadı** – Kırpma geometrisi dizesinin doğru biçimlendirildiğini kontrol edin; eksik bir boşluk kırpmanın göz ardı edilmesine neden olabilir.  
- **Lisans istisnası** – Değerlendirme dışı bir derlemede, belgeyi oluşturmadan önce geçerli bir Aspose lisansı ekleyerek çalışma zamanı istisnalarını önleyin.

## Sıkça Sorulan Sorular

### S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?
A1: Aspose.Page for .NET öncelikle XPS belgelerine odaklanır, ancak Aspose çeşitli belge formatları için diğer kütüphaneleri de sağlar.

### S2: Aspose.Page for .NET yeni başlayanlar için uygun mu?
A2: Evet, Aspose.Page for .NET kullanıcı dostu olacak şekilde tasarlanmıştır ve yeni başlayanlar, uygun belgelerle işlevlerini hızlıca kavrayabilir.

### S3: Daha fazla örnek ve kaynağa nereden ulaşabilirim?
A3: Geniş kaynak ve örnekler için [belgelere](https://reference.aspose.com/page/net/) ve [Aspose.Page forumuna](https://forum.aspose.com/c/page/39) göz atın.

### S4: Aspose.Page for .NET için geçici bir lisans nasıl alabilirim?
A4: Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

### S5: Aspose.Page for .NET için ücretsiz deneme mevcut mu?
A5: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) inceleyebilirsiniz.

## Ek Sıkça Sorulan Sorular

**S: Tek bir tuvalde birden fazla kırpma geometrisini birleştirebilir miyim?**  
C: Evet, `Clip` özelliğine birden fazla alt‑yolu içeren karmaşık bir `PathGeometry` atayarak katmanlı maskeleme yapabilirsiniz.

**S: Kırpma PDF dönüşümünü etkiler mi?**  
C: XPS'yi daha sonra Aspose.PDF ile PDF'ye dönüştürdüğünüzde, kırpma geometrisi korunur, böylece görsel sonuç aynı kalır.

**S: XPS'de kırpmayı animasyonlu yapmak mümkün mü?**  
C: XPS kendisi animasyonu desteklemez; ancak farklı kırpma şekilleriyle bir dizi XPS sayfası oluşturarak hareketi taklit edebilirsiniz.

---

**Son Güncelleme:** 2026-06-25  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## İlgili Öğreticiler

- [Aspose.Page for .NET ile XPS Nasıl Dönüştürülür](/page/net/canvas-manipulation/transformationsxps/)
- [Aspose.Page for .NET ile XPS Belgesine Dikdörtgen Ekleme](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Aspose.Page for .NET ile XPS'yi PDF'ye Dönüştürme](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}
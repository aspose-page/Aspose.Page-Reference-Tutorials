---
date: 2026-01-07
description: Aspose.Page kullanarak .NET'te XPS belgesi oluşturmayı öğrenin. Bu kılavuz,
  daha zengin belge görselleri için görüntüyle doldurulmuş glifler ve yabancı görüntüler
  eklemeyi gösterir.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Aspose.Page ile .NET’te XPS Belgesi Oluşturma – Görüntü Dolu Glif ve Yabancı
  Görüntü
url: /tr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS belgesi .NET oluşturma – Aspose.Page ile Görüntü Dolu Glif & Yabancı Görüntü

## Giriş

Eğer **create XPS document .NET** uygulamalarının şık ve profesyonel görünmesini istiyorsanız, Aspose.Page size görüntüleri doğrudan gliflere gömmek ve grafik kaynaklarını belgeler arasında yeniden kullanmak için araçlar sunar. Bu öğreticide iki XPS dosyası oluşturmayı, glifleri bir görüntü fırçası ile doldurmayı ve ardından bu fırçayı ikinci bir belgede yeniden kullanmayı adım adım göstereceğiz. Sonunda bu yaklaşımın belleği nasıl tasarruf ettirdiğini, stil oluşturmayı nasıl basitleştirdiğini ve raporlar, faturalar veya herhangi bir yazdırılabilir içerik için yaratıcı olasılıkları nasıl açtığını anlayacaksınız.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.Page for .NET ile XPS belgeleri arasında görüntü‑dolu glifler ekleme ve yeniden kullanma.  
- **Hedeflenen birincil anahtar kelime nedir?** `create xps document .net`.  
- **Önkoşullar?** .NET geliştirme ortamı, Aspose.Page for .NET ve XPS dosyalarınız için bir klasör.  
- **Uygulama ne kadar sürer?** Çalışan bir prototip için yaklaşık 10‑15 dakika.  
- **Diğer görüntü formatlarını kullanabilir miyim?** Evet – .NET’in `System.Drawing.Image` tarafından desteklenen herhangi bir format.

## Önkoşullar

Koda geçmeden önce aşağıdakilerin hazır olduğundan emin olun:

- **Aspose.Page for .NET** – en son kütüphaneyi [buradan](https://releases.aspose.com/page/net/) indirin.  
- **Geliştirme Ortamı** – Visual Studio 2022 (veya .NET 6+ destekleyen herhangi bir IDE).  
- **Belge Dizini** – giriş görüntülerini ve oluşturulan XPS dosyalarını tutacak bir klasör oluşturun; kod parçacıklarında buna **Your Document Directory** diye atıfta bulunacağız.

## Ad Alanlarını İçe Aktarma

XPS nesneleri ve çizim yardımcılarıyla çalışmak için gerekli ad alanlarını içe aktararak başlayın.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Adım‑Adım Kılavuz

### Adım 1: İlk XPS Belgesini Oluşturma

Boş bir XPS belgesi oluşturacağız; bu belge görüntü‑dolu glifi barındıracak.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Adım 2: İlk Belgeye Glifler Ekleme

Daha sonra, daha sonra bir görüntü fırçası ile dolduracağımız bir glif (metin karakteri) ekleyeceğiz.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Adım 3: Glifleri Görüntü Fırçası ile Doldurma

Burada veri dizinimizdeki bir TIFF dosyasından bir `ImageBrush` oluşturup glife uyguluyoruz. Fırça, glif alanı görüntü boyutunu aşarsa görüntünün tekrarlanması için döşeme (tile) modunda ayarlanır.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Adım 4: İkinci XPS Belgesini Oluşturma

Şimdi, birinci belgede tanımlanan glif stilini ve görüntü fırçasını yeniden kullanacak ikinci bir XPS belgesi oluşturacağız.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Adım 5: İlk Belgeden Font ile Glifler Ekleme

İkinci belgeye bir glif ekliyoruz ve birinci belgeden aynı font nesnesini yeniden kullanıyoruz. Bu, iki dosya arasında görsel tutarlılığı sağlar.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Adım 6: İlk Belgenin Doldurmasından Görüntü Fırçası Oluşturma

Görüntüyü tekrar yüklemek yerine, `glyphs1` den fırçayı klonlayıp `glyphs2` ye atıyoruz. Bu, **create XPS document .NET** iş akışlarında kaynakları verimli bir şekilde paylaşmanın nasıl yapılacağını gösterir.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Adım 7: Belgeleri Kaydetme

Son olarak, her iki XPS dosyasını da diske kaydediyoruz. Artık herhangi bir XPS görüntüleyici ile açıp görüntü‑dolu glif etkisini görebilirsiniz.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## XPS belgesi .NET oluştururken neden görüntü‑dolu glifler kullanmalısınız?

- **Görsel Etki** – Düz metni, sayfanın tamamını rasterleştirmeden grafik‑zengin öğelere dönüştürün.  
- **Kaynak Yeniden Kullanımı** – Fırçalar ve fontlar birden fazla belge arasında paylaşılır, bellek ayak izi azalır.  
- **Esneklik** – Görüntü fırçasını döşeme, germe veya döndürme gibi işlemlerle özel desenler veya marka kimliği oluşturabilirsiniz.

## Yaygın Sorunlar ve İpuçları

- **Dosya Yolu Hataları** – `dataDir` değişkeninin işletim sisteminize uygun bir yol ayırıcı (`\` veya `/`) ile bittiğinden emin olun.  
- **Desteklenmeyen Görüntü Formatları** – Aspose.Page en iyi TIFF, PNG ve JPEG ile çalışır. Diğer formatları kullanmadan önce dönüştürün.  
- **TileMode Uygulanmadı** – `TileMode` ayarlamadan önce `XpsImageBrush` tipine dönüştürdüğünüzden emin olun; aksi takdirde özellik yok sayılır.

## Sıkça Sorulan Sorular

### S1: Glifleri doldurmak için farklı görüntü formatları kullanabilir miyim?

**C:** Evet, Aspose.Page TIFF, PNG, JPEG, BMP ve GIF formatlarını destekler. `CreateImageBrush` çağrısında doğru dosya uzantısını belirtmeniz yeterlidir.

### S2: Gliflerin görünümünü daha da özelleştirebilir miyim?

**C:** `XpsGlyphs` üzerindeki `Opacity`, `RenderTransform` ve `Stroke` gibi ek özellikleri keşfederek renderlamayı ince ayar yapabilirsiniz.

### S3: Aspose.Page büyük belge setlerini işlemek için uygun mu?

**C:** Kesinlikle. Kütüphane yüksek performanslı senaryolar için optimize edilmiştir ve toplu işler halinde binlerce XPS dosyasını işleyebilir.

### S4: Tek tek gliflere farklı stiller uygulayabilir miyim?

**C:** Evet. Her `XpsGlyphs` örneği kendi doldurma, kontur ve dönüşüm ayarlarına sahip olabilir, bu da size ayrıntılı kontrol sağlar.

### S5: Aspose.Page diğer belge işleme araçlarına göre ne gibi avantajlar sunar?

**C:** Aspose.Page, XPS oluşturma, manipülasyon ve dönüşüm için tam, lisans‑ücretsiz bir API sunar; kapsamlı dokümantasyon ve 7/24 destek ile birlikte gelir.

---

**Son Güncelleme:** 2026-01-07  
**Test Edilen Sürüm:** Aspose.Page 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
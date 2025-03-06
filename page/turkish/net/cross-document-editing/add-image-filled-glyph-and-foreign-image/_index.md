---
title: Aspose.Page .NET ile Resim Dolgulu Glif ve Yabancı Resim Ekleme
linktitle: Resimle Dolu Glif ve Yabancı Resim Ekle
second_title: Aspose.Page .NET API'si
description: Aspose.Page ile .NET'te belge işlemenin gücünün kilidini açın. Görüntü dolu glifleri zahmetsizce ekleyin. Görselleri geliştirin ve iş akışınızı kolaylaştırın.
weight: 11
url: /tr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET ile Resim Dolgulu Glif ve Yabancı Resim Ekleme

## giriiş

.NET geliştirme dünyasında Aspose.Page, belge işleme görevlerini yerine getirmek için güçlü bir araç seti olarak öne çıkıyor. Bu eğitim, Aspose.Page for .NET'i kullanarak görüntü dolu glifler ekleme ve yabancı görüntüleri birleştirme sürecinde size rehberlik edecektir. Bu kılavuzun sonunda belge işleme yeteneklerinizi nasıl geliştireceğiniz konusunda sağlam bir anlayışa sahip olacaksınız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

- Geliştirme Ortamı: Visual Studio veya tercih edilen herhangi bir IDE ile çalışan bir .NET geliştirme ortamı kurun.

- Belge Dizini: Belgelerinizi saklayacağınız bir dizin oluşturun. Kod örneklerinde buna "Belge Dizininiz" adı verilecektir.

## Ad Alanlarını İçe Aktar

.NET uygulamanızda, Aspose.Page tarafından sağlanan sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. Adım: İlk XPS Belgesini Oluşturun

Aspose.Page'i kullanarak ilk XPS belgesini oluşturarak başlayın. Bu belge, görüntü dolu gliflerin eklenmesi için temel oluşturacaktır.

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";

// İlk XPS Belgesini oluşturun
XpsDocument doc1 = new XpsDocument();
```

## Adım 2: İlk Belgeye Glifler Ekleme

Yazı tipini, boyutunu, stilini ve konumunu belirterek ilk belgeye glifler ekleyin.

```csharp
// İlk belgeye glifler ekleme
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 3. Adım: Glifleri Görüntü Fırçasıyla Doldurun

Veri dizininizdeki bir görüntüyü kullanarak glifleri bir görüntü fırçasıyla doldurun.

```csharp
// Glifleri bir görüntü fırçasıyla doldurun
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 4. Adım: İkinci XPS Belgesini Oluşturun

Şimdi, ilk belgedeki glifleri içerecek ikinci XPS belgesini oluşturun.

```csharp
// İkinci XPS Belgesini oluşturun
XpsDocument doc2 = new XpsDocument();
```

## Adım 5: İlk Belgedeki Yazı Tipiyle Glifleri Ekleme

İlk belgedeki yazı tipini kullanarak ikinci belgeye glifler ekleyin.

```csharp
// İlk belgedeki yazı tipini içeren glifleri ikinci belgeye ekleme
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Adım 6: İlk Belgenin Dolgusundan Görüntü Fırçası Oluşturun

İlk belgenin dolgusundan bir görüntü fırçası oluşturun ve bunu ikinci belgedeki glifleri doldurmak için kullanın.

```csharp
// İlk belgenin dolgusundan bir görüntü fırçası oluşturun ve ikinci belgedeki glifleri doldurun
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Adım 7: Belgeleri Kaydedin

Hem birinci hem de ikinci XPS belgelerini kaydedin.

```csharp
// İlk XPS belgesini kaydedin
doc1.Save(dataDir + "out1.xps");

// İkinci XPS belgesini kaydedin
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak başarıyla görüntü dolu glifler eklediniz ve yabancı görüntüleri dahil ettiniz. Bu eğitim, belge işleme yeteneklerinizi geliştirmek için bir temel sağlayarak yaratıcı ve görsel olarak çekici belgeler için yeni olanaklar sunar.

## SSS'ler

### S1: Glifleri doldurmak için farklı görüntü formatlarını kullanabilir miyim?

Cevap1: Evet, Aspose.Page çeşitli görüntü formatlarını destekler. Seçilen görüntü formatıyla uyumluluğu sağlayın.

### S2: Gliflerin görünümünü nasıl daha da özelleştirebilirim?

Cevap2: Glif görünümüne ince ayar yapmaya yönelik ek özellikler ve yöntemler için Aspose.Page belgelerini inceleyin.

### S3: Aspose.Page büyük belge kümelerini işlemeye uygun mudur?

Cevap3: Aspose.Page, hem küçük hem de büyük belge setlerini verimli bir şekilde işleyecek şekilde tasarlanmıştır.

### S4: Bireysel gliflere farklı stiller uygulayabilir miyim?

Cevap4: Evet, her bir glif için stilleri bağımsız olarak özelleştirerek yüksek düzeyde esneklik sağlayabilirsiniz.

### S5: Aspose.Page'i kullanmanın diğer belge işleme araçlarına göre avantajları nelerdir?

Cevap5: Aspose.Page, kapsamlı özellikler, mükemmel performans ve kapsamlı belgeler sunarak birçok geliştiricinin tercih ettiği seçenek haline geliyor.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

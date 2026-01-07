---
date: 2026-01-07
description: Aspose.Page for .NET ile XPS belgesi oluşturmayı, glif klonları eklemeyi,
  katı renk fırçası kullanmayı ve XPS dosyasını kaydetmeyi öğrenin.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: XPS Belgesi Oluştur – Aspose.Page for .NET ile Glif Kopyası Ekle ve Rengi Değiştir
url: /tr/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgesi Oluşturma – Glyph Kopyası Ekleme ve Renk Değiştirme Aspose.Page for .NET ile

## Giriş

Bu adım adım kılavuza hoş geldiniz; bu kılavuz **XPS belge** dosyaları oluşturmayı, glyph'leri kopyalamayı ve renklerini Aspose.Page for .NET kullanarak değiştirmeyi gösterir. Dinamik raporlar, faturalar veya özel grafikler oluşturuyor olsanız da, bu teknikleri ustalaşarak .NET ekosisteminden çıkmadan görsel açıdan zengin XPS çıktısı üretebilirsiniz.

## Hızlı Yanıtlar
- **Birincil hedef nedir?** XPS belgesi oluşturmak, glyph kopyaları eklemek ve renklerini değiştirmek.  
- **Hangi kütüphane kullanılıyor?** Aspose.Page for .NET.  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans mevcuttur; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Sonucu nasıl kaydederim?** XPS dosyasını diske yazmak için `Save` metodunu kullanın.

## Önkoşullar

- C# programlama diline temel bir anlayış.  
- Visual Studio ya da tercih ettiğiniz başka bir C# geliştirme ortamı yüklü.  
- Aspose.Page for .NET kütüphanesi. Bunu [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- XPS belge formatına aşinalık.  

## Ad Alanlarını İçe Aktarma

To get started, include the necessary namespaces in your C# project:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## XPS Belgesi Oluşturma ve Glyph Kopyası Ekleme

### Adım 1: Belge Dizinini Ayarlayın

Begin by setting up the directory where your documents will be stored:

```csharp
string dataDir = "Your Document Directory";
```

### Adım 2: İlk XPS Belgesini Oluşturun

Now, let's create the first XPS document:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Adım 3: İlk Belgeye Glyph'ler Ekleyin

Add glyphs to the first document using the specified parameters:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Adım 4: Glyph'leri Katı Renk Fırçası ile Doldurun

Fill the glyphs in the first document with a **solid color brush**, for example, green:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Adım 5: İkinci XPS Belgesini Oluşturun

Now, create the second XPS document:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Adım 6: Glyph Kopyasını Başka Bir Belgeye Nasıl Eklenir

Clone glyphs from the first document and add them to the second document:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Adım 7: Kopyalanan Glyph'in Rengini Nasıl Değiştirirsiniz

Change the color of the cloned glyphs in the second document, for example, to red. This demonstrates **how to change color** of a glyph after cloning:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Adım 8: XPS Dosyasını Kaydet – İlk Belge

Save the first XPS document to the folder you defined earlier:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Adım 9: XPS Dosyasını Kaydet – İkinci Belge

Save the second XPS document:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Tebrikler! Aspose.Page for .NET kullanarak **XPS belge** dosyalarını başarıyla oluşturdu, glyph kopyaları ekledi ve renklerini değiştirdiniz.

## Glyph Kopyalama ve Renk Değiştirmeyi Neden Kullanmalısınız?

- **Yeniden Kullanılabilirlik:** Mevcut glyph'leri kopyalayarak karmaşık vektör şekillerini yeniden tanımlamadan yeniden kullanın.  
- **Performans:** Glyph'leri sıfırdan yeniden oluşturmak yerine işleme süresini azaltır.  
- **Tasarım Esnekliği:** Aynı glyph'e farklı `SolidColorBrush` örnekleri uygulayarak çeşitli görsel temalar elde edin.  
- **Çoklu Belge Düzenleme:** Glyph'leri birden fazla XPS dosyası arasında kopyalayarak raporlar arasında tutarlı marka kimliği sağlar.  

## Yaygın Sorunlar ve Sorun Giderme

| Sorun | Çözüm |
|-------|----------|
| **Kopya null döner** | Kopyalamadan önce kaynak glyph (`glyphs`) ilk belgeye eklenmiş olduğundan emin olun. |
| **Renk değişmiyor** | `glyphs.Fill` özelliğini `Color` özelliğini ayarlamadan önce `XpsSolidColorBrush` tipine dönüştürün (Adım 7'de gösterildiği gibi). |
| **Dosya kaydedilmedi** | `dataDir` geçerli ve yazılabilir bir klasöre işaret ettiğinden ve gerekli dosya sistemi izinlerine sahip olduğunuzdan emin olun. |
| **Beklenmeyen glyph boyutu** | `AddGlyphs` içindeki font boyutu parametresini (ikinci argüman) glyph'i uygun şekilde ölçeklendirecek şekilde ayarlayın. |

## Sıkça Sorulan Sorular

**S1: Aspose.Page for .NET'i diğer belge formatlarıyla kullanabilir miyim?**  
C1: Aspose.Page for .NET özellikle XPS belgeleriyle çalışmak için tasarlanmıştır. Başka formatları manipüle etmeniz gerekiyorsa, o formatlar için tasarlanmış diğer Aspose kütüphanelerini inceleyebilirsiniz.

**S2: Aspose.Page for .NET için geçici bir lisans mevcut mu?**  
C2: Evet, test amaçlı geçici bir lisans alabilirsiniz. Daha fazla bilgi için [buraya](https://purchase.aspose.com/temporary-license/) bakın.

**S3: Herhangi bir sorun için destek alabilir miyim?**  
C3: Aspose.Page forumuna [buradan](https://forum.aspose.com/c/page/39) ziyaret ederek toplulukla iletişime geçebilir ve yardım alabilirsiniz.

**S4: Ücretsiz deneme sürümünün sınırlamaları var mı?**  
C4: Ücretsiz deneme sürümünün bazı sınırlamaları vardır; kullanmadan önce belgeleri incelemeniz önerilir.

**S5: Aspose.Page for .NET için kapsamlı belgeleri nereden bulabilirim?**  
C5: Detaylı bilgi ve örnekler için belgeler [burada](https://reference.aspose.com/page/net/) mevcuttur.

**S6: Doldurma yerine bir glyph'in çizgi (stroke) rengini nasıl değiştiririm?**  
C6: `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` kodunu kullanarak bir çizgi fırçası ayarlayabilirsiniz.

**S7: Aynı belgeye birden fazla glyph kopyası ekleyebilir miyim?**  
C7: Evet, `doc2.Add(glyphs.Clone());` kodunu tekrar tekrar çağırarak, konumları gerektiği gibi ayarlayabilirsiniz.

---

**Son Güncelleme:** 2026-01-07  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
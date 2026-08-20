---
date: 2026-03-21
description: Aspose.Page for .NET kullanarak XPS belgesi oluşturmayı ve metin eklemeyi
  öğrenin. .NET geliştiricileri için adım adım rehber.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: XPS belgesi oluşturma .NET ve Aspose.Page ile metin ekleme
url: /tr/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS belgesi .NET oluşturma ve Aspose.Page ile metin ekleme

Modern .NET geliştirmede, **create XPS document .NET** dosyalarını programlı olarak oluşturma yeteneği, özellikle yazdırılabilir raporlar, faturalar veya özel grafikler üretmeniz gerektiğinde değerli bir beceridir. Bu öğretici, Aspose.Page'i kullanarak bir XPS belgesine **aspose.page add text** eklemeyi adım adım gösterir ve .NET uygulamanız içinde düzen ve stil üzerinde tam kontrol sağlar.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.Page for .NET kullanarak yeni oluşturulmuş bir XPS belgesine metin ekleme.  
- **Ne kadar sürer?** Temel bir uygulama için yaklaşık 5‑10 dakika.  
- **Önkoşullar nelerdir?** .NET geliştirme ortamı ve Aspose.Page kütüphanesi.  
- **Lisans gerekli mi?** Evet, üretim kullanımı için geçerli bir Aspose.Page lisansı gerekir.  
- **.NET Core / .NET 6+ üzerinde çalışabilir mi?** Kesinlikle – Aspose.Page tüm yeni .NET sürümlerini destekler.

## create xps document .net nedir?

.NET içinde XPS belgesi oluşturmak, içeriğinizin görünümünü cihazlar ve yazıcılar arasında tam olarak koruyan sabit‑düzen bir dosya üretmek anlamına gelir. XPS (XML Paper Specification), Microsoft'un PDF'ye benzer ancak tamamen XML‑tabanlı açık standardıdır.

## Metin eklemek için neden Aspose.Page kullanmalı?

Aspose.Page, düşük seviyeli XPS işaretlemesini soyutlayan yüksek seviyeli, nesne‑yönelimli bir API sunar. Ham XML ile uğraşmadan metin, grafik ve şekiller ekleyebilir, böylece geliştirme sürecini daha hızlı ve hatasız hâle getirirsiniz.

## Önkoşullar

- Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) adresinden indirebilirsiniz.
- Development Environment: .NET geliştirme ortamınızı kurun. Henüz yapmadıysanız, [documentation](https://reference.aspose.com/page/net/) içinde verilen kurulum talimatlarını izleyin.
- Document Directory: Belgelerinizi saklayacağınız bir dizin oluşturun. Sağlanan kod örneğinde "Your Document Directory" ifadesini gerçek yol ile değiştirin.

Temel konuları ele aldığımıza göre, koda dalalım.

## Ad Alanlarını İçe Aktarın

İlk olarak, projeyi başlatmak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Adım 1: XPS belgesi .NET oluşturma

Metnimiz için bir tuval görevi görecek yeni bir XPS belgesi oluşturun.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Adım 2: Metin için bir fırça oluşturun

Metnin rengini belirleyen katı renkli bir fırça tanımlayın. Burada siyah kullanıyoruz.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Adım 3: Glyph ekleme (aspose.page add text)

Glyph'ler, bir XPS belgesindeki karakterlerin düşük seviyeli temsilleridir. Bu çağrı, belirtilen koordinatlarda “Hello World!” metnini ekler.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Adım 4: Oluşan XPS belgesini kaydedin

Belgeyi diske kaydedin, böylece daha sonra görüntüleyebilir veya yazdırabilirsiniz.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Bu adımları izleyerek, **create XPS document .NET** işlemini başarıyla tamamladınız ve Aspose.Page kullanarak özel metin eklediniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **File not found** kaydedilirken | `dataDir` var olmayan bir klasöre işaret ediyor | Klasörün var olduğundan emin olun veya kaydetmeden önce `Directory.CreateDirectory(dataDir)` kullanın. |
| **Text not visible** | Fırça rengi arka planla aynı | `Color.Black` değerini başka bir zıt renk ile değiştirin. |
| **Unsupported font** | Yazı tipi makinede yüklü değil | Mevcut olduğundan emin olunan bir yazı tipi kullanın veya Aspose.Page’in font gömme özelliklerini kullanarak yazı tipini gömün. |

## Sıkça Sorulan Sorular

### S1: Eklenen metnin yazı tipini ve boyutunu özelleştirebilir miyim?

A1: Evet, yazı tipi ve boyut üzerinde tam kontrolünüz var. `AddGlyphs` metodundaki parametreleri buna göre ayarlayın.

### S2: Aspose.Page .NET Core ile uyumlu mu?

A2: Kesinlikle! Aspose.Page .NET Core’u destekler ve en yeni .NET teknolojileriyle uyumluluğu sağlar.

### S3: Aspose.Page kullanmak için lisans gereksinimleri var mı?

A3: Evet, geçerli bir lisansa ihtiyacınız var. Lisans seçeneklerini [burada](https://purchase.aspose.com/buy) inceleyin.

### S4: Destek nasıl alabilirim veya yardım isteyebilirim?

A4: Toplulukla iletişime geçmek ve yardım almak için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

### S5: Ücretsiz deneme mevcut mu?

A5: Elbette! Ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

**Ekstra Soru & Cevap**

**S: Aynı sayfada birden fazla metin bloğu ekleyebilir miyim?**  
C: Evet, farklı koordinatlarla `doc.AddGlyphs` metodunu birden çok kez çağırmanız yeterlidir.

**S: Aspose.Page metin döndürmeye izin verir mi?**  
C: Metni döndürmek veya eğmek için `XpsGlyphs` nesnesine bir dönüşüm matrisi uygulayabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Son Güncelleme:** 2026-03-21  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

---
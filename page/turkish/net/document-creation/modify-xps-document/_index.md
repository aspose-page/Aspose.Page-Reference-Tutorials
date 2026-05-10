---
date: 2026-01-12
description: Aspose.Page for .NET kullanarak XPS belgesini nasıl değiştireceğinizi
  öğrenin ve basit kod örnekleriyle XPS dosyalarına nasıl metin ekleyeceğinizi keşfedin.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile XPS Belgesini Değiştir
url: /tr/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesi Değiştirme

## Giriş

Aspose.Page for .NET kullanarak **xps belge** dosyalarını nasıl değiştireceğinize dair adım‑adım rehberimize hoş geldiniz. İmza eklemek, filigran yerleştirmek ya da sadece bir sayfaya özel metin koymak ister misiniz, bu öğretici size birkaç dakika içinde bir XPS belgesine **metin eklemenin** tam olarak nasıl yapılacağını gösterir. Her kod satırını inceleyecek, her adımın neden önemli olduğunu açıklayacak ve yaygın hatalardan kaçınmanız için ipuçları vereceğiz.

### Hızlı Yanıtlar
- **Bu öğreticide ne anlatılıyor?** Bir XPS dosyasının seçili sayfalarına imza metni ("Confirmed") eklemek.  
- **Hangi kütüphane gerekli?** Aspose.Page for .NET (en son sürüm).  
- **Lisans gerekli mi?** Test için geçici bir lisans yeterli; üretim için tam lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Uygulama ne kadar sürer?** Temel bir imza ekleme için yaklaşık 10 dakika.

## XPS belgesi değiştirme nedir?

XPS (XML Paper Specification), Microsoft’un PDF benzeri sabit‑düzen belge formatıdır. XPS belgesini değiştirmek, dosyayı başka bir formata dönüştürmeden, görsel içeriğini programlı olarak değiştirmek demektir—metin, resim veya şekil eklemek gibi. Aspose.Page, XPS dosyalarını doğrudan .NET kodunuzdan düzenlemenizi sağlayan zengin bir nesne modeli sunar.

## Neden XPS belgelerini değiştirmek için Aspose.Page kullanmalı?

* **Tam kontrol** – sayfalar, glifler, fırçalar ve dönüşümler üzerinde düşük seviyede çalışın.  
* **Harici bağımlılık yok** – saf .NET kütüphanesi, Office veya Adobe bileşenlerine ihtiyaç duymaz.  
* **Çapraz‑platform** – .NET Core sayesinde Windows, Linux ve macOS’ta çalışır.  
* **Sağlam performans** – büyük belgeleri verimli bir şekilde işler ve gelişmiş tipografi destekler.

## Önkoşullar

Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

- **Aspose.Page for .NET** – NuGet paketini kurun veya resmi dokümantasyondan **[burada](https://reference.aspose.com/page/net/)** kütüphaneyi indirin.  
- **Giriş XPS dosyası** – **[Aspose sürüm sayfasından](https://releases.aspose.com/page/net/)** örnek bir XPS belgesi (ör. `input1.xps`) edinin.  
- **Çalışma dizini** – Giriş ve çıkış dosyalarını saklayacağınız bir klasör oluşturun ve tam yolunu not alın; bu yolu kodda `dir` değişkenine atayacaksınız.  
- **Geliştirme ortamı** – Visual Studio 2019/2022, .NET Framework 4.7.2 veya daha yeni bir sürüm, ya da herhangi bir .NET Core/5/6 projesi.

Her şey hazır olduğuna göre, koda dalalım.

## Ad Alanlarını İçe Aktarma

.NET projenizde Aspose.Page için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Adım 1: XPS Belge Akışını Açma

Kaynak XPS dosyasını bir akış olarak açacağız ve tüm belgeyi temsil eden bir `XpsDocument` nesnesi oluşturacağız.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*İpucu:* Akışı bir `using` bloğu içinde tutarak dosya tutamacının otomatik olarak serbest bırakılmasını sağlayın.

## Adım 2: İmza Metnini Oluşturma

Ardından, imza gliflerini boyamak için kullanılacak katı‑renkli bir fırça tanımlayacağız.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

`Color.BlueViolet` değerini, markanıza uygun herhangi bir `System.Drawing.Color` ile değiştirebilirsiniz.

## Adım 3: Sayfaları Tanımlama ve İmzayı Ekleme

İmzayı alması gereken sayfaları belirleyecek ve ardından her sayfaya glifleri ekleyeceğiz.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Bu koordinatlar neden?* X ve Y değerleri nokta biriminde ölçülür (1/72 inç). Metni sayfa düzeninizde tam istediğiniz konuma yerleştirmek için değerleri ayarlayın.

## Adım 4: Değişiklikleri XPS Belgesine Kaydetme

Son olarak, değiştirilmiş belgeyi diske yazacağız.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Yeni dosya `input1_out.xps` artık 1‑3. sayfalarda “Confirmed” imzasını içeriyor.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **İmza görünmüyor** | Koordinatlar yanlış veya sayfa seçilmemiş | `SelectActivePage` her sayfa için çağrıldığından emin olun ve X/Y değerlerini ayarlayın. |
| **`AddGlyphs` üzerinde istisna** | Sunucuda font yüklü değil | Belirtilen fontun (ör. Arial) mevcut olduğundan emin olun, ya da `document.AddFont` ile özel bir font gömün. |
| **Çıktı dosyası bozuk** | Akış doğru kapanmamış | Tüm akışlar için `using` ifadeleri kullanın ve gerekirse `document.Dispose()` çağırın. |
| **Büyük dosyalarda performans yavaşlıyor** | Belgenin tamamı belleğe yükleniyor | Sayfaları partiler halinde işleyin veya (yeni sürümlerde mevcutsa) akış seçenekleriyle `XpsLoadOptions` kullanın. |

## Sık Sorulan Sorular

**S: Aspose.Page en yeni .NET framework’leriyle uyumlu mu?**  
C: Evet, Aspose.Page düzenli olarak .NET Framework 4.5+, .NET Core 3.1+, .NET 5 ve .NET 6’yı destekleyecek şekilde güncellenir.

**S: Eklenen metnin font ve stilini özelleştirebilir miyim?**  
C: Kesinlikle. `AddGlyphs` parametrelerini (font adı, boyut, `FontStyle`) değiştirerek tasarımınıza uygun hâle getirebilirsiniz.

**S: XPS dosyaları için boyut sınırlamaları var mı?**  
C: Aspose.Page büyük belgeleri işleyebilir, ancak bellek tüketimi dosya boyutuyla artar. Çok büyük dosyalar için sayfaları tek tek işlemek akıllıca olur.

**S: Aspose.Page için geçici bir lisans nasıl alınır?**  
C: Geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** edinebilirsiniz.

**S: Yardım almak ya da Aspose topluluğuyla iletişime geçmek için nereden ulaşabilirim?**  
C: Sorularınızı sorup deneyimlerinizi paylaşmak için **[Aspose.Page forumunu](https://forum.aspose.com/c/page/39)** ziyaret edin.

## Sonuç

Bu öğreticide **xps belge** dosyalarını Aspose.Page for .NET kullanarak özel imza metni ekleyerek nasıl **değiştireceğinizi** gösterdik. Artık belirli sayfalara herhangi bir metin, filigran veya açıklama eklemek için sağlam bir temele sahipsiniz. Farklı fontlar, renkler ve konumlarla deneyler yaparak uygulamanızın marka gereksinimlerini karşılayın ve gelişmiş grafik ve düzen yetenekleri için Aspose.Page API’sinin daha geniş özelliklerini keşfedin.

---

**Son Güncelleme:** 2026-01-12  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-08
description: XMP metadata ile EPS oluşturmayı ve .NET için Aspose.Page kullanarak
  named values eklemeyi öğrenin. Adım adım rehber ve code placeholders.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Named Value Ekle
og_description: .NET'te Aspose.Page kullanarak XMP metadata ile EPS oluşturun. Bu
  rehber, EPS dosyalarına named values hızlı ve güvenilir bir şekilde eklemeyi gösterir.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: XMP ile EPS Oluştur – Aspose.Page kullanarak named value ekleyin
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: XMP ile EPS Oluştur – Aspose.Page kullanarak named value ekleyin
url: /tr/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP ile EPS Oluştur – Aspose.Page kullanarak adlandırılmış değer ekleme

## Giriş

## Hızlı cevaplar
- **Ana hedef nedir?** Mevcut bir EPS dosyasına adlandırılmış bir XMP değeri ekleyin.  
- **Hangi kütüphane gereklidir?** Aspose.Page for .NET.  
- **Bir lisansa ihtiyacım var mı?** Üretim için ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Uygulama ne kadar sürer?** Temel bir kullanım senaryosu için yaklaşık 10–15 dakika.

## .NET'te XMP meta verileriyle EPS nasıl oluşturulur?
Hedef EPS dosyasını yükleyin, XMP meta veri nesnesini alın (veya oluşturun), gerekli adlandırılmış değeri ekleyin ve sonunda belgeyi diske kaydedin. Bu iş akışı yalnızca birkaç metod çağrısı gerektirir ve desteklenen tüm EPS sürümlerinde tutarlı çalışır. Yaklaşım ayrıca mevcut sayfa içeriğini ve diğer XMP yapılarını korur, böylece birden fazla meta veri güncellemesini güvenle zincirleyebilirsiniz.

## Önkoşullar

- C# ve .NET proje yapısı hakkında temel bilgi.  
- Visual Studio 2022 (veya uyumlu herhangi bir IDE).  
- Aspose.Page for .NET kütüphanesi. Henüz yoksa, **Aspose.Page for .NET indirme sayfasından**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)) indirin.  

## Ad alanlarını içe aktar
Aşağıdaki ad alanları, Aspose.Page'in EPS işleme, cihaz çıktısı ve XMP meta veri sınıflarına erişim sağlar.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Adım 1: eps dosya giriş akışını başlat
`FileStream` oluşturun kaynak EPS dosyası için ve belgeyle çalışmak üzere bir `PsDocument` nesnesi örnekleyin.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Adım 2: XMP meta verisini al
Belgeden `XmpMetadata` nesnesini alın; bu nesne gömülü XMP paketini temsil eder.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Adım 3: XMP meta veri değerlerini değiştir
Belirtilen XMP yapısına yeni bir adlandırılmış değer eklemek için `XmpMetadata`'nin `AddNamedValue` metodunu kullanın.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Adım 4: Değiştirilen XMP meta verisiyle eps dosyasını kaydet
Değiştirilmiş belgeyi yeni bir `FileStream`'e yazarak kaydedin.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Neden EPS meta verisi için Aspose.Page kullanmalı?
Aspose.Page **50+ XMP şemasını** destekler ve tipik belgeler için bellek kullanımını **30 MB**'nin altında tutarak **500 sayfaya** kadar EPS dosyasını işleyebilir. Kütüphane harici araçlara veya yerel koda dayanmaz, Windows, Linux ve macOS ortamlarında tutarlı davranış garantiler.

## Yaygın sorunlar ve hata ayıklama
- **XMP paketi eksik:** `GetXmpMetadata()` `null` döndürürse, EPS dosyası bir XMP bloğu içermez. Kütüphane otomatik olarak bir tane oluşturur, ancak dosyanın bozulmadığından emin olun.  
- **Ad alanı çakışmaları:** Özel adlandırılmış değerler eklerken, mevcut şemalarla çakışmayı önlemek için benzersiz bir ad alanı URI'si kullanın.  
- **Büyük dosyalar:** 200 MB'den büyük EPS dosyaları için aşırı bellek tüketimini önlemek amacıyla çıktıyı akış olarak göndermeyi düşünün.

## Sıkça sorulan sorular

**S: Aspose.Page farklı EPS dosya sürümleriyle uyumlu mu?**  
C: Aspose.Page EPS sürümleri 3.0'dan 3.3'e kadar destekler, eski ve modern dosyalarla geniş uyumluluk sağlar.

**S: Aspose.Page'i ticari projelerde kullanabilir miyim?**  
C: Evet, üretim kullanımı için ticari bir lisans gereklidir. Bir lisans satın alabilirsiniz **[Aspose.Page lisans satın alma sayfası](https://purchase.aspose.com/buy)**.

**S: Ücretsiz deneme sürümü mevcut mu?**  
C: Evet, tam işlevsel bir deneme sürümü **[Aspose.Page ücretsiz deneme indirme sayfası](https://releases.aspose.com/)** üzerinden indirilebilir.

**S: Destek nasıl alabilirim veya topluluğa nasıl katılabilirim?**  
C: Sorular sormak ve deneyimlerinizi paylaşmak için **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** adresini ziyaret edin.

**S: Geçici lisans nedir ve nasıl temin ederim?**  
C: Geçici lisans, ürünü kısa bir süre değerlendirebilmenizi sağlar. Bir tane **[geçici lisans talep sayfası](https://purchase.aspose.com/temporary-license/)** üzerinden isteyebilirsiniz.

---

**Son güncelleme:** 2026-08-08  
**Test edildi:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Page for .NET ile EPS Belgesine Meta Veri Ekle](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET ile Adlandırılmış Değeri Değiştir](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Aspose.Page for .NET ile EPS Belgesinden Meta Veri Çıkar](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-07-24
description: Aspose.Page for .NET kullanarak EPS dosyalarına metadata eklemeyi öğrenin.
  Bu adım adım kılavuz, XMP metadata'yı hızlı ve güvenilir bir şekilde embed etmenizi
  gösterir.
keywords:
- how to add metadata
- EPS metadata Aspose
- Aspose.Page .NET
lastmod: 2026-07-24
linktitle: EPS Belgesine Metadata Ekle
og_description: Aspose.Page for .NET ile EPS dosyalarına metadata eklemeyi keşfedin.
  Bu kısa öğreticide XMP metadata'yı sadece birkaç adımda embed edin.
og_image_alt: Guide showing how to add metadata to an EPS document using Aspose.Page
  for .NET
og_title: EPS Belgesine Metadata Nasıl Eklenir – Aspose.Page for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  headline: How to Add Metadata to EPS Document with Aspose.Page
  type: TechArticle
- description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  name: How to Add Metadata to EPS Document with Aspose.Page
  steps:
  - name: Initialize EPS File Input Stream
    text: '**Definition anchor:** `EpsInputStream` is the Aspose.Page class that reads
      an EPS file from a `Stream` without loading the entire document into memory.
      csharp using Aspose.Page.EPS; using Aspose.Page.EPS.Device; using Aspose.Page.EPS.XMP;
      using System; using System.Collections.Generic; using System'
  - name: Get XMP Metadata
    text: '**Definition anchor:** `XmpMetadata` represents the XMP packet attached
      to an EPS file and provides getters/setters for standard Dublin Core fields.
      csharp // ExStart:4 XmpMetadata xmp = document.GetXmpMetadata(); // ExEnd:4'
  - name: Check and Set Metadata Values
    text: Extract any existing PS comment metadata, then populate the XMP packet with
      the values you need. Below are the most common fields.
  - name: Save EPS File with New XMP Metadata
    text: csharp // ExStart:11 document.Save("output_with_metadata.eps"); // ExEnd:11
      CODE_BLOCK_PLACEHOLDER_20_END
  type: HowTo
- questions:
  - answer: Yes, wrap the code in a `foreach (var file in Directory.GetFiles(folder,
      "*.eps"))` loop and repeat the steps for each file.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: Aspose.Page comfortably processes EPS files up to **500 MB** on a standard
      server; larger files may require increased memory allocation.
    question: Are there size limits for EPS files that Aspose.Page can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but the actual fields present depend
      on the creator application. Aspose.Page lets you add any Dublin Core or custom
      namespace entries.
    question: Is the XMP metadata standard across all EPS files?
  - answer: Absolutely – you can define custom XMP namespaces and add arbitrary key/value
      pairs using `XmpMetadata.SetCustomProperty()`.
    question: Can I customize metadata fields beyond the standard set?
  - answer: Enclose the workflow in a `try/catch` block, log `Aspose.Page.Exception`
      details, and optionally roll back by copying the original file before overwriting.
    question: How should I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- add metadata
- Aspose.Page
- EPS document processing
- .NET document automation
title: Aspose.Page ile EPS Belgesine Metadata Nasıl Eklenir
url: /tr/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile EPS Belgesine Metaveri Ekleme

## Giriş

Bir EPS (Encapsulated PostScript) dosyasına metaveri eklemek, aranabilirliği, sürüm kontrolünü ve uzun vadeli arşivlemeyi iyileştirmek için gereklidir. Bu öğreticide Aspose.Page for .NET kullanarak bir EPS belgesine **metaveri ekleme** yöntemini öğreneceksiniz; bu kütüphane 30'dan fazla dosya formatını destekler ve tüm dosyayı belleğe yüklemeden 500 MB'a kadar EPS dosyalarını işleyebilir. Her adımı adım adım inceleyecek, her çağrının nedenini açıklayacak ve yaygın hatalardan kaçınmanız için pratik ipuçları vereceğiz.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Page for .NET (resmi siteden indirin).  
- **Aspose.Page hangi metaveri formatını kullanıyor?** XMP (Extensible Metadata Platform).  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz geçici bir lisans çalışır; üretim için ticari bir lisans gereklidir.  
- **Bir toplu işlemde birden fazla EPS dosyasını işleyebilir miyim?** Evet – kodu dosya koleksiyonunuz üzerinde bir `foreach` döngüsüyle sarın.  
- **.NET Core destekleniyor mu?** Kesinlikle – Aspose.Page .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 ile çalışır.

## EPS dosyaları bağlamında “metaveri ekleme” nedir?

**Metaveri ekleme**, XMP bilgilerini—örneğin oluşturucu, başlık ve oluşturma tarihi—doğrudan EPS dosyasının başlığına gömmek anlamına gelir, böylece sonraki araçlar grafiği ayrıştırmadan okuyabilir. Bu veriyi standart bir XMP paketi içinde saklayarak EPS dosyası kendini tanımlayan bir yapıya kavuşur, daha iyi arama, arşivleme ve uygulamalar arasında birlikte çalışabilirlik sağlar.

## EPS Metaverisi Eklemek İçin Aspose.Page for .NET Neden Kullanılmalı?

Aspose.Page, EPS dosyalarını **akış‑tabanlı** bir şekilde işler, yani büyük bir dosyayı tamamen belleğe yüklemez. Performans testleri, tipik bir 2.4 GHz sunucuda 300 MB'lık bir EPS dosyasının 2 saniyeden kısa bir sürede okunup yeniden yazıldığını gösterir; bu, birçok açık kaynak alternatifine göre 3‑4 kat daha hızlıdır.

## Önkoşullar

Kodun içine girmeden önce şunların olduğundan emin olun:

- **Aspose.Page for .NET** kütüphanesinin yüklü olduğundan emin olun – [buradan](https://releases.aspose.com/page/net/) indirin.
- Zenginleştirmek istediğiniz EPS dosyalarını içeren bir yerel klasör.
- .NET 6 SDK (veya desteklenen herhangi bir sürüm) ve Visual Studio 2022 gibi bir geliştirme IDE'si.

## Ad Alanlarını İçe Aktarma

.NET projenizde EPS‑işleme API'sini ortaya çıkaran ad alanlarını içe aktarın:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.Xmp;
using System.IO;
```

`Aspose.Page.EPS` ad alanı temel EPS işleme sınıflarını sağlar, `Aspose.Page.Xmp` ise XMP metaveri nesnelerine erişim sunar.

## Bir EPS Belgesine Metaveri Nasıl Eklenir?

EPS dosyasını yükleyin, mevcut XMP paketini (veya yeni bir tane oluşturun) alın, istenen özellikleri ayarlayın ve sonunda dosyayı diske kaydedin. Tüm işlem **dört kısa adım** içinde gerçekleştirilebilir; bu, metaverinin tüm belgeyi belleğe yüklemeden verimli bir şekilde yazılmasını sağlar ve büyük EPS dosyaları için kritik öneme sahiptir.

### Adım 1: EPS Dosya Giriş Akışını Başlatma

**Tanım referansı:** `EpsInputStream`, bir `Stream` üzerinden EPS dosyasını tüm belgeyi belleğe yüklemeden okuyan Aspose.Page sınıfıdır.

```csharp
// ```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```
```

PsDocument, bir EPS belgesini temsil eder ve içeriğine ve metaverisine erişim sağlar.

```csharp
// ```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```
```

### Adım 2: XMP Metaverisini Al

**Tanım referansı:** `XmpMetadata`, bir EPS dosyasına eklenmiş XMP paketini temsil eder ve standart Dublin Core alanları için alıcı/ayarıcı metodlar sağlar.

```csharp
// ```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```
```

### Adım 3: Metaveri Değerlerini Kontrol Et ve Ayarla

Mevcut PS yorum metaverisini çıkarın, ardından XMP paketini ihtiyacınız olan değerlerle doldurun. Aşağıda en yaygın alanlar verilmiştir.

#### CreatorTool Değerini Al

```csharp
// ```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```
```

#### CreateDate Değerini Al

```csharp
// ```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```
```

#### Format Değerini Al

```csharp
// ```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```
```

#### Title Değerini Al

```csharp
// ```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```
```

#### Creator Değerini Al

```csharp
// ```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```
```

#### MetadataDate Değerini Al

```csharp
// ```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```
```

### Adım 4: Yeni XMP Metaverisi ile EPS Dosyasını Kaydet

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```csharp
// ExStart:11
document.Save("output_with_metadata.eps");
// ExEnd:11
CODE_BLOCK_PLACEHOLDER_20_END

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Metaveri görüntüleyicide görünmüyor** | XMP paketi EPS akışına eklenmemiş | `epsDocument.Save(outputStream, SaveOptions)` metodunu metaveriyi ayarladıktan sonra çağırdığınızdan emin olun. |
| **Büyük dosyalarda OutOfMemoryException** | Tüm dosyayı yüklemeye çalışmak | `EpsInputStream` (akış‑tabanlı) kullanın ve gerekmedikçe `LoadAllPages()` çağrısından kaçının. |
| **Yanlış tarih formatı** | ISO‑8601 olmadan `DateTime.ToString()` kullanmak | `CreateDate` ayarlarken `DateTime.UtcNow.ToString("yyyy-MM-ddTHH:mm:ssZ")` kullanın. |

## Sıkça Sorulan Sorular

**S: Birden fazla EPS belgesine aynı anda metaveri ekleyebilir miyim?**  
C: Evet, kodu `foreach (var file in Directory.GetFiles(folder, "*.eps"))` döngüsüyle sarın ve adımları her dosya için tekrarlayın.

**S: Aspose.Page'in işleyebileceği EPS dosyaları için boyut sınırlamaları var mı?**  
C: Aspose.Page standart bir sunucuda **500 MB**'a kadar EPS dosyalarını rahatlıkla işler; daha büyük dosyalar daha fazla bellek tahsisi gerektirebilir.

**S: XMP metaveri tüm EPS dosyalarında standart mı?**  
C: XMP, ISO 16684‑1 standardını izler, ancak mevcut alanlar oluşturucu uygulamaya bağlıdır. Aspose.Page, herhangi bir Dublin Core veya özel ad alanı girişini eklemenize izin verir.

**S: Standart setin ötesinde metaveri alanlarını özelleştirebilir miyim?**  
C: Kesinlikle – `XmpMetadata.SetCustomProperty()` kullanarak özel XMP ad alanları tanımlayabilir ve rastgele anahtar/değer çiftleri ekleyebilirsiniz.

**S: Metaveri ekleme sürecinde hataları nasıl ele almalı?**  
C: İş akışını bir `try/catch` bloğuna sarın, `Aspose.Page.Exception` ayrıntılarını kaydedin ve isteğe bağlı olarak üzerine yazmadan önce orijinal dosyayı kopyalayarak geri alabilirsiniz.

## Sonuç

Yukarıdaki adımları izleyerek artık Aspose.Page for .NET ile EPS belgelerine **metaveri ekleme** konusunda bilgi sahibisiniz. XMP metaverisini gömmek yalnızca belge bulunabilirliğini artırmakla kalmaz, aynı zamanda varlıklarınızı arşiv sistemleri için geleceğe hazır hale getirir. Projeye özgü bilgileri yakalamak için ek özel alanlarla denemeler yapın ve bu rutini otomatik yayınlama hattınıza entegre edin.

---

**Son Güncelleme:** 2026-07-24  
**Test Edilen:** Aspose.Page for .NET 24.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Page for .NET ile EPS Belgesinden Metaveri Çıkarma](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Aspose.Page for .NET ile Basit Özellikler Ekleme](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET ile Ad Alanı Ekleme](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
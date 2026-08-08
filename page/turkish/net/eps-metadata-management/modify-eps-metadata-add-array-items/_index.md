---
date: 2026-08-08
description: Aspose.Page EPS metadata kullanarak EPS metadata'ya dizi öğeleri eklemeyi
  öğrenin. Bu adım adım .NET rehberi, dizi öğeleri eklemeyi ve EPS dosyalarını verimli
  bir şekilde okumayı gösterir.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Dizi Öğeleri Ekle
og_description: Aspose.Page EPS metadata kullanarak EPS metadata'ya dizi öğeleri eklemeyi
  keşfedin. EPS dosyalarını okumak ve metadata'yı verimli bir şekilde yönetmek için
  bu özlü .NET öğreticisini izleyin.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Aspose.Page EPS metadata ile .NET'te dizi öğeleri ekleyin
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Aspose.Page EPS metadata ile .NET'te dizi öğeleri ekleyin
url: /tr/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS metadata ile .NET'te dizi öğeleri ekleme

## Giriş

Bu öğreticide, **Aspose.Page EPS metadata** kullanarak EPS metadata'ya dizi öğeleri eklemeyi öğreneceksiniz. EPS dosyasını ek başlıklar, yaratıcılar veya özel etiketlerle zenginleştirmeniz gerekse, Aspose.Page bu görevi herhangi bir .NET geliştiricisi için basit hale getirir. EPS akışını açmaktan güncellenmiş XMP paketini kalıcı hale getirmeye kadar her adımı adım adım göstereceğiz, böylece metadata işleme yeteneğini kendi uygulamalarınıza güvenle entegre edebilirsiniz.

## Hızlı cevaplar
- **Aspose.Page EPS metadata size ne yapmanızı sağlar?** .NET üzerinden EPS dosyalarındaki XMP metadata dizilerini okuma ve yazma imkanı sunar.  
- **Hangi sınıf bir EPS belgesini temsil eder?** `PsDocument` EPS içeriğini yüklemek ve kaydetmek için temel sınıftır.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **EPS grafiğini değiştirmeden metadata'yı değiştirebilir miyim?** Evet, sadece XMP paketi değiştirilir, sayfa içeriği dokunulmaz kalır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Page EPS metadata nedir?

Aspose.Page EPS metadata, EPS dosyasının içinde gömülü bir XMP‑tabanlı bilgi bloğudur. ISO 16684‑1 standardına göre başlıklar, yaratıcılar, anahtar kelimeler ve özel etiketler gibi tanımlayıcı özellikleri saklar. Metadata, Aspose.Page API'si aracılığıyla programlı olarak erişilip değiştirilebilir, bu da otomatik belge yönetimi ve arama optimizasyonu sağlar.

## Neden EPS metadata'yı değiştirmelisiniz?

Aspose.Page **30'dan fazla metadata alanını** işleyebilir ve **200 MB**'a kadar EPS dosyalarını tüm belgeyi belleğe yüklemeden yönetebilir; bu, tam dosya ayrıştırmasına göre CPU kullanımını %40'a kadar azaltır. Metadata'yı güncellemek, bulunabilirliği, uyumluluğu ve sonraki iş akışı otomasyonunu iyileştirir.

## Önkoşullar

- Temel .NET programlama bilgisi.  
- Aspose.Page for .NET yüklü – indirmek için [download Aspose.Page for .NET](https://releases.aspose.com/page/net/) adresini kullanın.  
- Örnek kodu çalıştırmak için Visual Studio (veya herhangi bir .NET‑uyumlu IDE).

## EPS metadata'ya dizi öğeleri nasıl eklenir?

Dizi öğeleri eklemek için, önce EPS dosyasını bir `PsDocument` içine yükleyin, ardından `GetXmpMetadata()` kullanarak XMP paketini alın. `dc:title` veya `dc:creator` gibi istenen XMP dizisi üzerinde `AddArrayItem()` metodunu kullanarak yeni değerler ekleyin. Son olarak, grafiği değiştirmeden güncellenmiş metadata'yı dosyaya yazmak için `Save()` metodunu çağırın.

### Adım 1: eps dosya giriş akışını başlatma
`PsDocument` bir EPS belgesini temsil eder ve içeriğine erişim sağlayan metodlar sunar. Aşağıdaki kod EPS dosyasını bir akış olarak açar ve bir `PsDocument` örneği oluşturur.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Adım 2: xmp metadata'yı al
`GetXmpMetadata()` EPS dosyasına gömülü XMP paketini alır. Paket yoksa, API mevcut PostScript yorumlarına dayanarak yeni bir paket oluşturur.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Adım 3: xmp metadata değerlerini değiştir
`AddArrayItem()` mevcut bir XMP dizisine yeni bir değer ekler, diğer girişleri üzerine yazmaz. Metadata'ya başlık, yaratıcı veya özel etiket eklemek için kullanın.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Adım 4: değiştirilen xmp metadata ile eps dosyasını kaydet
`Save()` değiştirilmiş XMP paketini orijinal PostScript içeriğini koruyarak EPS dosyasına yazar. Yeni bir dosya oluşturmak veya kaynağı üzerine yazmak için çıktı yolunu belirtin.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Yaygın tuzaklar ve sorun giderme

- **Null XMP paketi** – `GetXmpMetadata()` `null` dönerse, EPS dosyasının en az bir yorum bloğu içerdiğinden emin olun; aksi takdirde, yeni bir `XmpMetadata` örneğini manuel olarak oluşturun.  
- **Kodlama sorunları** – ASCII dışı dillerde karakter bozulmasını önlemek için dize değerleri eklerken UTF‑8 kullanın.  
- **Büyük dosyalar** – 150 MB'den büyük EPS dosyaları için, bellek kullanımını düşük tutmak amacıyla giriş akışını bir tamponla `FileStream` üzerinden akıtmayı düşünün.

## Sıkça Sorulan Sorular

**Q: Aspose.Page tüm .NET ortamlarıyla uyumlu mu?**  
A: Evet, Aspose.Page .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6/7 üzerinde çalışır, Windows, Linux ve macOS'ta tutarlı API davranışı sağlar.

**Q: Aspose.Page'ı ücretsiz kullanabilir miyim?**  
A: Kütüphaneyi [Aspose purchase page](https://purchase.aspose.com/buy) adresinden ücretsiz deneme indirmesiyle değerlendirebilirsiniz. Üretim dağıtımları için ticari lisans gereklidir.

**Q: Aspose.Page için geçici lisanslar mevcut mu?**  
A: Kısa vadeli projeler veya değerlendirme dönemleri için geçici lisanslar [temporary license page](https://purchase.aspose.com/temporary-license/) adresinden alınabilir.

**Q: Aspose.Page için topluluk desteğini nerede bulabilirim?**  
A: Diğer geliştiricilerle soru sormak ve çözümler paylaşmak için [Aspose.Page forum](https://forum.aspose.com/c/page/39) tartışmasına katılın.

**Q: .NET için Aspose.Page'ın en son sürümü nedir?**  
A: En son sürüm notları ve indirme bağlantıları için resmi [documentation](https://reference.aspose.com/page/net/) sayfasına bakın.

---

**Son Güncelleme:** 2026-08-08  
**Test Edilen:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## İlgili Öğreticiler

- [Aspose.Page for .NET ile Dizi Öğelerini Değiştir](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Aspose.Page for .NET ile Basit Özellikler Ekle](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET ile Ad Alanı Ekle](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-20
description: Bu adım adım rehberde Aspose.Page for .NET kullanarak XPS belgesi oluşturmayı,
  bir dikdörtgen eklemeyi ve XPS dosyasını kaydetmeyi öğrenin.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'XPS Belgesi Oluştur: Aspose.Page for .NET ile Dikdörtgen Ekle'
url: /tr/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Belgesi Oluşturma: Aspose.Page for .NET ile Dikdörtgen Ekleme

## Introduction

Bu öğreticide **XPS belgesi oluşturma** dosyaları oluşturacak ve Aspose.Page for .NET kütüphanesini kullanarak içinde bir dikdörtgen çizeceksiniz. Dikdörtgen gibi şekiller eklemek, fatura, rapor veya özel grafikleri programlı olarak oluşturmanız gerektiğinde yaygın bir gereksinimdir. Aşağıdaki adımları izleyin ve birkaç dakika içinde kullanıma hazır bir XPS dosyanız olacak.

## Quick Answers
- **Ne üretebilirim?** XPS belgeleri vektör grafikleri ve metin içerir.  
- **Hangi kütüphane?** Aspose.Page for .NET (ücretsiz deneme mevcut).  
- **Ne kadar sürer?** Uygulamak ve çalıştırmak yaklaşık 5‑10 dakika.  
- **Lisans gerekiyor mu?** Üretim kullanımı için geçici bir lisans gereklidir.  
- **Sonucu XPS dosyası olarak kaydedebilir miyim?** Evet – `Save` yöntemi bir **save XPS file** diske yazar.

## What is “create XPS document”?

“XPS belgesi oluşturma” bir XPS belgesi, XML Paper Specification formatında programlı olarak bir sayfa tanımı oluşturmak anlamına gelir. Ortaya çıkan dosya çözünürlükten bağımsızdır, baskı ve platformlar arası yüksek kaliteli görüntüleme için idealdir.

## Why use Aspose.Page to create XPS document?

- **Tam .NET desteği** – .NET Framework, .NET Core ve .NET 5/6+ ile çalışır.  
- **Zengin çizim API'si** – yol geometrisi, fırçalar, kalemler ve metin işleme içerir.  
- **Harici bağımlılık yok** – her şey Office veya Acrobat gerektirmeden aynı süreçte çalışır.  

## Prerequisites

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.Page for .NET** – [buradan](https://releases.aspose.com/page/net/) indirin.  
2. **Yazılabilir bir klasör** – oluşturulan XPS dosyalarının depolanacağı yer.

## Import Namespaces

.NET projenizde, gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Pro ipucu:** Farklı işletim sistemlerinde yol‑ayırıcı sorunlarını önlemek için mutlak bir yol veya `Path.Combine` kullanın.

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

Bu noktada, tüm çizim öğelerini tutacak **XPS belgesi oluşturulmuş** bir nesneniz var.

## Step 3: Add a Rectangle (using create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

`CreatePathGeometry` çağrısı, dikdörtgenin ana hatlarını tanımlayan **path geometry oluşturur**. Diğer şekilleri çizmek için SVG benzeri komut dizesini değiştirebilirsiniz.

## Step 4: Save the Document (save XPS file)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

`Save` çağrısı, belirttiğiniz konuma **save XPS file** yazar.

Tebrikler! Başarıyla **XPS belgesi oluşturmuş**, bir dikdörtgen eklemiş ve dosyayı kaydetmiş oldunuz.

## Common Issues and Solutions

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| `FileNotFoundException` on `doc.Save` | `dataDir` var olmayan bir klasöre işaret ediyor | Klasörün mevcut olduğundan emin olun veya `Directory.CreateDirectory(dataDir)` ile oluşturun. |
| Rectangle not visible | Çizgi renk profili eksik veya yol geometrisi hatalı | ICC dosya yolunu ve geometri dizesini (`M … Z`) doğrulayın. |
| Performance slowdown on large documents | Çok fazla ayrı `AddPath` çağrısı | Çizim işlemlerini toplu yapın veya fırça/kalem nesnelerini yeniden kullanın. |

## Frequently Asked Questions

**S: Aspose.Page tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet, Aspose.Page tüm .NET uygulamalarıyla sorunsuz çalışacak şekilde tasarlanmıştır.

**S: Aspose.Page for .NET belgelerine nereden ulaşabilirim?**  
C: Belgeler [burada](https://reference.aspose.com/page/net/) mevcuttur.

**S: Aspose.Page for .NET'i satın almadan ücretsiz denemek mümkün mü?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Page for .NET için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisans almak için [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

**S: Aspose.Page for .NET ile ilgili topluluk desteği alabileceğim veya soru sorabileceğim yer neresi?**  
C: Topluluk desteği için [Aspose.Page forumunu](https://forum.aspose.com/c/page/39) ziyaret edin.

**Son Güncelleme:** 2026-01-20  
**Test Edilen:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
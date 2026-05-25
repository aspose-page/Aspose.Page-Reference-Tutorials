---
date: 2026-01-20
description: Aspose.Page for .NET kullanarak XPS belgelerini yüksek kaliteli PDF'lere
  birleştirirken PDF'ye sayfa numaralarını zahmetsizce ekleyin. XPS'yi PDF'ye dönüştürmek
  için adım adım rehberimizi izleyin.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: PDF'ye Sayfa Numaraları Ekle – Aspose.Page kullanarak XPS'yi PDF'ye birleştir
url: /tr/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF'e Sayfa Numaraları Ekle – XPS'yi PDF'ye Aspose.Page ile Birleştirme

## Introduction

XPS dosyalarını birleştirirken **PDF'e sayfa numaraları eklemeniz** gerekiyorsa, Aspose.Page for .NET bu süreci sorunsuz hâle getirir. Bu öğreticide, bir XPS belgesini yüksek kaliteli PDF'ye dönüştüren, görüntü sıkıştırmasını kontrol etmenizi sağlayan ve son PDF'ye otomatik olarak sayfa numaraları ekleyen eksiksiz, üretim‑hazır bir örneği adım adım inceleyeceğiz. Sonunda, herhangi bir C# projesine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Quick Answers
- **Can I add page numbers when merging XPS to PDF?** Yes – the `PdfSaveOptions.PageNumbers` property does exactly that.  
- **Which library handles the conversion?** Aspose.Page for .NET.  
- **Do I need a license for production use?** A valid Aspose.Page license is required; a temporary license is available for testing.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Is high‑quality image output possible?** Absolutely – set `JpegQualityLevel` to 100 and choose `PdfImageCompression.Jpeg`.

## Prerequisites

Tutoriala başlamadan önce aşağıdaki ön koşulların karşılandığından emin olun:

- Aspose.Page for .NET: Aspose.Page kütüphanesinin yüklü olduğundan emin olun. İndirmek için [buraya](https://releases.aspose.com/page/net/) tıklayın.

- Document Files: Belirttiğiniz dizinde XPS belgesi (`input.xps`) hazır bulunsun.

## Import Namespaces

.NET projenizde Aspose.Page ile çalışmak için gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
```

Bu adım, belge dönüşümü için gereken sınıf ve metodlara erişiminizi sağlar.

## How to add page numbers PDF when merging XPS documents

`PdfSaveOptions.PageNumbers` koleksiyonu, çıktıda PDF'e hangi sayfaların (veya sayfa aralıklarının) yer alacağını tam olarak belirlemenizi sağlar. İstediğiniz sayfa numaralarını bu koleksiyona eklediğinizde, Aspose.Page otomatik olarak doğru numaralandırmayı ekler.

### Step 1: Initialize Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Bu adım, XPS ve PDF dosyaları için giriş ve çıkış akışlarını ayarlamayı içerir. Doğru yol ve dosya adlarının kullanıldığından emin olun.

### Step 2: Load XPS Document

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Burada, XPS belgesi `XpsDocument` nesnesine yüklenir ve sonraki işlemler için hazırlanır.

### Step 3: Initialize Save Options (merge xps to pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

`PdfSaveOptions` nesnesini tercihlerinize göre özelleştirin; görüntü sıkıştırması, metin sıkıştırması ve **sayfa numaraları** gibi parametreleri belirleyin. `JpegQualityLevel` değerini 100 olarak ayarlamak, **yüksek kaliteli PDF görüntüleri** elde etmenizi sağlar.

### Step 4: Create Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice`, XPS belgesini PDF formatına dönüştürmekten sorumlu araçtır.

### Step 5: Save the Document (c# xps to pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Son olarak, render cihazı ve belirttiğiniz seçeneklerle belgeyi kaydedin. Çıktı PDF, seçilen sayfaları otomatik eklenmiş sayfa numaralarıyla içerecektir.

## Why use Aspose.Page for this conversion?

- **Reliability** – Karmaşık XPS özelliklerini kayıpsız işler.  
- **Performance** – Akış‑tabanlı işleme, tüm dosyaları belleğe yüklemeyi önler.  
- **Flexibility** – Görüntü kalitesi, sıkıştırma ve sayfa numaralandırma üzerinde ince ayar kontrolü.  
- **Cross‑platform** – .NET Core ile Windows, Linux ve macOS üzerinde çalışır.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | Verify that the XPS file path is correct and that the file is not corrupted. |
| **Page numbers not appearing** | Ensure `PageNumbers` is set to the correct zero‑based page indices (e.g., `new int[] {1,2,6}`). |
| **Low‑quality images** | Increase `JpegQualityLevel` and choose `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | Process the XPS in smaller chunks or increase the application’s memory limit. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

A1: Yes, you can. Simply adjust the `PageNumbers` parameter in the `PdfSaveOptions` to include the desired pages from different XPS files, or load each XPS sequentially and call `document.Save` on the same `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

A2: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

A3: Aspose.Page for .NET does not impose strict limitations on file size, but optimal performance is achieved with reasonably sized files. For very large XPS documents, consider processing them in streams to reduce memory consumption.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

A4: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation. After conversion, you can use the Aspose.PDF library to add watermarks, annotations, or other enhancements.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

A5: Yes, Aspose.Page for .NET is designed to work seamlessly across various platforms, including Windows, Linux, and macOS, when used with .NET Core or .NET 5/6.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
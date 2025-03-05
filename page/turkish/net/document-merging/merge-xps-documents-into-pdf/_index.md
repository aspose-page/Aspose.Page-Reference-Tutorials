---
title: Aspose.Page for .NET ile XPS Belgelerini PDF olarak birleştirin
linktitle: XPS Belgelerini PDF'ye Birleştir
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak XPS belgelerini zahmetsizce yüksek kaliteli PDF'lerle birleştirin. Sorunsuz bir belge dönüştürme deneyimi için adım adım kılavuzumuzu izleyin.
type: docs
weight: 11
url: /tr/net/document-merging/merge-xps-documents-into-pdf/
---
## giriiş

Aspose.Page for .NET, belge işlemenin sürekli gelişen ortamında, XPS belgelerini PDF formatına sorunsuz bir şekilde birleştirmek için güçlü bir araç olarak ortaya çıkıyor. Bu eğitim, sorunsuz ve etkili bir uygulama sağlamak için her adımı parçalara ayırarak süreç boyunca size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Page for .NET: Aspose.Page kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

- Belge Dosyaları: XPS belgesini edinin (`input.xps`) belirttiğiniz dizinde hazır.

## Ad Alanlarını İçe Aktar

.NET projenize Aspose.Page ile çalışmak için gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
```

Bu adım, belge dönüştürme için gereken sınıflara ve yöntemlere erişiminizin olmasını sağlar.

## 1. Adım: Akışları Başlatın

```csharp
// ExStart:3
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// PDF çıktı akışını başlat
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// XPS giriş akışını başlat
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Bu adım, XPS ve PDF dosyaları için giriş ve çıkış akışlarının ayarlanmasını içerir. Doğru yolların ve dosya adlarının kullanıldığından emin olun.

## Adım 2: XPS Belgesini Yükleyin

```csharp
// ExStart:4
// Akıştan XPS belgesini yükleyin
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// veya XPS belgesini doğrudan dosyadan yükleyin. O zaman xpsStream'e gerek yok.
//XpsDocument belgesi = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExBitiş:4
```

 Burada XPS belgesini yüklüyoruz.`XpsDocument` nesneyi daha sonraki işlemlere hazırlamak.

## 3. Adım: Kaydetme Seçeneklerini Başlatın

```csharp
// ExStart:5
// Seçenekler nesnesini gerekli parametrelerle başlatın.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExBitiş:5
```

 Özelleştirin`PdfSaveOptions` görüntü sıkıştırma, metin sıkıştırma ve sayfa numaraları gibi parametreleri belirterek tercihlerinize göre nesneyi seçin.

## Adım 4: İşleme Cihazı Oluşturun

```csharp
// ExStart:6
// PDF formatı için işleme cihazı oluşturun
PdfDevice device = new PdfDevice(pdfStream);
// ExBitiş:6
```

`PdfDevice` XPS belgesinin PDF formatına dönüştürülmesinden sorumlu araçtır.

## Adım 5: Belgeyi Kaydedin

```csharp
// ExStart:7
document.Save(device, options);
// ExBitiş:7
```

Son olarak, oluşturma cihazını ve belirtilen seçenekleri kullanarak belgeyi kaydedin.

## Çözüm

Tebrikler! Aspose.Page for .NET'i kullanarak XPS belgelerini PDF'ye başarıyla birleştirdiniz. Bu kusursuz süreç, belge kalitesinin ve biçimlendirmesinin korunmasını sağlar.

## SSS'ler

### S1: Birden fazla XPS dosyasını tek bir PDF'de birleştirebilir miyim?

 A1: Evet, yapabilirsin. Basitçe ayarlayın`PageNumbers` parametresi`PdfSaveOptions` Farklı XPS dosyalarından istenilen sayfaları dahil etmek için.

### S2: Aspose.Page for .NET için geçici bir lisans mevcut mu?

 Cevap2: Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) test amaçlı.

### S3: Aspose.Page'i belge dönüştürme için kullanırken dosya boyutunda herhangi bir sınırlama var mı?

Cevap3: Aspose.Page for .NET, dosya boyutuna katı sınırlamalar getirmez ancak optimum performans, makul dosya boyutlarıyla elde edilir.

### S4: Çıktı PDF'sini filigran veya ek açıklamalar ekleyerek daha da özelleştirebilir miyim?

Cevap4: Evet, Aspose.Page for .NET, PDF manipülasyonu için kapsamlı özellikler sağlar. Gelişmiş özelleştirme seçenekleri için belgelere bakın.

### S5: Aspose.Page for .NET platformlar arası geliştirmeyi destekliyor mu?

Cevap5: Evet, Aspose.Page for .NET, çeşitli platformlarda sorunsuz çalışacak şekilde tasarlanmıştır.
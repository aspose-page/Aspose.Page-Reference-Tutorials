---
title: Aspose.Page for .NET ile Basit Özellikler Ekleme
linktitle: Basit Özellikler Ekle
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile EPS dosyalarını geliştirin. Özelleştirilmiş belge meta verileri için basit özellikleri zahmetsizce ekleyin.
weight: 14
url: /tr/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile Basit Özellikler Ekleme

## giriiş

Belge işleme ve geliştirme alanında Aspose.Page for .NET, geliştiricilere EPS dosyalarına XMP meta verilerini sorunsuz bir şekilde ekleme ve değiştirme yeteneği sağlayan güçlü bir araç olarak ortaya çıkıyor. Bu eğitim, Aspose.Page for .NET'i kullanarak bir EPS dosyasına basit özellikler ekleme sürecinde size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1.  Aspose.Page for .NET: Geliştirme ortamınızda Aspose.Page for .NET'in kurulu olduğundan emin olun. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

2.  Belge Dizini: EPS dosyalarınızı depolamak için bir dizin ayarlayın. Güncelleme`dataDir` sağlanan kod parçacığında belge dizininizin yolunu içeren değişken.

## Ad Alanlarını İçe Aktar

Başlamak için Aspose.Page for .NET ile iletişimi etkinleştirmek için gerekli ad alanlarını içe aktarın. Kod dosyanızın başına aşağıdaki satırları ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 1. Adım: EPS Dosya Giriş Akışını Başlatın

```csharp
// ExStart:1
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// EPS dosyası giriş akışını başlat
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Akıştan PsDocument örneği oluşturun
PsDocument document = new PsDocument(psStream);
```

## 2. Adım: XMP Meta Verilerini Alın

```csharp
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarından gelen değerlerle dolu yeni bir tane alırız (%%Creator, %%CreateDate, %%Title, vb.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## 3. Adım: XMP Meta Veri Değerlerini Değiştirin

```csharp
// XMP meta veri değerlerini değiştirme
DateTime now = DateTime.UtcNow;

// Tamsayı özelliği ekle
xmp.Add("xmp:Intg1", new XmpValue(111));

// DateTime özelliği ekle
xmp.Add("xmp:Date1", new XmpValue(now));

// Çift mülk ekle
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Dize özelliği ekle
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Adım 4: EPS Dosyasını Değiştirilmiş XMP Meta Verileriyle Kaydetme

```csharp
// EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin

// Çıkış akışı oluştur
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS dosyasını kaydet
    document.Save(outPsStream);
}
```

## Adım 5: FileStream'i kapatın

```csharp
finally
{
    psStream.Close();
}
```

Bu adımları izleyerek, Aspose.Page for .NET'i kullanarak basit özellikleri EPS dosyalarınıza zahmetsizce dahil edebilirsiniz.

## Çözüm

Sonuç olarak, Aspose.Page for .NET, EPS dosyalarını özel XMP meta verileriyle geliştirmek isteyen geliştiriciler için paha biçilmez bir varlık olduğunu kanıtlıyor. Basit özellikler ekleyerek, belgelerinizi özel gereksinimleri karşılayacak şekilde özelleştirebilir ve zenginleştirebilirsiniz, böylece belge işleme için bir olasılıklar dünyasının kapılarını açabilirsiniz.

## SSS'ler

### S1: Aspose.Page for .NET tüm EPS dosyalarıyla uyumlu mudur?

Cevap1: Aspose.Page for .NET çok çeşitli EPS dosyalarını destekler. Ancak uyumluluk, tek tek dosyaların karmaşıklığına ve yapısına bağlı olarak değişiklik gösterebilir.

### S2: Mevcut XMP meta verilerini Aspose.Page for .NET ile değiştirebilir miyim?

A2: Kesinlikle! Bu eğitimde gösterildiği gibi, mevcut XMP meta veri değerlerini kolayca değiştirebilir veya ihtiyaçlarınıza uyacak şekilde yenilerini ekleyebilirsiniz.

### S3: Ekleyebileceğim özellik türlerinde herhangi bir sınırlama var mı?

Cevap3: Aspose.Page for .NET, tamsayılar, tarihler, çiftler ve dizeler dahil olmak üzere özellikler için çeşitli veri türlerini destekler. Meta verileriniz için uygun türü seçme konusunda esnekliğe sahipsiniz.

### S4: Aspose.Page for .NET için nasıl teknik destek alabilirim?

 Cevap4: Teknik yardım için şu adresi ziyaret edin:[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) veya keşfedin[dokümantasyon](https://reference.aspose.com/page/net/) kapsamlı rehberlik için.

### S5: Aspose.Page for .NET'in ücretsiz deneme sürümü mevcut mu?

 C5: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

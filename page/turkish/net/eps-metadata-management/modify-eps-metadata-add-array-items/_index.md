---
title: Aspose.Page ile Dizi Öğeleri Ekleme
linktitle: Dizi Öğeleri Ekle
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET kullanarak EPS dosyalarına dizi öğelerinin nasıl ekleneceğini keşfedin. Kusursuz belge işleme için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile Dizi Öğeleri Ekleme

## giriiş

.NET'te belge işleme ve işleme alanında Aspose.Page güçlü bir araç olarak öne çıkıyor. Pek çok özelliğinin yanı sıra, bir EPS dosyasındaki dizi öğelerinin işlenmesi de ortak bir gereksinimdir. Bu eğitimde, .NET ortamında Aspose.Page kullanarak dizi öğeleri ekleme işlemini adım adım inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlayan biri olun, bu kılavuz süreç boyunca size net ve kesin bir şekilde yol gösterecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- .NET programlamanın temel anlayışı.
-  Aspose.Page for .NET kuruldu. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/page/net/).
- Örneklerle birlikte takip edilecek Visual Studio gibi bir kod düzenleyici.

## Ad Alanlarını İçe Aktar

.NET projenizde Aspose.Page işlevlerini kullanmak için gerekli ad alanlarını içe aktardığınızdan emin olun. Kodunuzun başına aşağıdaki satırları ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu ad alanları, EPS dosyasının işlenmesi için gereken temel sınıflara ve yöntemlere erişim sağlar.

## 1. Adım: EPS dosyası giriş akışını başlatın

```csharp
// ExStart:3
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// EPS dosyası giriş akışını başlat
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Akıştan PsDocument örneği oluşturun
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

 Burada, EPS dosyası için ilk giriş akışını kuruyoruz ve bir`PsDocument` misal.

## 2. Adım: XMP meta verilerini alın

```csharp
// ExStart:4
// XMP meta verilerini alın. EPS dosyası XMP meta verileri içermiyorsa, PS meta veri yorumlarından gelen değerlerle dolu yeni bir dosya alırız (%%Creator, %%CreateDate, %%Title vb.)
XmpMetadata xmp = document.GetXmpMetadata();
// ExBitiş:4
```

XMP meta verilerini EPS dosyasından alın. EPS dosyasında XMP meta verileri yoksa PS meta veri yorumlarından alınan değerlerle yeni bir tane oluşturulur.

## 3. Adım: XMP meta veri değerlerini değiştirin

```csharp
// ExStart:5
// XMP meta veri değerlerini değiştirme

// Bir başlık daha ekleyin. Varsayılan olarak dizinin sonuna eklenecektir.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Bir yaratıcı daha ekleyin. Diziye bir indeks (0) ile eklenecektir.
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExBitiş:5
```

Diziye yeni başlıklar ve yaratıcılar ekleyerek XMP meta verilerini değiştirin.

## Adım 4: EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin

```csharp
// ExStart:6
// EPS dosyasını değiştirilmiş XMP meta verileriyle kaydedin

// Çıkış akışı oluştur
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS dosyasını kaydet
    document.Save(outPsStream);
}
// ExBitiş:6
```

Son olarak, EPS dosyasını güncellenmiş XMP meta verileriyle kaydedin. Dizi öğelerinde yapılan değişiklikler çıktı dosyasına yansıtılacaktır.

## Çözüm

Bu eğitimde gösterildiği gibi, .NET'te Aspose.Page ile dizi öğeleri eklemek basit bir işlemdir. Geliştiriciler, doğru ön koşullar ve adım adım kılavuzla, EPS dosyalarını sorunsuz bir şekilde işleyebilir ve belgelerinin belirli meta veri gereksinimlerini karşıladığından emin olabilirler.

## SSS'ler

### S1: Aspose.Page tüm .NET ortamlarıyla uyumlu mudur?

C1: Evet, Aspose.Page tüm .NET ortamlarıyla sorunsuz çalışacak ve platformlar arasında tutarlı işlevsellik sağlayacak şekilde tasarlanmıştır.

### S2: Aspose.Page'i ücretsiz kullanabilir miyim?

 Cevap2: Aspose.Page, kullanıcıların özelliklerini keşfetmesine olanak tanıyan ücretsiz bir deneme sürümü sunuyor. Sürekli kullanım için adresinden bir lisans satın alınmalıdır.[Burada](https://purchase.aspose.com/buy).

### S3: Aspose.Page için geçici lisanslar mevcut mu?

 C3: Evet, geçici lisanslar şu adresten alınabilir:[Burada](https://purchase.aspose.com/temporary-license/) Kısa vadeli proje ihtiyaçları için.

### S4: Aspose.Page için topluluk desteğini nerede bulabilirim?

Cevap4: Topluluk tartışmaları ve desteği için şu adresi ziyaret edin:[Aspose.Page forumu](https://forum.aspose.com/c/page/39).

### S5: Aspose.Page for .NET'in en son sürümü nedir?

 Cevap5: Aspose.Page for .NET'in en son sürümüne erişmek için bkz.[dokümantasyon](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

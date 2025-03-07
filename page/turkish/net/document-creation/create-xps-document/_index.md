---
title: Aspose.Page for .NET ile XPS Belgesi Oluşturun
linktitle: XPS Belgesi Oluştur
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET ile XPS belge oluşturma dünyasını keşfedin. Zahmetsizce elektronik belgeler oluşturmak için adım adım kılavuzumuzu izleyin.
weight: 10
url: /tr/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile XPS Belgesi Oluşturun

## giriiş

Aspose.Page for .NET'i kullanarak XPS belgeleri oluşturmaya ilişkin adım adım kılavuzumuza hoş geldiniz. Bu eğitimde, elektronik belgeler için yaygın olarak kullanılan bir format olan XPS dosyalarını oluşturma sürecini inceleyeceğiz. İster deneyimli bir geliştirici olun ister Aspose.Page'e yeni başlıyor olun, bu kılavuz net örnekler ve ayrıntılı açıklamalarla XPS belgelerini sorunsuz bir şekilde oluşturmanıza yardımcı olmak için özel olarak hazırlanmıştır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Page for .NET Kütüphanesi: Aspose.Page kütüphanesini şu adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/page/net/).

2. Belge Dizininiz: Sisteminizde çıktı XPS dosyalarını kaydetmek istediğiniz dizini seçin veya oluşturun.

Şimdi öğreticiye geçelim!

## Ad Alanlarını İçe Aktar

Aspose.Page for .NET'i kullanmak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu adımları takip et:

### Adım 1: Aspose.Page'e Referans Ekle

Projenize Aspose.Page for .NET kitaplığına bir referans ekleyin. Gerekli DLL'yi indirilen pakette bulabilirsiniz.

### 2. Adım: Ad Alanlarını İçe Aktarın

Kod dosyanıza aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Artık önkoşulları ayarladığımıza ve gerekli ad alanlarını içe aktardığımıza göre, XPS belgesi oluşturma sürecini birden çok adıma ayıralım.

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
string dir = "Your Document Directory";
```

 Değiştirildiğinden emin olun`"Your Document Directory"` çıktı XPS dosyasını kaydetmek istediğiniz gerçek yolla.

## Adım 2: XPS Belgesi Oluşturun

```csharp
XpsDocument xDocs = new XpsDocument();
```

 kullanarak yeni bir XPS belgesi başlatın.`XpsDocument` sınıf.

## 3. Adım: Belgeye Glifler Ekleme

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 Kullan`AddGlyphs` Belgeye glifler (metin) ekleme yöntemi. Yazı tipini, boyutunu, stilini ve konumunu gerektiği gibi özelleştirin.

## Adım 4: Glif Dolgu Rengini Ayarlayın

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Eklenen gliflerin dolgu rengini belirtin. Bu örnekte siyah kullanıyoruz ama siz istediğiniz rengi seçebilirsiniz.

## Adım 5: Sonucu Kaydet

```csharp
xDocs.Save(dir + "output.xps");
```

Son olarak XPS belgesini istediğiniz dosya adıyla belirtilen dizine kaydedin. Ortaya çıkan XPS dosyası "Merhaba Dünya!" metin.

Tebrikler! Aspose.Page for .NET'i kullanarak başarıyla bir XPS belgesi oluşturdunuz.

## Çözüm

Bu eğitimde Aspose.Page for .NET'i kullanarak XPS belgeleri oluşturma sürecini anlattık. Bu güçlü kitaplık, elektronik belgeleri kolaylıkla oluşturmanın kusursuz bir yolunu sunar. XPS dosyalarınızı özel ihtiyaçlarınıza göre uyarlamak için farklı yazı tipleri, stiller ve içeriklerle denemeler yapın.

## SSS'ler

### S1: XPS belgemde özel yazı tipleri kullanabilir miyim?

Cevap1: Evet, XPS belgenize glifler eklerken yazı tipi ailesini ve boyutunu belirtebilirsiniz.

### S2: Aspose.Page .NET Core ile uyumlu mu?

C2: Evet, Aspose.Page .NET Core'u destekleyerek platformlar arası uygulamalarda kullanmanıza olanak tanır.

### S3: XPS belgesine nasıl resim ekleyebilirim?

Cevap3: Aspose.Page, XPS belgenize resim ekleme yöntemleri sağlar. Ayrıntılı örnekler için belgelere bakın.

### S4: Çok sayfalı XPS belgeleri oluşturabilir miyim?

Cevap4: Kesinlikle! Aspose.Page kütüphanesini kullanarak XPS belgenize birden fazla sayfa ekleyebilirsiniz.

### S5: Deneme sürümü mevcut mu?

 Cevap5: Evet, Aspose.Page'in özelliklerini indirerek keşfedebilirsiniz.[ücretsiz deneme](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

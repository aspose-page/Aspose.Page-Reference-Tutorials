---
title: Aspose.Page ile XPS Belgesine Unicode Dizeli Metin Ekleme
linktitle: XPS Belgesine Unicode Dizeli Metin Ekleme
second_title: Aspose.Page .NET API'si
description: XPS belgelerine Unicode metin eklemeye ilişkin adım adım kılavuzumuzla Aspose.Page for .NET'in gücünü keşfedin.
weight: 12
url: /tr/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile XPS Belgesine Unicode Dizeli Metin Ekleme

## giriiş

Sürekli gelişen .NET geliştirme ortamında Aspose.Page, XPS belgelerini yönetmek için güçlü bir araç olarak öne çıkıyor. Pek çok özelliği arasında, XPS belgesine Unicode dizeleri içeren metin ekleme yeteneği değerli bir işlevselliktir. Bu adım adım kılavuz, süreç boyunca size yol gösterecek ve bu yetenekten etkili bir şekilde yararlanmanızı sağlayacaktır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- .NET geliştirmenin temel anlayışı.
- Makinenizde Visual Studio yüklü.
-  .NET kütüphanesi için Aspose.Page. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/page/net/).

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını projenize aktardığınızdan emin olun. Bu, Aspose.Page ile çalışmak için gerekli sınıfları ve işlevleri sağlayacaktır. Temel ad alanları şunlardır:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. Adım: Belgeyi Ayarlayın

Öncelikle Unicode metnini ekleyeceğiniz yeni bir XPS belgesi oluşturun. Aşağıdaki kod parçacığını izleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
// Yeni XPS Belgesi oluştur
XpsDocument doc = new XpsDocument();
```

## 2. Adım: Unicode Metin Ekleme

Şimdi XPS belgesine Unicode metin ekleyelim. Bu örnek, Arial yazı tipini kullanır, yazı tipi boyutunu 20 olarak ayarlar ve metni koordinatlara (400f, 200f) konumlandırır. Bu durumda Unicode dizesi "TEN.rof SPX.esopsA"dır. Aşağıdaki kod parçacığını inceleyin:

```csharp
// Yazı ekle
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 3. Adım: Belgeyi Kaydedin

Unicode metni eklendikten sonra ortaya çıkan XPS belgesini kaydedin. İşte son adım:

```csharp
// Ortaya çıkan XPS belgesini kaydedin
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Tebrikler! Aspose.Page for .NET'i kullanarak bir XPS belgesine Unicode metni başarıyla eklediniz.

## Çözüm

Bu eğitimde Aspose.Page for .NET kullanarak XPS belgelerine Unicode metin ekleme sürecini inceledik. Bu işlevsellik, .NET ortamında çeşitli ve dinamik belge oluşturmanın kapılarını açar.

## SSS'ler

### S1: Aspose.Page en yeni .NET çerçeveleriyle uyumlu mu?

Cevap1: Evet, Aspose.Page, en yeni .NET çerçeveleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir.

### S2: Metin eklerken yazı tipi stilini ve boyutunu özelleştirebilir miyim?

A2: Kesinlikle! Sağlanan örnek kod, yazı tipi stilini, boyutunu ve diğer nitelikleri kolayca özelleştirmenize olanak tanır.

### S3: Aspose.Page için ek belgeleri nerede bulabilirim?

 A3: Belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/page/net/) Kapsamlı bilgi ve örnekler için.

### S4: Aspose.Page'i kullanmaya başlamak için ücretsiz kaynaklar var mı?

 A4: Evet, keşfedebilirsiniz[Aspose.Page forumu](https://forum.aspose.com/c/page/39) topluluk desteği ve tartışmalar için.

### S5: Satın alma işleminden önce deneme sürümü mevcut mu?

 A5: Kesinlikle! Ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/) bir satın alma işlemi yapmadan önce.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

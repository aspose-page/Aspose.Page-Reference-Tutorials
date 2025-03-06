---
title: Aspose.Page ile PostScript'e (PS) Yatay Degrade Ekleme
linktitle: PostScript'e (PS) Yatay Degrade Ekleme
second_title: Aspose.Page .NET API'si
description: Aspose.Page for .NET'i kullanarak PostScript belgelerini çarpıcı yatay degradelerle geliştirin. Sorunsuz uygulama için adım adım eğitimimizi izleyin.
weight: 12
url: /tr/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript'e (PS) Yatay Degrade Ekleme

## giriiş

Aspose.Page for .NET kullanarak PostScript (PS) belgelerine yatay degradeler eklemeyi konu alan bu kapsamlı eğitime hoş geldiniz. Aspose.Page, çeşitli formatlarda belge manipülasyonunu kolaylaştıran, geliştiricilere belgeleri sorunsuz bir şekilde oluşturmak, değiştirmek ve işlemek için ihtiyaç duydukları araçları sağlayan güçlü bir kütüphanedir.

Bu eğitimde, göz alıcı yatay degradeler ekleyerek PostScript belgelerinizi geliştirmeye odaklanacağız. Uygulama hakkında sağlam bir anlayışa sahip olmanızı sağlamak için sürecin her adımında size yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Page for .NET Kütüphanesi: Aspose.Page for .NET kütüphanesinin geliştirme ortamınıza entegre olduğundan emin olun. adresinden indirebilirsiniz.[.NET belgeleri için Aspose.Page](https://reference.aspose.com/page/net/).

- Belge Dizini: Belgelerinizi saklamak için bir dizin oluşturun ve sağlanan koddaki "Belge Dizininiz"i gerçek yolla değiştirin.

Şimdi bir PostScript belgesine adım adım yatay degradenin nasıl ekleneceğini inceleyelim.

## Ad Alanlarını İçe Aktar

Başlamadan önce Aspose.Page tarafından sağlanan işlevselliklere erişmek için gerekli ad alanlarını içe aktarmanız önemlidir. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. Adım: Belgeyi Ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";

// PostScript belgesi için çıktı akışı oluşturun
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // A4 boyutunda kaydetme seçenekleri oluşturun
    PsSaveOptions options = new PsSaveOptions();

    // Yeni 1 sayfalık PS Belgesi oluştur
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Adım 2: Degrade Dikdörtgeni ve Renkleri Tanımlayın

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // İlk dikdörtgenden grafik yolu oluşturun
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Sınırlar, başlangıç ve bitiş renkleri olarak dikdörtgen içeren doğrusal degrade fırça oluşturma
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Adım 3: Fırça için Dönüşümü Ayarlayın

```csharp
    // Fırça için bir dönüşüm oluşturun. X ve Y ölçek bileşeni sırasıyla dikdörtgenin genişliğine ve yüksekliğine eşit olmalıdır.
    // Çeviri bileşenleri dikdörtgenin uzaklıklarıdır
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Dönüşümü ayarla
    brush.Transform = brushTransform;
```

## Adım 4: Boyayı Ayarlayın ve Dikdörtgeni Doldurun

```csharp
    // Boyayı ayarla
    document.SetPaint(brush);

    // Dikdörtgeni doldur
    document.Fill(path);
```

## Adım 5: Metni Degradeyle Doldurun

```csharp
    // Metni degradeyle doldurma
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Adım 6: Kontur ve Anahat Metnini Ayarlayın

```csharp
    // Geçerli vuruşu ayarla
    document.SetStroke(new Pen(brush, 5));
    // Gradyanlı anahat metni
    document.OutlineText("ABC", font, 200, 400);
```

## Adım 7: Geçerli Sayfayı Kapatın ve Belgeyi Kaydedin

```csharp
    // Geçerli sayfayı kapat
    document.ClosePage();

    // Belgeyi kaydet
    document.Save();
}
```

Tebrikler! Aspose.Page for .NET'i kullanarak PostScript belgesine başarıyla yatay degrade eklediniz.

## Çözüm

Bu eğitimde, Aspose.Page for .NET kitaplığını kullanarak PostScript belgelerinizi yatay degradelerle geliştirme sürecini ele aldık. Adım adım kılavuzu takip ederek, belge işleme için bu güçlü araçtan yararlanma konusunda değerli bilgiler elde ettiniz.

## SSS'ler

### S1: Degradeleri dikdörtgenlerin yanı sıra diğer şekillere de uygulayabilir miyim?

 Cevap1: Evet, Aspose.Page'i kullanarak çeşitli şekillere degradeler uygulayabilirsiniz. Değiştirmek`GraphicsPath` Özel şeklinize uyacak şekilde yaratım.

### S2: Degrade renklerini nasıl değiştirebilirim?

 A2: Ayarlayın`Color.FromArgb` içindeki değerler`LinearGradientBrush` İstenilen degrade renklerini elde etmek için örnekleme.

### S3: Aspose.Page farklı belge formatlarıyla uyumlu mudur?

Cevap3: Aspose.Page, XPS, PS, PDF ve daha fazlası dahil olmak üzere çeşitli belge formatlarını destekler. Kapsamlı bir liste için belgelere bakın.

### S4: Aspose.Page'i ticari projeler için kullanabilir miyim?

 Cevap4: Evet, Aspose.Page ticari lisanslama seçenekleriyle birlikte gelir. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) detaylar için.

### S5: Aspose.Page kullanıcıları için bir topluluk forumu var mı?

 C5: Evet, Aspose.Page topluluğuna şu adresten katılın:[Aspose.Page Forumu](https://forum.aspose.com/c/page/39) diğer kullanıcılarla bağlantı kurmak ve yardım istemek için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

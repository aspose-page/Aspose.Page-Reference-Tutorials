---
date: 2026-03-03
description: Aspose.Page for .NET kullanarak özel sayfa boyutu ayarlamayı ve bir PostScript
  belgesine ikinci bir PS sayfası eklemeyi öğrenin.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page ile PS Belgesinde Özel Sayfa Boyutu Ayarlama
url: /tr/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page ile PostScript (PS) Belgesine Sayfa Ekle

## Giriş

.NET geliştirme ortamında **özel sayfa boyutu ayarlama** ve **ikinci bir PS sayfası ekleme** yeteneği, oluşturulan baskıların, raporların veya grafiklerin düzeni üzerinde ince ayar yapmanızı sağlar. Aspose.Page for .NET, temiz ve nesne‑yönelimli bir API ile bu görevi basitleştirir. Bu öğreticide, çok sayfalı bir PS dosyası oluşturmayı, her sayfa için özel bir boyut tanımlamayı ve sonucu kaydetmeyi—sadece birkaç satır C# kodu ile—öğreneceksiniz.

## Hızlı Yanıtlar
- **Özel bir sayfa boyutu ayarlayabilir miyim?** Evet – bir sayfa açarken genişlik ve yüksekliği geçirmeniz yeterlidir.  
- **İkinci bir PS sayfası nasıl eklenir?** `document.OpenPage(width, height)` metodunu ikinci kez çağırın.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Lisans gerekir mi?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Aspose.Page'i nereden indirebilirim?** Aşağıdaki resmi indirme sayfasından.

## Önkoşullar

Bu öğreticiye başlamadan önce aşağıdaki önkoşulların sağlandığından emin olun:

- .NET geliştirme konusunda temel bilgi.  
- Makinenizde Visual Studio yüklü.  
- Aspose.Page for .NET kütüphanesi, bunu [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- Test için tercih ettiğiniz belge dizini.

## Ad Alanlarını İçe Aktarın

Aspose.Page tarafından sağlanan işlevlere erişmek için projenizde gerekli ad alanlarını eklediğinizden emin olun. Verilen örnekte ad alanları dolaylı olarak dahil edilmiştir, ancak proje yapınıza göre kontrol edip gerekirse ayarlamalar yapmanız önemlidir.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Adım 1: Projenizi Kurun

Visual Studio’da yeni bir .NET projesi oluşturun ve gerekli yapılandırmaları yapın. Aspose.Page kütüphanesini projenize referans olarak eklediğinizden emin olun.

## Özel Sayfa Boyutu Ayarla ve İkinci PS Sayfasını Ekle

Bu bölüm, **her sayfa için özel sayfa boyutu ayarlamayı** ve aynı belgeye **ikinci bir PS sayfası eklemeyi** tam olarak gösterir.

### Adım 2: Belgeyi Başlat

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Adım 3: İlk Sayfayı Ekle (varsayılan boyut)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Adım 4: Farklı (Özel) Bir Boyutla İkinci Sayfayı Ekle

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Adım 5: Belgeyi Kaydet

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Bu adımları titizlikle izleyin; böylece Aspose.Page for .NET kullanarak **özel sayfa boyutu ayarlayabilir** ve bir PostScript belgesine **ikinci bir PS sayfası ekleyebilirsiniz**.

## Neden Önemli

- **Kesin Düzen** – Özel sayfa boyutları, yazıcı özelliklerine uymanızı veya benzersiz broşür formatları oluşturmanızı sağlar.  
- **Çoklu Sayfalar** – İkinci (veya daha fazla) sayfa eklemek, harici birleştirme araçları olmadan çok sayfalı raporlar oluşturmanıza olanak tanır.  
- **Çapraz Platform** – Oluşturulan PS dosyası, herhangi bir PostScript uyumlu cihazda görüntülenebilir veya daha sonra PDF'ye dönüştürülebilir.

## Yaygın Tuzaklar ve Sorun Giderme

- **Yanlış Yol** – `dataDir` bir yol ayırıcıyla bitiyor olduğundan emin olun veya `Path.Combine` kullanın.  
- **Lisans Sorunları** – Geçerli bir lisans olmadan, kütüphane filigran ekleyebilir veya sayfa sayısını sınırlayabilir.  
- **Birim Karışıklığı** – Genişlik ve yükseklik point biriminde ölçülür (1 point = 1/72 inç). Buna göre ayarlayın.

## Sıkça Sorulan Sorular

**S1: Aspose.Page farklı belge formatlarıyla uyumlu mu?**  
C1: Aspose.Page öncelikle PostScript belge manipülasyonuna odaklanır. Diğer formatlar için ihtiyaçlarınıza yönelik özel Aspose kütüphanelerini inceleyebilirsiniz.

**S2: Aspose.Page'de sayfa boyutunu özelleştirebilir miyim?**  
C2: Kesinlikle! Öğreticide gösterildiği gibi, her sayfa için gereksinimlerinize göre farklı boyutlar belirtebilirsiniz.

**S3: Daha fazla örnek ve dokümantasyona nereden ulaşabilirim?**  
C3: Kapsamlı bilgi ve çeşitli örnekler için [dokümantasyon](https://reference.aspose.com/page/net/) sayfasını ziyaret edin.

**S4: Aspose.Page için geçici bir lisans nasıl alınır?**  
C4: Test amaçlı geçici lisans edinmek için [bu bağlantıya](https://purchase.aspose.com/temporary-license/) gidin.

**S5: Topluluk desteği veya soru sormak için nereden ulaşabilirim?**  
C5: Diğer geliştiricilerle bağlantı kurmak, deneyim paylaşmak ve yardım almak için [Aspose.Page topluluk forumuna](https://forum.aspose.com/c/page/39) katılın.

---

**Son Güncelleme:** 2026-03-03  
**Test Edilen Sürüm:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
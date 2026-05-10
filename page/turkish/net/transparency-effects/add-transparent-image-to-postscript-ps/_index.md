---
date: 2026-03-26
description: Aspose.Page kullanarak .NET’te PostScript belgesi oluşturmayı ve şeffaf
  bir görüntü eklemeyi öğrenin. Bu adım adım rehber, ön koşulları, kodu ve ipuçlarını
  kapsar.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: .NET'te şeffaf görüntülü PostScript belgesi oluşturma (Aspose.Page)
url: /tr/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Şeffaf Görüntülü .NET PostScript Belgesi Oluşturma (Aspose.Page)

## Introduction

Bu öğreticide **PostScript belgesi .NET nasıl oluşturulur** ve Aspose.Page for .NET kullanarak şeffaf bir PNG nasıl gömülür öğrenacaksınız. Şeffaf görüntüler eklemek, daha zengin, katmanlı grafikler oluşturmanıza olanak tanır—su işaretleri, bindirmeler veya bir PS dosyası içindeki UI mock‑up'ları için mükemmeldir. Ortamı kurmaktan opak ve şeffaf görüntüleri render etmeye kadar her adımı göstereceğiz.

## Quick Answers
- **Aspose.Page ne yapar?** .NET'te PostScript (PS) ve XPS belgeleri oluşturmak, düzenlemek ve render etmek için tam özellikli bir API sağlar.  
- **Şeffaf PNG ekleyebilir miyim?** Evet—opaklığı kontrol etmek için `DrawTransparentImage` kullanın.  
- **Hangi .NET sürümleri destekleniyor?** Tüm yeni .NET Framework, .NET Core ve .NET 5/6 sürümleri.  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için bir lisans gerekir.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.

## Prerequisites

Başlamadan önce, şunların olduğundan emin olun:

- **Aspose.Page for .NET** – [download link](https://releases.aspose.com/page/net/) adresinden indirin.  
- PS belgesini ve gömmek istediğiniz görüntüyü tutacağınız bir klasör.  
- Şeffaf katman için kullanılacak yarı saydam bir PNG (ör. `mask1.png`).

## Import Namespaces

İlk olarak, ihtiyacımız olan sınıfları içeren ad alanlarını (namespaces) içe aktarın. Bu, PS belge modeline, grafik yardımcı programlarına ve temel .NET çizim türlerine erişim sağlar.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Document Directory

Kaynak görüntünün ve çıktı PS dosyasının bulunacağı yolu tanımlayın. Yer tutucuyu, makinenizdeki gerçek yol ile değiştirin.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

Oluşturulan PS içeriğini bir dosya akışına (stream) yazacağız. Bu akış daha sonra `PsDocument` yapıcısına (constructor) geçirilir.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Step 3: Set Save Options and Background Color

`PsSaveOptions`'ı dosyanın nasıl kaydedileceğini tanımlamak için yapılandırın. Arka plan rengini ayarlamak, şeffaf öğelerin arkasında katı bir tuval istediğinizde faydalıdır.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Step 4: Create a New 1‑Paged PS Document

Yukarıda tanımlanan akış ve seçenekleri kullanarak belgeyi oluşturun. `false` bayrağı, Aspose.Page'in akışı otomatik olarak kapatmasını engeller.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Write Graphics Save and Translate

Çizmeye başlamadan önce, mevcut grafik durumunu kaydeder ve kökeni (origin) çeviririz, böylece görüntüler sayfada istenen konumda görünür.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## How to add transparent image to a PostScript document

### Step 6: Add Opaque RGB Image

İlk olarak aynı PNG'yi normal opak bir görüntü olarak ekliyoruz. Bu, daha sonra şeffaflık uyguladığımızda görsel farkı gösterir.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Step 7: Add Transparent Image

Şimdi PNG'yi bir opaklık değeriyle render etmek için `DrawTransparentImage` kullanıyoruz. Üçüncü parametre (`255`) tam opaklığı temsil eder; daha düşük değerler şeffaflığı artırır. İşte **image transparency .NET ayarladığımız** yer burası.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** Görüntüyü %50 şeffaf yapmak için `255` yerine `128` gönderin.

## Step 8: Write Graphics Restore and Close Page

Çizimden sonra, önceki grafik durumunu geri yükleyin ve içeriği tamamlamak için sayfayı kapatın.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Step 9: Save the Document

Son olarak, PS dosyasını diske kaydedin.

```csharp
document.Save();
```

Bu adımları izleyerek, hem opak hem de şeffaf bir görüntü içeren **PostScript belgesi .NET** oluşturmuş oldunuz ve Aspose.Page ile **draw transparent image C#** nasıl yapılır gösterildi.

## Why use Aspose.Page for transparency effects?

- **Tam kontrol** grafik durumu, matrisler ve opaklık seviyeleri üzerinde.  
- **Harici bağımlılık yok**—her şey saf .NET kodu içinde çalışır.  
- **Çapraz platform** desteği, Windows, Linux veya macOS'ta PS dosyaları oluşturmanıza olanak tanır.

## Common Pitfalls & Troubleshooting

| Sorun | Çözüm |
|-------|----------|
| `DrawTransparentImage` kullandıktan sonra görüntü tamamen opak görünüyor | Alfa değerinin (üçüncü argüman) `255`'ten düşük olduğundan emin olun. |
| PS dosyası boş bir sayfa gösteriyor | Arka plan renginin ayarlandığını ve akış yolunun doğru olduğunu doğrulayın. |
| “File not found” istisnası | `dataDir`'i ve `mask1.png` dosyasının o klasörde mevcut olduğunu iki kez kontrol edin. |

## Frequently Asked Questions

**S: Şeffaflık için PNG dışında başka görüntü formatları kullanabilir miyim?**  
C: Evet—Aspose.Page şeffaf render için PNG, GIF ve TIFF formatlarını destekler.

**S: Aspose.Page en yeni .NET framework ile uyumlu mu?**  
C: Kesinlikle. Kütüphane .NET 6, .NET 7 ve daha yenileri için düzenli olarak güncellenir.

**S: Mevcut bir PS belgesine şeffaflık uygulayabilir miyim?**  
C: Evet. Belgeyi `PsDocument` ile açın, yeni bir sayfa ekleyin veya mevcut bir sayfayı değiştirin, ardından aynı `DrawTransparentImage` yöntemini kullanın.

**S: Aspose.Page, genel grafik kütüphanelerine göre ne gibi avantajlar sunar?**  
C: PS/XPS için özel olarak tasarlanmıştır; vektör grafikler, yazı tipleri ve görüntü işleme üzerinde tam kontrol sağlar ve tam bir render motoruna ihtiyaç duymaz.

**S: Ayarlayabileceğim şeffaflık seviyesinde bir sınırlama var mı?**  
C: Hayır. `0` (tamamen şeffaf) ile `255` (tamamen opak) arasında herhangi bir alfa değeri belirtebilirsiniz.

## Conclusion

Aspose.Page kullanarak **PostScript belgesi .NET** oluşturmayı ve hem opak hem de şeffaf görüntüleri gömmeyi gösterdik. Bu teknik, karmaşık belge düzenleri, su işareti ekleme ve katmanlı grafikler için kapıyı açar—hepsi C#'dan programatik olarak üretilir.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
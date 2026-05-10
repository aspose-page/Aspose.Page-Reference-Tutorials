---
date: 2026-03-16
description: Aspose.Page kullanarak .NET’te EPS görüntülerini nasıl kırpacağınızı
  ve EPS görüntü dosyalarını nasıl yeniden boyutlandıracağınızı öğrenin. EPS’yi kırpmak
  ve EPS görüntüsünü zahmetsizce yeniden boyutlandırmak için bu adım adım kılavuzu
  izleyin.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET ile EPS Görüntülerini Nasıl Kırpılır?
url: /tr/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET ile EPS Görüntülerini Nasıl Kırpılır

## Giriş

Bir .NET uygulamasında **EPS görüntülerini nasıl kırpacağınızı** öğrenmek istiyorsanız, doğru yerdesiniz. Bu öğreticide, güçlü Aspose.Page for .NET kütüphanesini kullanarak EPS dosyalarını kırpma ve yeniden boyutlandırma sürecini adım adım göstereceğiz. Raporlama aracını iyileştiriyor ya da bir web servisi için grafikler hazırlıyor olun, bu tekniği öğrenmek zaman kazandıracak ve piksel‑tam sonuçlar elde etmenizi sağlayacaktır.

## Hızlı Yanıtlar
- **EPS kırpma işlemini hangi kütüphane yönetir?** Aspose.Page for .NET  
- **Ana yöntem?** `doc.CropEps(outputStream, newBoundingBox)`  
- **EPS'yi yeniden boyutlandırabilir miyim?** Evet – inç, milimetre veya yüzde cinsinden `ResizeEps` kullanın.  
- **Önkoşullar?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page yüklü, bir EPS dosyası.  
- **Tipik uygulama süresi?** Temel bir kırpma‑ve‑yeniden boyutlandırma iş akışı için yaklaşık 10 dakika.

## Önkoşullar

Koda başlamadan önce, şunların olduğundan emin olun:

- .NET geliştirme konusunda çalışma bilgisi.  
- Aspose.Page for .NET kütüphanesi yüklü. Yüklü değilse, [buradan](https://releases.aspose.com/page/net/) indirebilirsiniz.  
- Bir örnek EPS görüntüsü (koddaki `"input.eps"` ifadesini gerçek dosyanızla değiştirin).

## Ad Alanlarını İçe Aktarma

EPS işleme sınıflarına erişim sağlayan ad alanlarını içe aktararak başlayalım.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## EPS Görüntülerini Kırpma – Adım‑Adım Kılavuz

### Adım 1: `PsDocument`'i Başlatma

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Giriş EPS akışından bir `PsDocument` örneği oluştururuz. Bu nesne EPS dosyasını bellekte temsil eder ve kırpma ve yeniden boyutlandırma yöntemlerine erişim sağlar.

### Adım 2: Orijinal Sınırlama Kutusunu Çıkarma

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Sınırlama kutusu, EPS tuvalinin mevcut boyutlarını gösterir. Bu değerleri bilmek, güvenli bir kırpma dikdörtgeni tanımlamanıza yardımcı olur.

### Adım 3: Çıktı Akışı Oluşturma

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Kırpılmış EPS'nin kaydedileceği yazılabilir bir akış açarız. Bir `using` bloğu kullanmak, akışın düzgün bir şekilde kapatılmasını garanti eder.

### Adım 4: Yeni Bir Sınırlama Kutusu Tanımlama

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Sayıları, tutmak istediğiniz koordinatlarla değiştirin. Yeni değerlerin orijinal sınırlama kutusunun içinde kalmasını sağlayın; aksi takdirde işlem başarısız olur.

### Adım 5: EPS'yi Kırp ve Kaydet

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Bu tek satır kırpma işlemini gerçekleştirir ve sonucu `output_crop.eps` dosyasına yazar. Metot, belgeyi bellek içinde değiştirir, böylece gerekirse daha fazla işlem zincirleyebilirsiniz.

## EPS Görüntüsünü Yeniden Boyutlandırma

Kırpma işleminden sonra, EPS'yi görüntüleme veya baskı için boyutunu değiştirmek isteyebilirsiniz. Aspose.Page üç ölçü birimini destekler.

### İnç Cinsinden Yeniden Boyutlandırma

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Milimetre Cinsinden Yeniden Boyutlandırma

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Yüzde Cinsinden Yeniden Boyutlandırma

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Her çağrı önceki çıktıyı üzerine yazar, bu yüzden her boyut için ayrı dosyalara ihtiyacınız varsa yeni bir akış oluşturduğunuzdan emin olun.

## Yaygın Sorunlar ve Sorun Giderme

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| **Sınırlama kutusu değerleri aralık dışı** | Yeni kutu, orijinal boyutları aşıyor | `initialBoundingBox` değerlerini doğrulayın ve bu aralık içinde koordinatlar seçin. |
| **Çıktı dosyası boş** | Çıktı akışı temizlenmemiş veya kapatılmamış | `using` bloğunun dosyaya erişmeden önce tamamlandığından emin olun veya `outputEpsStream.Flush()` çağırın. |
| **Beklenmeyen ölçekleme** | Birimlerin karışması (ör. inç vs. milimetre) | Boyut değerlerinizle eşleşen doğru `Units` enumunu her zaman belirtin. |

## SSS

### S1: Aspose.Page for .NET'i diğer görüntü formatlarıyla kullanabilir miyim?

C1: Aspose.Page öncelikle EPS görüntülerine odaklanır, ancak Aspose farklı formatlar için çeşitli kütüphaneler sunar. Belirli formatlar için belgelerine bakın.

### S2: Aspose.Page for .NET için geçici bir lisans nasıl alabilirim?

C2: Test amaçlı geçici bir lisans almak için [bu linki](https://purchase.aspose.com/temporary-license/) ziyaret edin.

### S3: Aspose.Page for .NET ile işleyebileceğim görüntü boyutu konusunda herhangi bir sınırlama var mı?

C3: Aspose.Page çeşitli boyutlardaki görüntüleri işlemek üzere tasarlanmıştır. Ancak, performans görüntünün karmaşıklığına bağlı olarak değişebilir.

### S4: Aspose.Page tartışmaları için bir topluluk forumu var mı?

C5: Evet, Aspose.Page topluluğu ile [buradan](https://forum.aspose.com/c/page/39) etkileşime geçebilirsiniz.

### S5: Aspose.Page for .NET için ayrıntılı belgeleri nerede bulabilirim?

C5: Belgeleri [buradan](https://reference.aspose.com/page/net/) inceleyin.

---

**Son Güncelleme:** 2026-03-16  
**Test Edilen Versiyon:** Aspose.Page 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}